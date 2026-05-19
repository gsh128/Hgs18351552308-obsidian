# Obsidian中git常用命令

## 常用命令

| 原文 | 翻译 | 解释 |
|------|------|------|
| Git: Pull | Git：拉取 | 从远程仓库拉取最新代码并合并到当前分支 |
| Git: Push | Git：推送 | 将本地提交推送到远程仓库 |
| Git: Fetch | Git：获取 | 只拉取远程更新但不合并 |
| Git: Commit | Git：提交 | 提交已暂存的更改到本地仓库 |
| Git: Raw command | Git：原始命令 | 手动输入任意 Git 命令 |
| Git: Amend staged | Git：修改上次提交 | 将已暂存的更改合并到上一次提交中 |
| Git: Edit remotes | Git：编辑远程仓库 | 修改远程仓库地址或名称 |
| Git: Delete branch | Git：删除分支 | 删除本地分支 |
| Git: Remove remote | Git：移除远程仓库 | 删除关联的远程仓库配置 |
| Git: Switch branch | Git：切换分支 | 切换到另一个已有分支 |
| Git: Commit-and-sync | Git：提交并同步 | 提交后立即拉取并推送（相当于 commit + pull + push） |

## 进阶/管理命令

| 原文 | 翻译 | 解释 |
|------|------|------|
| Git: Edit .gitignore | Git：编辑忽略文件 | 编辑 `.gitignore` 配置文件 |
| Git: Create new branch | Git：新建分支 | 基于当前分支创建新分支 |
| Git: Open history view | Git：打开历史视图 | 查看提交日志、文件变更等 |
| Git: Commit all changes | Git：提交所有更改 | 自动暂存并提交所有修改 |
| Git: List changed files | Git：列出变更文件 | 显示当前工作区中有哪些文件被修改 |
| Git: Set upstream branch | Git：设置上游分支 | 建立本地分支与远程分支的追踪关系 |
| Git: Initialize a new repo | Git：初始化新仓库 | 在当前目录创建新的 Git 仓库 |
| Git: Switch to remote branch | Git：切换到远程分支 | 拉取并切换到远程分支的本地副本 |
| Git: Open source control view | Git：打开源代码管理视图 | 打开 Git 管理界面（类似 IDE 中的侧边栏） |
| Git: CAUTION: Delete repository | Git：⚠️ 删除仓库（谨慎） | 彻底删除 Git 仓库及历史记录（不可逆） |
| Git: CAUTION: Discard all changes | Git：⚠️ 丢弃所有更改（谨慎） | 回退所有未提交的修改（不可恢复） |
| Git: Commit with specific message | Git：输入提交信息并提交 | 提交时要求输入提交说明 |
| Git: Clone an existing remote repo | Git：克隆现有远程仓库 | 复制一个远程仓库到本地 |
| Git: Toggle line author information | Git：切换行作者信息 | 显示或隐藏每行代码的提交作者（如 Git Blame） |
| Git: Pause/Resume automatic routines | Git：暂停/恢复自动任务 | 控制后台自动拉取、刷新等行为 |
| Git: Commit-and-sync with specific message | Git：提交并同步（带信息） | 提交输入信息，然后同步 |
| Git: Commit-and-sync and then close Obsidian | Git：提交并同步后关闭 Obsidian | 执行 commit-and-sync 完成后退出 Obsidian |
| Git: Commit all changes with specific message | Git：提交所有更改（带信息） | 输入信息后提交所有修改 |

---

> ⚠️ 带 `CAUTION:` 的命令不可逆转，使用时务必小心。  
> 📘 这些命令常见于 Obsidian 的 Git 插件（如 Obsidian Git）或 VS Code 的 Git 命令面板。