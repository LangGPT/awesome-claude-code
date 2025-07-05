# 创建功能分支

创建一个新的功能分支，遵循团队的分支命名规范。

## 使用方法

将此文件保存为 `.claude/commands/create-feature-branch.md`，然后使用 `/create-feature-branch` 命令。

## 命令内容

```markdown
# 创建功能分支

请帮我创建一个新的功能分支，遵循以下步骤：

1. 确保当前在 main/master 分支
2. 拉取最新的代码
3. 创建新的功能分支

## 分支命名规范

- 功能分支: `feature/功能描述`
- 修复分支: `bugfix/问题描述`
- 热修复: `hotfix/紧急修复描述`

## 分支名称

功能描述: $ARGUMENTS

## 执行步骤

1. 检查当前分支状态
2. 确保工作区干净
3. 切换到主分支
4. 拉取最新代码
5. 创建并切换到新分支
6. 推送新分支到远程仓库

请执行这些步骤，并在每个步骤完成后给我反馈。
```

## 示例用法

```bash
# 创建用户认证功能分支
/create-feature-branch 用户认证功能

# 创建购物车功能分支
/create-feature-branch 购物车模块

# 创建 API 优化分支
/create-feature-branch api-performance-optimization
```

## 预期输出

Claude Code 将会：

1. 检查当前 Git 状态
2. 切换到主分支
3. 拉取最新代码
4. 创建新的功能分支 (例如: `feature/用户认证功能`)
5. 推送分支到远程仓库
6. 提供分支创建成功的确认信息

## 相关命令

- `/finish-feature` - 完成功能开发
- `/sync-branch` - 同步分支代码
- `/create-pr` - 创建 Pull Request