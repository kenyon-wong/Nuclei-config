# Nuclei-config

一个经过优化的 Nuclei 扫描器配置文件，专注于企业级安全扫描场景。

## ⚡️ 快速开始

```bash
nuclei -config My-nuclei-config.yaml -l targets.txt
```

## 🔨 主要配置项

### 基础连接配置
```yaml
proxy: 'http://127.0.0.1:8080'  # 代理设置
timeout: 5                       # 请求超时时间
no-max-host-error: true         # 忽略最大主机错误
```

### 性能优化配置
```yaml
bulk-size: 50        # 单模板并行主机数
concurrency: 50      # 并行模板数量
rate-limit: 500      # 每秒请求限制
```

### 认证与安全配置
```yaml
secret-file: 'Secret.yaml'  # 认证密钥文件
prefetch-secrets: true      # 预加载密钥
```

### 更新与平台控制
```yaml
update-templates: false        # 禁用模板更新
disable-update-check: true    # 禁用程序更新
no-interactsh: true          # 禁用反连平台
cloud-upload: false          # 禁用云上传
```

## 📋 模板管理

### 包含的安全检测类型
- 默认登录检测
- WAF 探测
- Spring Boot 相关漏洞
- Nacos 配置检测
- WebLogic 系列漏洞
- 各类 CVE 漏洞检测
- API 暴露检测
- 配置文件泄露检测

### 排除的检测类型
- XSS 漏洞
- DOS 攻击
- OSINT 信息收集
- 恶意软件检测
- 凭证填充攻击
- WordPress 相关

## 🔍 特色功能

1. **企业级优化**
   - 针对企业内网环境优化的扫描配置
   - 已禁用不适用于内网的反连检测功能

2. **性能调优**
   - 优化并行扫描参数
   - 合理的请求速率限制

3. **报告输出**
   ```yaml
   markdown-export: markdown-export
   report-db: report-db
   ```

## ⚠️ 使用注意事项

1. **路径兼容性**
   - Windows 与 Unix 系统路径分隔符差异
   - 使用前检查模板路径格式

2. **代理设置**
   - 确保代理配置与本地环境匹配
   - 可根据需要修改代理设置

3. **性能调整**
   - 可根据目标系统承受能力调整并发参数
   - 注意监控扫描对目标系统的影响

## 📚 参考文档

- [Nuclei 官方文档](https://docs.projectdiscovery.io/tools/nuclei/running#nuclei-config)
- [认证扫描配置](https://docs.projectdiscovery.io/tools/nuclei/authenticated-scans#static-authentication)

## 🤝 贡献

欢迎提交 Issue 或 Pull Request 来改进配置文件。
