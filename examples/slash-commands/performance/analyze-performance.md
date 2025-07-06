# 性能分析命令

全面的应用性能分析和优化建议，包含前端、后端和数据库性能检测。

## 使用方法

将此文件保存为 `.claude/commands/analyze-performance.md`，然后使用 `/analyze-performance` 命令。

## 命令内容

```markdown
# 应用性能分析

执行全面的性能分析，识别性能瓶颈并提供优化建议。

## 分析范围

性能分析类型: $ARGUMENTS (可选: frontend, backend, database, network, memory, all)

## 性能分析流程

### 1. 前端性能分析

#### Web 应用性能检测
```bash
# 使用 Lighthouse 分析
if command -v lighthouse &> /dev/null; then
    echo "正在进行 Lighthouse 性能分析..."
    lighthouse http://localhost:3000 --output=json --output-path=./performance-reports/lighthouse-$(date +%Y%m%d).json
    lighthouse http://localhost:3000 --output=html --output-path=./performance-reports/lighthouse-$(date +%Y%m%d).html
fi

# 使用 WebPageTest API (如果配置了)
if [ ! -z "$WPT_API_KEY" ]; then
    echo "正在进行 WebPageTest 分析..."
    curl "https://www.webpagetest.org/runtest.php?url=http://localhost:3000&k=$WPT_API_KEY&f=json"
fi
```

#### Bundle 分析
```bash
# JavaScript Bundle 分析
if [ -f "package.json" ]; then
    echo "分析 JavaScript Bundle 大小..."
    
    # Webpack Bundle Analyzer
    if grep -q "webpack-bundle-analyzer" package.json; then
        npm run analyze
    fi
    
    # Next.js Bundle Analyzer
    if grep -q "next" package.json; then
        npx @next/bundle-analyzer build
    fi
    
    # Vite Bundle Analyzer
    if grep -q "vite" package.json; then
        npx vite-bundle-analyzer dist
    fi
    
    # 检查依赖项大小
    npx bundlephobia-cli --interactive
fi
```

#### 前端性能指标收集
```bash
# 创建性能测试脚本
cat > performance-test.js << 'EOF'
const puppeteer = require('puppeteer');

(async () => {
  const browser = await puppeteer.launch();
  const page = await browser.newPage();
  
  // 启用性能监控
  await page.tracing.start({path: 'trace.json'});
  
  // 收集性能指标
  const metrics = await page.metrics();
  console.log('性能指标:', metrics);
  
  // 导航到页面
  const response = await page.goto('http://localhost:3000');
  
  // 收集 Core Web Vitals
  const vitals = await page.evaluate(() => {
    return new Promise((resolve) => {
      new PerformanceObserver((list) => {
        const entries = list.getEntries();
        resolve(entries.map(entry => ({
          name: entry.name,
          value: entry.value,
          rating: entry.rating
        })));
      }).observe({entryTypes: ['largest-contentful-paint', 'first-input', 'cumulative-layout-shift']});
    });
  });
  
  console.log('Core Web Vitals:', vitals);
  
  await page.tracing.stop();
  await browser.close();
})();
EOF

if [ -f "package.json" ] && npm list puppeteer &> /dev/null; then
    node performance-test.js
fi
```

### 2. 后端性能分析

#### Node.js 性能分析
```bash
if [ -f "package.json" ]; then
    echo "Node.js 性能分析..."
    
    # 使用 clinic.js 性能分析
    if npm list @clinic/doctor &> /dev/null; then
        clinic doctor -- node server.js &
        sleep 30
        kill $!
    fi
    
    # 内存使用分析
    if npm list heapdump &> /dev/null; then
        node --inspect server.js &
        sleep 10
        kill $!
    fi
    
    # 使用 autocannon 进行负载测试
    if npm list autocannon &> /dev/null; then
        autocannon -c 10 -d 30 http://localhost:3000/api/health
    fi
fi
```

#### Python 性能分析
```bash
if [ -f "requirements.txt" ] || [ -f "pyproject.toml" ]; then
    echo "Python 性能分析..."
    
    # 使用 cProfile 分析
    python -m cProfile -o profile_stats.prof main.py
    
    # 使用 py-spy 进行采样分析
    if command -v py-spy &> /dev/null; then
        py-spy record -o profile.svg -- python main.py &
        sleep 30
        kill $!
    fi
    
    # 内存分析
    if pip list | grep -q memory-profiler; then
        python -m memory_profiler main.py
    fi
    
    # Django 性能分析
    if [ -f "manage.py" ]; then
        python manage.py shell << 'EOF'
