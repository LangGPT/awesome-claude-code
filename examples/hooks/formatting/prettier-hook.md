# Prettier 代码格式化钩子

这个钩子会在每次文件编辑后自动运行 Prettier 格式化代码。

## 配置方法

1. 运行 `/hooks` 命令
2. 选择 `PostToolUse` 钩子事件
3. 将以下脚本保存到指定位置

## 钩子脚本

```bash
#!/bin/bash

# Prettier 格式化钩子
# 在文件编辑后自动运行 Prettier

# 检查是否安装了 Prettier
if ! command -v prettier &> /dev/null; then
    echo "Prettier 未安装，跳过格式化"
    exit 0
fi

# 获取编辑的文件路径
EDITED_FILE="$1"

# 检查文件是否存在
if [ ! -f "$EDITED_FILE" ]; then
    echo "文件不存在: $EDITED_FILE"
    exit 0
fi

# 检查文件扩展名
FILE_EXT="${EDITED_FILE##*.}"

# 支持的文件类型
SUPPORTED_EXTENSIONS=("js" "jsx" "ts" "tsx" "json" "html" "css" "scss" "md" "vue")

# 检查是否为支持的文件类型
if [[ " ${SUPPORTED_EXTENSIONS[@]} " =~ " ${FILE_EXT} " ]]; then
    echo "🎨 正在格式化: $EDITED_FILE"
    
    # 运行 Prettier
    if prettier --write "$EDITED_FILE"; then
        echo "✅ 格式化完成: $EDITED_FILE"
    else
        echo "❌ 格式化失败: $EDITED_FILE"
        exit 1
    fi
else
    echo "跳过格式化 (不支持的文件类型): $EDITED_FILE"
fi

exit 0
```

## 高级配置

### 带配置文件的版本

```bash
#!/bin/bash

# 高级 Prettier 格式化钩子
# 支持项目特定的配置文件

EDITED_FILE="$1"
PROJECT_ROOT=$(git rev-parse --show-toplevel 2>/dev/null || pwd)

# 检查是否安装了 Prettier
if ! command -v prettier &> /dev/null; then
    echo "Prettier 未安装，跳过格式化"
    exit 0
fi

# 检查是否有 Prettier 配置文件
PRETTIER_CONFIG=""
if [ -f "$PROJECT_ROOT/.prettierrc" ]; then
    PRETTIER_CONFIG="$PROJECT_ROOT/.prettierrc"
elif [ -f "$PROJECT_ROOT/.prettierrc.json" ]; then
    PRETTIER_CONFIG="$PROJECT_ROOT/.prettierrc.json"
elif [ -f "$PROJECT_ROOT/.prettierrc.js" ]; then
    PRETTIER_CONFIG="$PROJECT_ROOT/.prettierrc.js"
elif [ -f "$PROJECT_ROOT/prettier.config.js" ]; then
    PRETTIER_CONFIG="$PROJECT_ROOT/prettier.config.js"
fi

# 检查是否有忽略文件
PRETTIER_IGNORE=""
if [ -f "$PROJECT_ROOT/.prettierignore" ]; then
    PRETTIER_IGNORE="$PROJECT_ROOT/.prettierignore"
fi

# 检查文件是否应该被忽略
if [ -n "$PRETTIER_IGNORE" ] && grep -q "$(basename "$EDITED_FILE")" "$PRETTIER_IGNORE"; then
    echo "文件被忽略，跳过格式化: $EDITED_FILE"
    exit 0
fi

# 检查文件扩展名
FILE_EXT="${EDITED_FILE##*.}"
SUPPORTED_EXTENSIONS=("js" "jsx" "ts" "tsx" "json" "html" "css" "scss" "md" "vue" "yaml" "yml")

if [[ " ${SUPPORTED_EXTENSIONS[@]} " =~ " ${FILE_EXT} " ]]; then
    echo "🎨 正在格式化: $EDITED_FILE"
    
    # 构建 Prettier 命令
    PRETTIER_CMD="prettier --write"
    
    if [ -n "$PRETTIER_CONFIG" ]; then
        PRETTIER_CMD="$PRETTIER_CMD --config $PRETTIER_CONFIG"
    fi
    
    if [ -n "$PRETTIER_IGNORE" ]; then
        PRETTIER_CMD="$PRETTIER_CMD --ignore-path $PRETTIER_IGNORE"
    fi
    
    # 运行 Prettier
    if eval "$PRETTIER_CMD \"$EDITED_FILE\""; then
        echo "✅ 格式化完成: $EDITED_FILE"
    else
        echo "❌ 格式化失败: $EDITED_FILE"
        exit 1
    fi
else
    echo "跳过格式化 (不支持的文件类型): $EDITED_FILE"
fi

exit 0
```

## 项目配置示例

### .prettierrc.json

```json
{
  "semi": true,
  "trailingComma": "es5",
  "singleQuote": true,
  "printWidth": 80,
  "tabWidth": 2,
  "useTabs": false,
  "bracketSpacing": true,
  "arrowParens": "avoid",
  "endOfLine": "lf"
}
```

### .prettierignore

```
# 忽略构建输出
dist/
build/
public/
.next/

# 忽略依赖
node_modules/
*.min.js
*.min.css

# 忽略生成的文件
*.generated.js
*.generated.ts

# 忽略配置文件
.env*
```

## 使用场景

1. **团队协作**: 确保所有团队成员的代码格式一致
2. **自动化工作流**: 减少手动格式化的工作
3. **代码质量**: 保持代码的可读性和一致性
4. **CI/CD 集成**: 确保提交的代码符合格式要求

## 注意事项

- 确保项目中已安装 Prettier
- 建议配置 `.prettierrc` 文件以保持格式一致
- 对于大型项目，考虑性能影响
- 可以通过 `.prettierignore` 排除不需要格式化的文件

## 故障排除

### 常见问题

1. **Prettier 未安装**
   ```bash
   npm install --save-dev prettier
   # 或者全局安装
   npm install -g prettier
   ```

2. **权限问题**
   ```bash
   chmod +x /path/to/hook/script
   ```

3. **配置文件格式错误**
   - 检查 `.prettierrc` 文件的 JSON 格式
   - 使用 `prettier --check` 验证配置

## 扩展功能

- 结合 ESLint 进行代码质量检查
- 添加 Git 钩子进行提交前检查
- 集成到 CI/CD 流程中
- 支持多种代码格式化工具