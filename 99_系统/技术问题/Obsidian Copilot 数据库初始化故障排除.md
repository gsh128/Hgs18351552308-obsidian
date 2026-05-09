---
type: troubleshooting
status: solved
date: 2026-05-09
tags: [obsidian, copilot, 故障排除, 数据库]
area: [[工具]]
---

# Obsidian Copilot 数据库初始化故障排除

## 问题描述

- **错误信息**：`Failed to initialize Copilot database. Some features may be limited.`
- **发生时间**：2026-05-09
- **Copilot 版本**：3.2.8
- **Obsidian 环境**：Windows

## 问题原因

Copilot 插件使用 SQLite 数据库（通过 `better-sqlite3` 原生模块）存储：
- 聊天记录
- 向量索引
- 内存存储
- 自定义提示词

当数据库文件：
- ❌ 不存在
- ❌ 损坏
- ❌ 权限不足
- ❌ better-sqlite3 模块版本不匹配

就会初始化失败。

## 解决方案

### 方案 1：禁用并重新启用插件 ⭐ 推荐

1. 打开 Obsidian
2. 进入 `设置 → 社区插件`
3. 找到 `Copilot`，**关闭开关**
4. **完全重启 Obsidian**
5. 再次进入 `设置 → 社区插件`
6. 重新启用 `Copilot`
7. 再次重启 Obsidian

### 方案 2：使用 BRAT 重新安装

1. 按 `Ctrl+P` 打开命令面板
2. 输入 `BRAT: Add a beta plugin for testing`
3. 输入仓库地址：`logancyang/obsidian-copilot`
4. 等待安装完成
5. 重启 Obsidian

### 方案 3：手动重新下载

1. 关闭 Obsidian
2. 删除 `.obsidian/plugins/copilot/` 整个文件夹
3. 从 [GitHub Releases](https://github.com/logancyang/obsidian-copilot/releases) 下载最新版本
4. 解压到 `.obsidian/plugins/copilot/`
5. 重启 Obsidian

### 方案 4：检查文件权限

确保 Obsidian 对以下目录有完整读写权限：
- `.obsidian/plugins/copilot/`
- 数据库文件创建位置（通常是插件目录内）

在 Windows 上：
- 右键点击仓库文件夹
- 属性 → 安全 → 确保您的用户有完全控制权限

### 方案 5：降级版本

如果最新版本有问题：

1. 下载 [v3.1.0](https://github.com/logancyang/obsidian-copilot/releases/tag/v3.1.0) 或其他稳定版本
2. 替换 `.obsidian/plugins/copilot/` 中的文件

## 预防措施

1. **定期备份配置**：备份 `.obsidian/plugins/copilot/data.json`
2. **关注更新**：查看 Copilot 的 [GitHub Issues](https://github.com/logancyang/obsidian-copilot/issues)
3. **测试后再升级**：升级前等待社区反馈
4. **关闭自动索引**：如果不需要，可在 Copilot 设置中关闭 `indexVaultToVectorStore`

## 相关资源

- [Copilot GitHub](https://github.com/logancyang/obsidian-copilot)
- [Copilot 文档](https://github.com/logancyang/obsidian-copilot#readme)
- [Obsidian 论坛](https://forum.obsidian.md/)

## 解决状态

✅ 已创建故障排除笔记，等待用户执行方案 1 或 2

---

*最后更新：2026-05-09*
