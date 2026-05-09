---
title: "普通人 7 天上手 Claude Code + Obsidian 完整指南"
source: "https://www.toutiao.com/article/7637052949411217971/?app=news_article&category_new=__all__&module_name=Android_tt_others&share_did=MS4wLjACAAAA4s8tyKo3vQ8l9K2znbW_td8vBPh-C0c751f2bJTSEPk&share_uid=MS4wLjABAAAAMcptXTTTfsCbC1WtKjznhRvLVGBpw3RgCpA45NHJO9U&timestamp=1778301548&tt_from=wechat&upstream_biz=Android_wechat&utm_campaign=client_share&utm_medium=toutiao_android&utm_source=wechat&share_token=efa8de94-6e9f-4b43-8972-17a1cda38211&source=m_redirect"
author:
  - "[[乐心的AI进化笔记]]"
published: 2026-05-08
created: 2026-05-09
description: "这份指南解决一个问题：** 你听说过 Claude Code 和 Obsidian，你知道它们很强大，但你不知道从哪里开始，也不知道它们加在一起到底能做什么。7 天后，你会有一个真正能用的 AI 知识库，以及一套让 AI 帮你整理信息、写内"
tags:
  - "clippings"
---
作品声明：个人观点、仅供参考

这份指南解决一个问题：\*\* 你听说过 Claude Code 和 Obsidian，你知道它们很强大，但你不知道从哪里开始，也不知道它们加在一起到底能做什么。

> 7 天后，你会有一个真正能用的 AI 知识库，以及一套让 AI 帮你整理信息、写内容、管理工作的工作流。

---

