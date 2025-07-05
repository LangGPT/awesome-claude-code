# Python/FastAPI 项目 CLAUDE.md 模板

```markdown
# CLAUDE.md

这个文件为 Claude Code 提供项目特定的指导信息。

## 项目概述

这是一个使用 Python 和 FastAPI 构建的现代后端 API 服务。

## 技术栈

- **框架**: FastAPI 0.104+
- **语言**: Python 3.11+
- **数据库**: PostgreSQL 15+ / SQLite (开发)
- **ORM**: SQLAlchemy 2.0
- **数据验证**: Pydantic v2
- **认证**: JWT + OAuth2
- **测试**: pytest + httpx
- **任务队列**: Celery + Redis
- **文档**: 自动生成 OpenAPI/Swagger
- **部署**: Docker + Docker Compose

## 项目结构

```
app/
├── __init__.py
├── main.py              # FastAPI 应用入口
├── config.py            # 配置管理
├── dependencies.py      # 依赖注入
├── database.py          # 数据库连接
├── models/              # SQLAlchemy 模型
│   ├── __init__.py
│   ├── user.py
│   └── base.py
├── schemas/             # Pydantic 模式
│   ├── __init__.py
│   ├── user.py
│   └── base.py
├── api/                 # API 路由
│   ├── __init__.py
│   ├── v1/
│   │   ├── __init__.py
│   │   ├── endpoints/
│   │   │   ├── users.py
│   │   │   └── auth.py
│   │   └── api.py
│   └── deps.py
├── core/                # 核心功能
│   ├── __init__.py
│   ├── auth.py          # 认证相关
│   ├── security.py      # 安全工具
│   └── utils.py         # 工具函数
├── services/            # 业务逻辑
│   ├── __init__.py
│   └── user_service.py
├── tests/               # 测试文件
│   ├── __init__.py
│   ├── conftest.py
│   ├── test_main.py
│   └── test_users.py
└── alembic/             # 数据库迁移
    ├── env.py
    └── versions/
```

## 常用命令

### 开发环境
- `uvicorn app.main:app --reload`: 启动开发服务器
- `python -m pytest`: 运行所有测试
- `python -m pytest -v`: 详细模式运行测试
- `python -m pytest tests/test_users.py`: 运行特定测试
- `python -m pytest --cov=app`: 运行测试并生成覆盖率报告

### 数据库管理
- `alembic revision --autogenerate -m "描述"`: 生成迁移文件
- `alembic upgrade head`: 应用所有迁移
- `alembic downgrade -1`: 回滚最近的迁移
- `alembic current`: 查看当前迁移版本

### 代码质量
- `black .`: 格式化代码
- `isort .`: 整理导入
- `flake8 .`: 检查代码风格
- `mypy .`: 类型检查
- `bandit -r app/`: 安全检查

### Docker
- `docker-compose up -d`: 启动所有服务
- `docker-compose exec web bash`: 进入 web 容器
- `docker-compose logs -f web`: 查看 web 服务日志

## 代码规范

### 文件命名
- 模块名使用 snake_case
- 类名使用 PascalCase
- 函数名使用 snake_case
- 常量使用 UPPER_CASE

### 导入规范
```python
# 标准库
import os
from datetime import datetime
from typing import Optional, List

# 第三方库
from fastapi import FastAPI, Depends, HTTPException
from sqlalchemy.orm import Session
from pydantic import BaseModel

# 本地导入
from app.database import get_db
from app.models.user import User
from app.schemas.user import UserCreate, UserResponse
```

### API 路由规范
```python
@router.post("/users/", response_model=UserResponse)
async def create_user(
    user: UserCreate,
    db: Session = Depends(get_db),
    current_user: User = Depends(get_current_user)
):
    """创建新用户"""
    # 实现逻辑
    pass
```

### 异常处理
```python
# 使用 FastAPI 的 HTTPException
raise HTTPException(
    status_code=404,
    detail="用户不存在"
)

# 自定义异常
class UserNotFoundError(Exception):
    pass
```

## 数据库最佳实践

### 模型定义
```python
class User(Base):
    __tablename__ = "users"
    
    id = Column(Integer, primary_key=True, index=True)
    email = Column(String, unique=True, index=True, nullable=False)
    created_at = Column(DateTime, default=datetime.utcnow)
    updated_at = Column(DateTime, default=datetime.utcnow, onupdate=datetime.utcnow)
```

### 查询优化
- 使用 `select` 语句而不是 `query`
- 合理使用 `join` 和 `selectinload`
- 避免 N+1 查询问题
- 使用数据库索引

## 测试策略

### 测试结构
```python
# conftest.py
@pytest.fixture
def client():
    with TestClient(app) as c:
        yield c

@pytest.fixture
def db_session():
    # 测试数据库会话
    pass

# 测试用例
def test_create_user(client, db_session):
    response = client.post(
        "/api/v1/users/",
        json={"email": "test@example.com", "password": "testpass"}
    )
    assert response.status_code == 201
```

### 测试类型
- 单元测试: 测试单个函数
- 集成测试: 测试 API 端点
- 数据库测试: 测试数据库操作
- 性能测试: 测试 API 性能

## 安全最佳实践

### 认证和授权
```python
# JWT 令牌配置
SECRET_KEY = "your-secret-key"
ALGORITHM = "HS256"
ACCESS_TOKEN_EXPIRE_MINUTES = 30

# 密码加密
def hash_password(password: str) -> str:
    return pwd_context.hash(password)
```

### 数据验证
```python
class UserCreate(BaseModel):
    email: EmailStr
    password: str = Field(..., min_length=8)
    
    @validator('password')
    def validate_password(cls, v):
        # 密码强度验证
        return v
```

## 环境配置

### 环境变量
```python
# .env
DATABASE_URL=postgresql://user:password@localhost/dbname
SECRET_KEY=your-secret-key
DEBUG=True
REDIS_URL=redis://localhost:6379
```

### 配置管理
```python
class Settings(BaseSettings):
    database_url: str
    secret_key: str
    debug: bool = False
    
    class Config:
        env_file = ".env"
```

## 性能优化

1. **数据库优化**
   - 使用连接池
   - 合理使用索引
   - 查询优化

2. **缓存策略**
   - Redis 缓存
   - 查询结果缓存
   - 会话缓存

3. **异步处理**
   - 使用 async/await
   - 后台任务处理
   - 队列系统

## 监控和日志

### 日志配置
```python
import logging

logging.basicConfig(
    level=logging.INFO,
    format="%(asctime)s - %(name)s - %(levelname)s - %(message)s"
)
```

### 性能监控
- 使用 Prometheus + Grafana
- API 响应时间监控
- 数据库查询监控

## 部署配置

### Docker
```dockerfile
FROM python:3.11-slim

WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt

COPY . .
CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]
```

### 生产环境
- 使用 Gunicorn + Uvicorn workers
- 反向代理 (Nginx)
- HTTPS 配置
- 数据库连接池

## 不要做的事情

- 不要在生产环境中使用 `--reload`
- 不要在代码中硬编码敏感信息
- 不要忽略异常处理
- 不要在同步函数中调用异步函数
- 不要直接返回数据库模型 (使用 Pydantic 模式)

## 常见问题解决

1. **CORS 问题**: 正确配置 CORS 中间件
2. **数据库连接问题**: 检查连接字符串和网络
3. **认证问题**: 验证 JWT 配置和密钥
4. **性能问题**: 使用 profiler 分析瓶颈
```