# Angular 项目 CLAUDE.md 模板

```markdown
# CLAUDE.md

这个文件为 Claude Code 提供项目特定的指导信息。

## 项目概述

这是一个使用 Angular 构建的企业级前端应用。

## 技术栈

- **框架**: Angular 17+
- **语言**: TypeScript 5.2+
- **状态管理**: NgRx
- **UI 框架**: Angular Material / PrimeNG
- **样式**: SCSS + Angular Flex Layout
- **构建工具**: Angular CLI + Webpack
- **测试**: Jasmine + Karma + Protractor
- **包管理器**: npm

## 项目结构

```
src/
├── main.ts                 # 应用启动文件
├── index.html              # HTML 模板
├── styles.scss             # 全局样式
├── app/
│   ├── app.module.ts       # 根模块
│   ├── app.component.ts    # 根组件
│   ├── app-routing.module.ts # 路由配置
│   ├── core/               # 核心模块
│   │   ├── core.module.ts
│   │   ├── guards/         # 路由守卫
│   │   ├── interceptors/   # HTTP 拦截器
│   │   ├── services/       # 核心服务
│   │   └── models/         # 数据模型
│   ├── shared/             # 共享模块
│   │   ├── shared.module.ts
│   │   ├── components/     # 共享组件
│   │   ├── directives/     # 指令
│   │   ├── pipes/          # 管道
│   │   └── validators/     # 验证器
│   ├── features/           # 功能模块
│   │   ├── auth/           # 认证模块
│   │   ├── dashboard/      # 仪表板模块
│   │   └── user-management/ # 用户管理模块
│   └── layout/             # 布局组件
│       ├── header/
│       ├── sidebar/
│       └── footer/
└── assets/                 # 静态资源
    ├── images/
    ├── icons/
    └── i18n/               # 国际化文件
```

## 常用命令

### 开发相关
- `ng serve`: 启动开发服务器
- `ng build`: 构建应用
- `ng build --prod`: 生产环境构建
- `ng test`: 运行单元测试
- `ng e2e`: 运行端到端测试
- `ng lint`: 代码检查

### 代码生成
- `ng generate component <name>`: 生成组件
- `ng generate service <name>`: 生成服务
- `ng generate module <name>`: 生成模块
- `ng generate guard <name>`: 生成守卫
- `ng generate pipe <name>`: 生成管道
- `ng generate directive <name>`: 生成指令

## 代码规范

### 组件规范
- 使用 OnPush 变更检测策略
- 组件名使用 PascalCase，文件名使用 kebab-case
- 实现生命周期钩子接口
- 使用 Angular 依赖注入

```typescript
@Component({
  selector: 'app-user-card',
  templateUrl: './user-card.component.html',
  styleUrls: ['./user-card.component.scss'],
  changeDetection: ChangeDetectionStrategy.OnPush
})
export class UserCardComponent implements OnInit, OnDestroy {
  @Input() user!: User;
  @Output() userSelected = new EventEmitter<User>();
  
  private destroy$ = new Subject<void>();
  
  constructor(
    private userService: UserService,
    private cdr: ChangeDetectorRef
  ) {}
  
  ngOnInit(): void {
    this.loadUserData();
  }
  
  ngOnDestroy(): void {
    this.destroy$.next();
    this.destroy$.complete();
  }
  
  private loadUserData(): void {
    this.userService.getUser(this.user.id)
      .pipe(takeUntil(this.destroy$))
      .subscribe(user => {
        this.user = user;
        this.cdr.markForCheck();
      });
  }
}
```

### 服务规范
- 使用 Injectable 装饰器
- 在 root 注入器中提供服务
- 处理 HTTP 错误和重试逻辑

```typescript
@Injectable({ providedIn: 'root' })
export class UserService {
  private readonly apiUrl = `${environment.apiUrl}/users`;
  
  constructor(private http: HttpClient) {}
  
  getUsers(): Observable<User[]> {
    return this.http.get<User[]>(this.apiUrl).pipe(
      retry(3),
      catchError(this.handleError)
    );
  }
  
  createUser(user: CreateUserDto): Observable<User> {
    return this.http.post<User>(this.apiUrl, user).pipe(
      catchError(this.handleError)
    );
  }
  
  private handleError(error: HttpErrorResponse): Observable<never> {
    console.error('API Error:', error);
    return throwError(() => new Error('Something went wrong'));
  }
}
```

### 模块规范
- 功能模块应该是自包含的
- 使用懒加载优化性能
- 正确配置模块的 imports、declarations、exports

```typescript
@NgModule({
  declarations: [
    UserListComponent,
    UserCardComponent,
    UserFormComponent
  ],
  imports: [
    CommonModule,
    UserManagementRoutingModule,
    ReactiveFormsModule,
    MaterialModule
  ],
  providers: [
    UserService,
    UserResolver
  ]
})
export class UserManagementModule {}
```

## 状态管理 (NgRx)

### Store 结构
```typescript
// state/app.state.ts
export interface AppState {
  auth: AuthState;
  users: UserState;
  ui: UiState;
}

