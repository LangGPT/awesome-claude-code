# Awesome Claude Code 中文资源 [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> 精选的 Claude Code 资源、工具和工作流程列表

Claude Code 是 Anthropic 开发的智能编程助手，直接在终端中运行，无需额外的服务器或复杂配置。

## 目录

- [官方文档](#官方文档)
- [快速开始](#快速开始)
- [核心功能](#核心功能)
- [IDE 集成](#ide-集成)
- [工作流程](#工作流程)
- [记忆管理](#记忆管理)
- [MCP 支持](#mcp-支持)
- [实用工具](#实用工具)
- [社区资源](#社区资源)
- [贡献指南](#贡献指南)

## 官方文档

### 中文文档
- [概述](https://docs.anthropic.com/zh-CN/docs/claude-code/overview) - Claude Code 的基本介绍和核心特性
- [安装设置](https://docs.anthropic.com/zh-CN/docs/claude-code/setup) - 完整的安装和配置指南
- [快速开始](https://docs.anthropic.com/zh-CN/docs/claude-code/quickstart) - 5分钟快速上手指南
- [记忆管理](https://docs.anthropic.com/zh-CN/docs/claude-code/memory) - CLAUDE.md 文件和项目记忆
- [常见工作流程](https://docs.anthropic.com/zh-CN/docs/claude-code/common-workflows) - 典型使用场景和最佳实践
- [IDE 集成](https://docs.anthropic.com/zh-CN/docs/claude-code/ide-integrations) - VS Code、JetBrains 等集成指南
- [MCP 协议](https://docs.anthropic.com/zh-CN/docs/claude-code/mcp) - 模型上下文协议支持
- [GitHub Actions](https://docs.anthropic.com/zh-CN/docs/claude-code/github-actions) - CI/CD 集成
- [SDK 开发](https://docs.anthropic.com/zh-CN/docs/claude-code/sdk) - 开发者工具包
- [故障排除](https://docs.anthropic.com/zh-CN/docs/claude-code/troubleshooting) - 常见问题解决方案

## 快速开始

### 安装

```bash
# 使用 npm 安装
npm install -g @anthropic-ai/claude-code

# 启动 Claude Code
claude
```

### 基本用法

```bash
# 交互式会话
claude

# 执行单次任务
claude "分析这个项目的架构"

# 创建 Git 提交
claude commit

# 显示帮助
claude --help
```

## 核心功能

### 🔧 代码操作
- **文件编辑**: 直接编辑和修复代码库错误
- **代码分析**: 回答关于代码架构和逻辑的问题
- **测试执行**: 运行和修复测试及代码检查
- **Git 集成**: 搜索 Git 历史记录和解决合并冲突

### 🔍 项目理解
- **架构分析**: 理解整个项目结构
- **代码导航**: 快速定位相关文件和函数
- **依赖关系**: 分析模块间的交互关系
- **最佳实践**: 遵循项目的编码规范

### 🚀 自动化任务
- **提交创建**: 智能生成 Git 提交和 PR
- **文档生成**: 自动创建和更新文档
- **重构辅助**: 识别过时 API 并建议现代化方案
- **错误修复**: 根据错误消息提供具体解决方案

## IDE 集成

### Visual Studio Code
- **快捷键**: `Cmd+Esc` (Mac) 或 `Ctrl+Esc` (Windows/Linux)
- **自动安装**: 在集成终端中运行 `claude` 命令
- **上下文共享**: 自动分享当前选中的代码或文件

### JetBrains IDEs
- **支持产品**: PyCharm、WebStorm、IntelliJ、GoLand
- **插件安装**: 从市场安装插件或在集成终端运行 `claude`
- **诊断集成**: 自动分享 IDE 诊断错误信息

### 配置技巧
```bash
# 启用 IDE 特定功能
/config

# 设置差异查看器为自动检测
# 在配置中设置 difference viewer 为 "auto"
```

## 工作流程

### 💡 理解新代码库
1. **概览分析**: "给我这个代码库的概述"
2. **架构深入**: 逐步深入特定组件和模式
3. **约定理解**: 了解编码规范和项目术语

### 🐛 错误修复和调试
1. **错误分析**: 分享错误消息和堆栈跟踪
2. **解决方案**: 获取具体的修复建议
3. **根因分析**: 识别问题的根本原因

### 🔄 代码重构
1. **现代化**: 识别过时的 API 使用
2. **优化建议**: 获取代码改进建议
3. **增量应用**: 通过测试验证渐进式更改

## 记忆管理

### 记忆文件类型
- **项目记忆** (`./CLAUDE.md`): 团队共享的项目架构和工作流程
- **用户记忆** (`~/.claude/CLAUDE.md`): 跨项目的个人偏好设置
- **已弃用** (`./CLAUDE.local.md`): 本地项目记忆（不推荐使用）

### 最佳实践
```markdown
# 项目架构指南
- 使用 TypeScript 进行类型安全
- 遵循 ESLint 配置
- 测试文件放在 `__tests__` 目录

# 编码规范
- 使用 Prettier 格式化代码
- 提交消息使用常规提交格式
- 组件命名使用 PascalCase
```

### 记忆管理命令
```bash
# 编辑记忆文件
/memory

# 快速添加记忆（使用 # 前缀）
# 在聊天中输入以 # 开头的消息
```

## MCP 支持

### 模型上下文协议功能
- **外部工具**: 连接到外部工具和数据源
- **多服务器**: 支持 stdio、SSE 和 HTTP 服务器
- **OAuth 认证**: 安全连接到远程服务器
- **资源引用**: 使用 "@" 提及外部资源

### 服务器作用域
1. **本地作用域**: 当前项目私有
2. **项目作用域**: 通过 `.mcp.json` 文件共享
3. **用户作用域**: 所有项目可用

### 安全提醒
⚠️ **警告**: 使用第三方 MCP 服务器需要自行承担风险。确保信任 MCP 服务器，特别是通过互联网通信的服务器。

## 实用工具

### 版本控制
- **Git 集成**: 智能提交消息生成
- **分支管理**: 并行工作流程支持
- **合并冲突**: 自动解决复杂冲突

### 代码分析
- **静态分析**: 代码质量检查
- **性能分析**: 识别性能瓶颈
- **依赖分析**: 依赖关系可视化

### 文档生成
- **API 文档**: 自动生成 API 文档
- **变更日志**: 智能生成更新记录
- **README**: 项目文档自动化

## 社区资源

### 英文资源
- [Awesome Claude Code](https://github.com/hesreallyhim/awesome-claude-code) - 官方精选资源列表
- [Claude Code GitHub](https://github.com/anthropics/claude-code) - 官方 GitHub 仓库

### 工作流程和知识指南
- 探索社区贡献的工作流程
- 学习最佳实践和使用技巧
- 发现创新的使用方式

### 扩展工具
- **Hooks**: 自定义工作流程钩子
- **Slash Commands**: 扩展命令功能
- **CLAUDE.md Templates**: 各种项目模板

## 企业集成

### 云平台支持
- **Amazon Bedrock**: 企业级安全部署
- **Google Vertex AI**: 云端集成解决方案
- **直连 API**: 无中间服务器的安全连接

### 安全特性
- **直接连接**: 查询直接发送到 Anthropic API
- **无中间服务器**: 降低安全风险
- **上下文感知**: 智能理解项目结构

## 贡献指南

我们欢迎社区贡献！请遵循以下准则：

1. **Fork 仓库**: 创建您自己的分支
2. **添加资源**: 确保资源质量和相关性
3. **描述清晰**: 为每个资源提供简洁的中文描述
4. **分类正确**: 将资源放在合适的分类中
5. **测试链接**: 确保所有链接都有效
6. **遵循格式**: 保持与现有条目的格式一致

### 贡献类型
- 📚 **文档翻译**: 将官方文档翻译成中文
- 🛠️ **工具开发**: 开发 Claude Code 相关工具
- 📖 **教程创作**: 编写使用教程和最佳实践
- 🔧 **工作流程**: 分享实用的工作流程配置
- 🎯 **用例分享**: 分享实际应用场景

## 许可证

本项目采用 [MIT 许可证](LICENSE)。

---

**⭐ 如果这个资源对您有帮助，请给个 Star！**

**🤝 欢迎提交 Issue 和 Pull Request 来完善这个列表！**