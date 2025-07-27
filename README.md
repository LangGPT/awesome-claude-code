# Awesome Claude Code [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> 精选的 Claude Code 相关仓库、工具和资源列表

**作者：** 云中江树，微信公众号「云中江树」

Claude Code 是 Anthropic 推出的智能编程助手，它生活在你的终端中，理解你的代码库，并通过执行复杂的编程任务帮助你更快地编码。

[English](awesome-claude-code-README-EN.md) | 简体中文

## 📋 目录

- [官方仓库](#官方仓库)
- [核心扩展与集成](#核心扩展与集成)
- [GUI 和 Web 界面](#gui-和-web-界面)
- [IDE 和编辑器扩展](#ide-和编辑器扩展)
- [开发工具与实用程序](#开发工具与实用程序)
- [监控与分析](#监控与分析)
- [代理与 API 工具](#代理与-api-工具)
- [框架扩展](#框架扩展)
- [MCP 服务器与插件](#mcp-服务器与插件)
- [指南与文档](#指南与文档)

## 官方仓库

|名称|Stars|简介|备注|
|-------|-------|-------|------|
|[claude-code](https://github.com/anthropics/claude-code) | ![GitHub Repo stars](https://badgen.net/github/stars/anthropics/claude-code) | 官方 Claude Code 终端智能编程助手 | Anthropic 官方发布|
|[claude-code-action](https://github.com/anthropics/claude-code-action) | ![GitHub Repo stars](https://badgen.net/github/stars/anthropics/claude-code-action) | Claude Code 的 GitHub Actions 集成 | 官方 CI/CD 集成|
|[claude-code-base-action](https://github.com/anthropics/claude-code-base-action) | ![GitHub Repo stars](https://badgen.net/github/stars/anthropics/claude-code-base-action) | base-action 内容的镜像仓库 | 官方基础操作|
|[claude-code-sdk-python](https://github.com/anthropics/claude-code-sdk-python) | ![GitHub Repo stars](https://badgen.net/github/stars/anthropics/claude-code-sdk-python) | 官方 Python SDK | 官方 Python 支持|
|[devcontainer-features](https://github.com/anthropics/devcontainer-features) | ![GitHub Repo stars](https://badgen.net/github/stars/anthropics/devcontainer-features) | 包含 Claude Code CLI 的开发容器特性 | 官方容器支持|

## 核心扩展与集成

|名称|Stars|简介|备注|
|-------|-------|-------|------|
|[SuperClaude_Framework](https://github.com/SuperClaude-Org/SuperClaude_Framework) | ![GitHub Repo stars](https://badgen.net/github/stars/SuperClaude-Org/SuperClaude_Framework) | 增强 Claude Code 的配置框架，包含专用命令和认知角色 | 功能增强框架|
|[claude-code-router](https://github.com/musistudio/claude-code-router) | ![GitHub Repo stars](https://badgen.net/github/stars/musistudio/claude-code-router) | 以 Claude Code 为基础的编程基础设施 | 路由管理工具|
|[analysis_claude_code](https://github.com/shareAI-lab/analysis_claude_code) | ![GitHub Repo stars](https://badgen.net/github/stars/shareAI-lab/analysis_claude_code) | Claude Code v1.0.33 逆向工程完整研究分析 | 逆向工程分析|
|[context-engineering-intro](https://github.com/coleam00/context-engineering-intro) | ![GitHub Repo stars](https://badgen.net/github/stars/coleam00/context-engineering-intro) | 上下文工程介绍 - AI 编程助手的新编程方式 | 上下文工程指南|
|[claudia](https://github.com/getAsterisk/claudia) | ![GitHub Repo stars](https://badgen.net/github/stars/getAsterisk/claudia) | 强大的 Claude Code GUI 应用和工具包 | GUI 管理工具|
|[awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code) | ![GitHub Repo stars](https://badgen.net/github/stars/hesreallyhim/awesome-claude-code) | Claude Code 精选命令、文件和工作流列表 | 资源集合|

## GUI 和 Web 界面

|名称|Stars|简介|备注|
|-------|-------|-------|------|
|[claudecodeui](https://github.com/siteboon/claudecodeui) | ![GitHub Repo stars](https://badgen.net/github/stars/siteboon/claudecodeui) | 在移动端和 Web 上使用 Claude Code 的 UI 界面 | 跨平台 Web UI|
|[claude-code-webui](https://github.com/sugyan/claude-code-webui) | ![GitHub Repo stars](https://badgen.net/github/stars/sugyan/claude-code-webui) | 支持流式聊天响应的 Claude CLI Web 界面 | 流式 Web 界面|
|[claude-code-chat](https://github.com/andrepimenta/claude-code-chat) | ![GitHub Repo stars](https://badgen.net/github/stars/andrepimenta/claude-code-chat) | VS Code 中的美观 Claude Code 聊天界面 | VS Code 聊天界面|
|[Claude-Code-Web-GUI](https://github.com/binggg/Claude-Code-Web-GUI) | ![GitHub Repo stars](https://badgen.net/github/stars/binggg/Claude-Code-Web-GUI) | 在浏览器中浏览和查看 Claude Code 会话历史 | 会话历史查看器|

## IDE 和编辑器扩展

|名称|Stars|简介|备注|
|-------|-------|-------|------|
|[claude-coder](https://github.com/kodu-ai/claude-coder) | ![GitHub Repo stars](https://badgen.net/github/stars/kodu-ai/claude-coder) | 居住在 IDE 中的自主编程代理 VSCode 扩展 | VS Code 扩展|
|[claude-code.nvim](https://github.com/greggh/claude-code.nvim) | ![GitHub Repo stars](https://badgen.net/github/stars/greggh/claude-code.nvim) | Claude Code AI 助手与 Neovim 的无缝集成 | Neovim 集成|
|[claudecode.nvim](https://github.com/coder/claudecode.nvim) | ![GitHub Repo stars](https://badgen.net/github/stars/coder/claudecode.nvim) | Claude Code Neovim IDE 扩展 | Neovim IDE 扩展|
|[claude-code.el](https://github.com/stevemolitor/claude-code.el) | ![GitHub Repo stars](https://badgen.net/github/stars/stevemolitor/claude-code.el) | Claude Code Emacs 集成 | Emacs 集成|
|[claude-code-ide.el](https://github.com/manzaltu/claude-code-ide.el) | ![GitHub Repo stars](https://badgen.net/github/stars/manzaltu/claude-code-ide.el) | Emacs 的 Claude Code IDE 集成 | Emacs IDE 集成|
|[claude-code-zed](https://github.com/jiahaoxiang2000/claude-code-zed) | ![GitHub Repo stars](https://badgen.net/github/stars/jiahaoxiang2000/claude-code-zed) | Claude Code CLI 集成的 Zed 编辑器扩展 | Zed 编辑器扩展|
|[claudemacs](https://github.com/cpoile/claudemacs) | ![GitHub Repo stars](https://badgen.net/github/stars/cpoile/claudemacs) | 在 Emacs 中与 Claude Code 进行 AI 结对编程 | Emacs AI 编程|

## 开发工具与实用程序

|名称|Stars|简介|备注|
|-------|-------|-------|------|
|[code2prompt](https://github.com/mufeedvh/code2prompt) | ![GitHub Repo stars](https://badgen.net/github/stars/mufeedvh/code2prompt) | 将代码库转换为单个 LLM 提示的 CLI 工具 | 代码转提示工具|
|[kilocode](https://github.com/Kilo-Org/kilocode) | ![GitHub Repo stars](https://badgen.net/github/stars/Kilo-Org/kilocode) | 开源 AI 编程助手，用于规划、构建和修复代码 | 开源 AI 助手|
|[zen-mcp-server](https://github.com/BeehiveInnovations/zen-mcp-server) | ![GitHub Repo stars](https://badgen.net/github/stars/BeehiveInnovations/zen-mcp-server) | Claude Code + 多模型整合的强大组合 | MCP 服务器|
|[ccusage](https://github.com/ryoppippi/ccusage) | ![GitHub Repo stars](https://badgen.net/github/stars/ryoppippi/ccusage) | 分析本地 JSONL 文件中 Claude Code 使用情况的 CLI 工具 | 使用情况分析|
|[codecompanion.nvim](https://github.com/olimorris/codecompanion.nvim) | ![GitHub Repo stars](https://badgen.net/github/stars/olimorris/codecompanion.nvim) | 在 Neovim 中的 AI 驱动编程体验 | Neovim AI 编程|
|[crystal](https://github.com/stravu/crystal) | ![GitHub Repo stars](https://badgen.net/github/stars/stravu/crystal) | 在并行 git 工作树中运行多个 Claude Code AI 会话 | 并行会话管理|
|[dotai](https://github.com/udecode/dotai) | ![GitHub Repo stars](https://badgen.net/github/stars/udecode/dotai) | 终极 AI 开发栈：Claude Code + Task Master + Cursor | AI 开发栈|
|[ccseva](https://github.com/Iamshankhadeep/ccseva) | ![GitHub Repo stars](https://badgen.net/github/stars/Iamshankhadeep/ccseva) | 实时跟踪 Claude Code 使用情况的美观 macOS 菜单栏应用 | macOS 监控应用|
|[ccundo](https://github.com/RonitSachdev/ccundo) | ![GitHub Repo stars](https://badgen.net/github/stars/RonitSachdev/ccundo) | 为 Claude Code 提供细粒度撤销功能 | 撤销功能工具|

## 监控与分析

|名称|Stars|简介|备注|
|-------|-------|-------|------|
|[Claude-Code-Usage-Monitor](https://github.com/Maciek-roboblog/Claude-Code-Usage-Monitor) | ![GitHub Repo stars](https://badgen.net/github/stars/Maciek-roboblog/Claude-Code-Usage-Monitor) | 实时 Claude Code 使用监控器，带预测和警告功能 | 实时监控工具|
|[sniffly](https://github.com/chiphuyen/sniffly) | ![GitHub Repo stars](https://badgen.net/github/stars/chiphuyen/sniffly) | Claude Code 仪表板，包含使用统计和错误分析 | 分析仪表板|
|[claude-code-log](https://github.com/daaain/claude-code-log) | ![GitHub Repo stars](https://badgen.net/github/stars/daaain/claude-code-log) | 将 Claude Code 转录 JSONL 文件转换为可读 HTML 格式 | 日志转换工具|
|[claude-code-costs](https://github.com/philipp-spiess/claude-code-costs) | ![GitHub Repo stars](https://badgen.net/github/stars/philipp-spiess/claude-code-costs) | Claude Code 使用成本跟踪 | 成本跟踪工具|
|[cctrace](https://github.com/jimmc414/cctrace) | ![GitHub Repo stars](https://badgen.net/github/stars/jimmc414/cctrace) | 将 Claude Code 聊天会话导出为 markdown 和 XML | 会话导出工具|
|[claude-code-otel](https://github.com/ColeMurray/claude-code-otel) | ![GitHub Repo stars](https://badgen.net/github/stars/ColeMurray/claude-code-otel) | 监控 Claude Code 使用情况、性能和成本的综合可观测性解决方案 | 可观测性解决方案|

## 代理与 API 工具

|名称|Stars|简介|备注|
|-------|-------|-------|------|
|[claude-code-proxy](https://github.com/1rgs/claude-code-proxy) | ![GitHub Repo stars](https://badgen.net/github/stars/1rgs/claude-code-proxy) | 在 OpenAI 模型上运行 Claude Code | OpenAI 代理|
|[claude-code-proxy](https://github.com/fuergaosi233/claude-code-proxy) | ![GitHub Repo stars](https://badgen.net/github/stars/fuergaosi233/claude-code-proxy) | Claude Code 到 OpenAI API 代理 | API 代理服务|
|[claude-relay-service](https://github.com/Wei-Shaw/claude-relay-service) | ![GitHub Repo stars](https://badgen.net/github/stars/Wei-Shaw/claude-relay-service) | 自建 Claude code 镜像服务，支持多账户切换 | 中继服务|
|[claude-code-kimi-groq](https://github.com/fakerybakery/claude-code-kimi-groq) | ![GitHub Repo stars](https://badgen.net/github/stars/fakerybakery/claude-code-kimi-groq) | 通过 Groq 在 Claude Code 上使用 Kimi K2 的基本代理 | Kimi 代理|
|[y-router](https://github.com/luohy15/y-router) | ![GitHub Repo stars](https://badgen.net/github/stars/luohy15/y-router) | 使 Claude Code 能够与 OpenRouter 配合工作的简单代理 | OpenRouter 代理|
|[claude-code-openai-wrapper](https://github.com/RichardAtCT/claude-code-openai-wrapper) | ![GitHub Repo stars](https://badgen.net/github/stars/RichardAtCT/claude-code-openai-wrapper) | Claude Code 的 OpenAI API 兼容包装器 | OpenAI 兼容包装|
|[anyclaude](https://github.com/coder/anyclaude) | ![GitHub Repo stars](https://badgen.net/github/stars/coder/anyclaude) | 与任意 LLM 配合使用的 Claude Code | 多模型支持|
|[claude-code-open](https://github.com/Davincible/claude-code-open) | ![GitHub Repo stars](https://badgen.net/github/stars/Davincible/claude-code-open) | 支持任意 LLM 提供商的 Claude Code | 开放式 LLM 支持|

## 框架扩展

|名称|Stars|简介|备注|
|-------|-------|-------|------|
|[n8n-mcp](https://github.com/czlonkowski/n8n-mcp) | ![GitHub Repo stars](https://badgen.net/github/stars/czlonkowski/n8n-mcp) | 为 Claude Desktop/Code 构建 n8n 工作流的 MCP | n8n 工作流集成|
|[claude-flow](https://github.com/ruvnet/claude-flow) | ![GitHub Repo stars](https://badgen.net/github/stars/ruvnet/claude-flow) | AI 驱动开发编排的革命性飞跃 | 开发编排框架|
|[claude-squad](https://github.com/smtg-ai/claude-squad) | ![GitHub Repo stars](https://badgen.net/github/stars/smtg-ai/claude-squad) | 管理多个 AI 终端代理，如 Claude Code、Aider 等 | 多代理管理|
|[awesome-ai-system-prompts](https://github.com/dontriskit/awesome-ai-system-prompts) | ![GitHub Repo stars](https://badgen.net/github/stars/dontriskit/awesome-ai-system-prompts) | 顶级 AI 工具的系统提示精选集合 | 提示工程集合|
|[agent-rules](https://github.com/steipete/agent-rules) | ![GitHub Repo stars](https://badgen.net/github/stars/steipete/agent-rules) | 与 Claude Code 或 Cursor 等代理更好协作的规则和知识 | 代理协作规则|
|[claude-on-rails](https://github.com/obie/claude-on-rails) | ![GitHub Repo stars](https://badgen.net/github/stars/obie/claude-on-rails) | 使用 Claude Code 的 Ruby on Rails 开发框架 | Rails 开发框架|
|[claude-simone](https://github.com/Helmi/claude-simone) | ![GitHub Repo stars](https://badgen.net/github/stars/Helmi/claude-simone) | 使用 Claude Code 进行 AI 辅助开发的项目管理框架 | 项目管理框架|

## MCP 服务器与插件

|名称|Stars|简介|备注|
|-------|-------|-------|------|
|[git-mcp](https://github.com/idosal/git-mcp) | ![GitHub Repo stars](https://badgen.net/github/stars/idosal/git-mcp) | 为任何 GitHub 项目提供免费开源远程 MCP 服务器 | Git 集成 MCP|
|[codemcp](https://github.com/ezyang/codemcp) | ![GitHub Repo stars](https://badgen.net/github/stars/ezyang/codemcp) | Claude Desktop 的编程助手 MCP | 编程助手 MCP|
|[claude-code-mcp](https://github.com/steipete/claude-code-mcp) | ![GitHub Repo stars](https://badgen.net/github/stars/steipete/claude-code-mcp) | 将 Claude Code 作为一次性 MCP 服务器 | 嵌套代理 MCP|
|[mcp-memory-service](https://github.com/doobidoo/mcp-memory-service) | ![GitHub Repo stars](https://badgen.net/github/stars/doobidoo/mcp-memory-service) | 为 Claude 提供语义内存和持久存储功能的 MCP 服务器 | 内存服务 MCP|
|[mcp-server](https://github.com/e2b-dev/mcp-server) | ![GitHub Repo stars](https://badgen.net/github/stars/e2b-dev/mcp-server) | 通过 MCP 为 Claude 提供 E2B 代码运行能力 | 代码执行 MCP|
|[code-context](https://github.com/zilliztech/code-context) | ![GitHub Repo stars](https://badgen.net/github/stars/zilliztech/code-context) | 语义代码搜索的 MCP 插件 | 代码搜索 MCP|
|[mcp-claude-code](https://github.com/SDGLBL/mcp-claude-code) | ![GitHub Repo stars](https://badgen.net/github/stars/SDGLBL/mcp-claude-code) | Claude Code 功能的 MCP 实现 | 功能实现 MCP|
|[claude_code-gemini-mcp](https://github.com/RaiAnsar/claude_code-gemini-mcp) | ![GitHub Repo stars](https://badgen.net/github/stars/RaiAnsar/claude_code-gemini-mcp) | 为 Claude Code 简化的 Gemini | Gemini 集成|
|[claude-gemini-mcp-slim](https://github.com/cmdaltctr/claude-gemini-mcp-slim) | ![GitHub Repo stars](https://badgen.net/github/stars/cmdaltctr/claude-gemini-mcp-slim) | 轻量级 MCP 集成，为 Claude Code 带来 Gemini AI 功能 | 轻量级 Gemini 集成|
|[mcp-gemini-assistant](https://github.com/peterkrueck/mcp-gemini-assistant) | ![GitHub Repo stars](https://badgen.net/github/stars/peterkrueck/mcp-gemini-assistant) | Claude Code 的 MCP Gemini 编程助手 | Gemini 编程助手|

## 指南与文档

|名称|Stars|简介|备注|
|-------|-------|-------|------|
|[claude-code-requirements-builder](https://github.com/rizethereum/claude-code-requirements-builder) | ![GitHub Repo stars](https://badgen.net/github/stars/rizethereum/claude-code-requirements-builder) | Claude Code 项目的需求构建工具 | 需求构建工具|
|[claude-code-guide](https://github.com/zebbern/claude-code-guide) | ![GitHub Repo stars](https://badgen.net/github/stars/zebbern/claude-code-guide) | Claude 技巧和窍门的完整指南 | 使用指南|
|[claude-code-templates](https://github.com/davila7/claude-code-templates) | ![GitHub Repo stars](https://badgen.net/github/stars/davila7/claude-code-templates) | 配置和监控 Claude Code 的 CLI 工具 | 配置模板|
|[building-an-agentic-system](https://github.com/gerred/building-an-agentic-system) | ![GitHub Repo stars](https://badgen.net/github/stars/gerred/building-an-agentic-system) | 构建智能代理系统（如 Claude Code）的深度指南 | 代理系统指南|
|[claude-code-cookbook](https://github.com/wasabeef/claude-code-cookbook) | ![GitHub Repo stars](https://badgen.net/github/stars/wasabeef/claude-code-cookbook) | 让 Claude Code 更加便利使用的配置集 | 配置烹饪书|
|[claude-code-guide](https://github.com/revfactory/claude-code-guide) | ![GitHub Repo stars](https://badgen.net/github/stars/revfactory/claude-code-guide) | 与 Claude Code 一起进行潮流编程 | 韩语指南|
|[claude-code-cheat-sheet](https://github.com/Njengah/claude-code-cheat-sheet) | ![GitHub Repo stars](https://badgen.net/github/stars/Njengah/claude-code-cheat-sheet) | Claude Code 技巧、窍门和工作流的终极集合 | 备忘单|
|[Claude-React-Jumpstart](https://github.com/Bklieger/Claude-React-Jumpstart) | ![GitHub Repo stars](https://badgen.net/github/stars/Bklieger/Claude-React-Jumpstart) | 初学者本地运行 Claude 生成的 React 代码的分步指南 | React 快速开始|
|[claude-code-training](https://github.com/kousen/claude-code-training) | ![GitHub Repo stars](https://badgen.net/github/stars/kousen/claude-code-training) | Claude Code 培训课程的幻灯片和演示 | 培训材料|

## 其他工具与实用程序

|名称|Stars|简介|备注|
|-------|-------|-------|------|
|[kimi-cc](https://github.com/LLM-Red-Team/kimi-cc) | ![GitHub Repo stars](https://badgen.net/github/stars/LLM-Red-Team/kimi-cc) | 使用 Kimi 最新模型驱动你的 Claude Code | Kimi 模型集成|
|[Claude-Code-Development-Kit](https://github.com/peterkrueck/Claude-Code-Development-Kit) | ![GitHub Repo stars](https://badgen.net/github/stars/peterkrueck/Claude-Code-Development-Kit) | 大规模解决 Claude Code 的上下文管理问题 | 开发工具包|
|[claude-code-spec-workflow](https://github.com/Pimzino/claude-code-spec-workflow) | ![GitHub Repo stars](https://badgen.net/github/stars/Pimzino/claude-code-spec-workflow) | Claude Code 的自动化规范驱动工作流 | 规范工作流|
|[agentapi](https://github.com/coder/agentapi) | ![GitHub Repo stars](https://badgen.net/github/stars/coder/agentapi) | Claude Code、Goose、Aider、Gemini 和 Codex 的 HTTP API | 多代理 API|
|[claudebox](https://github.com/RchGrav/claudebox) | ![GitHub Repo stars](https://badgen.net/github/stars/RchGrav/claudebox) | 终极 Claude Code Docker 开发环境 | Docker 开发环境|
|[ccmanager](https://github.com/kbwo/ccmanager) | ![GitHub Repo stars](https://badgen.net/github/stars/kbwo/ccmanager) | Claude Code/Gemini CLI/Codex CLI 会话管理器 | 会话管理器|
|[claude-cmd](https://github.com/kiliczsh/claude-cmd) | ![GitHub Repo stars](https://badgen.net/github/stars/kiliczsh/claude-cmd) | Claude Code 命令管理器 | 命令管理器|
|[code-graph-rag](https://github.com/vitali87/code-graph-rag) | ![GitHub Repo stars](https://badgen.net/github/stars/vitali87/code-graph-rag) | 比 Claude Code 或 Gemini CLI 更适合 Monorepos | Monorepo 工具|
|[CodeWebChat](https://github.com/robertpiosik/CodeWebChat) | ![GitHub Repo stars](https://badgen.net/github/stars/robertpiosik/CodeWebChat) | 为所有人提供免费 AI 编程 | 免费 AI 编程|
|[opencoder](https://github.com/ducan-ne/opencoder) | ![GitHub Repo stars](https://badgen.net/github/stars/ducan-ne/opencoder) | Claude Code 的替代方案 | 开源替代品|
|[async-code](https://github.com/ObservedObserver/async-code) | ![GitHub Repo stars](https://badgen.net/github/stars/ObservedObserver/async-code) | 使用 Claude Code/CodeX CLI 并行执行多个任务 | 并行任务执行|
|[CursorLens](https://github.com/HamedMP/CursorLens) | ![GitHub Repo stars](https://badgen.net/github/stars/HamedMP/CursorLens) | Cursor.sh IDE 的开源仪表板 | Cursor 监控面板|
|[win-claude-code](https://github.com/somersby10ml/win-claude-code) | ![GitHub Repo stars](https://badgen.net/github/stars/somersby10ml/win-claude-code) | Windows 版 Claude Code：无需 WSL，无需 Docker | Windows 原生支持|

## 逆向工程与分析

|名称|Stars|简介|备注|
|-------|-------|-------|------|
|[claude-code-source-code-deobfuscation](https://github.com/ghuntley/claude-code-source-code-deobfuscation) | ![GitHub Repo stars](https://badgen.net/github/stars/ghuntley/claude-code-source-code-deobfuscation) | 官方 Claude Code npm 包的洁净室反混淆 | 源码反混淆|
|[claude-code-reverse](https://github.com/Yuyz0112/claude-code-reverse) | ![GitHub Repo stars](https://badgen.net/github/stars/Yuyz0112/claude-code-reverse) | 使用 LLM 逆向工程 Claude Code | 逆向工程研究|
|[claude-code-induced-introspection](https://github.com/mo-haggag/claude-code-induced-introspection) | ![GitHub Repo stars](https://badgen.net/github/stars/mo-haggag/claude-code-induced-introspection) | Claude Code 通过诱导内省解释自身 | 内省分析|

## SDK 与开发工具

|名称|Stars|简介|备注|
|-------|-------|-------|------|
|[claude-code-sdk-ts](https://github.com/instantlyeasy/claude-code-sdk-ts) | ![GitHub Repo stars](https://badgen.net/github/stars/instantlyeasy/claude-code-sdk-ts) | 流畅的链式 TypeScript SDK | TypeScript SDK|
|[claude-code-js](https://github.com/s-soroosh/claude-code-js) | ![GitHub Repo stars](https://badgen.net/github/stars/s-soroosh/claude-code-js) | Javascript 和 Typescript 的 Claude Code SDK | JS/TS SDK|
|[claude-code-boost](https://github.com/yifanzz/claude-code-boost) | ![GitHub Repo stars](https://badgen.net/github/stars/yifanzz/claude-code-boost) | Claude Code 的钩子实用程序和智能自动批准 | 增强工具|
|[claude-code-sandbox](https://github.com/textcortex/claude-code-sandbox) | ![GitHub Repo stars](https://badgen.net/github/stars/textcortex/claude-code-sandbox) | 在本地 Docker 容器中安全运行 Claude Code | 沙盒环境|
|[claude-docker](https://github.com/VishalJ99/claude-docker) | ![GitHub Repo stars](https://badgen.net/github/stars/VishalJ99/claude-docker) | 具有完整权限和 Twilio 通知的 Claude Code Docker 容器 | Docker 容器|
|[claude-code-ntfy](https://github.com/Veraticus/claude-code-ntfy) | ![GitHub Repo stars](https://badgen.net/github/stars/Veraticus/claude-code-ntfy) | Claude Code 到 ntfy.sh 的桥接 | 通知桥接|
|[ai-sdk-provider-claude-code](https://github.com/ben-vargas/ai-sdk-provider-claude-code) | ![GitHub Repo stars](https://badgen.net/github/stars/ben-vargas/ai-sdk-provider-claude-code) | Claude Code SDK 的 Vercel AI SDK 社区提供商 | Vercel AI SDK 集成|

---

## 🤝 贡献

发现了很棒的 Claude Code 相关项目？欢迎提交 Pull Request 贡献！

## 📄 许可证

本精选列表在 [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/) 许可证下发布。