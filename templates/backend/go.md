# Go 项目 CLAUDE.md 模板

```markdown
# CLAUDE.md

这个文件为 Claude Code 提供项目特定的指导信息。

## 项目概述

这是一个使用 Go 语言构建的高性能后端服务。

## 技术栈

- **语言**: Go 1.21+
- **Web 框架**: Gin / Echo / Fiber
- **数据库**: PostgreSQL / MySQL
- **ORM**: GORM / Ent
- **缓存**: Redis
- **消息队列**: RabbitMQ / Apache Kafka
- **日志**: Logrus / Zap
- **配置**: Viper
- **测试**: testify
- **文档**: Swagger
- **部署**: Docker + Kubernetes

## 项目结构

```
project/
├── cmd/
│   └── server/
│       └── main.go              # 应用入口
├── internal/
│   ├── config/
│   │   └── config.go            # 配置管理
│   ├── domain/
│   │   ├── entity/              # 实体定义
│   │   │   └── user.go
│   │   ├── repository/          # 仓库接口
│   │   │   └── user.go
│   │   └── service/             # 服务接口
│   │       └── user.go
│   ├── infrastructure/
│   │   ├── database/            # 数据库实现
│   │   │   ├── postgres.go
│   │   │   └── migration/
│   │   ├── repository/          # 仓库实现
│   │   │   └── user.go
│   │   ├── cache/               # 缓存实现
│   │   │   └── redis.go
│   │   └── messaging/           # 消息队列
│   │       └── rabbitmq.go
│   ├── application/
│   │   ├── service/             # 应用服务
│   │   │   └── user.go
│   │   └── dto/                 # 数据传输对象
│   │       ├── request/
│   │       │   └── user.go
│   │       └── response/
│   │           └── user.go
│   ├── interfaces/
│   │   ├── http/                # HTTP 接口
│   │   │   ├── handler/
│   │   │   │   └── user.go
│   │   │   ├── middleware/
│   │   │   │   ├── auth.go
│   │   │   │   ├── cors.go
│   │   │   │   └── logger.go
│   │   │   └── router/
│   │   │       └── router.go
│   │   └── grpc/                # gRPC 接口
│   │       └── server/
│   │           └── user.go
│   └── pkg/
│       ├── logger/              # 日志工具
│       │   └── logger.go
│       ├── validator/           # 验证器
│       │   └── validator.go
│       ├── jwt/                 # JWT 工具
│       │   └── jwt.go
│       └── utils/               # 工具函数
│           └── utils.go
├── api/
│   ├── proto/                   # Protobuf 定义
│   │   └── user.proto
│   └── swagger/                 # Swagger 文档
│       └── swagger.yaml
├── scripts/
│   ├── build.sh                 # 构建脚本
│   ├── test.sh                  # 测试脚本
│   └── migrate.sh               # 迁移脚本
├── deployments/
│   ├── docker/
│   │   └── Dockerfile
│   └── k8s/
│       ├── deployment.yaml
│       └── service.yaml
├── go.mod
├── go.sum
├── Makefile
└── README.md
```

## 常用命令

### 开发环境
- `go run cmd/server/main.go`: 启动开发服务器
- `go build -o bin/server cmd/server/main.go`: 构建二进制文件
- `go test ./...`: 运行所有测试
- `go test -v ./...`: 详细模式运行测试
- `go test -cover ./...`: 运行测试并显示覆盖率

### 依赖管理
- `go mod init project-name`: 初始化模块
- `go mod tidy`: 整理依赖
- `go mod download`: 下载依赖
- `go mod vendor`: 创建 vendor 目录

### 代码质量
- `go fmt ./...`: 格式化代码
- `go vet ./...`: 静态分析
- `golangci-lint run`: 代码检查
- `goimports -w .`: 整理导入

### 构建和部署
- `make build`: 构建应用
- `make test`: 运行测试
- `make docker-build`: 构建 Docker 镜像
- `make deploy`: 部署应用

## 代码规范

### 实体定义
```go
// internal/domain/entity/user.go
package entity

import (
    "time"
    "github.com/google/uuid"
)