from django.test.utils import override_settings
from django.core.management import call_command
import time

# 测试数据库查询性能
from django.db import connection
start_time = time.time()
# 执行一些查询
print(f"数据库查询耗时: {time.time() - start_time:.2f}秒")
print(f"查询数量: {len(connection.queries)}")
EOF
    fi
fi
```

#### Java 性能分析
```bash
if [ -f "pom.xml" ] || [ -f "build.gradle" ]; then
    echo "Java 性能分析..."
    
    # JVM 性能监控
    jps -l
    jstat -gc $(jps -l | grep -v Jps | head -1 | cut -d' ' -f1) 5s 10
    
    # 堆内存分析
    jmap -histo $(jps -l | grep -v Jps | head -1 | cut -d' ' -f1)
    
    # 使用 JProfiler 或 VisualVM 分析
    echo "建议使用 JProfiler 或 VisualVM 进行详细分析"
fi
```

#### Go 性能分析
```bash
if [ -f "go.mod" ]; then
    echo "Go 性能分析..."
    
    # CPU 性能分析
    go test -cpuprofile=cpu.prof -bench=.
    go tool pprof cpu.prof
    
    # 内存分析
    go test -memprofile=mem.prof -bench=.
    go tool pprof mem.prof
    
    # 使用 go-torch 生成火焰图
    if command -v go-torch &> /dev/null; then
        go-torch -b cpu.prof
    fi
    
    # 运行时性能监控
    curl http://localhost:6060/debug/pprof/profile?seconds=30 > runtime.prof
fi
```

### 3. 数据库性能分析

#### PostgreSQL 性能分析
```bash
if command -v psql &> /dev/null; then
    echo "PostgreSQL 性能分析..."
    
    psql -h localhost -d mydb -c "
    -- 查询性能统计
    SELECT query, calls, total_time, mean_time, rows 
    FROM pg_stat_statements 
    ORDER BY total_time DESC 
    LIMIT 10;
    
    -- 索引使用情况
    SELECT 
        schemaname, tablename, attname, 
        n_distinct, correlation 
    FROM pg_stats 
    WHERE schemaname = 'public';
    
    -- 慢查询分析
    SELECT 
        query, 
        mean_time, 
        calls, 
        total_time 
    FROM pg_stat_statements 
    WHERE mean_time > 1000 
    ORDER BY mean_time DESC;
    
    -- 锁等待分析
    SELECT 
        blocked_locks.pid AS blocked_pid,
        blocked_activity.usename AS blocked_user,
        blocking_locks.pid AS blocking_pid,
        blocking_activity.usename AS blocking_user,
        blocked_activity.query AS blocked_statement
    FROM pg_catalog.pg_locks blocked_locks
    JOIN pg_catalog.pg_stat_activity blocked_activity ON blocked_activity.pid = blocked_locks.pid
    JOIN pg_catalog.pg_locks blocking_locks ON blocking_locks.locktype = blocked_locks.locktype
    JOIN pg_catalog.pg_stat_activity blocking_activity ON blocking_activity.pid = blocking_locks.pid
    WHERE NOT blocked_locks.granted;
    "
fi
```

#### MySQL 性能分析
```bash
if command -v mysql &> /dev/null; then
    echo "MySQL 性能分析..."
    
    mysql -h localhost -u root -p mydb << 'EOF'
-- 慢查询分析
SELECT 
    query_time, 
    lock_time, 
    rows_sent, 
    rows_examined, 
    sql_text 
FROM mysql.slow_log 
ORDER BY query_time DESC 
LIMIT 10;

-- 性能统计
SHOW ENGINE INNODB STATUS;

-- 查询缓存状态
SHOW STATUS LIKE 'Qcache%';

