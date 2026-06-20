# 🙏 致谢
本项目基于 https://github.com/cmliu/CF-Workers-SUB 二次开发，在原项目基础上新增 NOADS、USER/PASS 登录鉴权变量以及前端 UI 优化，特此感谢原作者 cmliu 的开源贡献。
# ⚙ CF-SUB-LIAN

这是一个将多个节点和订阅合并为单一链接的工具，支持自动适配与自定义分流，简化了订阅管理。

> [!CAUTION]
> **汇聚订阅非base64订阅时**，会自动生成一个**有效期为24小时的临时订阅**，并提交给**订阅转换后端**来完成订阅转换，可避免您的汇聚订阅地址泄露。

> [!WARNING]
> **汇聚订阅非base64订阅时**，如果您的节点数量十分庞大，订阅转换后端将需要较长时间才能完成订阅转换，这会导致部分梯子客户端在订阅时提示超时而无法完成订阅。
>
> 可自行删减订阅节点数量，提高订阅转换效率！

## 🛠 功能特点
1. 节点链接自动转换成base64订阅链接
2. 多订阅汇聚成单一订阅链接
3. 自动适配不同客户端格式（依赖订阅转换服务）
4. 自定义分流规则
5. 更多功能等待发掘...


## 📦 Pages 部署方法

### 1. Fork 并部署
在 Cloudflare Pages 连接 GitHub 仓库

### 2. 自定义域
绑定你的子域名

### 3. TOKEN 入口
设置 TOKEN 变量作为订阅入口

### 4. KV 配置
绑定 KV 并写入节点或订阅链接

## 🛠 Worker 部署方法

### 1. 创建 Worker
粘贴 _worker.js

### 2. 配置 TOKEN
修改订阅入口路径

### 3. KV 绑定
绑定 KV 命名空间

## 📋 变量说明（完整）

| 变量名 | 说明 | 示例 | 是否必填 |
|------|------|------|--------|
| TOKEN | 订阅入口路径 | auto / sub / token | ✅ |
| GUEST | 访客订阅TOKEN | test | ❌ |
| LINK | 节点或订阅链接（KV未启用时使用） | vless://xxx / https://xxx | ❌ |
| USER | 管理员用户名（CF环境变量） | admin | ❌ |
| PASS | 管理员密码（CF环境变量） | 123456 | ❌ |
| NOADS | 节点关键词过滤（匹配到关键词的节点将被屏蔽） | 例如: netflix / ads / test | ❌ |
| TGTOKEN | Telegram Bot Token | 123456:ABC-xxx | ❌ |
| TGID | Telegram 接收ID | 123456789 | ❌ |
| SUBNAME | 订阅名称 | CF-SUB-LIAN | ❌ |
| SUBAPI | 订阅转换API | sub.example.com | ❌ |
| SUBCONFIG | Clash/Singbox配置文件 | https://xxx.ini | ❌ |

---


## ⚠️ 注意事项
请妥善保管 TOKEN 与 TG 配置。

## ⭐ Star
项目持续优化中。