type User struct {
    ID        uuid.UUID `json:"id" gorm:"type:uuid;primary_key;default:gen_random_uuid()"`
    Username  string    `json:"username" gorm:"type:varchar(50);unique;not null"`
    Email     string    `json:"email" gorm:"type:varchar(100);unique;not null"`
    Password  string    `json:"-" gorm:"type:varchar(255);not null"`
    FirstName string    `json:"first_name" gorm:"type:varchar(50)"`
    LastName  string    `json:"last_name" gorm:"type:varchar(50)"`
    IsActive  bool      `json:"is_active" gorm:"default:true"`
    CreatedAt time.Time `json:"created_at" gorm:"autoCreateTime"`
    UpdatedAt time.Time `json:"updated_at" gorm:"autoUpdateTime"`
}

func (u *User) TableName() string {
    return "users"
}

func (u *User) GetFullName() string {
    return u.FirstName + " " + u.LastName
}

func (u *User) Validate() error {
    if u.Username == "" {
        return errors.New("username is required")
    }
    if u.Email == "" {
        return errors.New("email is required")
    }
    return nil
}
```

### 仓库接口
```go
// internal/domain/repository/user.go
package repository

import (
    "context"
    "github.com/google/uuid"
    "project/internal/domain/entity"
)

type UserRepository interface {
    Create(ctx context.Context, user *entity.User) error
    GetByID(ctx context.Context, id uuid.UUID) (*entity.User, error)
    GetByEmail(ctx context.Context, email string) (*entity.User, error)
    Update(ctx context.Context, user *entity.User) error
    Delete(ctx context.Context, id uuid.UUID) error
    List(ctx context.Context, limit, offset int) ([]*entity.User, int64, error)
    ExistsByEmail(ctx context.Context, email string) (bool, error)
}
```

### 仓库实现
```go
// internal/infrastructure/repository/user.go
package repository

import (
    "context"
    "github.com/google/uuid"
    "gorm.io/gorm"
    
    "project/internal/domain/entity"
    "project/internal/domain/repository"
)

type userRepository struct {
    db *gorm.DB
}

func NewUserRepository(db *gorm.DB) repository.UserRepository {
    return &userRepository{db: db}
}

func (r *userRepository) Create(ctx context.Context, user *entity.User) error {
    return r.db.WithContext(ctx).Create(user).Error
}

func (r *userRepository) GetByID(ctx context.Context, id uuid.UUID) (*entity.User, error) {
    var user entity.User
    err := r.db.WithContext(ctx).Where("id = ?", id).First(&user).Error
    if err != nil {
        return nil, err
    }
    return &user, nil
}

func (r *userRepository) GetByEmail(ctx context.Context, email string) (*entity.User, error) {
    var user entity.User
    err := r.db.WithContext(ctx).Where("email = ?", email).First(&user).Error
    if err != nil {
        return nil, err
    }
    return &user, nil
}

func (r *userRepository) Update(ctx context.Context, user *entity.User) error {
    return r.db.WithContext(ctx).Save(user).Error
}

func (r *userRepository) Delete(ctx context.Context, id uuid.UUID) error {
    return r.db.WithContext(ctx).Delete(&entity.User{}, id).Error
}

func (r *userRepository) List(ctx context.Context, limit, offset int) ([]*entity.User, int64, error) {
    var users []*entity.User
    var total int64
    
    // 获取总数
    if err := r.db.WithContext(ctx).Model(&entity.User{}).Count(&total).Error; err != nil {
        return nil, 0, err
    }
    
    // 获取分页数据
    err := r.db.WithContext(ctx).
        Limit(limit).
        Offset(offset).
        Order("created_at DESC").
        Find(&users).Error
    
    return users, total, err
}

func (r *userRepository) ExistsByEmail(ctx context.Context, email string) (bool, error) {
    var count int64
    err := r.db.WithContext(ctx).
        Model(&entity.User{}).
        Where("email = ?", email).
        Count(&count).Error
    return count > 0, err
}
```

### 服务层
```go
// internal/application/service/user.go
package service

import (
    "context"
    "errors"
    "fmt"
    
    "github.com/google/uuid"
    "golang.org/x/crypto/bcrypt"
    
    "project/internal/application/dto/request"
    "project/internal/application/dto/response"
    "project/internal/domain/entity"
    "project/internal/domain/repository"
    "project/internal/pkg/logger"
)

