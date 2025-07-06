# Vue.js 项目 CLAUDE.md 模板

```markdown
# CLAUDE.md

这个文件为 Claude Code 提供项目特定的指导信息。

## 项目概述

这是一个使用 Vue.js 构建的现代前端应用。

## 技术栈

- **框架**: Vue.js 3.4+
- **语言**: TypeScript 5.2+
- **构建工具**: Vite 5.0
- **状态管理**: Pinia
- **路由**: Vue Router 4
- **UI 框架**: Element Plus / Vuetify / Quasar
- **样式**: SCSS + CSS Modules
- **包管理器**: pnpm
- **代码质量**: ESLint + Prettier
- **测试**: Vitest + Vue Test Utils

## 项目结构

```
src/
├── main.ts             # 应用入口
├── App.vue             # 根组件
├── router/             # 路由配置
│   ├── index.ts        # 路由主文件
│   └── routes.ts       # 路由定义
├── stores/             # Pinia 状态管理
│   ├── index.ts        # Store 入口
│   ├── user.ts         # 用户状态
│   └── app.ts          # 应用状态
├── views/              # 页面组件
│   ├── Home.vue
│   ├── About.vue
│   └── auth/
│       ├── Login.vue
│       └── Register.vue
├── components/         # 可复用组件
│   ├── common/         # 通用组件
│   ├── ui/             # UI 组件
│   └── forms/          # 表单组件
├── composables/        # 组合式函数
│   ├── useAuth.ts
│   ├── useApi.ts
│   └── useUtils.ts
├── utils/              # 工具函数
│   ├── api.ts          # API 客户端
│   ├── helpers.ts      # 帮助函数
│   └── constants.ts    # 常量定义
├── types/              # TypeScript 类型
│   ├── api.ts          # API 类型
│   ├── user.ts         # 用户类型
│   └── common.ts       # 通用类型
└── assets/             # 静态资源
    ├── styles/         # 样式文件
    ├── images/         # 图片资源
    └── icons/          # 图标文件
```

## 常用命令

- `pnpm dev`: 启动开发服务器
- `pnpm build`: 构建生产版本
- `pnpm preview`: 预览生产构建
- `pnpm test`: 运行单元测试
- `pnpm test:coverage`: 运行测试并生成覆盖率报告
- `pnpm lint`: 运行 ESLint 检查
- `pnpm lint:fix`: 自动修复 ESLint 错误
- `pnpm type-check`: 运行 TypeScript 类型检查

## 代码规范

### 组件规范
- 使用 Composition API 和 `<script setup>`
- 组件名使用 PascalCase
- 文件名使用 PascalCase
- Props 和 emits 必须定义 TypeScript 类型

```vue
<script setup lang="ts">
interface Props {
  title: string
  count?: number
}

interface Emits {
  update: [value: string]
  close: []
}

const props = withDefaults(defineProps<Props>(), {
  count: 0
})

const emit = defineEmits<Emits>()
</script>
```

### 样式规范
- 使用 SCSS 预处理器
- 采用 BEM 命名规范
- 优先使用 CSS Modules 或 scoped 样式
- 响应式设计使用 Flexbox 和 Grid

```vue
<style lang="scss" scoped>
.user-card {
  padding: 1rem;
  border-radius: 8px;
  
  &__header {
    display: flex;
    align-items: center;
    margin-bottom: 1rem;
  }
  
  &__title {
    font-size: 1.2rem;
    font-weight: 600;
  }
  
  @media (max-width: 768px) {
    padding: 0.5rem;
  }
}
</style>
```

### 状态管理规范
- 使用 Pinia 进行状态管理
- Store 按功能模块划分
- 使用 TypeScript 定义 Store 类型

```typescript
// stores/user.ts
export const useUserStore = defineStore('user', () => {
  const user = ref<User | null>(null)
  const isLoggedIn = computed(() => !!user.value)
  
  const login = async (credentials: LoginCredentials) => {
    const response = await authApi.login(credentials)
    user.value = response.user
  }
  
  const logout = () => {
    user.value = null
  }
  
  return {
    user: readonly(user),
    isLoggedIn,
    login,
    logout
  }
})
```

### 组合式函数规范
- 函数名以 `use` 开头
- 返回响应式数据和方法
- 处理副作用和清理

```typescript
// composables/useApi.ts
export function useApi<T>(url: string) {
  const data = ref<T | null>(null)
  const loading = ref(false)
  const error = ref<string | null>(null)
  
  const fetch = async () => {
    loading.value = true
    error.value = null
    
    try {
      const response = await api.get<T>(url)
      data.value = response.data
    } catch (err) {
      error.value = err.message
    } finally {
      loading.value = false
    }
  }
  
  onMounted(fetch)
  
  return {
    data: readonly(data),
    loading: readonly(loading),
    error: readonly(error),
    refetch: fetch
  }
}
```

## 路由配置

```typescript
// router/routes.ts
export const routes: RouteRecordRaw[] = [
  {
    path: '/',
    name: 'Home',
    component: () => import('@/views/Home.vue'),
    meta: { title: '首页' }
  },
  {
    path: '/auth',
    component: () => import('@/layouts/AuthLayout.vue'),
    children: [
      {
        path: 'login',
        name: 'Login',
        component: () => import('@/views/auth/Login.vue'),
        meta: { title: '登录' }
      }
    ]
  }
]
```

## 测试策略

### 组件测试
```typescript
// components/__tests__/UserCard.spec.ts
import { mount } from '@vue/test-utils'
import UserCard from '../UserCard.vue'

