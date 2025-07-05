# React/Next.js 项目 CLAUDE.md 模板

```markdown
# CLAUDE.md

这个文件为 Claude Code 提供项目特定的指导信息。

## 项目概述

这是一个使用 React 和 Next.js 构建的现代前端应用。

## 技术栈

- **框架**: Next.js 14 (App Router)
- **语言**: TypeScript 5.2+
- **样式**: Tailwind CSS 3.4
- **状态管理**: Zustand / Redux Toolkit
- **UI 组件**: Shadcn/ui
- **包管理器**: pnpm
- **代码质量**: ESLint + Prettier
- **测试**: Jest + React Testing Library

## 项目结构

```
src/
├── app/                 # Next.js App Router 页面
│   ├── (auth)/         # 认证相关页面组
│   ├── dashboard/      # 仪表板页面
│   ├── api/           # API 路由
│   ├── globals.css    # 全局样式
│   └── layout.tsx     # 根布局
├── components/         # 可复用组件
│   ├── ui/            # 基础 UI 组件
│   ├── forms/         # 表单组件
│   └── layout/        # 布局组件
├── lib/               # 工具函数和配置
│   ├── utils.ts       # 通用工具函数
│   ├── validations.ts # 表单验证
│   └── api.ts         # API 客户端
├── hooks/             # 自定义 React Hooks
├── stores/            # 状态管理
├── types/             # TypeScript 类型定义
└── styles/            # 样式文件
```

## 常用命令

- `pnpm dev`: 启动开发服务器
- `pnpm build`: 构建生产版本
- `pnpm start`: 启动生产服务器
- `pnpm test`: 运行测试
- `pnpm test:watch`: 监视模式运行测试
- `pnpm lint`: 运行 ESLint 检查
- `pnpm lint:fix`: 自动修复 ESLint 错误
- `pnpm type-check`: 运行 TypeScript 类型检查

## 代码规范

### 组件规范
- 使用函数组件和 Hooks
- 组件名使用 PascalCase
- 文件名使用 kebab-case
- 优先使用 TypeScript 接口定义 props

### 样式规范
- 使用 Tailwind CSS 类名
- 避免内联样式
- 使用 CSS 模块处理复杂样式
- 遵循移动优先的响应式设计

### 导入规范
- 使用绝对路径导入 (@ 别名)
- 第三方库导入放在顶部
- 组件导入按字母顺序排列

```typescript
// 第三方库
import React from 'react'
import { NextPage } from 'next'

// 内部组件
import { Button } from '@/components/ui/button'
import { Header } from '@/components/layout/header'

// 工具函数
import { cn } from '@/lib/utils'
```

### 状态管理
- 使用 Zustand 进行全局状态管理
- 本地状态优先使用 useState
- 复杂状态逻辑使用 useReducer
- 异步状态使用 React Query/SWR

## 文件命名约定

- 组件文件: `component-name.tsx`
- 页面文件: `page.tsx`
- 布局文件: `layout.tsx`
- 工具函数: `utils.ts`
- 类型定义: `types.ts`
- 测试文件: `component-name.test.tsx`

## 开发最佳实践

1. **组件设计**
   - 单一职责原则
   - 可复用性优先
   - 使用 TypeScript 进行类型安全

2. **性能优化**
   - 使用 React.memo 优化重渲染
   - 合理使用 useMemo 和 useCallback
   - 图片使用 Next.js Image 组件

3. **错误处理**
   - 使用 Error Boundary 处理组件错误
   - API 错误统一处理
   - 用户友好的错误提示

## 测试策略

- 单元测试: 覆盖工具函数和 Hooks
- 组件测试: 测试用户交互和渲染
- 集成测试: 测试页面级别的功能
- E2E 测试: 使用 Playwright 进行端到端测试

## 不要做的事情

- 不要直接修改 node_modules
- 不要在组件中直接使用 console.log
- 不要绕过 TypeScript 类型检查
- 不要在生产代码中使用 any 类型
- 不要直接操作 DOM (除非必要)

## 常见问题解决

1. **性能问题**: 使用 React DevTools Profiler 分析
2. **样式问题**: 检查 Tailwind 配置和 CSS 优先级
3. **路由问题**: 确认 App Router 的文件结构
4. **构建错误**: 检查 TypeScript 类型和 ESLint 规则

## 部署说明

- 使用 Vercel 进行部署
- 环境变量配置在 `.env.local`
- 确保所有测试通过后再部署
- 使用 Preview 部署进行测试
```