type UserService interface {
    CreateUser(ctx context.Context, req *request.CreateUserRequest) (*response.UserResponse, error)
    GetUser(ctx context.Context, id uuid.UUID) (*response.UserResponse, error)
    UpdateUser(ctx context.Context, id uuid.UUID, req *request.UpdateUserRequest) (*response.UserResponse, error)
    DeleteUser(ctx context.Context, id uuid.UUID) error
    ListUsers(ctx context.Context, limit, offset int) (*response.UserListResponse, error)
    AuthenticateUser(ctx context.Context, email, password string) (*response.UserResponse, error)
}

type userService struct {
    userRepo repository.UserRepository
    logger   logger.Logger
}

func NewUserService(userRepo repository.UserRepository, logger logger.Logger) UserService {
    return &userService{
        userRepo: userRepo,
        logger:   logger,
    }
}

func (s *userService) CreateUser(ctx context.Context, req *request.CreateUserRequest) (*response.UserResponse, error) {
    // 验证邮箱是否已存在
    exists, err := s.userRepo.ExistsByEmail(ctx, req.Email)
    if err != nil {
        s.logger.Error("Failed to check email existence", "error", err)
        return nil, fmt.Errorf("failed to validate email: %w", err)
    }
    if exists {
        return nil, errors.New("email already exists")
    }
    
    // 加密密码
    hashedPassword, err := bcrypt.GenerateFromPassword([]byte(req.Password), bcrypt.DefaultCost)
    if err != nil {
        s.logger.Error("Failed to hash password", "error", err)
        return nil, fmt.Errorf("failed to process password: %w", err)
    }
    
    // 创建用户实体
    user := &entity.User{
        Username:  req.Username,
        Email:     req.Email,
        Password:  string(hashedPassword),
        FirstName: req.FirstName,
        LastName:  req.LastName,
        IsActive:  true,
    }
    
    // 验证用户数据
    if err := user.Validate(); err != nil {
        return nil, fmt.Errorf("validation failed: %w", err)
    }
    
    // 保存用户
    if err := s.userRepo.Create(ctx, user); err != nil {
        s.logger.Error("Failed to create user", "error", err)
        return nil, fmt.Errorf("failed to create user: %w", err)
    }
    
    s.logger.Info("User created successfully", "user_id", user.ID)
    
    return &response.UserResponse{
        ID:        user.ID,
        Username:  user.Username,
        Email:     user.Email,
        FirstName: user.FirstName,
        LastName:  user.LastName,
        IsActive:  user.IsActive,
        CreatedAt: user.CreatedAt,
        UpdatedAt: user.UpdatedAt,
    }, nil
}

func (s *userService) AuthenticateUser(ctx context.Context, email, password string) (*response.UserResponse, error) {
    user, err := s.userRepo.GetByEmail(ctx, email)
    if err != nil {
        return nil, errors.New("invalid credentials")
    }
    
    // 验证密码
    if err := bcrypt.CompareHashAndPassword([]byte(user.Password), []byte(password)); err != nil {
        return nil, errors.New("invalid credentials")
    }
    
    if !user.IsActive {
        return nil, errors.New("account is inactive")
    }
    
    return &response.UserResponse{
        ID:        user.ID,
        Username:  user.Username,
        Email:     user.Email,
        FirstName: user.FirstName,
        LastName:  user.LastName,
        IsActive:  user.IsActive,
        CreatedAt: user.CreatedAt,
        UpdatedAt: user.UpdatedAt,
    }, nil
}
```

### HTTP 处理器
```go
// internal/interfaces/http/handler/user.go
package handler

import (
    "net/http"
    "strconv"
    
    "github.com/gin-gonic/gin"
    "github.com/google/uuid"
    
    "project/internal/application/dto/request"
    "project/internal/application/service"
    "project/internal/pkg/logger"
)

type UserHandler struct {
    userService service.UserService
    logger      logger.Logger
}

func NewUserHandler(userService service.UserService, logger logger.Logger) *UserHandler {
    return &UserHandler{
        userService: userService,
        logger:      logger,
    }
}

