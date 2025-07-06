# ESLint 代码质量检查钩子

在文件编辑后自动运行 ESLint 检查，确保代码质量。

## 配置方法

1. 运行 `/hooks` 命令
2. 选择 `PostToolUse` 钩子事件
3. 将以下脚本保存到指定位置

## 钩子脚本

```bash
#!/bin/bash

# ESLint 代码质量检查钩子
# 在文件编辑后自动运行 ESLint

EDITED_FILE="$1"
PROJECT_ROOT=$(git rev-parse --show-toplevel 2>/dev/null || pwd)

# 检查是否安装了 ESLint
if ! command -v eslint &> /dev/null; then
    if [ -f "$PROJECT_ROOT/node_modules/.bin/eslint" ]; then
        ESLINT_CMD="$PROJECT_ROOT/node_modules/.bin/eslint"
    else
        echo "ESLint 未安装，跳过代码质量检查"
        exit 0
    fi
else
    ESLINT_CMD="eslint"
fi

# 检查文件是否存在
if [ ! -f "$EDITED_FILE" ]; then
    echo "文件不存在: $EDITED_FILE"
    exit 0
fi

# 检查文件扩展名
FILE_EXT="${EDITED_FILE##*.}"
SUPPORTED_EXTENSIONS=("js" "jsx" "ts" "tsx" "vue")

# 检查是否为支持的文件类型
if [[ " ${SUPPORTED_EXTENSIONS[@]} " =~ " ${FILE_EXT} " ]]; then
    echo "🔍 正在进行代码质量检查: $EDITED_FILE"
    
    # 查找 ESLint 配置文件
    ESLINT_CONFIG=""
    if [ -f "$PROJECT_ROOT/.eslintrc.js" ]; then
        ESLINT_CONFIG="$PROJECT_ROOT/.eslintrc.js"
    elif [ -f "$PROJECT_ROOT/.eslintrc.json" ]; then
        ESLINT_CONFIG="$PROJECT_ROOT/.eslintrc.json"
    elif [ -f "$PROJECT_ROOT/.eslintrc.yml" ]; then
        ESLINT_CONFIG="$PROJECT_ROOT/.eslintrc.yml"
    elif [ -f "$PROJECT_ROOT/eslint.config.js" ]; then
        ESLINT_CONFIG="$PROJECT_ROOT/eslint.config.js"
    fi
    
    # 构建 ESLint 命令
    ESLINT_FULL_CMD="$ESLINT_CMD"
    
    if [ -n "$ESLINT_CONFIG" ]; then
        ESLINT_FULL_CMD="$ESLINT_FULL_CMD --config $ESLINT_CONFIG"
    fi
    
    # 运行 ESLint 检查
    ESLINT_OUTPUT=$(eval "$ESLINT_FULL_CMD \"$EDITED_FILE\"" 2>&1)
    ESLINT_EXIT_CODE=$?
    
    if [ $ESLINT_EXIT_CODE -eq 0 ]; then
        echo "✅ 代码质量检查通过: $EDITED_FILE"
    else
        echo "❌ 发现代码质量问题: $EDITED_FILE"
        echo "=========================="
        echo "$ESLINT_OUTPUT"
        echo "=========================="
        
        # 尝试自动修复
        echo "🔧 尝试自动修复..."
        FIX_OUTPUT=$(eval "$ESLINT_FULL_CMD --fix \"$EDITED_FILE\"" 2>&1)
        FIX_EXIT_CODE=$?
        
        if [ $FIX_EXIT_CODE -eq 0 ]; then
            echo "✅ 已自动修复部分问题"
            
            # 再次检查是否还有问题
            RECHECK_OUTPUT=$(eval "$ESLINT_FULL_CMD \"$EDITED_FILE\"" 2>&1)
            RECHECK_EXIT_CODE=$?
            
            if [ $RECHECK_EXIT_CODE -eq 0 ]; then
                echo "✅ 所有问题已修复"
            else
                echo "⚠️  仍有问题需要手动修复:"
                echo "$RECHECK_OUTPUT"
            fi
        else
            echo "❌ 自动修复失败，需要手动处理"
        fi
        
        exit 1
    fi
else
    echo "跳过代码质量检查 (不支持的文件类型): $EDITED_FILE"
fi

exit 0
```

## 高级配置版本

### 带详细配置的版本

