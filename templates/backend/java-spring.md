# Java/Spring Boot 项目 CLAUDE.md 模板

```markdown
# CLAUDE.md

这个文件为 Claude Code 提供项目特定的指导信息。

## 项目概述

这是一个使用 Java 和 Spring Boot 构建的企业级后端应用。

## 技术栈

- **框架**: Spring Boot 3.2+
- **语言**: Java 21 (LTS)
- **数据库**: PostgreSQL 15+ / MySQL 8+
- **ORM**: Spring Data JPA + Hibernate
- **安全**: Spring Security 6
- **缓存**: Redis 7+ / Caffeine
- **消息队列**: RabbitMQ / Apache Kafka
- **构建工具**: Maven 3.9+ / Gradle 8+
- **测试**: JUnit 5 + Mockito + TestContainers
- **文档**: SpringDoc OpenAPI 3

## 项目结构

```
src/
├── main/
│   ├── java/
│   │   └── com/company/project/
│   │       ├── ProjectApplication.java
│   │       ├── config/              # 配置类
│   │       │   ├── SecurityConfig.java
│   │       │   ├── DatabaseConfig.java
│   │       │   └── RedisConfig.java
│   │       ├── controller/          # REST 控制器
│   │       │   ├── AuthController.java
│   │       │   └── UserController.java
│   │       ├── service/             # 业务逻辑层
│   │       │   ├── UserService.java
│   │       │   └── impl/
│   │       │       └── UserServiceImpl.java
│   │       ├── repository/          # 数据访问层
│   │       │   ├── UserRepository.java
│   │       │   └── custom/
│   │       │       └── CustomUserRepository.java
│   │       ├── entity/              # JPA 实体
│   │       │   ├── User.java
│   │       │   └── BaseEntity.java
│   │       ├── dto/                 # 数据传输对象
│   │       │   ├── request/
│   │       │   │   └── CreateUserRequest.java
│   │       │   └── response/
│   │       │       └── UserResponse.java
│   │       ├── mapper/              # 对象映射器
│   │       │   └── UserMapper.java
│   │       ├── exception/           # 异常处理
│   │       │   ├── GlobalExceptionHandler.java
│   │       │   └── BusinessException.java
│   │       ├── security/            # 安全相关
│   │       │   ├── JwtTokenProvider.java
│   │       │   └── UserPrincipal.java
│   │       └── util/                # 工具类
│   │           └── DateUtils.java
│   └── resources/
│       ├── application.yml          # 主配置文件
│       ├── application-dev.yml      # 开发环境配置
│       ├── application-prod.yml     # 生产环境配置
│       ├── db/migration/            # Flyway 数据库迁移
│       └── static/                  # 静态资源
└── test/
    └── java/
        └── com/company/project/
            ├── controller/          # 控制器测试
            ├── service/             # 服务测试
            ├── repository/          # 仓库测试
            └── integration/         # 集成测试
```

## 常用命令

### Maven 项目
- `mvn clean compile`: 清理并编译项目
- `mvn spring-boot:run`: 启动应用
- `mvn test`: 运行测试
- `mvn package`: 打包应用
- `mvn spring-boot:build-image`: 构建 Docker 镜像

### Gradle 项目
- `./gradlew clean build`: 清理并构建项目
- `./gradlew bootRun`: 启动应用
- `./gradlew test`: 运行测试
- `./gradlew bootJar`: 打包 JAR
- `./gradlew bootBuildImage`: 构建 Docker 镜像

### 数据库相关
- `mvn flyway:migrate`: 执行数据库迁移
- `mvn flyway:info`: 查看迁移状态
- `mvn flyway:clean`: 清理数据库

## 代码规范

### 实体类规范
- 使用 JPA 注解
- 继承 BaseEntity 基类
- 实现 equals 和 hashCode 方法

```java
@Entity
@Table(name = "users")
@Data
@EqualsAndHashCode(callSuper = true)
@NoArgsConstructor
@AllArgsConstructor
@Builder
public class User extends BaseEntity {
    
    @Column(name = "username", unique = true, nullable = false)
    private String username;
    
    @Column(name = "email", unique = true, nullable = false)
    @Email
    private String email;
    
    @Column(name = "password", nullable = false)
    private String password;
    
    @Enumerated(EnumType.STRING)
    @Column(name = "role")
    private UserRole role;
    
    @OneToMany(mappedBy = "user", cascade = CascadeType.ALL, fetch = FetchType.LAZY)
    private List<Order> orders = new ArrayList<>();
}

@MappedSuperclass
@Data
@EntityListeners(AuditingEntityListener.class)
public abstract class BaseEntity {
    
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    
    @CreatedDate
    @Column(name = "created_at", nullable = false, updatable = false)
    private LocalDateTime createdAt;
    