![](https://p3-sign.toutiaoimg.com/tos-cn-i-axegupay5k/a2b0805d05eb4e0b87c26d14577e0097~tplv-tt-origin-web:gif.jpeg?_iz=58558&from=article.pc_detail&lk3s=953192f4&x-expires=1778912853&x-signature=J5BJ78twtr6tfFEBRsbH3m82qp0%3D)

## 在开始之前：你需要知道的一件事

这个组合的核心逻辑只有一句话：

> Obsidian 是你的大脑，Claude Code 是你的助理。

Obsidian 存放你所有的知识、想法、项目记录。Claude Code 负责帮你整理、提取、写作、自动化——而且它就运行在你的电脑上，直接操作你的文件，没有任何中间层。

你不需要会编程。你需要的只是：能打开终端，能复制粘贴命令。

---

## Day 1 · 理解工具，安装 Obsidian

**今天的目标：** 装好 Obsidian，写下你的第一篇 Markdown 笔记

**预计时间：** 1-2 小时

---

## 为什么选 Obsidian，而不是 Notion 或 Word？

这是很多人第一个问题。简单说三点：

1. **数据完全在你电脑上。** 纯 Markdown 文件，不依赖任何云服务。Notion 哪天倒了，你的笔记就没了；Obsidian 的文件永远是你的。
2. **AI 能直接读懂它。** Markdown 是大模型最友好的格式。你的 Obsidian 笔记，Claude 可以直接读取和修改，不需要任何转换。
3. **双向链接 + 知识图谱。** 用 \[\[笔记名\]\] 就能把两篇笔记连起来，形成知识网络。这是 Word 和 Notion 做不到的。

---

## Markdown 速成：你只需要掌握这些

```markdown
# 一级标题（文章主标题）
## 二级标题（章节）
### 三级标题（小节）

**加粗**
*斜体*

- 无序列表项
- 无序列表项

1. 有序列表
2. 有序列表

> 引用一段话

[[另一篇笔记的名字]]   ← Obsidian 专有，双向链接
```

就这些。上手 10 分钟就记住了。

---

## 安装步骤

**Windows：**

1. 访问 https://obsidian.md/download 下载安装包
2. 双击安装，选「是」允许权限
3. 选择安装路径，等待完成

**Mac：**

1. 访问 https://obsidian.md/download 点击下载
2. 打开 DMG 文件，把 Obsidian 拖入 Applications 文件夹
3. 从启动台打开

---

## 创建你的第一个仓库

打开 Obsidian 后，点击「创建」新建一个仓库（Vault）。

> 命名建议： 用英文，比如 my-vault 或 second-brain。中文路径有时候会出问题。

**今日作业：** 在 Obsidian 里新建一篇笔记，写下：「我为什么开始用 AI 工具」。练习用 Markdown 排版，加几个标题和列表。

---

## Day 2 · 建立你的仓库结构

**今天的目标：** 下载 OrbitOS 模板，搭建有逻辑的知识库结构

**预计时间：** 1 小时

---

## 为什么需要一个结构？

一个没有结构的知识库，三个月后会变成一个垃圾堆。

你会有：随手记的想法、收藏的文章、进行中的项目、已经完成的工作、长期积累的知识——这些东西需要有不同的"家"。

---

## 推荐结构：OrbitOS 模板

OrbitOS 是一个专为「Claude Code + Obsidian」设计的仓库模板，主要目录如下：

```
00_收件箱/     ← 快速记录，先扔进来再整理
10_日记/       ← 每天的日志和计划
20_项目/       ← 正在推进的项目
30_研究/       ← 深度研究笔记
40_知识库/     ← 原子化的知识卡片
50_资源/       ← 收藏的文章、工具
90_收藏箱/     ← 浏览器剪藏、外部内容
99_系统/       ← 模板和系统配置
```

---

## 下载和安装

**方法一（Mac/终端）：**  
打开终端，进入你想存放仓库的目录，运行：

```nginx
npx degit MarsWang42/OrbitOS/CN my-vault
```

**方法二（Windows/直接下载）：**

1. 访问 https://github.com/MarsWang42/OrbitOS
2. 点击绿色「Code」按钮 → Download ZIP
3. 解压后，把 CN 目录重命名为你想要的名字（推荐英文）

下载完成后，在 Obsidian 里「打开文件夹作为仓库」，选择这个目录。

**今日作业：** 打开下载好的仓库，浏览每个目录，理解每个文件夹的用途。然后在 00\_收件箱/ 里新建一篇笔记，记录你今天最想解决的一个问题。

---

## Day 3 · 安装 Claude Code，让 AI 进入你的电脑

**今天的目标：** 安装 Claude Code，第一次用 AI 操作你的文件

**预计时间：** 1-2 小时（主要是等待安装）

---

## Claude Code 是什么？

Claude Code 是 Anthropic 出的命令行工具。它不只是一个聊天机器人——它可以 **直接读取、创建、修改你电脑上的文件** 。

当你告诉它「帮我整理 Obsidian 里的所有笔记，按主题分类」，它真的会去翻你的文件，然后帮你做。

---

## 安装步骤

**第一步：安装 Node.js**  
访问 https://nodejs.org/，下载并安装 LTS 版本。

**第二步：安装 Claude Code**  
打开终端（Windows: PowerShell 或命令提示符，Mac: Terminal），运行：

```coffeescript
npm install -g @anthropic-ai/claude-code
```

**第三步：登录 Claude 账号**

```nginx
claude
```

第一次运行会提示你登录。按照提示完成授权。

---

## 第一次使用 Claude Code

进入你的 Obsidian 仓库目录：

```bash
cd /你的仓库路径/my-vault
claude
```

然后告诉它：

```
帮我在 00_收件箱 里新建一篇笔记，标题是「我的第一次 AI 协作」，
内容包含：今天的日期、我正在学习的工具名称、我希望用这个工具解决的问题
```

看着 AI 帮你创建文件。

**今日作业：** 用 Claude Code 帮你创建 3 篇不同的笔记，感受「用自然语言指挥 AI 操作文件」的体验。

---

## Day 4 · 安装 Claudian 插件，在 Obsidian 里直接对话

**今天的目标：** 把 AI 对话框嵌入 Obsidian 右侧，不再需要切换窗口

**预计时间：** 30 分钟

---

## 为什么需要 Claudian？

目前的方式是：打开终端 → 进入目录 → 运行 claude → 对话。

有了 Claudian 插件，你可以直接在 Obsidian 右侧的对话框里和 Claude Code 交流，看着 AI 修改你正在编辑的笔记，体验完全不同。

---

## 安装方式

打开终端，进入你的仓库目录，启动 Claude Code 的「无限制模式」：

```lua
claude --dangerously-skip-permissions
```

然后粘贴这句话：

```
https://github.com/YishenTu/claudian
这个是 Obsidian 的插件，帮我安装到当前目录的 vault 下
```

等待安装完成（大约 1-2 分钟）。

完成后重新打开 Obsidian，进入「设置 → 社区插件」，找到 Claudian， **打开开关** 。

---

## 测试是否成功

在 Obsidian 右侧栏你会看到一个对话框。输入「你好，你能看到我的仓库吗？」，如果 AI 能回答并提到你的文件，说明安装成功。

**今日作业：** 用 Claudian 对话框，让 AI 帮你整理今天写的笔记，按照 Markdown 规范重新排版。

---

## Day 5 · 安装 Skills，激活内置工作流

**今天的目标：** 安装 obsidian-skills，用 /start-my-day 开启第一次 AI 日规划

**预计时间：** 30 分钟

---

## Skills 是什么？

Skills 是预设的 AI 工作流，每个 Skill 就是一个「指令包」。

比如 /start-my-day 这个 Skill，AI 会自动：

- 读取昨天的日记，找出未完成的任务
- 查看你的活跃项目状态
- 搜集今日 AI 资讯
- 创建今天的日记，填好待办事项

你只需要说一句 /start-my-day，其他的 AI 帮你做。

---

## 安装步骤

在 Claudian 对话框里粘贴：

```
https://github.com/kepano/obsidian-skills
这个下面的 skills 帮我安装到这个项目下
```

等待安装完成。

---

## 试用 /start-my-day

安装完成后，在 Claudian 对话框输入：

```sql
/start-my-day
```

AI 会开始读取你的仓库，然后创建今天的日记。

> 注意： 第一次可能会问你今天的目标是什么，直接用文字回答就行，不需要选择题。

**今日作业：** 用 /start-my-day 创建今天的日记，然后在日记里记录你今天的学习感受。

---

## Day 6 · 建立收藏系统，让信息自动流进知识库

**今天的目标：** 安装网页剪藏工具，把第一篇文章剪藏进 Obsidian

**预计时间：** 1 小时

---

## 信息收藏的三个来源

1. **网页文章** → 用 Obsidian Web Clipper（Chrome 浏览器插件）
2. **微信公众号文章** → 用 NotionMpClipper 小程序 + Obsidian 插件
3. **推特/X** → 手动剪藏，或用浏览器插件

---

## 安装 Obsidian Web Clipper

1. 打开 Chrome 扩展商店，搜索「Obsidian Web Clipper」
2. 点击安装
3. 在插件设置里，把默认保存目录改为 90\_收藏箱/网页剪藏

**使用方式：**  
打开任何网页，点击 Chrome 右上角的插件图标，点击「Add to Obsidian」，文章就会保存到 Obsidian。

---

## 用 AI 处理剪藏内容

剪藏进来的文章是原始格式。用 Claude Code 来提取精华：

在 Claudian 对话框输入：

```coffeescript
@90_收藏箱/网页剪藏/刚剪藏的文章名.md
帮我从这篇文章里提取3个核心观点，每个观点写成一张原子卡片，
保存到 40_知识库/ 目录下
```

**今日作业：** 剪藏一篇你觉得有价值的文章，用 AI 提取核心观点，保存为知识卡片。

---

## Day 7 · 把一切串联起来，设计你的日常工作流

**今天的目标：** 建立个人的 AI 工作 SOP，开始真正使用这个系统

**预计时间：** 2 小时

---

## 你的标准工作流（建议）

**每天早上（15分钟）：**

1. 打开 Obsidian
2. 在 Claudian 输入 /start-my-day
3. AI 自动生成今日日记，检查昨日未完成任务
4. 确认今天的 3 件优先事项

**工作过程中（随时）：**

- 有想法 → 发到 00\_收件箱/（可以对 AI 说「帮我记一条想法：……」）
- 看到好文章 → 浏览器插件一键剪藏
- 需要整理 → 让 AI 帮你分类、提取、写成卡片

**每天结束前（10分钟）：**

- 在当天日记里记录：今天完成了什么，明天继续什么
- AI 会在明天的 /start-my-day 里帮你带入未完成任务

---

## 进阶玩法（掌握基础后再探索）

**内容创作工作流：**  
安装 baoyu-skills 后，可以用 /rewritepost 命令，给一个文章链接，AI 自动生成三种风格的改写版本（娓娓道来、犀利点评、故事叙述），每篇还能配上 AI 生成的图片。

```coffeescript
/rewritepost https://你想改写的文章链接
```

**公众号一键发布：**  
把文章写好后，AI 可以直接帮你发到微信公众号草稿箱：

```python
@你的文章.md 这篇文章发送到公众号草稿箱
```

**Canvas 知识图谱：**  
当你积累了足够多的知识卡片后，可以让 AI 帮你画一张可视化的知识地图：

```
帮我把 40_知识库/ 里关于 AI 工具的笔记，画成一张 canvas 知识图谱
```

---

## 今日作业：写下你的个人 SOP

在 99\_系统/ 目录下新建一篇笔记，标题「我的 AI 工作 SOP」，写下：

- 我每天早上用 AI 做什么（5分钟内）
- 我处理新信息的流程是什么
- 我用 AI 帮我做哪些重复性工作

这份 SOP 会随着你的使用不断进化。

---

## 七天总结

| 天数 | 完成的事 | 你获得的能力 |
| --- | --- | --- |
| Day 1 | 安装 Obsidian，写第一篇 Markdown 笔记 | 用结构化方式记笔记 |
| Day 2 | 下载 OrbitOS 模板，建立仓库结构 | 有逻辑地组织信息 |
| Day 3 | 安装 Claude Code，用 AI 操作文件 | 用自然语言指挥 AI |
| Day 4 | 安装 Claudian 插件，在 Obsidian 内对话 | AI 嵌入工作环境 |
| Day 5 | 安装 Skills，用  /start-my-day | AI 自动化日常规划 |
| Day 6 | 安装剪藏工具，第一篇文章变知识卡片 | 信息自动流入知识库 |
| Day 7 | 建立个人 SOP，串联所有工具 | 拥有完整 AI 工作系统 |

---

## 常见问题

**Q：我不会用终端，怎么办？**  
A：终端只需要你会「复制粘贴命令」和「按回车」。本指南的每条命令都可以直接复制，不需要理解原理。

**Q：Claude Code 要付费吗？**  
A：Claude Code 本身免费，但需要 Anthropic 账号，会消耗 API Token。个人使用每月几十元以内。

**Q：Obsidian 免费吗？**  
A：个人使用完全免费。只有官方云同步（Sync）是付费的，但你可以用 iCloud 或 OneDrive 免费同步。

**Q：Windows 和 Mac 的步骤一样吗？**  
A：大部分一样。主要区别是：Windows 用 PowerShell 代替终端；Mac 安装软件方式略有不同。本指南在关键步骤都有区分说明。

**Q：我的笔记会被 AI 看到吗？安全吗？**  
A：Claude Code 运行在本地，你的文件内容会在对话时发送给 Claude API 处理，但 Anthropic 声明不会用这些数据训练模型。如果你有高度敏感的内容，不要让 AI 读取那些文件就好。

---

## 下一步

七天只是开始。真正的价值在于：

- 你开始 **持续使用** ，让知识库慢慢积累
- 你开始 **自定义 Skills** ，创造符合自己工作流的 AI 指令
- 你开始 **用这套系统工作、创作、赚钱**

如果你完成了这七天，欢迎在评论区告诉我你搭好了什么。

---

作者：乐心的AI进化笔记 · 2026年5月  
本指南基于实际使用经验整理，所有工具均已亲测可用