```bash
#!/bin/bash

# 高级 ESLint 代码质量检查钩子
# 支持更多配置选项和详细报告

EDITED_FILE="$1"
PROJECT_ROOT=$(git rev-parse --show-toplevel 2>/dev/null || pwd)
TIMESTAMP=$(date '+%Y-%m-%d %H:%M:%S')

# 配置选项
ENABLE_AUTO_FIX=true
ENABLE_DETAILED_REPORT=true
ENABLE_PERFORMANCE_TIMING=true
MAX_WARNINGS=10
FAIL_ON_ERROR=true

# 日志函数
log_info() {
    echo "[$TIMESTAMP] ℹ️  $1"
}

log_success() {
    echo "[$TIMESTAMP] ✅ $1"
}

log_warning() {
    echo "[$TIMESTAMP] ⚠️  $1"
}

log_error() {
    echo "[$TIMESTAMP] ❌ $1"
}

# 检查 ESLint 安装
check_eslint_installation() {
    if command -v eslint &> /dev/null; then
        ESLINT_CMD="eslint"
        ESLINT_VERSION=$(eslint --version)
        log_info "使用全局 ESLint: $ESLINT_VERSION"
    elif [ -f "$PROJECT_ROOT/node_modules/.bin/eslint" ]; then
        ESLINT_CMD="$PROJECT_ROOT/node_modules/.bin/eslint"
        ESLINT_VERSION=$($ESLINT_CMD --version)
        log_info "使用项目本地 ESLint: $ESLINT_VERSION"
    else
        log_warning "ESLint 未安装，跳过代码质量检查"
        return 1
    fi
    return 0
}

# 查找配置文件
find_eslint_config() {
    local config_files=(
        ".eslintrc.js"
        ".eslintrc.cjs"
        ".eslintrc.mjs"
        ".eslintrc.json"
        ".eslintrc.yml"
        ".eslintrc.yaml"
        "eslint.config.js"
        "eslint.config.mjs"
        "eslint.config.cjs"
    )
    
    for config_file in "${config_files[@]}"; do
        if [ -f "$PROJECT_ROOT/$config_file" ]; then
            ESLINT_CONFIG="$PROJECT_ROOT/$config_file"
            log_info "使用配置文件: $config_file"
            return 0
        fi
    done
    
    # 检查 package.json 中的 eslintConfig
    if [ -f "$PROJECT_ROOT/package.json" ] && grep -q "eslintConfig" "$PROJECT_ROOT/package.json"; then
        log_info "使用 package.json 中的 ESLint 配置"
        return 0
    fi
    
    log_warning "未找到 ESLint 配置文件"
    return 1
}

# 检查忽略文件
check_eslint_ignore() {
    if [ -f "$PROJECT_ROOT/.eslintignore" ]; then
        if grep -q "$(basename "$EDITED_FILE")" "$PROJECT_ROOT/.eslintignore"; then
            log_info "文件被 .eslintignore 忽略: $EDITED_FILE"
            return 1
        fi
        
        # 检查路径模式
        local relative_path=${EDITED_FILE#$PROJECT_ROOT/}
        while IFS= read -r pattern; do
            if [[ "$relative_path" == $pattern* ]]; then
                log_info "文件路径匹配忽略模式: $pattern"
                return 1
            fi
        done < "$PROJECT_ROOT/.eslintignore"
    fi
    return 0
}

# 运行 ESLint 检查
run_eslint_check() {
    local file="$1"
    local start_time=""
    
    if [ "$ENABLE_PERFORMANCE_TIMING" = true ]; then
        start_time=$(date +%s%N)
    fi
    
    log_info "正在检查: $file"
    
    # 构建 ESLint 命令
    local cmd="$ESLINT_CMD"
    [ -n "$ESLINT_CONFIG" ] && cmd="$cmd --config $ESLINT_CONFIG"
    cmd="$cmd --format json"
    
    # 执行检查
    local output
    local exit_code
    output=$(eval "$cmd \"$file\"" 2>&1)
    exit_code=$?
    
    if [ "$ENABLE_PERFORMANCE_TIMING" = true ]; then
        local end_time=$(date +%s%N)
        local duration=$(( (end_time - start_time) / 1000000 ))
        log_info "检查耗时: ${duration}ms"
    fi
    
    # 解析结果
    if [ $exit_code -eq 0 ]; then
        log_success "代码质量检查通过"
        return 0
    else
        # 解析 JSON 输出
        local error_count=0
        local warning_count=0
        
        if command -v jq &> /dev/null; then
            error_count=$(echo "$output" | jq '.[0].errorCount // 0')
            warning_count=$(echo "$output" | jq '.[0].warningCount // 0')
            
            if [ "$ENABLE_DETAILED_REPORT" = true ]; then
                echo "$output" | jq -r '.[0].messages[] | "  \(.line):\(.column) \(.severity | if . == 2 then "error" else "warning" end): \(.message) (\(.ruleId // "unknown"))"'
            fi
        fi
        
        log_error "发现 $error_count 个错误和 $warning_count 个警告"
        
        # 检查是否超过警告阈值
        if [ $warning_count -gt $MAX_WARNINGS ]; then
            log_warning "警告数量 ($warning_count) 超过阈值 ($MAX_WARNINGS)"
        fi
        
        return $exit_code
    fi
}

# 自动修复
run_eslint_fix() {
    if [ "$ENABLE_AUTO_FIX" != true ]; then
        return 0
    fi
    
    local file="$1"
    log_info "尝试自动修复..."
    
    local cmd="$ESLINT_CMD"
    [ -n "$ESLINT_CONFIG" ] && cmd="$cmd --config $ESLINT_CONFIG"
    cmd="$cmd --fix"
    
    if eval "$cmd \"$file\"" 2>/dev/null; then
        log_success "自动修复完成"
        return 0
    else
        log_warning "自动修复失败"
        return 1
    fi
}

# 生成报告
generate_report() {
    local file="$1"
    local report_file="$PROJECT_ROOT/.eslint-reports/$(basename "$file" .${file##*.})-$(date +%Y%m%d-%H%M%S).json"
    
    mkdir -p "$(dirname "$report_file")"
    
    local cmd="$ESLINT_CMD"
    [ -n "$ESLINT_CONFIG" ] && cmd="$cmd --config $ESLINT_CONFIG"
    cmd="$cmd --format json --output-file $report_file"
    
    if eval "$cmd \"$file\"" 2>/dev/null; then
        log_info "报告已生成: $report_file"
    fi
}

# 主流程
main() {
    # 检查文件
    if [ ! -f "$EDITED_FILE" ]; then
        log_error "文件不存在: $EDITED_FILE"
        exit 1
    fi
    
    # 检查文件类型
    local file_ext="${EDITED_FILE##*.}"
    local supported_extensions=("js" "jsx" "ts" "tsx" "vue" "mjs" "cjs")
    
    if [[ ! " ${supported_extensions[@]} " =~ " ${file_ext} " ]]; then
        log_info "跳过检查 (不支持的文件类型): $EDITED_FILE"
        exit 0
    fi
    
    # 检查 ESLint 安装
    if ! check_eslint_installation; then
        exit 0
    fi
    
    # 查找配置
    find_eslint_config
    
    # 检查忽略规则
    if ! check_eslint_ignore; then
        exit 0
    fi
    
    # 运行检查
    if run_eslint_check "$EDITED_FILE"; then
        exit 0
    fi
    
    # 尝试自动修复
    if run_eslint_fix "$EDITED_FILE"; then
        # 再次检查
        if run_eslint_check "$EDITED_FILE"; then
            log_success "问题已修复"
            exit 0
        fi
    fi
    
    # 生成详细报告
    if [ "$ENABLE_DETAILED_REPORT" = true ]; then
        generate_report "$EDITED_FILE"
    fi
    
    # 根据配置决定是否失败
    if [ "$FAIL_ON_ERROR" = true ]; then
        log_error "代码质量检查失败"
        exit 1
    else
        log_warning "代码质量检查有问题，但允许继续"
        exit 0
    fi
}

# 执行主流程
main
```