// CreateUser godoc
// @Summary Create a new user
// @Description Create a new user with the provided information
// @Tags users
// @Accept json
// @Produce json
// @Param user body request.CreateUserRequest true "User information"
// @Success 201 {object} response.UserResponse
// @Failure 400 {object} ErrorResponse
// @Failure 500 {object} ErrorResponse
// @Router /users [post]
func (h *UserHandler) CreateUser(c *gin.Context) {
    var req request.CreateUserRequest
    if err := c.ShouldBindJSON(&req); err != nil {
        h.logger.Error("Failed to bind request", "error", err)
        c.JSON(http.StatusBadRequest, gin.H{"error": "Invalid request format"})
        return
    }
    
    // 验证请求数据
    if err := req.Validate(); err != nil {
        c.JSON(http.StatusBadRequest, gin.H{"error": err.Error()})
        return
    }
    
    user, err := h.userService.CreateUser(c.Request.Context(), &req)
    if err != nil {
        h.logger.Error("Failed to create user", "error", err)
        c.JSON(http.StatusInternalServerError, gin.H{"error": "Failed to create user"})
        return
    }
    
    c.JSON(http.StatusCreated, gin.H{"data": user})
}

// GetUser godoc
// @Summary Get user by ID
// @Description Get user information by user ID
// @Tags users
// @Accept json
// @Produce json
// @Param id path string true "User ID"
// @Success 200 {object} response.UserResponse
// @Failure 400 {object} ErrorResponse
// @Failure 404 {object} ErrorResponse
// @Router /users/{id} [get]
func (h *UserHandler) GetUser(c *gin.Context) {
    idStr := c.Param("id")
    id, err := uuid.Parse(idStr)
    if err != nil {
        c.JSON(http.StatusBadRequest, gin.H{"error": "Invalid user ID"})
        return
    }
    
    user, err := h.userService.GetUser(c.Request.Context(), id)
    if err != nil {
        h.logger.Error("Failed to get user", "user_id", id, "error", err)
        c.JSON(http.StatusNotFound, gin.H{"error": "User not found"})
        return
    }
    
    c.JSON(http.StatusOK, gin.H{"data": user})
}

// ListUsers godoc
// @Summary List users
// @Description Get a paginated list of users
// @Tags users
// @Accept json
// @Produce json
// @Param limit query int false "Limit" default(10)
// @Param offset query int false "Offset" default(0)
// @Success 200 {object} response.UserListResponse
// @Failure 400 {object} ErrorResponse
// @Failure 500 {object} ErrorResponse
// @Router /users [get]
func (h *UserHandler) ListUsers(c *gin.Context) {
    limit, _ := strconv.Atoi(c.DefaultQuery("limit", "10"))
    offset, _ := strconv.Atoi(c.DefaultQuery("offset", "0"))
    
    if limit <= 0 || limit > 100 {
        limit = 10
    }
    if offset < 0 {
        offset = 0
    }
    
    users, err := h.userService.ListUsers(c.Request.Context(), limit, offset)
    if err != nil {
        h.logger.Error("Failed to list users", "error", err)
        c.JSON(http.StatusInternalServerError, gin.H{"error": "Failed to retrieve users"})
        return
    }
    
    c.JSON(http.StatusOK, gin.H{"data": users})
}
```

### 配置管理
```go
// internal/config/config.go
package config

import (
    "time"
    
    "github.com/spf13/viper"
)

type Config struct {
    Server   ServerConfig   `mapstructure:"server"`
    Database DatabaseConfig `mapstructure:"database"`
    Redis    RedisConfig    `mapstructure:"redis"`
    JWT      JWTConfig      `mapstructure:"jwt"`
    Logger   LoggerConfig   `mapstructure:"logger"`
}

type ServerConfig struct {
    Host         string        `mapstructure:"host"`
    Port         int           `mapstructure:"port"`
    ReadTimeout  time.Duration `mapstructure:"read_timeout"`
    WriteTimeout time.Duration `mapstructure:"write_timeout"`
    IdleTimeout  time.Duration `mapstructure:"idle_timeout"`
}