    @LastModifiedDate
    @Column(name = "updated_at")
    private LocalDateTime updatedAt;
    
    @CreatedBy
    @Column(name = "created_by")
    private String createdBy;
    
    @LastModifiedBy
    @Column(name = "updated_by")
    private String updatedBy;
}
```

### 服务层规范
- 接口和实现分离
- 使用 @Transactional 注解
- 统一异常处理

```java
@Service
@RequiredArgsConstructor
@Transactional(readOnly = true)
public class UserServiceImpl implements UserService {
    
    private final UserRepository userRepository;
    private final PasswordEncoder passwordEncoder;
    private final UserMapper userMapper;
    
    @Override
    @Transactional
    public UserResponse createUser(CreateUserRequest request) {
        // 验证用户是否已存在
        if (userRepository.existsByEmail(request.getEmail())) {
            throw new BusinessException("Email already exists");
        }
        
        // 创建用户实体
        User user = User.builder()
            .username(request.getUsername())
            .email(request.getEmail())
            .password(passwordEncoder.encode(request.getPassword()))
            .role(UserRole.USER)
            .build();
            
        User savedUser = userRepository.save(user);
        return userMapper.toResponse(savedUser);
    }
    
    @Override
    public Page<UserResponse> getUsers(Pageable pageable) {
        Page<User> users = userRepository.findAll(pageable);
        return users.map(userMapper::toResponse);
    }
    
    @Override
    @Cacheable(value = "users", key = "#id")
    public UserResponse getUserById(Long id) {
        User user = userRepository.findById(id)
            .orElseThrow(() -> new EntityNotFoundException("User not found"));
        return userMapper.toResponse(user);
    }
}
```

### 控制器规范
- 使用 REST 规范
- 统一响应格式
- 参数验证

```java
@RestController
@RequestMapping("/api/v1/users")
@RequiredArgsConstructor
@Validated
@Tag(name = "User Management", description = "用户管理相关接口")
public class UserController {
    
    private final UserService userService;
    
    @PostMapping
    @Operation(summary = "创建用户", description = "创建新用户")
    @ApiResponse(responseCode = "201", description = "用户创建成功")
    public ResponseEntity<ApiResponse<UserResponse>> createUser(
            @RequestBody @Valid CreateUserRequest request) {
        UserResponse user = userService.createUser(request);
        return ResponseEntity.status(HttpStatus.CREATED)
            .body(ApiResponse.success(user, "用户创建成功"));
    }
    
    @GetMapping
    @Operation(summary = "获取用户列表", description = "分页获取用户列表")
    public ResponseEntity<ApiResponse<Page<UserResponse>>> getUsers(
            @PageableDefault(size = 20) Pageable pageable) {
        Page<UserResponse> users = userService.getUsers(pageable);
        return ResponseEntity.ok(ApiResponse.success(users));
    }
    
    @GetMapping("/{id}")
    @Operation(summary = "获取用户详情", description = "根据ID获取用户详情")
    public ResponseEntity<ApiResponse<UserResponse>> getUserById(
            @PathVariable @Positive Long id) {
        UserResponse user = userService.getUserById(id);
        return ResponseEntity.ok(ApiResponse.success(user));
    }
}
```

### DTO 规范
- 使用 Jakarta Bean Validation
- 分离请求和响应 DTO
- 使用 Builder 模式

```java
@Data
@Builder
@NoArgsConstructor
@AllArgsConstructor
public class CreateUserRequest {
    
    @NotBlank(message = "用户名不能为空")
    @Size(min = 3, max = 20, message = "用户名长度必须在3-20个字符之间")
    private String username;
    
    @NotBlank(message = "邮箱不能为空")
    @Email(message = "邮箱格式不正确")
    private String email;
    
    @NotBlank(message = "密码不能为空")
    @Pattern(regexp = "^(?=.*[a-z])(?=.*[A-Z])(?=.*\\d)[a-zA-Z\\d@$!%*?&]{8,}$",
             message = "密码必须包含大小写字母和数字，长度至少8位")
    private String password;
}

