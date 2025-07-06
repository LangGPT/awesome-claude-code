# 安全审计命令

全面的安全审计和漏洞扫描，包含代码、依赖项和配置的安全检查。

## 使用方法

将此文件保存为 `.claude/commands/security-audit.md`，然后使用 `/security-audit` 命令。

## 命令内容

```markdown
# 项目安全审计

执行全面的安全审计，检查代码、依赖项、配置和部署的安全漏洞。

## 审计范围

审计类型: $ARGUMENTS (可选: code, dependencies, config, infrastructure, all)

## 安全审计流程

### 1. 代码安全扫描

#### JavaScript/TypeScript 项目
```bash
# npm 安全审计
npm audit --audit-level=moderate

# 使用 ESLint 安全规则
npx eslint . --ext .js,.ts --config .eslintrc-security.json

# Snyk 代码扫描
npx snyk code test

# 检查敏感信息泄露
git secrets --scan-history || gitleaks detect
```

#### Python 项目
```bash
# 依赖安全检查
safety check

# Bandit 代码安全扫描
bandit -r . -f json -o bandit-report.json

# Semgrep 安全规则检查
semgrep scan --config=auto .

# 检查硬编码密钥
git secrets --scan-history || truffleHog --regex --entropy=False .
```

#### Java 项目
```bash
# OWASP Dependency Check
mvn org.owasp:dependency-check-maven:check

# SpotBugs 安全检查
mvn com.github.spotbugs:spotbugs-maven-plugin:check

# 检查已知漏洞
snyk test --severity-threshold=medium
```

#### Go 项目
```bash
# Go 安全检查
gosec ./...

# Nancy 依赖检查
nancy sleuth

# 检查已知漏洞
govulncheck ./...
```

#### .NET 项目
```bash
# 安全审计
dotnet list package --vulnerable

# Security Code Scan
dotnet build --verbosity normal
```

### 2. 依赖项安全审计

#### 检查过时依赖
```bash
# Node.js
npm outdated
npm audit fix

# Python
pip list --outdated
pip-audit

# Java (Maven)
mvn versions:display-dependency-updates
mvn org.owasp:dependency-check-maven:check

# Go
go list -u -m all
```

#### 许可证合规检查
```bash
# JavaScript
npx license-checker --summary

# Python
pip-licenses

# Java
mvn org.codehaus.mojo:license-maven-plugin:third-party-report
```

### 3. 配置安全检查

#### 环境变量和密钥检查
```bash
# 检查 .env 文件
if [ -f .env ]; then
    echo "警告: 发现 .env 文件，请确保不包含敏感信息"
    grep -E "(password|secret|key|token)" .env || echo "未发现明显的敏感信息"
fi

# 检查配置文件中的硬编码密钥
grep -r -E "(password|secret|key|token|api_key).*=" . --include="*.json" --include="*.yaml" --include="*.yml" --include="*.xml"
```

#### Docker 安全检查
```bash
# Dockerfile 安全检查
if [ -f Dockerfile ]; then
    # 使用 hadolint 检查 Dockerfile
    hadolint Dockerfile
    
    # 检查基础镜像安全
    docker scan $(grep FROM Dockerfile | awk '{print $2}' | head -1)
fi
```

#### Kubernetes 配置检查
```bash
# 使用 kube-score 检查 K8s 配置
if ls *.yaml 1> /dev/null 2>&1; then
    kube-score score *.yaml
fi

