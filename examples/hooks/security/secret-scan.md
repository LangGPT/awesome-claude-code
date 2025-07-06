# 密钥扫描安全钩子

在文件编辑后自动扫描敏感信息和密钥泄露，确保代码安全。

## 配置方法

1. 运行 `/hooks` 命令
2. 选择 `PostToolUse` 钩子事件
3. 将以下脚本保存到指定位置

## 钩子脚本

```bash
#!/bin/bash

# 密钥扫描安全钩子
# 在文件编辑后自动扫描敏感信息泄露

EDITED_FILE="$1"
PROJECT_ROOT=$(git rev-parse --show-toplevel 2>/dev/null || pwd)
TIMESTAMP=$(date '+%Y-%m-%d %H:%M:%S')

# 配置选项
ENABLE_DETAILED_SCAN=true
ENABLE_PATTERN_MATCHING=true
ENABLE_ENTROPY_DETECTION=true
FAIL_ON_SECRETS=true
REPORT_FILE="$PROJECT_ROOT/.security-scan-reports/secrets-$(date +%Y%m%d).log"

# 密钥模式定义
declare -a SECRET_PATTERNS=(
    # API 密钥
    "api[_-]?key['\"]?\s*[:=]\s*['\"][a-zA-Z0-9_-]{20,}['\"]"
    "apikey['\"]?\s*[:=]\s*['\"][a-zA-Z0-9_-]{20,}['\"]"
    
    # AWS 密钥
    "aws[_-]?access[_-]?key[_-]?id['\"]?\s*[:=]\s*['\"]AKIA[0-9A-Z]{16}['\"]"
    "aws[_-]?secret[_-]?access[_-]?key['\"]?\s*[:=]\s*['\"][a-zA-Z0-9/+]{40}['\"]"
    
    # Google API 密钥
    "AIza[0-9A-Za-z\\-_]{35}"
    
    # GitHub 令牌
    "gh[pousr]_[A-Za-z0-9_]{36,255}"
    "github_pat_[a-zA-Z0-9]{22}_[a-zA-Z0-9]{59}"
    
    # JWT 令牌
    "eyJ[A-Za-z0-9_-]*\\.eyJ[A-Za-z0-9_-]*\\.[A-Za-z0-9_-]*"
    
    # 数据库连接字符串
    "(mysql|postgresql|mongodb)://[^\\s]+"
    "postgres://[^\\s]+"
    
    # 私钥
    "-----BEGIN [A-Z ]+PRIVATE KEY-----"
    "-----BEGIN RSA PRIVATE KEY-----"
    "-----BEGIN OPENSSH PRIVATE KEY-----"
    
    # 其他敏感信息
    "password['\"]?\s*[:=]\s*['\"][^'\"\\s]{8,}['\"]"
    "secret['\"]?\s*[:=]\s*['\"][^'\"\\s]{8,}['\"]"
    "token['\"]?\s*[:=]\s*['\"][a-zA-Z0-9_-]{20,}['\"]"
    
    # 信用卡号 (简单检测)
    "[0-9]{4}[\\s-]?[0-9]{4}[\\s-]?[0-9]{4}[\\s-]?[0-9]{4}"
    
    # 社会安全号码 (美国)
    "[0-9]{3}-[0-9]{2}-[0-9]{4}"
    
    # 电话号码
    "\\+?[1-9][0-9]{7,14}"
    
    # 邮箱地址 (在某些上下文中可能敏感)
    "[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\\.[a-zA-Z]{2,}"
    
    # IP 地址
    "([0-9]{1,3}\\.){3}[0-9]{1,3}"
    
    # Base64 编码的潜在密钥 (长度 > 40)
    "[A-Za-z0-9+/]{40,}={0,2}"
)

# 文件类型白名单 (这些文件通常包含敏感信息但是合法的)
declare -a WHITELIST_EXTENSIONS=(
    "key"
    "pem"
    "crt"
    "p12"
    "pfx"
    "jks"
)

# 目录白名单
declare -a WHITELIST_DIRS=(
    ".git"
    "node_modules"
    ".vscode"
    ".idea"
    "dist"
    "build"
    "coverage"
)

# 日志函数
log_info() {
    echo "[$TIMESTAMP] ℹ️  $1"
    [ "$ENABLE_DETAILED_SCAN" = true ] && echo "[$TIMESTAMP] ℹ️  $1" >> "$REPORT_FILE"
}

log_warning() {
    echo "[$TIMESTAMP] ⚠️  $1"
    echo "[$TIMESTAMP] ⚠️  $1" >> "$REPORT_FILE"
}

log_error() {
    echo "[$TIMESTAMP] ❌ $1"
    echo "[$TIMESTAMP] ❌ $1" >> "$REPORT_FILE"
}

log_critical() {
    echo "[$TIMESTAMP] 🚨 $1"
    echo "[$TIMESTAMP] 🚨 $1" >> "$REPORT_FILE"
}

# 检查文件是否应该被扫描
should_scan_file() {
    local file="$1"
    
    # 检查文件是否存在
    if [ ! -f "$file" ]; then
        log_info "文件不存在: $file"
        return 1
    fi
    
    # 检查文件大小 (跳过过大的文件)
    local file_size=$(stat -f%z "$file" 2>/dev/null || stat -c%s "$file" 2>/dev/null || echo 0)
    if [ "$file_size" -gt 10485760 ]; then  # 10MB
        log_info "跳过大文件: $file (${file_size} bytes)"
        return 1
    fi
    
    # 检查是否为二进制文件
    if file "$file" | grep -q "binary"; then
        log_info "跳过二进制文件: $file"
        return 1
    fi
    
    # 检查目录白名单
    for whitelist_dir in "${WHITELIST_DIRS[@]}"; do
        if [[ "$file" == *"/$whitelist_dir/"* ]]; then
            log_info "跳过白名单目录中的文件: $file"
            return 1
        fi
    done
    
    # 检查文件扩展名白名单
    local file_ext="${file##*.}"
    for whitelist_ext in "${WHITELIST_EXTENSIONS[@]}"; do
        if [ "$file_ext" = "$whitelist_ext" ]; then
            log_info "跳过白名单扩展名文件: $file"
            return 1
        fi
    done
    
    return 0
}

# 熵值检测 (检测高熵字符串，可能是密钥)
calculate_entropy() {
    local string="$1"
    local length=${#string}
    
    if [ $length -eq 0 ]; then
        echo "0"
        return
    fi
    
    # 简单的熵值计算
    local unique_chars=$(echo "$string" | grep -o . | sort -u | wc -l)
    local entropy=$(echo "scale=2; $unique_chars / $length" | bc -l 2>/dev/null || echo "0")
    echo "$entropy"
}

# 检测高熵字符串
detect_high_entropy_strings() {
    local file="$1"
    local found_secrets=0
    
    if [ "$ENABLE_ENTROPY_DETECTION" != true ]; then
        return 0
    fi
    
    log_info "进行熵值检测: $file"
    
    # 查找长度 > 20 的字符串
    while IFS= read -r line_num; do
        local line_content=$(sed -n "${line_num}p" "$file")
        
        # 提取可能的密钥字符串 (引号内的长字符串)
        echo "$line_content" | grep -oE '["\047][A-Za-z0-9+/=_-]{20,}["\047]' | while read -r potential_secret; do
            # 移除引号
            local clean_secret=$(echo "$potential_secret" | sed 's/^["\047]//' | sed 's/["\047]$//')
            local entropy=$(calculate_entropy "$clean_secret")
            
            # 如果熵值 > 0.6，可能是密钥
            if (( $(echo "$entropy > 0.6" | bc -l 2>/dev/null || echo "0") )); then
                log_warning "高熵字符串检测 (行 $line_num): 熵值=$entropy"
                log_warning "  内容: ${clean_secret:0:20}..."
                found_secrets=$((found_secrets + 1))
            fi
        done
    done < <(grep -n '["\047][A-Za-z0-9+/=_-]{20,}["\047]' "$file" | cut -d: -f1)
    
    return $found_secrets
}

# 模式匹配检测
detect_secret_patterns() {
    local file="$1"
    local found_secrets=0
    
    if [ "$ENABLE_PATTERN_MATCHING" != true ]; then
        return 0
    fi
    
    log_info "进行模式匹配检测: $file"
    
    # 遍历所有密钥模式
    for pattern in "${SECRET_PATTERNS[@]}"; do
        local matches=$(grep -nE "$pattern" "$file" 2>/dev/null || true)
        
        if [ -n "$matches" ]; then
            found_secrets=$((found_secrets + 1))
            log_critical "发现潜在密钥泄露!"
            log_critical "  文件: $file"
            log_critical "  模式: ${pattern:0:50}..."
            log_critical "  匹配内容:"
            
            echo "$matches" | while IFS= read -r match; do
                local line_num=$(echo "$match" | cut -d: -f1)
                local content=$(echo "$match" | cut -d: -f2-)
                log_critical "    行 $line_num: ${content:0:100}..."
            done
        fi
    done
    
    return $found_secrets
}

# 检测常见的假密钥 (减少误报)
is_fake_secret() {
    local content="$1"
    
    # 常见的假密钥模式
    local fake_patterns=(
        "your-api-key"
        "your_api_key"
        "insert-key-here"
        "replace-with-your-key"
        "example-key"
        "test-key"
        "dummy-key"
        "fake-key"
        "placeholder"
        "xxxxxxxxxx"
        "0123456789"
        "abcdefghij"
        "password123"
        "secret123"
    )
    
    local lowercase_content=$(echo "$content" | tr '[:upper:]' '[:lower:]')
    
    for fake_pattern in "${fake_patterns[@]}"; do
        if [[ "$lowercase_content" == *"$fake_pattern"* ]]; then
            return 0
        fi
    done
    
    return 1
}

# 生成安全报告
generate_security_report() {
    local file="$1"
    local secrets_found="$2"
    
    mkdir -p "$(dirname "$REPORT_FILE")"
    
    cat >> "$REPORT_FILE" << EOF

========================================
安全扫描报告
========================================
时间: $TIMESTAMP
文件: $file
发现的敏感信息: $secrets_found

扫描配置:
- 模式匹配: $ENABLE_PATTERN_MATCHING
- 熵值检测: $ENABLE_ENTROPY_DETECTION
- 详细扫描: $ENABLE_DETAILED_SCAN

EOF

    if [ "$secrets_found" -gt 0 ]; then
        cat >> "$REPORT_FILE" << EOF
建议行动:
1. 立即移除或替换发现的敏感信息
2. 检查 Git 历史记录，确保敏感信息未被提交
3. 如果已提交，考虑使用 git-secrets 或 BFG 清理历史
4. 更新相关的密钥和凭证
5. 加强代码审查流程

EOF
    fi
}

# 主扫描函数
scan_file_for_secrets() {
    local file="$1"
    local total_secrets=0
    
    log_info "开始扫描文件: $file"
    
    # 模式匹配检测
    detect_secret_patterns "$file"
    local pattern_secrets=$?
    total_secrets=$((total_secrets + pattern_secrets))
    
    # 熵值检测
    detect_high_entropy_strings "$file"
    local entropy_secrets=$?
    total_secrets=$((total_secrets + entropy_secrets))
    
    # 生成报告
    generate_security_report "$file" "$total_secrets"
    
    if [ "$total_secrets" -gt 0 ]; then
        log_critical "发现 $total_secrets 个潜在的安全问题"
        log_critical "请检查报告: $REPORT_FILE"
        
        # 提供修复建议
        log_info "修复建议:"
        log_info "1. 使用环境变量存储敏感信息"
        log_info "2. 使用密钥管理服务 (如 AWS Secrets Manager)"
        log_info "3. 配置 .gitignore 忽略包含敏感信息的文件"
        log_info "4. 使用 git-secrets 防止意外提交"
        
        return 1
    else
        log_info "未发现敏感信息"
        return 0
    fi
}

# 安装和配置 git-secrets (如果可用)
setup_git_secrets() {
    if command -v git-secrets &> /dev/null; then
        log_info "配置 git-secrets..."
        
        # 安装 git hooks
        git secrets --install 2>/dev/null || true
        
        # 添加常见的密钥模式
        git secrets --register-aws 2>/dev/null || true
        
        # 添加自定义模式
        for pattern in "${SECRET_PATTERNS[@]:0:5}"; do  # 只添加前5个模式
            git secrets --add "$pattern" 2>/dev/null || true
        done
        
        log_info "git-secrets 配置完成"
    else
        log_info "建议安装 git-secrets: brew install git-secrets"
    fi
}

# 主流程
main() {
    # 检查是否应该扫描文件
    if ! should_scan_file "$EDITED_FILE"; then
        exit 0
    fi
    
    log_info "开始安全扫描: $EDITED_FILE"
    
    # 设置 git-secrets (一次性设置)
    if [ ! -f "$PROJECT_ROOT/.git/hooks/pre-commit" ]; then
        setup_git_secrets
    fi
    
    # 扫描文件
    if scan_file_for_secrets "$EDITED_FILE"; then
        log_info "安全扫描通过"
        exit 0
    else
        if [ "$FAIL_ON_SECRETS" = true ]; then
            log_error "安全扫描失败，发现敏感信息"
            exit 1
        else
            log_warning "发现敏感信息，但允许继续"
            exit 0
        fi
    fi
}

# 执行主流程
main
```