// state/user/user.state.ts
export interface UserState {
  users: User[];
  selectedUser: User | null;
  loading: boolean;
  error: string | null;
}
```

### Actions
```typescript
// state/user/user.actions.ts
export const UserActions = createActionGroup({
  source: 'User',
  events: {
    'Load Users': emptyProps(),
    'Load Users Success': props<{ users: User[] }>(),
    'Load Users Failure': props<{ error: string }>(),
    'Select User': props<{ userId: string }>(),
  }
});
```

### Reducer
```typescript
// state/user/user.reducer.ts
const initialState: UserState = {
  users: [],
  selectedUser: null,
  loading: false,
  error: null
};

export const userReducer = createReducer(
  initialState,
  on(UserActions.loadUsers, state => ({
    ...state,
    loading: true,
    error: null
  })),
  on(UserActions.loadUsersSuccess, (state, { users }) => ({
    ...state,
    users,
    loading: false
  })),
  on(UserActions.loadUsersFailure, (state, { error }) => ({
    ...state,
    loading: false,
    error
  }))
);
```

### Effects
```typescript
// state/user/user.effects.ts
@Injectable()
export class UserEffects {
  loadUsers$ = createEffect(() =>
    this.actions$.pipe(
      ofType(UserActions.loadUsers),
      switchMap(() =>
        this.userService.getUsers().pipe(
          map(users => UserActions.loadUsersSuccess({ users })),
          catchError(error => 
            of(UserActions.loadUsersFailure({ error: error.message }))
          )
        )
      )
    )
  );
  
  constructor(
    private actions$: Actions,
    private userService: UserService
  ) {}
}
```

## 路由配置

### 懒加载模块
```typescript
// app-routing.module.ts
const routes: Routes = [
  { path: '', redirectTo: '/dashboard', pathMatch: 'full' },
  {
    path: 'dashboard',
    loadChildren: () => import('./features/dashboard/dashboard.module')
      .then(m => m.DashboardModule),
    canActivate: [AuthGuard]
  },
  {
    path: 'users',
    loadChildren: () => import('./features/user-management/user-management.module')
      .then(m => m.UserManagementModule),
    canActivate: [AuthGuard],
    data: { roles: ['admin'] }
  }
];
```

### 路由守卫
```typescript
// core/guards/auth.guard.ts
@Injectable({ providedIn: 'root' })
export class AuthGuard implements CanActivate {
  constructor(
    private authService: AuthService,
    private router: Router
  ) {}
  
  canActivate(
    route: ActivatedRouteSnapshot,
    state: RouterStateSnapshot
  ): Observable<boolean> {
    return this.authService.isAuthenticated$.pipe(
      map(isAuthenticated => {
        if (!isAuthenticated) {
          this.router.navigate(['/auth/login']);
          return false;
        }
        return true;
      })
    );
  }
}
```

## 表单处理

### 响应式表单
```typescript
// components/user-form/user-form.component.ts
export class UserFormComponent implements OnInit {
  userForm: FormGroup;
  
  constructor(private fb: FormBuilder) {
    this.userForm = this.fb.group({
      name: ['', [Validators.required, Validators.minLength(2)]],
      email: ['', [Validators.required, Validators.email]],
      role: ['user', Validators.required],
      profile: this.fb.group({
        bio: [''],
        avatar: ['']
      })
    });
  }
  
  onSubmit(): void {
    if (this.userForm.valid) {
      const user = this.userForm.value;
      // 处理表单提交
    } else {
      this.markFormGroupTouched();
    }
  }
  
  private markFormGroupTouched(): void {
    Object.keys(this.userForm.controls).forEach(key => {
      const control = this.userForm.get(key);
      control?.markAsTouched();
    });
  }
}
```

### 自定义验证器
```typescript
// shared/validators/custom-validators.ts
export class CustomValidators {
  static passwordMatch(control: AbstractControl): ValidationErrors | null {
    const password = control.get('password');
    const confirmPassword = control.get('confirmPassword');
    
    if (password?.value !== confirmPassword?.value) {
      return { passwordMismatch: true };
    }
    return null;
  }
  
