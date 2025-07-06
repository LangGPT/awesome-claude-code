# 生产环境部署命令

安全可靠的生产环境部署流程，包含完整的检查和回滚机制。

## 使用方法

将此文件保存为 `.claude/commands/deploy-production.md`，然后使用 `/deploy-production` 命令。

## 命令内容

```markdown
# 生产环境部署

执行安全的生产环境部署流程，确保服务稳定性和数据安全。

## 部署目标

部署环境: $ARGUMENTS (默认为 production，可选: staging, production, canary)

## 部署前检查清单

1. **代码质量检查**
   - 确保所有测试通过
   - 运行代码质量检查 (lint, type-check)
   - 检查安全漏洞扫描结果
   - 验证依赖项安全性

2. **环境准备检查**
   - 验证部署权限和访问凭证
   - 检查目标环境状态和资源
   - 确认数据库迁移准备就绪
   - 验证配置文件和环境变量

3. **备份和回滚准备**
   - 创建当前版本的备份
   - 准备数据库备份 (如需要)
   - 确认回滚策略和流程
   - 记录当前版本信息

## 部署执行流程

### 阶段1: 预部署验证
```bash
# 检查工作区状态
git status

# 确保在正确的分支
git branch --show-current

# 拉取最新代码
git pull origin main

# 运行完整测试套件
npm run test:all || pytest || go test ./... || mvn test

# 代码质量检查
npm run lint && npm run type-check || flake8 && mypy . || golangci-lint run

# 安全扫描
npm audit || safety check || gosec ./...
```

### 阶段2: 构建和打包
```bash
# 构建生产版本
npm run build:prod || python -m build || go build -ldflags "-s -w" || mvn package

# Docker 镜像构建 (如果使用容器化)
docker build -t app:$(git rev-parse --short HEAD) .

# 镜像安全扫描
docker scan app:$(git rev-parse --short HEAD)

# 推送到镜像仓库
docker push app:$(git rev-parse --short HEAD)
```

### 阶段3: 数据库迁移 (如需要)
```bash
# 备份数据库
pg_dump dbname > backup_$(date +%Y%m%d_%H%M%S).sql

# 运行数据库迁移
python manage.py migrate || flyway migrate || alembic upgrade head

# 验证迁移结果
python manage.py showmigrations || flyway info
```

### 阶段4: 应用部署

根据部署方式选择：

#### Kubernetes 部署
```bash
# 更新部署配置
kubectl set image deployment/app app=app:$(git rev-parse --short HEAD)

# 等待部署完成
kubectl rollout status deployment/app

# 验证 Pod 状态
kubectl get pods -l app=app
```

#### Docker Compose 部署
```bash
# 更新 docker-compose.yml 中的镜像版本
sed -i "s/app:latest/app:$(git rev-parse --short HEAD)/g" docker-compose.prod.yml

# 重新部署服务
docker-compose -f docker-compose.prod.yml up -d

# 检查服务状态
docker-compose -f docker-compose.prod.yml ps
```

#### 传统服务器部署
```bash
# 停止当前服务
systemctl stop app-service

# 备份当前版本
cp -r /opt/app /opt/app-backup-$(date +%Y%m%d_%H%M%S)

# 部署新版本
rsync -av --delete dist/ /opt/app/

# 重启服务
systemctl start app-service
systemctl status app-service
```

### 阶段5: 部署后验证

1. **健康检查**
   - 验证应用启动状态
   - 检查健康检查端点
   - 确认关键功能正常

2. **性能验证**
   - 检查响应时间
   - 验证资源使用情况
   - 监控错误率

3. **集成验证**
   - 测试关键业务流程
   - 验证第三方服务集成
   - 检查数据库连接

```bash
# 健康检查
curl -f http://localhost:8080/health || exit 1

# 功能测试
curl -f http://localhost:8080/api/v1/status

# 性能检查
ab -n 100 -c 10 http://localhost:8080/api/v1/health
```

## 部署监控

### 监控指标
- 应用响应时间
- 错误率和异常
- 系统资源使用
- 数据库性能
- 用户访问情况

### 告警配置
- 设置关键指标告警
- 配置异常通知
- 监控日志错误

### 日志收集
```bash
# 检查应用日志
tail -f /var/log/app/app.log

# 检查系统日志
journalctl -u app-service -f

# 检查容器日志 (如果使用 Docker)
docker logs -f container_name
```

## 回滚流程

如果部署出现问题，立即执行回滚：

1. **快速回滚**
```bash
# Kubernetes 回滚
kubectl rollout undo deployment/app

# Docker 服务回滚
docker-compose -f docker-compose.prod.yml down
docker-compose -f docker-compose.prod.yml up -d --scale app=0
# 恢复之前的镜像版本

# 传统部署回滚
systemctl stop app-service
rm -rf /opt/app
mv /opt/app-backup-$(date +%Y%m%d_%H%M%S) /opt/app
systemctl start app-service
```

2. **数据库回滚** (如果需要)
```bash
# 恢复数据库备份
psql dbname < backup_$(date +%Y%m%d_%H%M%S).sql
```

3. **验证回滚结果**
   - 确认服务正常运行
   - 验证关键功能
   - 检查用户访问恢复

## 部署后任务

1. **更新文档**
   - 记录部署版本和时间
   - 更新变更日志
   - 通知相关团队

2. **性能基线更新**
   - 记录新版本性能数据
   - 更新监控基线
   - 调整告警阈值

3. **清理工作**
   - 清理旧的备份文件
   - 删除临时构建文件
   - 更新部署记录

## 安全注意事项

- 确保所有密钥和证书有效
- 验证访问权限和防火墙规则
- 检查 HTTPS 证书状态
- 确认安全扫描通过

## 紧急联系信息

在部署过程中如遇紧急情况：
- 立即执行回滚流程
- 通知运维团队和项目负责人
- 记录问题详情和解决方案
- 安排问题复盘和改进

请根据项目实际情况调整部署流程，确保每个步骤都经过验证后再继续。
```

## 示例用法

```bash
# 部署到生产环境
/deploy-production

# 部署到预发布环境
/deploy-production staging

# 金丝雀部署
/deploy-production canary
```

## 预期输出

Claude Code 将会：

1. 执行完整的部署前检查
2. 创建必要的备份
3. 按阶段执行部署流程
4. 进行部署后验证
5. 提供监控和维护建议
6. 在出现问题时提供回滚指导

## 相关命令

- `/rollback` - 快速回滚到上一版本
- `/health-check` - 检查应用健康状态
- `/monitor-deployment` - 监控部署状态
- `/backup-database` - 创建数据库备份