## 白名单配置文件

### .secretsignore

```bash
# 创建密钥扫描忽略文件
cat > .secretsignore << 'EOF'
# 测试文件和示例
**/test/**
**/tests/**
**/spec/**
**/*.test.*
**/*.spec.*
**/examples/**
**/sample/**
**/demo/**

# 文档文件
**/*.md
**/*.txt
**/*.rst
**/*.doc
**/*.pdf

# 配置模板
**/*.template
**/*.example
**/*.sample

# 已知安全的配置文件
docker-compose.yml
package.json
yarn.lock
package-lock.json

# 公开的证书文件
**/*.crt
**/*.cert
**/*.pub

# 编译输出
**/dist/**
**/build/**
**/target/**
**/out/**

# 依赖目录
**/node_modules/**
**/vendor/**
**/.venv/**

# IDE 文件
**/.vscode/**
**/.idea/**
EOF
```

## 密钥检测工具集成

### 使用 truffleHog 集成

```bash
#!/bin/bash

# 集成 truffleHog 进行深度扫描

run_trufflehog_scan() {
    local file="$1"
    
    if command -v trufflehog &> /dev/null; then
        log_info "运行 truffleHog 扫描..."
        
        # 扫描文件
        local output=$(trufflehog filesystem --directory="$(dirname "$file")" --include="$(basename "$file")" --json 2>/dev/null)
        
        if [ -n "$output" ]; then
            log_critical "truffleHog 发现潜在密钥:"
            echo "$output" | jq -r '.SourceMetadata.Data.Filesystem.file + ": " + .Raw' 2>/dev/null || echo "$output"
            return 1
        fi
    fi
    
    return 0
}
```

