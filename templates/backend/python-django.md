# Python/Django 项目 CLAUDE.md 模板

```markdown
# CLAUDE.md

这个文件为 Claude Code 提供项目特定的指导信息。

## 项目概述

这是一个使用 Python 和 Django 构建的全功能 Web 应用。

## 技术栈

- **框架**: Django 5.0+
- **语言**: Python 3.11+
- **数据库**: PostgreSQL 15+ / SQLite (开发)
- **ORM**: Django ORM
- **API**: Django REST Framework
- **认证**: Django-allauth / JWT
- **缓存**: Redis / Memcached
- **任务队列**: Celery + Redis
- **前端**: Django Templates / React (分离式)
- **测试**: pytest + pytest-django
- **部署**: Gunicorn + Nginx

## 项目结构

```
project_name/
├── manage.py
├── requirements/
│   ├── base.txt
│   ├── development.txt
│   └── production.txt
├── config/
│   ├── __init__.py
│   ├── settings/
│   │   ├── __init__.py
│   │   ├── base.py
│   │   ├── development.py
│   │   └── production.py
│   ├── urls.py
│   ├── wsgi.py
│   └── asgi.py
├── apps/
│   ├── __init__.py
│   ├── users/
│   │   ├── __init__.py
│   │   ├── admin.py
│   │   ├── apps.py
│   │   ├── models.py
│   │   ├── views.py
│   │   ├── serializers.py
│   │   ├── urls.py
│   │   ├── managers.py
│   │   ├── migrations/
│   │   └── tests/
│   │       ├── test_models.py
│   │       ├── test_views.py
│   │       └── test_serializers.py
│   ├── common/
│   │   ├── __init__.py
│   │   ├── models.py
│   │   ├── mixins.py
│   │   ├── validators.py
│   │   ├── permissions.py
│   │   └── utils.py
│   └── core/
│       ├── __init__.py
│       ├── exceptions.py
│       ├── pagination.py
│       └── renderers.py
├── static/
│   ├── css/
│   ├── js/
│   └── images/
├── media/
├── templates/
│   ├── base.html
│   └── registration/
├── locale/
└── docs/
```

## 常用命令

### 开发服务器
- `python manage.py runserver`: 启动开发服务器
- `python manage.py runserver 0.0.0.0:8000`: 指定地址启动

### 数据库管理
- `python manage.py makemigrations`: 创建迁移文件
- `python manage.py migrate`: 应用数据库迁移
- `python manage.py showmigrations`: 显示迁移状态
- `python manage.py sqlmigrate app_name migration_name`: 显示迁移 SQL
- `python manage.py dbshell`: 进入数据库 shell

### 用户管理
- `python manage.py createsuperuser`: 创建超级用户
- `python manage.py changepassword username`: 修改用户密码

### 静态文件
- `python manage.py collectstatic`: 收集静态文件
- `python manage.py findstatic filename`: 查找静态文件

### 测试和代码质量
- `pytest`: 运行测试
- `pytest --cov=apps`: 运行测试并生成覆盖率报告
- `black .`: 格式化代码
- `isort .`: 整理导入
- `flake8`: 代码风格检查
- `mypy .`: 类型检查

## 代码规范

### 模型规范
- 使用 Django 最佳实践
- 继承抽象基类
- 添加适当的索引和约束

```python
# apps/common/models.py
from django.db import models
from django.utils import timezone


class TimeStampedModel(models.Model):
    """抽象基类，提供创建和更新时间字段"""
    created_at = models.DateTimeField(default=timezone.now)
    updated_at = models.DateTimeField(auto_now=True)
    
    class Meta:
        abstract = True


# apps/users/models.py
from django.contrib.auth.models import AbstractUser
from django.db import models
from apps.common.models import TimeStampedModel


class User(AbstractUser, TimeStampedModel):
    """自定义用户模型"""
    email = models.EmailField(unique=True)
    phone = models.CharField(max_length=20, blank=True)
    avatar = models.ImageField(upload_to='avatars/', blank=True)
    is_verified = models.BooleanField(default=False)
    
    USERNAME_FIELD = 'email'
    REQUIRED_FIELDS = ['username']
    
    class Meta:
        db_table = 'users'
        verbose_name = 'User'
        verbose_name_plural = 'Users'
        indexes = [
            models.Index(fields=['email']),
            models.Index(fields=['created_at']),
        ]
    
    def __str__(self):
        return self.email
    
    def get_full_name(self):
        return f"{self.first_name} {self.last_name}".strip()