## 配置文件示例

### .eslintrc.json

```json
{
  "extends": [
    "eslint:recommended",
    "@typescript-eslint/recommended",
    "prettier"
  ],
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "ecmaVersion": 2022,
    "sourceType": "module",
    "ecmaFeatures": {
      "jsx": true
    }
  },
  "plugins": [
    "@typescript-eslint",
    "react",
    "react-hooks",
    "import",
    "security"
  ],
  "rules": {
    "no-console": "warn",
    "no-debugger": "error",
    "no-unused-vars": "off",
    "@typescript-eslint/no-unused-vars": "error",
    "react-hooks/rules-of-hooks": "error",
    "react-hooks/exhaustive-deps": "warn",
    "import/order": ["error", {
      "groups": ["builtin", "external", "internal", "parent", "sibling", "index"],
      "newlines-between": "always"
    }],
    "security/detect-object-injection": "warn"
  },
  "settings": {
    "react": {
      "version": "detect"
    }
  },
  "env": {
    "browser": true,
    "node": true,
    "es2022": true,
    "jest": true
  }
}
```

## 使用场景

1. **实时代码质量监控**: 在编辑文件时立即检查质量
2. **自动代码修复**: 自动修复可修复的问题
3. **团队代码规范**: 确保团队代码风格一致
4. **持续集成**: 作为 CI/CD 流水线的一部分

## 注意事项

- 确保项目中安装了 ESLint 和相关插件
- 配置合适的 ESLint 规则，避免过于严格
- 对于大型项目，考虑性能影响
- 可以通过 `.eslintignore` 排除不需要检查的文件

## 故障排除

### 常见问题

1. **ESLint 未找到**
   ```bash
   npm install eslint --save-dev
   # 或者全局安装
   npm install -g eslint
   ```

2. **配置文件错误**
   ```bash
   eslint --print-config .
   ```

3. **插件缺失**
   ```bash
   npm install @typescript-eslint/eslint-plugin --save-dev
   ```

4. **性能问题**
   - 使用 `.eslintignore` 排除大文件
   - 考虑只检查修改的文件
   - 调整检查规则的复杂度

## 扩展功能

- 集成 TypeScript 类型检查
- 添加自定义规则
- 集成 Prettier 格式化
- 生成代码质量报告
- 发送质量检查通知