describe('UserCard', () => {
  it('should render user information', () => {
    const wrapper = mount(UserCard, {
      props: {
        user: { name: 'John Doe', email: 'john@example.com' }
      }
    })
    
    expect(wrapper.text()).toContain('John Doe')
    expect(wrapper.text()).toContain('john@example.com')
  })
})
```

### 组合式函数测试
```typescript
// composables/__tests__/useCounter.spec.ts
import { useCounter } from '../useCounter'

describe('useCounter', () => {
  it('should increment count', () => {
    const { count, increment } = useCounter()
    
    expect(count.value).toBe(0)
    increment()
    expect(count.value).toBe(1)
  })
})
```

## 性能优化

1. **组件懒加载**
   ```typescript
   const AsyncComponent = defineAsyncComponent(() => import('./HeavyComponent.vue'))
   ```

2. **虚拟滚动**
   ```vue
   <virtual-list
     :data-key="'id'"
     :data-sources="items"
     :data-component="ItemComponent"
   />
   ```

3. **缓存优化**
   ```vue
   <keep-alive :include="['UserProfile', 'Dashboard']">
     <router-view />
   </keep-alive>
   ```

## 环境配置

### 开发环境变量
```bash
# .env.development
VITE_API_BASE_URL=http://localhost:3000/api
VITE_APP_TITLE=Vue App (Development)
VITE_ENABLE_MOCK=true
```

### 生产环境变量
```bash
# .env.production
VITE_API_BASE_URL=https://api.example.com
VITE_APP_TITLE=Vue App
VITE_ENABLE_MOCK=false
```

## 构建配置

```typescript
// vite.config.ts
export default defineConfig({
  plugins: [
    vue(),
    vueJsx(),
    Components({
      resolvers: [ElementPlusResolver()]
    })
  ],
  resolve: {
    alias: {
      '@': fileURLToPath(new URL('./src', import.meta.url))
    }
  },
  build: {
    rollupOptions: {
      output: {
        manualChunks: {
          'element-plus': ['element-plus'],
          'vue-vendor': ['vue', 'vue-router', 'pinia']
        }
      }
    }
  }
})
```

## 不要做的事情

- 不要在组件中直接操作 DOM
- 不要在 `<script setup>` 中定义大量计算属性
- 不要忽略 Vue 3 的响应式原理
- 不要在模板中使用复杂的表达式
- 不要滥用 Teleport 和动态组件

## 常见问题解决

1. **响应式丢失问题**
   ```typescript
   // 错误
   const { user } = store
   
   // 正确
   const { user } = storeToRefs(store)
   ```

2. **类型定义问题**
   ```typescript
   // 为组件 ref 定义类型
   const componentRef = ref<InstanceType<typeof MyComponent>>()
   ```

3. **样式穿透问题**
   ```vue
   <style scoped>
   .parent :deep(.child) {
     color: red;
   }
   </style>
   ```

## 部署说明

- 使用 Netlify/Vercel 进行静态部署
- 确保路由配置支持 SPA 模式
- 配置环境变量和构建钩子
- 启用 gzip 压缩和缓存策略
```