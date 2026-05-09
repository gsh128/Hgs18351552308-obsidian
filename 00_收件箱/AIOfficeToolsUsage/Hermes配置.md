# Hermes配置

## 安装运行WSL 

以管理员身份打开 PowerShell，逐条复制运行：

```powershell       
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```


```powershell       
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

执行完上面两条，必须重启电脑。 

重启后，安装 Ubuntu
```powershell
wsl --install -d Ubuntu
```

## 进入 WSL 终端

- 第一步：确认你的发行版（比如 Ubuntu）是否已安装 
1. 在左侧菜单栏，点击 发行版管理 
2. 在这里你可以看到已安装的 Linux 发行版（比如 Ubuntu、Debian 等） 
	- 如果列表里有 Ubuntu，说明已经装好了，直接跳到第二步 
	- 如果列表是空的，需要先安装一个发行版（推荐 Ubuntu）      
- 第二步：用最简单的方法打开 WSL 终端 这里给你三种最直接的方式，按推荐顺序来： 
	- 方法 1：开始菜单直接打开（最推荐） 
		- 点击 Windows 左下角的开始菜单 
		- 在搜索框输入 Ubuntu 
		- 点击搜索结果里的 Ubuntu 图标，就会自动弹出 WSL 终端窗口  
	- 方法 2：在 PowerShell 里输入命令 
		- 打开普通的 PowerShell（不用管理员权限）
		- 直接输入下面的命令，回车：

```powershell
 wsl
```

它会直接进入默认的 Linux 发行版终端。


## 一步到位：WSL 直接安装 Node.js 22.13.1
复制下面整段命令，粘贴到 WSL 里运行： 
```bash
sudo apt remove -y nodejs
curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt install -y nodejs
```


验证是否成功

```bash
node -v
```

只要输出 v22.13.1 就搞定 ✅

中间要输入wsl中设置的密码，若忘记比较麻烦(我本的是18351552308))

## 安装（一行命令）hermes

### 1）macOS / Linux / WSL2（推荐）

bash```
```
# 官方原版
curl -fsSL https://raw.githubusercontent.com/NousResearch/hermes-agent/main/scripts/install.sh | bash

# 国内加速（推荐，更快）
curl -fsSL https://res1.hermesagent.org.cn/install.sh | bash

# 刷新环境变量（二选一）
source ~/.bashrc
# 或
source ~/.zshrc
```

## hermes模型配置
虽然配置了 DeepSeek，但 Hermes 还是默认切回了 claude-opus-4.6，而且没有对应的 Anthropic Key，所以模型没配置成功，导致你感觉 "没配置过来"。下面给你两个解决办法

---

## 📋 当前配置总览 (2026-04-28)

### 核心参数

| 配置项 | 当前值 |
|--------|--------|
| 默认模型 | `deepseek-v4-pro` |
| 提供商 | DeepSeek |
| API Key | Anthropic `sk-c...29a2` （已设置） |
| 最大轮次 | 90 轮 |
| 终端超时 | 180s |
| 推理模式 | 关闭 |
| 人格 | `kawaii` ★ |
| 终端后端 | local |
| 上下文压缩 | 开启（阈值 50%，保留 20%） |

> ⚠️ 之前的 claude-opus-4.6 切回问题 **已解决** ✅ — 现在默认为 `deepseek-v4-pro`

### 关键路径

```
配置文件    →  ~/.hermes/config.yaml
密钥文件    →  ~/.hermes/.env
安装目录    →  ~/.hermes/hermes-agent
Session    →  ~/.hermes/sessions/
```

### 常用命令速查

| 命令 | 作用 |
|------|------|
| `hermes config` | 查看完整配置 |
| `hermes config edit` | 编辑配置文件 |
| `hermes model` | 切换模型/提供商 |
| `hermes setup` | 配置向导 |
| `hermes doctor` | 健康检查 |
| `hermes skills list` | 查看已安装技能 |
| `hermes tools` | 工具管理 (TUI 界面) |

### 可用人格

`helpful` · `concise` · `technical` · `creative` · `teacher` · `kawaii` · `catgirl` · `pirate` · `shakespeare` · `surfer` · `noir` · `uwu` · `philosopher` · `hype`

### Web UI

- 启动: `cd ~/hermes-webui && python3 bootstrap.py --no-browser`
- 访问: `http://localhost:8787`
- 工作区包括: `~/workspace` · `📓 Obsidian`

### 已开启的工具

- 文件读写、终端命令、浏览器、Python 执行
- 视觉分析、网页搜索
- 记忆存储、技能管理、Session 搜索
- 子代理委托、定时任务
- 语音转文字 (STT local)、文字转语音 (TTS Edge)


---
浏览器打开后不可关闭打开 的WSL 终端

## 解决方案：让服务后台运行（关闭终端也不中断）

给你两种最实用的方式，按需求选就行：

### 方案 1：最简单（临时后台运行）

启动时，在命令后面加个 `&`，再配合 `nohup`，就能让服务脱离终端运行：

```bash
# 先确保在项目目录 
cd /mnt/c/Users/huangs/hermes-webui 

# 后台启动服务（关闭终端也不会停） 

nohup python3 bootstrap.py > hermes.log 2>&1 &
```

- 执行完这行命令后，你就可以安全关闭 WSL 终端了
- 浏览器里的 `http://localhost:8787` 依然可以正常访问
- 日志会自动存在 `hermes.log` 文件里，方便排查问题

### 方案 2：一劳永逸（别名直接后台启动）

修改之前设置的别名，让它默认就后台运行，不用每次都敲命令：

- 在 WSL 终端里运行下面的命令，直接修改配置文件：

```bash
echo "alias hermes-start='cd /mnt/c/Users/huangs/hermes-webui && nohup python3 bootstrap.py > hermes.log 2>&1 &'" >> ~/.bashrc source ~/.bashrc
```

- 以后输入 `hermes-start`，服务会直接在后台启动，你可以直接关终端。

