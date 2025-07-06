# 运行测试命令

全面的测试执行命令，支持多种测试框架和配置。

## 使用方法

将此文件保存为 `.claude/commands/run-tests.md`，然后使用 `/run-tests` 命令。

## 命令内容

```markdown
# 运行项目测试

请帮我运行项目的测试套件，并根据项目类型选择合适的测试策略：

## 测试参数

测试类型: $ARGUMENTS (如果未指定，则运行所有测试)

## 检测和执行步骤

1. **项目类型检测**
   - 检查项目根目录的配置文件
   - 识别使用的测试框架

2. **根据项目类型执行测试**

### JavaScript/TypeScript 项目
- 如果存在 `package.json`：
  - 检查是否有 Jest: `npm test` 或 `yarn test`
  - 检查是否有 Vitest: `npm run test` 或 `pnpm test`
  - 检查是否有 Cypress: `npm run test:e2e`
  - 运行类型检查: `npm run type-check` (如果存在)

### Python 项目
- 如果存在 `pytest.ini` 或 `pyproject.toml`：
  - 运行 pytest: `pytest -v --cov=.`
  - 生成覆盖率报告: `pytest --cov-report=html`
- 如果存在 `manage.py` (Django)：
  - 运行 Django 测试: `python manage.py test`
- 运行类型检查: `mypy .` (如果安装了 mypy)

### Java 项目
- 如果存在 `pom.xml` (Maven)：
  - 运行测试: `mvn test`
  - 运行集成测试: `mvn verify`
- 如果存在 `build.gradle` (Gradle)：
  - 运行测试: `./gradlew test`
  - 运行集成测试: `./gradlew integrationTest`

### Go 项目
- 如果存在 `go.mod`：
  - 运行所有测试: `go test ./...`
  - 运行带覆盖率的测试: `go test -cover ./...`
  - 运行竞态检测: `go test -race ./...`
  - 运行基准测试: `go test -bench=. ./...`

### .NET 项目
- 如果存在 `.csproj` 或 `.sln`：
  - 运行测试: `dotnet test`
  - 运行带覆盖率的测试: `dotnet test --collect:"XPlat Code Coverage"`

### Ruby 项目
- 如果存在 `Gemfile`：
  - 运行 RSpec 测试: `bundle exec rspec`
  - 运行 Minitest: `bundle exec rake test`

### Rust 项目
- 如果存在 `Cargo.toml`：
  - 运行测试: `cargo test`
  - 运行文档测试: `cargo test --doc`

3. **测试结果分析**
   - 显示测试结果摘要
   - 如果有失败的测试，显示详细信息
   - 如果生成了覆盖率报告，提供查看路径

4. **后续建议**
   - 如果测试失败，提供修复建议
   - 如果覆盖率低，建议增加测试用例
   - 推荐相关的测试最佳实践

## 特殊选项处理

根据 $ARGUMENTS 参数执行特定测试：
- `unit`: 只运行单元测试
- `integration`: 只运行集成测试
- `e2e`: 只运行端到端测试
- `watch`: 启动监视模式
- `coverage`: 生成详细的覆盖率报告
- `performance`: 运行性能测试
- `security`: 运行安全测试

请根据项目实际情况执行合适的测试命令，并提供测试结果的详细分析。
```

## 示例用法

```bash
# 运行所有测试
/run-tests

# 只运行单元测试
/run-tests unit

# 运行测试并生成覆盖率报告
/run-tests coverage

# 启动监视模式
/run-tests watch

# 运行端到端测试
/run-tests e2e
```

## 预期输出

Claude Code 将会：

1. 自动检测项目类型和测试框架
2. 执行相应的测试命令
3. 分析测试结果和覆盖率
4. 提供失败测试的详细信息
5. 给出改进建议和下一步操作

## 相关命令

- `/fix-failing-tests` - 修复失败的测试
- `/test-coverage` - 详细的覆盖率分析
- `/create-test` - 创建新的测试文件
- `/test-performance` - 性能测试分析