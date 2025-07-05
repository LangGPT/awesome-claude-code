# Claude Code 快速入门

欢迎使用 Claude Code！这个指南将帮助您在 5 分钟内快速上手。

## 什么是 Claude Code？

Claude Code 是 Anthropic 开发的智能编程助手，直接在终端中运行，可以：

- 🔧 编辑文件和修复代码错误
- 💬 回答代码架构和逻辑问题
- 🧪 运行和修复测试
- 📚 搜索 Git 历史和解决合并冲突
- 🚀 创建提交和 Pull Request

## 安装步骤

### 1. 安装 Claude Code

```bash
# 使用 npm 安装
npm install -g @anthropic-ai/claude-code

# 或使用 yarn
yarn global add @anthropic-ai/claude-code
```

### 2. 验证安装

```bash
claude --version
```

如果看到版本号，说明安装成功！

## 首次使用

### 1. 启动 Claude Code

在您的项目目录中运行：

```bash
claude
```

第一次运行时，Claude Code 会引导您完成初始配置。

### 2. 基本交互

启动后，您会看到类似这样的界面：

```
Claude Code is ready to help! What would you like to do?
> 
```

### 3. 尝试第一个命令

输入一个简单的问题：

```
> 这个项目是做什么的？
```

Claude Code 会分析您的项目结构并给出回答。

## 常用操作

### 代码分析

```bash
# 分析项目结构
> 给我介绍一下这个项目的架构

# 查找特定功能
> 用户认证功能在哪个文件中？

# 解释复杂代码
> 解释一下这个函数的作用：@src/utils/helper.js:25-40
```

### 文件操作

```bash
# 创建新文件
> 创建一个新的 React 组件 Button

# 修改现有文件
> 在 App.js 中添加一个新的路由

# 修复错误
> 修复这个 TypeScript 错误：@src/components/Header.tsx:12
```

### Git 操作

```bash
# 查看项目状态
> 检查 Git 状态

# 创建提交
> 为当前更改创建一个提交

# 查看历史
> 显示最近的提交记录
```

## 实用技巧

### 1. 使用文件引用

您可以使用 `@` 符号引用文件：

```bash
# 引用整个文件
> 优化这个文件：@src/App.js

# 引用特定行
> 解释这段代码：@src/utils/api.js:15-25

# 引用多个文件
> 比较这两个文件的差异：@src/old.js @src/new.js
```

### 2. 使用斜杠命令

```bash
# 显示帮助
/help

# 编辑记忆文件
/memory

# 查看设置
/settings

# 退出 Claude Code
/exit
```

### 3. 项目记忆功能

创建 `CLAUDE.md` 文件来告诉 Claude Code 关于您的项目：

```markdown
# 项目说明

这是一个使用 React 和 TypeScript 的前端项目。

## 技术栈
- React 18
- TypeScript
- Tailwind CSS
- Vite

## 开发命令
- `npm run dev`: 启动开发服务器
- `npm run build`: 构建项目
- `npm run test`: 运行测试

## 代码规范
- 使用函数组件
- 所有组件必须有 TypeScript 类型
- 使用 Tailwind CSS 进行样式设计
```

## 常见用例

### 1. 学习新项目

```bash
# 了解项目结构
> 这个项目的主要组件是什么？

# 理解数据流
> 数据是如何在组件间传递的？

# 查找入口点
> 应用的入口文件是哪个？
```

### 2. 开发新功能

```bash
# 规划功能
> 我需要添加用户登录功能，应该如何设计？

# 创建文件
> 创建登录组件和相关的 API 调用

# 测试功能
> 为登录功能编写单元测试
```

### 3. 调试问题

```bash
# 分析错误
> 这个错误是什么意思？[粘贴错误信息]

# 查找问题
> 为什么这个函数没有按预期工作？

# 修复代码
> 修复这个 bug 并解释原因
```

## 高级功能预览

### 钩子 (Hooks)
自动化任务执行，如代码格式化、测试运行等。

### 自定义命令
创建您自己的斜杠命令来标准化常见任务。

### 团队协作
通过共享 CLAUDE.md 文件来标准化团队工作流程。

## 下一步

现在您已经掌握了基础用法，可以：

1. 阅读 [基本概念](./concepts.md) 了解更多理论知识
2. 查看 [常用命令](./commands.md) 学习更多命令
3. 探索 [配置管理](./configuration.md) 个性化您的体验
4. 尝试 [高级教程](../advanced/) 中的进阶功能

## 获取帮助

如果您遇到问题：

1. 在 Claude Code 中输入 `/help` 查看帮助
2. 查看 [故障排除](../troubleshooting/common-issues.md) 指南
3. 访问 [官方文档](https://docs.anthropic.com/zh-CN/docs/claude-code/overview)
4. 在 GitHub 上提交 Issue

祝您使用愉快！ 🚀