@Data
@Builder
@NoArgsConstructor
@AllArgsConstructor
public class UserResponse {
    private Long id;
    private String username;
    private String email;
    private UserRole role;
    private LocalDateTime createdAt;
    private LocalDateTime updatedAt;
}
```

## 数据库配置

### 应用配置
```yaml
# application.yml
spring:
  datasource:
    url: jdbc:postgresql://localhost:5432/myapp
    username: ${DB_USERNAME:myapp}
    password: ${DB_PASSWORD:password}
    driver-class-name: org.postgresql.Driver
    
  jpa:
    hibernate:
      ddl-auto: none  # 生产环境使用 none
    show-sql: false
    properties:
      hibernate:
        dialect: org.hibernate.dialect.PostgreSQLDialect
        format_sql: true
        
  flyway:
    enabled: true
    locations: classpath:db/migration
    baseline-on-migrate: true
    
  cache:
    type: redis
    redis:
      time-to-live: 3600000  # 1小时
      
  redis:
    host: localhost
    port: 6379
    database: 0
    timeout: 2000ms
    lettuce:
      pool:
        max-active: 10
        max-idle: 8
        min-idle: 2
```

### Flyway 迁移示例
```sql
-- V1__Create_users_table.sql
CREATE TABLE IF NOT EXISTS users (
    id BIGSERIAL PRIMARY KEY,
    username VARCHAR(50) UNIQUE NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL,
    role VARCHAR(20) NOT NULL DEFAULT 'USER',
    created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    created_by VARCHAR(50),
    updated_by VARCHAR(50)
);

CREATE INDEX idx_users_email ON users(email);
CREATE INDEX idx_users_username ON users(username);
```

## 安全配置

```java
@Configuration
@EnableWebSecurity
@EnableMethodSecurity
@RequiredArgsConstructor
public class SecurityConfig {
    
    private final JwtAuthenticationEntryPoint jwtAuthenticationEntryPoint;
    private final JwtAccessDeniedHandler jwtAccessDeniedHandler;
    private final UserDetailsService userDetailsService;
    
    @Bean
    public PasswordEncoder passwordEncoder() {
        return new BCryptPasswordEncoder(12);
    }
    
    @Bean
    public AuthenticationManager authenticationManager(
            AuthenticationConfiguration authConfig) throws Exception {
        return authConfig.getAuthenticationManager();
    }
    
    @Bean
    public SecurityFilterChain filterChain(HttpSecurity http) throws Exception {
        http
            .csrf(AbstractHttpConfigurer::disable)
            .sessionManagement(session -> 
                session.sessionCreationPolicy(SessionCreationPolicy.STATELESS))
            .authorizeHttpRequests(authz -> authz
                .requestMatchers("/api/v1/auth/**").permitAll()
                .requestMatchers("/swagger-ui/**", "/v3/api-docs/**").permitAll()
                .requestMatchers(HttpMethod.GET, "/api/v1/users/**").hasRole("USER")
                .requestMatchers("/api/v1/admin/**").hasRole("ADMIN")
                .anyRequest().authenticated()
            )
            .exceptionHandling(exceptions -> exceptions
                .authenticationEntryPoint(jwtAuthenticationEntryPoint)
                .accessDeniedHandler(jwtAccessDeniedHandler)
            )
            .addFilterBefore(jwtAuthenticationFilter(), 
                           UsernamePasswordAuthenticationFilter.class);
            
        return http.build();
    }
    
    @Bean
    public JwtAuthenticationFilter jwtAuthenticationFilter() {
        return new JwtAuthenticationFilter();
    }
}
```

## 测试策略

### 单元测试
```java
@ExtendWith(MockitoExtension.class)
class UserServiceImplTest {
    
    @Mock
    private UserRepository userRepository;
    
    @Mock
    private PasswordEncoder passwordEncoder;
    
    @Mock
    private UserMapper userMapper;
    
    @InjectMocks
    private UserServiceImpl userService;
    
    @Test
    @DisplayName("创建用户 - 成功")
    void createUser_Success() {
        // Given
        CreateUserRequest request = CreateUserRequest.builder()
            .username("testuser")
            .email("test@example.com")
            .password("Password123")
            .build();
            
        User savedUser = User.builder()
            .id(1L)
            .username("testuser")
            .email("test@example.com")
            .build();
            
        UserResponse expectedResponse = UserResponse.builder()
            .id(1L)
            .username("testuser")
            .email("test@example.com")
            .build();
            
        when(userRepository.existsByEmail(request.getEmail())).thenReturn(false);
        when(passwordEncoder.encode(request.getPassword())).thenReturn("encoded");
        when(userRepository.save(any(User.class))).thenReturn(savedUser);
        when(userMapper.toResponse(savedUser)).thenReturn(expectedResponse);
        
        // When
        UserResponse result = userService.createUser(request);
        
        // Then
        assertThat(result).isEqualTo(expectedResponse);
        verify(userRepository).existsByEmail(request.getEmail());
        verify(userRepository).save(any(User.class));
    }
}
```

### 集成测试
```java
@SpringBootTest(webEnvironment = SpringBootTest.WebEnvironment.RANDOM_PORT)
@Testcontainers
@TestPropertySource(properties = {
    "spring.datasource.url=jdbc:tc:postgresql:15:///testdb"
})
class UserControllerIntegrationTest {
    
