---
type: memo
created: 2026-05-19
tags: [hermes, ccx, wsl, 开机启动]
---

# Hermes & CCX 开机启动备忘

> 前提：开机后先打开 PowerShell，输入 `wsl` 回车进入 WSL 环境。

---

## CCX 启动（API 代理网关）

```bash
# 一步到位
ccx-ctl restart
```

- Web 管理面板 → http://localhost:3000
- 健康检查 → http://localhost:3000/health

---

## Hermes 启动

### 方式一：CLI 模式（常用）

```bash
hermes
```

### 方式二：Web UI 模式（后台常驻）

```bash
# 快捷方式（别名）
hermes-start

# 或完整命令
cd ~/hermes-webui && nohup python3 bootstrap.py > hermes.log 2>&1 &
```

- 访问 → http://localhost:8787

---

## 快速检查

| 检查项 | 命令 |
|--------|------|
| CCX 是否运行 | `curl http://localhost:3000/health` |
| Hermes 是否运行 | `ps aux \| grep hermes` |
| 退出 WSL | `exit` |

> 💡 关闭 WSL 终端后，CCX 和 Hermes Web UI 会继续后台运行（nohup），浏览器访问不受影响。