-- 连接状态
SHOW PROCESSLIST;
EOF
fi
```

#### Redis 性能分析
```bash
if command -v redis-cli &> /dev/null; then
    echo "Redis 性能分析..."
    
    # Redis 信息统计
    redis-cli INFO memory
    redis-cli INFO stats
    redis-cli INFO keyspace
    
    # 慢查询日志
    redis-cli SLOWLOG GET 10
    
    # 内存使用分析
    redis-cli --bigkeys
    
    # 延迟监控
    redis-cli --latency -h localhost -p 6379
fi
```

### 4. 网络性能分析

#### HTTP 性能测试
```bash
echo "网络性能分析..."

# 使用 ab (Apache Bench) 进行压力测试
if command -v ab &> /dev/null; then
    echo "Apache Bench 压力测试..."
    ab -n 1000 -c 10 http://localhost:3000/api/health
fi

# 使用 wrk 进行性能测试
if command -v wrk &> /dev/null; then
    echo "wrk 性能测试..."
    wrk -t12 -c400 -d30s http://localhost:3000/api/health
fi

# 使用 hey 进行负载测试
if command -v hey &> /dev/null; then
    echo "hey 负载测试..."
    hey -n 1000 -c 50 http://localhost:3000/api/health
fi

# TCP 连接分析
netstat -an | grep :3000 | wc -l
```

### 5. 系统资源监控

#### CPU 和内存监控
```bash
echo "系统资源监控..."

# CPU 使用情况
echo "=== CPU 使用情况 ==="
top -n 1 | head -20

# 内存使用情况
echo "=== 内存使用情况 ==="
free -h

# 磁盘 I/O 监控
echo "=== 磁盘 I/O ==="
if command -v iotop &> /dev/null; then
    iotop -a -o -d 1 -n 5
elif command -v iostat &> /dev/null; then
    iostat -x 1 5
fi

# 进程资源使用
echo "=== 进程资源使用 ==="
ps aux --sort=-%cpu | head -10
ps aux --sort=-%mem | head -10
```

## 性能报告生成

### 1. 创建性能报告
```bash
# 创建性能报告目录
mkdir -p performance-reports/$(date +%Y%m%d)

# 生成综合性能报告
cat > performance-reports/$(date +%Y%m%d)/performance-analysis.md << EOF
# 性能分析报告

**分析时间**: $(date)
**项目**: $(basename $(pwd))
**分析类型**: ${ARGUMENTS:-"all"}

## 性能指标概览

### 前端性能
- **首次内容绘制 (FCP)**: [数值]
- **最大内容绘制 (LCP)**: [数值]
- **首次输入延迟 (FID)**: [数值]
- **累积布局偏移 (CLS)**: [数值]

### 后端性能
- **平均响应时间**: [数值]
- **QPS (每秒查询数)**: [数值]
- **错误率**: [数值]
- **资源使用率**: [数值]

### 数据库性能
- **查询响应时间**: [数值]
- **连接数**: [数值]
- **慢查询数量**: [数值]
- **缓存命中率**: [数值]

## 性能瓶颈识别

### 关键问题
1. **[高优先级]** [具体问题描述]
2. **[中优先级]** [具体问题描述]
3. **[低优先级]** [具体问题描述]

## 优化建议

### 立即优化 (1-3天)
1. [具体优化建议]
2. [具体优化建议]

### 短期优化 (1-2周)
1. [具体优化建议]
2. [具体优化建议]

### 长期优化 (1个月+)
1. [具体优化建议]
2. [具体优化建议]

EOF
```

### 2. 性能基准记录
```bash
# 记录性能基准
cat > performance-reports/$(date +%Y%m%d)/performance-baseline.json << EOF
{
  "timestamp": "$(date -Iseconds)",
  "frontend": {
    "fcp": null,
    "lcp": null,
    "fid": null,
    "cls": null,
    "bundle_size": null
  },
  "backend": {
    "response_time": null,
    "qps": null,
    "error_rate": null,
    "cpu_usage": null,
    "memory_usage": null
  },
  "database": {
    "query_time": null,
    "connections": null,
    "slow_queries": null,
    "cache_hit_rate": null
  }
}
EOF
```

## 性能优化建议

### 前端优化
1. **代码分割**: 实现懒加载和代码分割
2. **资源压缩**: 启用 Gzip/Brotli 压缩
3. **图片优化**: 使用 WebP 格式和响应式图片
4. **缓存策略**: 合理设置 HTTP 缓存头
5. **CDN 加速**: 使用 CDN 分发静态资源

### 后端优化
1. **数据库优化**: 添加索引，优化查询
2. **缓存策略**: 实现多级缓存
3. **连接池**: 优化数据库连接池配置
4. **异步处理**: 使用异步 I/O 和消息队列
5. **负载均衡**: 实现水平扩展

### 数据库优化
1. **查询优化**: 重写慢查询，添加索引
2. **连接优化**: 调整连接池大小
3. **缓存配置**: 优化查询缓存设置
4. **分库分表**: 对大表进行分区
5. **读写分离**: 实现主从复制

## 持续性能监控

### 1. 自动化监控
```bash
# 设置性能监控脚本
cat > monitor-performance.sh << 'EOF'
#!/bin/bash