# 使用 kubesec 安全检查
if ls k8s/*.yaml 1> /dev/null 2>&1; then
    kubesec scan k8s/*.yaml
fi
```

### 4. 基础设施安全检查

#### 网络安全检查
```bash
# 检查开放端口
nmap -sS localhost

# SSL/TLS 配置检查
if command -v testssl &> /dev/null; then
    testssl --quiet --color 0 localhost:443
fi
```

#### 文件权限检查
```bash
# 检查敏感文件权限
find . -name "*.key" -o -name "*.pem" -o -name "*.p12" | xargs ls -la

# 检查可执行文件权限
find . -type f -perm -111 | head -20
```

### 5. Web 应用安全检查

#### OWASP ZAP 扫描 (如果应用正在运行)
```bash
if curl -s http://localhost:8080/health > /dev/null; then
    echo "检测到运行中的应用，执行 Web 安全扫描..."
    # 使用 ZAP 进行基础扫描
    zap-baseline.py -t http://localhost:8080
fi
```

#### 安全头检查
```bash
if curl -s http://localhost:8080 > /dev/null; then
    echo "检查安全响应头..."
    curl -I http://localhost:8080 | grep -E "(X-Frame-Options|X-Content-Type-Options|X-XSS-Protection|Strict-Transport-Security|Content-Security-Policy)"
fi
```

## 安全报告生成

### 1. 汇总扫描结果
```bash
# 创建安全报告目录
mkdir -p security-reports/$(date +%Y%m%d)

# 生成综合报告
cat > security-reports/$(date +%Y%m%d)/security-audit-summary.md << EOF
# 安全审计报告

**审计时间**: $(date)
**项目**: $(basename $(pwd))
**审计范围**: ${ARGUMENTS:-"all"}

## 发现的问题

### 高危漏洞
[此处列出高危问题]

### 中危漏洞
[此处列出中危问题]

### 低危漏洞
[此处列出低危问题]

## 修复建议

### 立即修复
1. [高危问题修复建议]

### 计划修复
1. [中危问题修复建议]

### 监控关注
1. [低危问题监控建议]

## 合规性检查

- [ ] OWASP Top 10 检查
- [ ] 数据保护合规
- [ ] 访问控制验证
- [ ] 加密传输检查

EOF
```

### 2. 生成详细报告
```bash
# 依赖项漏洞报告
echo "## 依赖项安全状态" >> security-reports/$(date +%Y%m%d)/dependencies.md

# 代码扫描报告
echo "## 代码安全扫描结果" >> security-reports/$(date +%Y%m%d)/code-scan.md

# 配置安全报告
echo "## 配置安全检查" >> security-reports/$(date +%Y%m%d)/config-security.md
```

## 修复建议和行动计划

### 高危漏洞修复 (立即处理)
1. **SQL 注入**: 使用参数化查询
2. **XSS 攻击**: 输入验证和输出编码
3. **身份验证绕过**: 强化认证机制
4. **敏感数据泄露**: 移除硬编码密钥

### 中危漏洞修复 (7天内处理)
1. **过时依赖**: 更新到安全版本
2. **弱密码策略**: 强化密码要求
3. **不安全通信**: 启用 HTTPS
4. **访问控制**: 实施最小权限原则

### 低危问题优化 (30天内处理)
1. **信息泄露**: 移除调试信息
2. **安全头缺失**: 添加安全响应头
3. **日志安全**: 避免记录敏感信息
4. **错误处理**: 统一错误响应

## 持续安全监控

### 1. 自动化安全检查
```bash
# 添加到 CI/CD 流水线
# .github/workflows/security.yml
name: Security Audit
on: [push, pull_request]
jobs:
  security:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Run Security Audit
        run: |
          npm audit
          npm run security-check
```

### 2. 定期安全审计
- 每周运行自动化安全扫描
- 每月进行人工安全审计
- 每季度进行渗透测试
- 年度第三方安全评估

### 3. 安全培训和意识
- 定期进行安全培训
- 建立安全编码规范
- 实施代码审查流程
- 维护安全知识库

## 合规性检查清单

- [ ] **数据保护**: GDPR、CCPA 合规检查
- [ ] **行业标准**: SOC 2、ISO 27001 要求
- [ ] **监管要求**: 特定行业安全标准
- [ ] **内部策略**: 公司安全政策合规

## 紧急响应计划

### 发现严重漏洞时的处理流程：
1. **立即评估**: 确定漏洞影响范围
2. **临时缓解**: 实施临时防护措施
3. **通知团队**: 告知相关技术和管理团队
4. **制定修复**: 开发和测试修复方案
5. **部署修复**: 尽快部署到生产环境
6. **验证修复**: 确认漏洞已被修复
7. **总结改进**: 分析原因并改进流程

请根据扫描结果的严重程度，按优先级处理发现的安全问题。
```

## 示例用法

```bash
# 完整安全审计
/security-audit

# 只检查依赖项安全
/security-audit dependencies

# 只检查代码安全
/security-audit code

# 只检查配置安全
/security-audit config

# 基础设施安全检查
/security-audit infrastructure
```

## 预期输出

Claude Code 将会：

1. 执行全面的安全扫描
2. 生成详细的安全报告
3. 按风险等级分类问题
4. 提供具体的修复建议
5. 建立持续监控机制
6. 制定紧急响应计划

## 相关命令

- `/fix-vulnerabilities` - 自动修复已知漏洞
- `/update-dependencies` - 更新依赖到安全版本
- `/generate-security-policy` - 生成安全策略文档
- `/compliance-check` - 合规性检查