class Profile(TimeStampedModel):
    """用户配置文件"""
    user = models.OneToOneField(
        User, 
        on_delete=models.CASCADE,
        related_name='profile'
    )
    bio = models.TextField(max_length=500, blank=True)
    location = models.CharField(max_length=30, blank=True)
    birth_date = models.DateField(null=True, blank=True)
    
    class Meta:
        db_table = 'user_profiles'
    
    def __str__(self):
        return f"{self.user.email}'s profile"
```

### 视图规范
- 使用类视图 (CBV)
- 遵循 REST 原则
- 适当的权限和认证

```python
# apps/users/views.py
from rest_framework import generics, status, permissions
from rest_framework.decorators import action
from rest_framework.response import Response
from rest_framework.viewsets import ModelViewSet
from django_filters.rest_framework import DjangoFilterBackend
from django.contrib.auth import get_user_model

from .models import Profile
from .serializers import UserSerializer, ProfileSerializer
from .filters import UserFilter
from apps.common.permissions import IsOwnerOrReadOnly

User = get_user_model()


class UserViewSet(ModelViewSet):
    """用户视图集"""
    queryset = User.objects.select_related('profile').all()
    serializer_class = UserSerializer
    permission_classes = [permissions.IsAuthenticated]
    filter_backends = [DjangoFilterBackend]
    filterset_class = UserFilter
    search_fields = ['username', 'email', 'first_name', 'last_name']
    ordering_fields = ['created_at', 'last_login']
    ordering = ['-created_at']
    
    def get_permissions(self):
        """根据动作设置权限"""
        if self.action == 'create':
            permission_classes = [permissions.AllowAny]
        elif self.action in ['update', 'partial_update', 'destroy']:
            permission_classes = [IsOwnerOrReadOnly]
        else:
            permission_classes = [permissions.IsAuthenticated]
        
        return [permission() for permission in permission_classes]
    
    @action(detail=True, methods=['get', 'put', 'patch'])
    def profile(self, request, pk=None):
        """用户配置文件操作"""
        user = self.get_object()
        profile, created = Profile.objects.get_or_create(user=user)
        
        if request.method == 'GET':
            serializer = ProfileSerializer(profile)
            return Response(serializer.data)
        
        elif request.method in ['PUT', 'PATCH']:
            partial = request.method == 'PATCH'
            serializer = ProfileSerializer(
                profile, 
                data=request.data, 
                partial=partial
            )
            if serializer.is_valid():
                serializer.save()
                return Response(serializer.data)
            return Response(
                serializer.errors, 
                status=status.HTTP_400_BAD_REQUEST
            )
    
    @action(detail=False, methods=['get'])
    def me(self, request):
        """获取当前用户信息"""
        serializer = self.get_serializer(request.user)
        return Response(serializer.data)
```

### 序列化器规范
- 使用 DRF 序列化器
- 分离不同用途的序列化器
- 添加验证逻辑

```python
# apps/users/serializers.py
from rest_framework import serializers
from django.contrib.auth import get_user_model
from django.contrib.auth.password_validation import validate_password

from .models import Profile

User = get_user_model()


class ProfileSerializer(serializers.ModelSerializer):
    """用户配置文件序列化器"""
    
    class Meta:
        model = Profile
        fields = ['bio', 'location', 'birth_date']


class UserSerializer(serializers.ModelSerializer):
    """用户序列化器"""
    profile = ProfileSerializer(read_only=True)
    password = serializers.CharField(write_only=True, validators=[validate_password])
    password_confirm = serializers.CharField(write_only=True)
    
    class Meta:
        model = User
        fields = [
            'id', 'username', 'email', 'first_name', 'last_name',
            'password', 'password_confirm', 'profile', 'is_verified',
            'created_at', 'updated_at'
        ]
        read_only_fields = ['id', 'is_verified', 'created_at', 'updated_at']
    
    def validate(self, attrs):
        """验证密码确认"""
        if attrs.get('password') != attrs.get('password_confirm'):
            raise serializers.ValidationError("密码不匹配")
        return attrs
    
    def create(self, validated_data):
        """创建用户"""
        validated_data.pop('password_confirm')
        password = validated_data.pop('password')
        user = User.objects.create_user(**validated_data)
        user.set_password(password)
        user.save()
        return user
    
    def update(self, instance, validated_data):
        """更新用户"""
        validated_data.pop('password_confirm', None)
        password = validated_data.pop('password', None)
        
        for attr, value in validated_data.items():
            setattr(instance, attr, value)
        
        if password:
            instance.set_password(password)
        
        instance.save()
        return instance