    @Autowired
    private TestRestTemplate restTemplate;
    
    @Autowired
    private UserRepository userRepository;
    
    @Container
    static PostgreSQLContainer<?> postgres = new PostgreSQLContainer<>("postgres:15")
            .withDatabaseName("testdb")
            .withUsername("test")
            .withPassword("test");
    
    @Test
    @DisplayName("创建用户 - 集成测试")
    void createUser_IntegrationTest() {
        // Given
        CreateUserRequest request = CreateUserRequest.builder()
            .username("testuser")
            .email("test@example.com")
            .password("Password123")
            .build();
            
        // When
        ResponseEntity<ApiResponse> response = restTemplate.postForEntity(
            "/api/v1/users", request, ApiResponse.class);
            
        // Then
        assertThat(response.getStatusCode()).isEqualTo(HttpStatus.CREATED);
        assertThat(userRepository.findByEmail("test@example.com")).isPresent();
    }
}
```

## 异常处理

```java
@RestControllerAdvice
@Slf4j
public class GlobalExceptionHandler {
    
    @ExceptionHandler(BusinessException.class)
    public ResponseEntity<ApiResponse<Void>> handleBusinessException(
            BusinessException e) {
        log.warn("Business exception: {}", e.getMessage());
        return ResponseEntity.badRequest()
            .body(ApiResponse.error(e.getMessage()));
    }
    
    @ExceptionHandler(EntityNotFoundException.class)
    public ResponseEntity<ApiResponse<Void>> handleEntityNotFoundException(
            EntityNotFoundException e) {
        log.warn("Entity not found: {}", e.getMessage());
        return ResponseEntity.status(HttpStatus.NOT_FOUND)
            .body(ApiResponse.error(e.getMessage()));
    }
    
    @ExceptionHandler(MethodArgumentNotValidException.class)
    public ResponseEntity<ApiResponse<Map<String, String>>> handleValidationException(
            MethodArgumentNotValidException e) {
        Map<String, String> errors = new HashMap<>();
        e.getBindingResult().getFieldErrors().forEach(error ->
            errors.put(error.getField(), error.getDefaultMessage()));
            
        return ResponseEntity.badRequest()
            .body(ApiResponse.error("参数验证失败", errors));
    }
    
    @ExceptionHandler(Exception.class)
    public ResponseEntity<ApiResponse<Void>> handleGenericException(
            Exception e) {
        log.error("Unexpected error occurred", e);
        return ResponseEntity.status(HttpStatus.INTERNAL_SERVER_ERROR)
            .body(ApiResponse.error("系统内部错误"));
    }
}
```

## 性能优化

### 数据库优化
1. **使用连接池**: HikariCP
2. **查询优化**: @Query 注解，避免 N+1 问题
3. **缓存策略**: Redis + Spring Cache
4. **分页查询**: Pageable

### JVM 优化
```bash
# JVM 参数优化
-Xms2g -Xmx4g
-XX:+UseG1GC
-XX:MaxGCPauseMillis=200
-XX:+PrintGCDetails
-XX:+PrintGCTimeStamps
```

## 部署配置

### Docker
```dockerfile
FROM openjdk:21-jdk-slim

WORKDIR /app

COPY target/*.jar app.jar

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```

### docker-compose.yml
```yaml
version: '3.8'
services:
  app:
    build: .
    ports:
      - "8080:8080"
    environment:
      - SPRING_PROFILES_ACTIVE=prod
      - DB_HOST=postgres
    depends_on:
      - postgres
      - redis
      
  postgres:
    image: postgres:15
    environment:
      POSTGRES_DB: myapp
      POSTGRES_USER: myapp
      POSTGRES_PASSWORD: password
    volumes:
      - postgres_data:/var/lib/postgresql/data
      
  redis:
    image: redis:7-alpine
    ports:
      - "6379:6379"

volumes:
  postgres_data:
```

## 不要做的事情

- 不要在 Controller 中处理业务逻辑
- 不要忽略事务边界
- 不要使用 @Autowired 字段注入，使用构造器注入
- 不要在循环中进行数据库查询
- 不要忽略异常处理和日志记录
- 不要在实体类中使用 @Data 注解（可能导致性能问题）

## 常见问题解决

1. **N+1 查询问题**: 使用 @EntityGraph 或 JOIN FETCH
2. **事务失效**: 确保方法是 public 且通过代理调用
3. **循环依赖**: 重新设计服务层架构
4. **内存泄漏**: 注意缓存和连接池配置
5. **性能问题**: 使用 JProfiler 或 Spring Boot Actuator 监控
```