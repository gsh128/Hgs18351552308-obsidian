# Codex 接入 DeepSeek V4 配置指南

> 来源：[B站视频：100%可用！将DeepSeek V4接入Codex和Claude桌面版的方法](https://www.bilibili.com/video/BV1Sv5f6WErW/)
> 整理日期：2026-05-18
> 🔄 更新：2026-05-21 — CCX 升级，密钥统一变更

---

## 📋 概述

本指南说明如何通过 **API 代理服务**，将 DeepSeek V4 模型接入 **Codex**（以及 Claude Desktop 等支持 OpenAI 兼容接口的工具）。


## 🎉ccx主要配置步骤

### 💡让claudian或hermes自动执行


```text
https://github.com/BenedictKing/ccx阅读理解这个项目
```

### ✅ CCX 安装完成！

**项目**：Claude / Codex / Gemini API 代理网关（BenedictKing/ccx）  
**用途**：统一接入多个 AI 模型供应商的 API，支持协议转换、多 Key 轮换、熔断降级
**🔄 2026-05-21 已升级至最新版**

### 🌐 访问方式

- **Web 管理界面**：在 Windows 浏览器打开 [http://localhost:3000](http://localhost:3000/)
- **健康检查**：[http://localhost:3000/health](http://localhost:3000/health)

### 🔑 密钥

| 用途   | 密钥值             | 备注                               |
| ---- | --------------- | -------------------------------- |
| 代理调用 | `56143316@qq` | Codex / Hermes 等客户端 API 认证      |
| 管理后台 | `56143316@qq` | 登录`http://localhost:3000` Web 管理面板 |

> ⚠️ 2026-05-21 CCX 升级后密钥统一为 `56143316@qq`，旧密钥 `ccx-proxy-key` / `ccx-admin-key` 已废弃


## 📍`CC Switch`配置


### 🚀API Key配置

API Key配置为 `56143316@qq`


### 🤖API请求地址

API请求地址为`http://localhost:3000/v1`



## ✅ 验证配置

### 启动应用

- 在 PowerShell 里输入 `wsl` 回车，进入 Linux 子系统。
- 启动服务：`ccx-ctl restart`


### 费用情况

#### 2026年5月18日
- **优云智算**
	- 2026年5月18日余额43.68元
	- 2026年5月18日当天消费0元

### 使用情况

- **codex**
	- 使用较好、反映快
- **obsidian中的codex插件**
	- 能使用但使用的模型渠道暂不清



## 📎 参考链接

- [DeepSeek 官网](https://www.deepseek.com/)
- [DeepSeek API 文档](https://platform.deepseek.com/api-docs)
- [new-api GitHub](https://github.com/Calcium-Ion/new-api)
- [one-api GitHub](https://github.com/songquanpeng/one-api)
- [Codex 官方文档](https://github.com/openai/codex)

---

> 🎯 **总结**：通过部署本地 API 代理，将 DeepSeek V4 转换为 OpenAI 兼容格式，Codex 只需修改 API 地址和 Key 即可无缝切换，无需额外适配。