class UserListSerializer(serializers.ModelSerializer):
    """用户列表序列化器（简化版）"""
    
    class Meta:
        model = User
        fields = ['id', 'username', 'email', 'first_name', 'last_name', 'created_at']
```

### URL 配置
```python
# apps/users/urls.py
from django.urls import path, include
from rest_framework.routers import DefaultRouter
from .views import UserViewSet

router = DefaultRouter()
router.register(r'users', UserViewSet)

urlpatterns = [
    path('api/v1/', include(router.urls)),
]

# config/urls.py
from django.contrib import admin
from django.urls import path, include
from django.conf import settings
from django.conf.urls.static import static

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('apps.users.urls')),
    path('api-auth/', include('rest_framework.urls')),
]

if settings.DEBUG:
    urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
    urlpatterns += static(settings.STATIC_URL, document_root=settings.STATIC_ROOT)
```

## 设置配置

### 基础设置
```python
# config/settings/base.py
import os
from pathlib import Path

BASE_DIR = Path(__file__).resolve().parent.parent.parent

SECRET_KEY = os.environ.get('SECRET_KEY', 'your-secret-key-here')

DEBUG = False

ALLOWED_HOSTS = []

# 应用配置
DJANGO_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
]

THIRD_PARTY_APPS = [
    'rest_framework',
    'django_filters',
    'corsheaders',
    'celery',
]

LOCAL_APPS = [
    'apps.users',
    'apps.common',
    'apps.core',
]

INSTALLED_APPS = DJANGO_APPS + THIRD_PARTY_APPS + LOCAL_APPS

MIDDLEWARE = [
    'django.middleware.security.SecurityMiddleware',
    'django.contrib.sessions.middleware.SessionMiddleware',
    'corsheaders.middleware.CorsMiddleware',
    'django.middleware.common.CommonMiddleware',
    'django.middleware.csrf.CsrfViewMiddleware',
    'django.contrib.auth.middleware.AuthenticationMiddleware',
    'django.contrib.messages.middleware.MessageMiddleware',
    'django.middleware.clickjacking.XFrameOptionsMiddleware',
]

ROOT_URLCONF = 'config.urls'

TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [BASE_DIR / 'templates'],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]

# 数据库配置
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': os.environ.get('DB_NAME', 'myproject'),
        'USER': os.environ.get('DB_USER', 'myproject'),
        'PASSWORD': os.environ.get('DB_PASSWORD', ''),
        'HOST': os.environ.get('DB_HOST', 'localhost'),
        'PORT': os.environ.get('DB_PORT', '5432'),
    }
}

# 国际化
LANGUAGE_CODE = 'zh-hans'
TIME_ZONE = 'Asia/Shanghai'
USE_I18N = True
USE_TZ = True

# 静态文件
STATIC_URL = '/static/'
STATICFILES_DIRS = [BASE_DIR / 'static']
STATIC_ROOT = BASE_DIR / 'staticfiles'

MEDIA_URL = '/media/'
MEDIA_ROOT = BASE_DIR / 'media'

# 自定义用户模型
AUTH_USER_MODEL = 'users.User'

# DRF 配置
REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': [
        'rest_framework.authentication.SessionAuthentication',
        'rest_framework_simplejwt.authentication.JWTAuthentication',
    ],
    'DEFAULT_PERMISSION_CLASSES': [
        'rest_framework.permissions.IsAuthenticated',
    ],
    'DEFAULT_PAGINATION_CLASS': 'rest_framework.pagination.PageNumberPagination',
    'PAGE_SIZE': 20,
    'DEFAULT_FILTER_BACKENDS': [
        'django_filters.rest_framework.DjangoFilterBackend',
        'rest_framework.filters.SearchFilter',
        'rest_framework.filters.OrderingFilter',
    ],
}

# Celery 配置
CELERY_BROKER_URL = os.environ.get('REDIS_URL', 'redis://localhost:6379/0')
CELERY_RESULT_BACKEND = os.environ.get('REDIS_URL', 'redis://localhost:6379/0')
CELERY_ACCEPT_CONTENT = ['json']
CELERY_TASK_SERIALIZER = 'json'
CELERY_RESULT_SERIALIZER = 'json'
CELERY_TIMEZONE = TIME_ZONE
```

### 开发环境设置
```python
# config/settings/development.py
from .base import *

