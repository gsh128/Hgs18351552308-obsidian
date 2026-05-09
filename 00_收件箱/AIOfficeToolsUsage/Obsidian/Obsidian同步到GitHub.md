# Obsidian 同步到 GitHub 完整指南

## 前置准备

- 安装 [Git](https://git-scm.com/download/win)
- 注册 [GitHub](https://github.com) 账号
- 在 GitHub 上创建一个**空仓库**（不要勾选 README、.gitignore）

---

## 一、首次设置 — 本地已有文件，推送到 GitHub

适用于：本地已有 Obsidian 笔记文件夹，想把它推送到 GitHub 远程仓库。

### 1. 打开终端

在 Obsidian 笔记文件夹中右键 → **Git Bash Here**，或打开 PowerShell 进入该目录：

```powershell
cd "你的笔记文件夹路径"
```

### 2. 初始化 Git 仓库

```bash
git init
```

### 3. 添加所有文件并提交

```bash
git add -A
git commit -m "初始提交"
```

### 4. 连接远程仓库

```bash
git remote add origin https://github.com/你的用户名/仓库名.git
```

### 5. 重命名分支为 main（如果需要）

```bash
git branch -M main
```

### 6. 推送到 GitHub

```bash
git push -u origin main
```

#### 认证方式

推送时会要求输入用户名和密码。**密码不是 GitHub 登录密码**，需要用 Personal Access Token：

1. GitHub 右上角头像 → Settings → Developer settings → Personal access tokens → Tokens (classic)
2. Generate new token → 勾选 `repo` → 生成后复制
3. 用户名填 GitHub 用户名，密码填 Token

#### 免密认证（推荐）

```bash
git config --global credential.helper manager
```

第一次输入后，Windows 会自动保存凭据，后续无需再输。

---

## 二、日常同步工作流

### 开始工作前 — 拉取远程更新

```bash
git pull origin main
```

### 编辑笔记后 — 提交并推送

```bash
git add -A
git commit -m "备份: 2026-04-30"
git push origin main
```

### 三步合一（简单版）

```bash
git add -A && git commit -m "备份: $(date '+%Y-%m-%d %H:%M')" && git push origin main
```

---

## 三、使用 Obsidian Git 插件自动同步

在 Obsidian 社区插件中搜索安装 **Obsidian Git**，配置如下：

- **Auto pull on boot**: 开启（打开 Obsidian 时自动拉取）
- **Auto backup after file change**: 开启（文件改动后自动备份）
- **Auto push interval**: 0（手动推送）或设置分钟数

---

## 四、常见问题处理

### 问题 1：`destination path already exists and is not an empty directory`

**原因**：目录已存在且非空，git clone 无法执行。

**解决**（以本地文件为准）：

```bash
cd 目录名
git init
git add -A
git commit -m "初始提交"
git remote add origin <仓库URL>
git branch -M main
git pull origin main --allow-unrelated-histories -X ours
git push -u origin main
```

### 问题 2：推送被拒 `GH013: Repository rule violations`

**原因**：提交的文件中包含明文 Token 或密钥，GitHub Push Protection 拦截。

**解决**：

```bash
# 从所有历史提交中移除敏感信息（将 <TOKEN> 替换为实际要清除的内容）
git filter-branch -f --tree-filter "grep -rl '<TOKEN>' . | xargs -r sed -i 's/<TOKEN>/<占位符>/g'" -- --all

# 强制推送重写后的历史
git push -u origin main --force
```

> **重要**：推送后立即到 GitHub Settings 撤销泄露的 Token，重新生成一个新的。

### 问题 3：`failed to push, remote contains work that you do not have locally`

**原因**：远程有本地没有的提交。

**解决**：

```bash
git pull origin main --rebase
git push origin main
```

### 问题 4：换电脑后如何在新设备上同步

```bash
git clone https://github.com/你的用户名/仓库名.git "你的Obsidian笔记文件夹"
```

---

## 五、常用命令速查

| 操作 | 命令 |
|------|------|
| 查看状态 | `git status` |
| 查看远程地址 | `git remote -v` |
| 查看提交历史 | `git log --oneline -10` |
| 撤销未提交的修改 | `git checkout -- 文件名` |
| 撤销 git add | `git reset HEAD 文件名` |
| 查看文件差异 | `git diff` |