type DatabaseConfig struct {
    Host         string `mapstructure:"host"`
    Port         int    `mapstructure:"port"`
    Username     string `mapstructure:"username"`
    Password     string `mapstructure:"password"`
    DatabaseName string `mapstructure:"database_name"`
    SSLMode      string `mapstructure:"ssl_mode"`
    MaxOpenConns int    `mapstructure:"max_open_conns"`
    MaxIdleConns int    `mapstructure:"max_idle_conns"`
}

type RedisConfig struct {
    Host     string `mapstructure:"host"`
    Port     int    `mapstructure:"port"`
    Password string `mapstructure:"password"`
    Database int    `mapstructure:"database"`
}

type JWTConfig struct {
    SecretKey      string        `mapstructure:"secret_key"`
    TokenDuration  time.Duration `mapstructure:"token_duration"`
    RefreshDuration time.Duration `mapstructure:"refresh_duration"`
}

type LoggerConfig struct {
    Level  string `mapstructure:"level"`
    Format string `mapstructure:"format"`
}

func Load(path string) (*Config, error) {
    viper.SetConfigFile(path)
    viper.AutomaticEnv()
    
    // 设置默认值
    setDefaults()
    
    if err := viper.ReadInConfig(); err != nil {
        return nil, err
    }
    
    var config Config
    if err := viper.Unmarshal(&config); err != nil {
        return nil, err
    }
    
    return &config, nil
}

func setDefaults() {
    viper.SetDefault("server.host", "0.0.0.0")
    viper.SetDefault("server.port", 8080)
    viper.SetDefault("server.read_timeout", "10s")
    viper.SetDefault("server.write_timeout", "10s")
    viper.SetDefault("server.idle_timeout", "60s")
    
    viper.SetDefault("database.host", "localhost")
    viper.SetDefault("database.port", 5432)
    viper.SetDefault("database.ssl_mode", "disable")
    viper.SetDefault("database.max_open_conns", 25)
    viper.SetDefault("database.max_idle_conns", 5)
    
    viper.SetDefault("redis.host", "localhost")
    viper.SetDefault("redis.port", 6379)
    viper.SetDefault("redis.database", 0)
    
    viper.SetDefault("jwt.token_duration", "24h")
    viper.SetDefault("jwt.refresh_duration", "720h")
    
    viper.SetDefault("logger.level", "info")
    viper.SetDefault("logger.format", "json")
}
```

## 测试策略

### 单元测试
```go
// internal/application/service/user_test.go
package service_test

import (
    "context"
    "testing"
    
    "github.com/google/uuid"
    "github.com/stretchr/testify/assert"
    "github.com/stretchr/testify/mock"
    
    "project/internal/application/dto/request"
    "project/internal/application/service"
    "project/internal/domain/entity"
    "project/internal/mocks"
)

func TestUserService_CreateUser(t *testing.T) {
    // 准备
    mockRepo := new(mocks.UserRepository)
    mockLogger := new(mocks.Logger)
    userService := service.NewUserService(mockRepo, mockLogger)
    
    req := &request.CreateUserRequest{
        Username:  "testuser",
        Email:     "test@example.com",
        Password:  "password123",
        FirstName: "Test",
        LastName:  "User",
    }
    
    // 设置 mock 期望
    mockRepo.On("ExistsByEmail", mock.Anything, req.Email).Return(false, nil)
    mockRepo.On("Create", mock.Anything, mock.AnythingOfType("*entity.User")).Return(nil)
    mockLogger.On("Info", mock.Anything, mock.Anything, mock.Anything)
    
    // 执行
    result, err := userService.CreateUser(context.Background(), req)
    
    // 断言
    assert.NoError(t, err)
    assert.NotNil(t, result)
    assert.Equal(t, req.Username, result.Username)
    assert.Equal(t, req.Email, result.Email)
    
    // 验证 mock 调用
    mockRepo.AssertExpectations(t)
    mockLogger.AssertExpectations(t)
}