DEBUG = True

ALLOWED_HOSTS = ['localhost', '127.0.0.1']

# 开发数据库（SQLite）
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    }
}

# 邮件后端（控制台输出）
EMAIL_BACKEND = 'django.core.mail.backends.console.EmailBackend'

# 调试工具栏
if DEBUG:
    INSTALLED_APPS += ['debug_toolbar']
    MIDDLEWARE += ['debug_toolbar.middleware.DebugToolbarMiddleware']
    INTERNAL_IPS = ['127.0.0.1']

# CORS 设置（开发环境）
CORS_ALLOW_ALL_ORIGINS = True
```

## 测试策略

### 模型测试
```python
# apps/users/tests/test_models.py
import pytest
from django.core.exceptions import ValidationError
from django.contrib.auth import get_user_model

User = get_user_model()


@pytest.mark.django_db
class TestUserModel:
    """用户模型测试"""
    
    def test_create_user(self):
        """测试创建用户"""
        user = User.objects.create_user(
            username='testuser',
            email='test@example.com',
            password='testpass123'
        )
        assert user.username == 'testuser'
        assert user.email == 'test@example.com'
        assert user.check_password('testpass123')
        assert not user.is_staff
        assert not user.is_superuser
    
    def test_create_superuser(self):
        """测试创建超级用户"""
        user = User.objects.create_superuser(
            username='admin',
            email='admin@example.com',
            password='adminpass123'
        )
        assert user.is_staff
        assert user.is_superuser
    
    def test_email_unique(self):
        """测试邮箱唯一性"""
        User.objects.create_user(
            username='user1',
            email='test@example.com',
            password='pass123'
        )
        
        with pytest.raises(ValidationError):
            User.objects.create_user(
                username='user2',
                email='test@example.com',
                password='pass123'
            )
```

### API 测试
```python
# apps/users/tests/test_views.py
import pytest
from django.urls import reverse
from rest_framework import status
from rest_framework.test import APIClient
from django.contrib.auth import get_user_model

User = get_user_model()


@pytest.mark.django_db
class TestUserAPI:
    """用户 API 测试"""
    
    def setup_method(self):
        """测试设置"""
        self.client = APIClient()
        self.user = User.objects.create_user(
            username='testuser',
            email='test@example.com',
            password='testpass123'
        )
    
    def test_create_user(self):
        """测试创建用户"""
        url = reverse('user-list')
        data = {
            'username': 'newuser',
            'email': 'new@example.com',
            'password': 'newpass123',
            'password_confirm': 'newpass123',
            'first_name': 'New',
            'last_name': 'User'
        }
        
        response = self.client.post(url, data)
        
        assert response.status_code == status.HTTP_201_CREATED
        assert User.objects.filter(email='new@example.com').exists()
    
    def test_get_user_list(self):
        """测试获取用户列表"""
        self.client.force_authenticate(user=self.user)
        url = reverse('user-list')
        
        response = self.client.get(url)
        
        assert response.status_code == status.HTTP_200_OK
        assert len(response.data['results']) >= 1
    
    def test_get_current_user(self):
        """测试获取当前用户信息"""
        self.client.force_authenticate(user=self.user)
        url = reverse('user-me')
        
        response = self.client.get(url)
        
        assert response.status_code == status.HTTP_200_OK
        assert response.data['email'] == self.user.email
```

## Celery 任务

```python
# apps/users/tasks.py
from celery import shared_task
from django.core.mail import send_mail
from django.conf import settings


@shared_task
def send_welcome_email(user_id):
    """发送欢迎邮件"""
    from django.contrib.auth import get_user_model
    User = get_user_model()
    
    try:
        user = User.objects.get(id=user_id)
        send_mail(
            subject='欢迎注册',
            message=f'欢迎 {user.get_full_name()}, 感谢您的注册！',
            from_email=settings.DEFAULT_FROM_EMAIL,
            recipient_list=[user.email],
        )
    except User.DoesNotExist:
        pass