### 使用 detect-secrets 集成

```bash
#!/bin/bash

# 集成 detect-secrets 进行扫描

run_detect_secrets_scan() {
    local file="$1"
    
    if command -v detect-secrets &> /dev/null; then
        log_info "运行 detect-secrets 扫描..."
        
        # 创建临时配置
        local temp_config=$(mktemp)
        cat > "$temp_config" << 'EOF'
{
  "version": "1.4.0",
  "plugins_used": [
    {
      "name": "ArtifactoryDetector"
    },
    {
      "name": "AWSKeyDetector"
    },
    {
      "name": "Base64HighEntropyString",
      "limit": 4.5
    },
    {
      "name": "BasicAuthDetector"
    },
    {
      "name": "CloudantDetector"
    },
    {
      "name": "HexHighEntropyString",
      "limit": 3.0
    },
    {
      "name": "JwtTokenDetector"
    },
    {
      "name": "KeywordDetector",
      "keyword_exclude": ""
    },
    {
      "name": "MailchimpDetector"
    },
    {
      "name": "PrivateKeyDetector"
    },
    {
      "name": "SlackDetector"
    },
    {
      "name": "SoftlayerDetector"
    },
    {
      "name": "SquareOAuthDetector"
    },
    {
      "name": "StripeDetector"
    },
    {
      "name": "TwilioKeyDetector"
    }
  ]
}
EOF
        
        # 扫描文件
        local output=$(detect-secrets scan --baseline "$temp_config" "$file" 2>/dev/null)
        
        if echo "$output" | jq -e '.results | length > 0' >/dev/null 2>&1; then
            log_critical "detect-secrets 发现潜在密钥:"
            echo "$output" | jq -r '.results | to_entries[] | .key + ": " + (.value | length | tostring) + " secrets"'
            rm -f "$temp_config"
            return 1
        fi
        
        rm -f "$temp_config"
    fi
    
    return 0
}
```

## 使用场景

1. **实时安全监控**: 在编辑文件时立即检查敏感信息
2. **防止密钥泄露**: 避免意外提交敏感信息到版本控制
3. **合规性检查**: 确保代码符合安全合规要求
4. **团队安全培训**: 提高团队的安全意识

## 最佳实践

1. **环境变量**: 使用环境变量存储敏感信息
2. **密钥管理**: 使用专业的密钥管理服务
3. **权限控制**: 实施最小权限原则
4. **定期轮换**: 定期更换密钥和凭证
5. **审计日志**: 记录密钥使用和访问日志

## 故障排除

### 误报处理

1. **添加到白名单**: 编辑 `.secretsignore` 文件
2. **调整检测阈值**: 修改熵值检测阈值
3. **自定义模式**: 添加项目特定的忽略模式

### 漏报处理

1. **添加新模式**: 根据发现的新威胁添加检测模式
2. **降低阈值**: 适当降低检测阈值
3. **手动审查**: 定期进行手动安全审查