func TestUserService_CreateUser_EmailExists(t *testing.T) {
    // 准备
    mockRepo := new(mocks.UserRepository)
    mockLogger := new(mocks.Logger)
    userService := service.NewUserService(mockRepo, mockLogger)
    
    req := &request.CreateUserRequest{
        Email: "existing@example.com",
    }
    
    // 设置 mock 期望
    mockRepo.On("ExistsByEmail", mock.Anything, req.Email).Return(true, nil)
    
    // 执行
    result, err := userService.CreateUser(context.Background(), req)
    
    // 断言
    assert.Error(t, err)
    assert.Nil(t, result)
    assert.Contains(t, err.Error(), "email already exists")
    
    mockRepo.AssertExpectations(t)
}
```

### 集成测试
```go
// test/integration/user_test.go
//go:build integration

package integration

import (
    "bytes"
    "encoding/json"
    "net/http"
    "net/http/httptest"
    "testing"
    
    "github.com/gin-gonic/gin"
    "github.com/stretchr/testify/assert"
    "github.com/stretchr/testify/suite"
    
    "project/internal/application/dto/request"
    "project/test/testutils"
)

type UserIntegrationTestSuite struct {
    suite.Suite
    router *gin.Engine
    db     *testutils.TestDB
}

func (suite *UserIntegrationTestSuite) SetupSuite() {
    // 设置测试数据库
    suite.db = testutils.SetupTestDB()
    
    // 设置路由
    suite.router = testutils.SetupTestRouter(suite.db)
}

func (suite *UserIntegrationTestSuite) TearDownSuite() {
    suite.db.Cleanup()
}

func (suite *UserIntegrationTestSuite) TestCreateUser() {
    // 准备测试数据
    req := request.CreateUserRequest{
        Username:  "testuser",
        Email:     "test@example.com",
        Password:  "password123",
        FirstName: "Test",
        LastName:  "User",
    }
    
    reqBody, _ := json.Marshal(req)
    
    // 发送请求
    w := httptest.NewRecorder()
    httpReq, _ := http.NewRequest("POST", "/api/v1/users", bytes.NewBuffer(reqBody))
    httpReq.Header.Set("Content-Type", "application/json")
    
    suite.router.ServeHTTP(w, httpReq)
    
    // 断言响应
    assert.Equal(suite.T(), http.StatusCreated, w.Code)
    
    var response map[string]interface{}
    err := json.Unmarshal(w.Body.Bytes(), &response)
    assert.NoError(suite.T(), err)
    
    data := response["data"].(map[string]interface{})
    assert.Equal(suite.T(), req.Username, data["username"])
    assert.Equal(suite.T(), req.Email, data["email"])
}

func TestUserIntegrationTestSuite(t *testing.T) {
    suite.Run(t, new(UserIntegrationTestSuite))
}
```

## 性能优化

### 数据库优化
```go
// 连接池配置
func setupDatabase(config *config.DatabaseConfig) (*gorm.DB, error) {
    dsn := fmt.Sprintf("host=%s user=%s password=%s dbname=%s port=%d sslmode=%s",
        config.Host, config.Username, config.Password, 
        config.DatabaseName, config.Port, config.SSLMode)
    
    db, err := gorm.Open(postgres.Open(dsn), &gorm.Config{
        Logger: logger.Default.LogMode(logger.Silent),
    })
    if err != nil {
        return nil, err
    }
    
    sqlDB, err := db.DB()
    if err != nil {
        return nil, err
    }
    
    // 设置连接池
    sqlDB.SetMaxOpenConns(config.MaxOpenConns)
    sqlDB.SetMaxIdleConns(config.MaxIdleConns)
    sqlDB.SetConnMaxLifetime(time.Hour)
    
    return db, nil
}

// 查询优化
func (r *userRepository) GetUsersWithProfiles(ctx context.Context) ([]*entity.User, error) {
    var users []*entity.User
    return users, r.db.WithContext(ctx).
        Preload("Profile").
        Find(&users).Error
}
```

### 缓存策略
```go
// internal/infrastructure/cache/redis.go
package cache

import (
    "context"
    "encoding/json"
    "time"
    
    "github.com/redis/go-redis/v9"
)

type Cache interface {
    Set(ctx context.Context, key string, value interface{}, expiration time.Duration) error
    Get(ctx context.Context, key string, dest interface{}) error
    Delete(ctx context.Context, key string) error
}

type redisCache struct {
    client *redis.Client
}