@shared_task
def cleanup_unverified_users():
    """清理未验证的用户"""
    from django.utils import timezone
    from datetime import timedelta
    from django.contrib.auth import get_user_model
    
    User = get_user_model()
    cutoff_date = timezone.now() - timedelta(days=7)
    
    unverified_users = User.objects.filter(
        is_verified=False,
        created_at__lt=cutoff_date
    )
    
    count = unverified_users.count()
    unverified_users.delete()
    
    return f"删除了 {count} 个未验证用户"
```

## 性能优化

### 数据库优化
```python
# 使用 select_related 和 prefetch_related
users = User.objects.select_related('profile').prefetch_related('orders')

# 使用索引
class User(models.Model):
    email = models.EmailField(db_index=True)
    
    class Meta:
        indexes = [
            models.Index(fields=['email', 'created_at']),
        ]

# 使用 only 和 defer
users = User.objects.only('id', 'email', 'username')
users = User.objects.defer('bio', 'avatar')
```

### 缓存配置
```python
# config/settings/base.py
CACHES = {
    'default': {
        'BACKEND': 'django_redis.cache.RedisCache',
        'LOCATION': 'redis://127.0.0.1:6379/1',
        'OPTIONS': {
            'CLIENT_CLASS': 'django_redis.client.DefaultClient',
        }
    }
}

# 使用缓存
from django.core.cache import cache

def get_user_profile(user_id):
    cache_key = f'user_profile_{user_id}'
    profile = cache.get(cache_key)
    
    if profile is None:
        profile = Profile.objects.select_related('user').get(user_id=user_id)
        cache.set(cache_key, profile, 3600)  # 缓存1小时
    
    return profile
```

## 部署配置

### 生产环境设置
```python
# config/settings/production.py
from .base import *

DEBUG = False

ALLOWED_HOSTS = ['yourdomain.com', 'www.yourdomain.com']

# 安全设置
SECURE_SSL_REDIRECT = True
SECURE_PROXY_SSL_HEADER = ('HTTP_X_FORWARDED_PROTO', 'https')
SECURE_HSTS_SECONDS = 31536000
SECURE_HSTS_INCLUDE_SUBDOMAINS = True
SECURE_HSTS_PRELOAD = True
SECURE_CONTENT_TYPE_NOSNIFF = True
SECURE_BROWSER_XSS_FILTER = True
X_FRAME_OPTIONS = 'DENY'

# 数据库连接池
DATABASES['default']['CONN_MAX_AGE'] = 60
DATABASES['default']['OPTIONS'] = {
    'MAX_CONNS': 20,
    'MIN_CONNS': 5,
}

# 邮件设置
EMAIL_BACKEND = 'django.core.mail.backends.smtp.EmailBackend'
EMAIL_HOST = os.environ.get('EMAIL_HOST')
EMAIL_PORT = int(os.environ.get('EMAIL_PORT', 587))
EMAIL_USE_TLS = True
EMAIL_HOST_USER = os.environ.get('EMAIL_HOST_USER')
EMAIL_HOST_PASSWORD = os.environ.get('EMAIL_HOST_PASSWORD')
DEFAULT_FROM_EMAIL = os.environ.get('DEFAULT_FROM_EMAIL')
```

### Docker 配置
```dockerfile
FROM python:3.11-slim

WORKDIR /app

# 安装系统依赖
RUN apt-get update && apt-get install -y \
    build-essential \
    libpq-dev \
    && rm -rf /var/lib/apt/lists/*

# 安装 Python 依赖
COPY requirements/production.txt requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# 复制项目文件
COPY . .

# 创建非 root 用户
RUN useradd --create-home --shell /bin/bash app
RUN chown -R app:app /app
USER app

EXPOSE 8000

CMD ["gunicorn", "--bind", "0.0.0.0:8000", "config.wsgi:application"]
```

## 不要做的事情

- 不要在模型中编写复杂的业务逻辑
- 不要忽略数据库查询优化（N+1 问题）
- 不要在视图中直接操作数据库
- 不要将敏感信息硬编码在代码中
- 不要忽略 CSRF 保护
- 不要在生产环境中启用 DEBUG

## 常见问题解决

1. **迁移冲突**: 使用 `python manage.py migrate --merge`
2. **静态文件问题**: 确保 `STATIC_ROOT` 配置正确
3. **时区问题**: 设置 `USE_TZ = True` 并使用 `timezone.now()`
4. **性能问题**: 使用 Django Debug Toolbar 分析查询
5. **CORS 问题**: 正确配置 `django-cors-headers`
```