  static uniqueEmail(userService: UserService): AsyncValidatorFn {
    return (control: AbstractControl): Observable<ValidationErrors | null> => {
      if (!control.value) {
        return of(null);
      }
      
      return userService.checkEmailExists(control.value).pipe(
        map(exists => exists ? { emailExists: true } : null),
        catchError(() => of(null))
      );
    };
  }
}
```

## HTTP 拦截器

```typescript
// core/interceptors/auth.interceptor.ts
@Injectable()
export class AuthInterceptor implements HttpInterceptor {
  constructor(private authService: AuthService) {}
  
  intercept(
    req: HttpRequest<any>,
    next: HttpHandler
  ): Observable<HttpEvent<any>> {
    const token = this.authService.getToken();
    
    if (token) {
      const authReq = req.clone({
        setHeaders: {
          Authorization: `Bearer ${token}`
        }
      });
      return next.handle(authReq);
    }
    
    return next.handle(req);
  }
}
```

## 测试策略

### 组件测试
```typescript
// components/user-card/user-card.component.spec.ts
describe('UserCardComponent', () => {
  let component: UserCardComponent;
  let fixture: ComponentFixture<UserCardComponent>;
  let userService: jasmine.SpyObj<UserService>;
  
  beforeEach(async () => {
    const spy = jasmine.createSpyObj('UserService', ['getUser']);
    
    await TestBed.configureTestingModule({
      declarations: [UserCardComponent],
      providers: [
        { provide: UserService, useValue: spy }
      ]
    }).compileComponents();
    
    fixture = TestBed.createComponent(UserCardComponent);
    component = fixture.componentInstance;
    userService = TestBed.inject(UserService) as jasmine.SpyObj<UserService>;
  });
  
  it('should display user information', () => {
    const mockUser = { id: '1', name: 'John Doe', email: 'john@example.com' };
    component.user = mockUser;
    
    fixture.detectChanges();
    
    expect(fixture.nativeElement.textContent).toContain('John Doe');
  });
});
```

### 服务测试
```typescript
// services/user.service.spec.ts
describe('UserService', () => {
  let service: UserService;
  let httpMock: HttpTestingController;
  
  beforeEach(() => {
    TestBed.configureTestingModule({
      imports: [HttpClientTestingModule],
      providers: [UserService]
    });
    
    service = TestBed.inject(UserService);
    httpMock = TestBed.inject(HttpTestingController);
  });
  
  it('should fetch users', () => {
    const mockUsers = [
      { id: '1', name: 'John' },
      { id: '2', name: 'Jane' }
    ];
    
    service.getUsers().subscribe(users => {
      expect(users).toEqual(mockUsers);
    });
    
    const req = httpMock.expectOne('/api/users');
    expect(req.request.method).toBe('GET');
    req.flush(mockUsers);
  });
});
```

## 国际化 (i18n)

### 配置
```typescript
// app.module.ts
import { registerLocaleData } from '@angular/common';
import localeZh from '@angular/common/locales/zh';

registerLocaleData(localeZh);

@NgModule({
  imports: [
    HttpClientModule,
    TranslateModule.forRoot({
      loader: {
        provide: TranslateLoader,
        useFactory: HttpLoaderFactory,
        deps: [HttpClient]
      }
    })
  ]
})
export class AppModule {}
```

### 使用
```html
<!-- 模板中使用 -->
<h1>{{ 'WELCOME_MESSAGE' | translate }}</h1>
<p>{{ 'USER_COUNT' | translate: { count: userCount } }}</p>
```

## 性能优化

1. **OnPush 变更检测**
2. **TrackBy 函数优化 ngFor**
3. **懒加载模块**
4. **预加载策略**
5. **Bundle 分析和优化**

```typescript
// 性能优化示例
@Component({
  changeDetection: ChangeDetectionStrategy.OnPush
})
export class OptimizedComponent {
  trackByFn(index: number, item: any): any {
    return item.id;
  }
}
```

## 构建和部署

### 生产构建
```bash
ng build --prod --aot --build-optimizer
```

### Docker 部署
```dockerfile
FROM node:16-alpine as build
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build

FROM nginx:alpine
COPY --from=build /app/dist /usr/share/nginx/html
COPY nginx.conf /etc/nginx/nginx.conf
```

## 不要做的事情

- 不要在组件中进行复杂的业务逻辑处理
- 不要忘记取消订阅 Observable
- 不要在模板中使用函数调用
- 不要忽略 Angular 的安全特性
- 不要在 ngFor 中不使用 trackBy

## 常见问题解决

1. **内存泄漏**: 使用 takeUntil 操作符
2. **变更检测问题**: 使用 OnPush 策略
3. **路由参数获取**: 使用 ActivatedRoute
4. **表单验证**: 使用响应式表单和自定义验证器

## 开发环境配置

```typescript
// environments/environment.ts
export const environment = {
  production: false,
  apiUrl: 'http://localhost:3000/api',
  enableDebugTools: true
};
```
```