func NewRedisCache(client *redis.Client) Cache {
    return &redisCache{client: client}
}

func (c *redisCache) Set(ctx context.Context, key string, value interface{}, expiration time.Duration) error {
    data, err := json.Marshal(value)
    if err != nil {
        return err
    }
    
    return c.client.Set(ctx, key, data, expiration).Err()
}

func (c *redisCache) Get(ctx context.Context, key string, dest interface{}) error {
    data, err := c.client.Get(ctx, key).Result()
    if err != nil {
        return err
    }
    
    return json.Unmarshal([]byte(data), dest)
}
```

## 部署配置

### Docker
```dockerfile
# deployments/docker/Dockerfile
FROM golang:1.21-alpine AS builder

WORKDIR /app

# 安装依赖
COPY go.mod go.sum ./
RUN go mod download

# 复制源代码
COPY . .

# 构建应用
RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o main cmd/server/main.go

# 最终镜像
FROM alpine:latest

RUN apk --no-cache add ca-certificates tzdata
WORKDIR /root/

# 复制二进制文件
COPY --from=builder /app/main .
COPY --from=builder /app/configs ./configs

EXPOSE 8080

CMD ["./main"]
```

### Kubernetes
```yaml
# deployments/k8s/deployment.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: go-app
spec:
  replicas: 3
  selector:
    matchLabels:
      app: go-app
  template:
    metadata:
      labels:
        app: go-app
    spec:
      containers:
      - name: go-app
        image: go-app:latest
        ports:
        - containerPort: 8080
        env:
        - name: DB_HOST
          value: "postgres-service"
        - name: REDIS_HOST
          value: "redis-service"
        resources:
          requests:
            memory: "64Mi"
            cpu: "50m"
          limits:
            memory: "128Mi"
            cpu: "100m"
        livenessProbe:
          httpGet:
            path: /health
            port: 8080
          initialDelaySeconds: 30
          periodSeconds: 10
        readinessProbe:
          httpGet:
            path: /ready
            port: 8080
          initialDelaySeconds: 5
          periodSeconds: 5
```

## Makefile
```makefile
.PHONY: build test clean run docker-build docker-run

# Variables
APP_NAME=myapp
DOCKER_IMAGE=$(APP_NAME):latest

# Build the application
build:
	go build -o bin/$(APP_NAME) cmd/server/main.go

# Run tests
test:
	go test -v -race -coverprofile=coverage.out ./...

# Run tests with coverage
test-coverage:
	go test -v -race -coverprofile=coverage.out ./...
	go tool cover -html=coverage.out

# Clean build artifacts
clean:
	rm -rf bin/
	rm -f coverage.out

# Run the application
run:
	go run cmd/server/main.go

# Format code
fmt:
	go fmt ./...
	goimports -w .

# Lint code
lint:
	golangci-lint run

# Run database migrations
migrate-up:
	migrate -path migrations -database "postgres://user:password@localhost/dbname?sslmode=disable" up

migrate-down:
	migrate -path migrations -database "postgres://user:password@localhost/dbname?sslmode=disable" down

# Docker commands
docker-build:
	docker build -t $(DOCKER_IMAGE) -f deployments/docker/Dockerfile .

docker-run:
	docker run -p 8080:8080 $(DOCKER_IMAGE)

# Development commands
dev:
	air -c .air.toml

# Generate mocks
generate-mocks:
	mockery --all --output=mocks

# Install dependencies
deps:
	go mod tidy
	go mod vendor
```

## 不要做的事情

- 不要忽略错误处理，始终检查和处理错误
- 不要在生产环境中使用 panic
- 不要在循环中进行数据库查询（N+1 问题）
- 不要忽略上下文取消和超时
- 不要在生产代码中使用 fmt.Print* 进行日志记录
- 不要忽略 Go 的代码规范和最佳实践

## 常见问题解决

1. **内存泄漏**: 使用 pprof 进行性能分析
2. **数据库连接**: 正确配置连接池参数
3. **并发安全**: 使用互斥锁保护共享资源
4. **错误处理**: 使用 errors.Is 和 errors.As
5. **性能问题**: 使用基准测试和性能分析工具
```