# 每小时执行一次性能检查
while true; do
    # 检查关键指标
    curl -w "@curl-format.txt" -o /dev/null -s http://localhost:3000/api/health
    
    # 记录系统资源使用
    echo "$(date): CPU: $(top -n1 | grep "Cpu(s)" | awk '{print $2}'), Memory: $(free | grep Mem | awk '{printf "%.1f%%", $3/$2 * 100.0}')" >> performance.log
    
    sleep 3600
done
EOF

chmod +x monitor-performance.sh
```

### 2. 告警设置
```bash
# 创建性能告警脚本
cat > performance-alert.sh << 'EOF'
#!/bin/bash

# 检查响应时间
response_time=$(curl -w "%{time_total}" -o /dev/null -s http://localhost:3000/api/health)
if (( $(echo "$response_time > 2.0" | bc -l) )); then
    echo "警告: 响应时间过长 ${response_time}s" | mail -s "性能告警" admin@example.com
fi

# 检查错误率
error_rate=$(curl -s http://localhost:3000/metrics | grep error_rate | cut -d' ' -f2)
if (( $(echo "$error_rate > 0.05" | bc -l) )); then
    echo "警告: 错误率过高 ${error_rate}" | mail -s "错误率告警" admin@example.com
fi
EOF
```

## 性能测试环境

### 1. 负载测试环境设置
```bash
# 创建负载测试配置
cat > load-test-config.json << EOF
{
  "scenarios": {
    "light_load": {
      "executor": "constant-vus",
      "vus": 10,
      "duration": "5m"
    },
    "heavy_load": {
      "executor": "ramping-vus",
      "startVUs": 0,
      "stages": [
        { "duration": "2m", "target": 100 },
        { "duration": "5m", "target": 100 },
        { "duration": "2m", "target": 200 },
        { "duration": "5m", "target": 200 },
        { "duration": "2m", "target": 0 }
      ]
    }
  }
}
EOF
```

### 2. 性能回归测试
```bash
# 创建性能回归测试脚本
cat > performance-regression.sh << 'EOF'
#!/bin/bash

# 运行性能基准测试
echo "运行性能基准测试..."
baseline_time=$(curl -w "%{time_total}" -o /dev/null -s http://localhost:3000/api/health)

# 与历史基准比较
if [ -f "performance-baseline.txt" ]; then
    previous_time=$(cat performance-baseline.txt)
    improvement=$(echo "scale=2; ($previous_time - $baseline_time) / $previous_time * 100" | bc)
    echo "性能变化: ${improvement}%"
fi

# 保存新的基准
echo $baseline_time > performance-baseline.txt
EOF
```

请根据分析结果制定具体的性能优化计划，并建立持续的性能监控机制。
```

## 示例用法

```bash
# 全面性能分析
/analyze-performance

# 只分析前端性能
/analyze-performance frontend

# 只分析后端性能
/analyze-performance backend

# 数据库性能分析
/analyze-performance database

# 内存使用分析
/analyze-performance memory
```

## 预期输出

Claude Code 将会：

1. 执行全面的性能分析
2. 生成详细的性能报告
3. 识别关键性能瓶颈
4. 提供分级优化建议
5. 建立性能监控机制
6. 设置性能告警系统

## 相关命令

- `/optimize-performance` - 自动执行性能优化
- `/benchmark-performance` - 性能基准测试
- `/monitor-metrics` - 实时性能监控
- `/load-test` - 负载测试执行