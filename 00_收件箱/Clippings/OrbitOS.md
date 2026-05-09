---
title: "MarsWang42/OrbitOS: An AI-powered personal productivity system where knowledge management and daily task planning are intelligently orchestrated by your AI assistant."
source: "https://github.com/MarsWang42/OrbitOS"
author:
published:
created: 2026-05-09
description: "An AI-powered personal productivity system where knowledge management and daily task planning are intelligently orchestrated by your AI assistant. - MarsWang42/OrbitOS"
tags:
  - "clippings"
---
## OrbitOS

英文 | [中文](https://github.com/MarsWang42/OrbitOS/blob/main/README_CN.md)

> 一个 **由人工智能驱动** 的个人生产力系统，知识 **管理和** **日常任务规划** 由你的AI助手智能地协调。

## 安装

**选项1：Git Sparse Checkout** （仅下载英文版）

```
git clone --filter=blob:none --sparse https://github.com/MarsWang42/OrbitOS.git my-vault
cd my-vault
git sparse-checkout set EN
mv EN/* EN/.* . 2>/dev/null; rmdir EN
```

**选项二：使用 Degit** （无 git 历史，更简单）

```
npx degit MarsWang42/OrbitOS/EN my-vault
```

---

## 什么是OrbitOS？

OrbitOS是一个基于Obsidian的生产力框架，围绕一个简单的原则设计： **一切都围绕着你旋转** 。你的项目、知识和日常任务都保持动态和连接——所有这些都通过与AI的自然语言对话来管理。

与需要手动整理的传统笔记系统不同，OrbitOS利用 **Claude Code** 或 **Gemini CLI** 作为您的智能知识管理器和每日计划工具。人工智能不仅存储你的信息——它会积极帮助你：

- **捕捉想法** 并将其转化为有结构、可执行的项目
- 根据你当前的工作情况， **规划你的一天**
- **研究主题** ，并自动将发现整理到你的知识库中
- 通过智能维基链接连接笔记、项目和概念
- **归档并清理** 已完成的工作，保持系统精简和专注

## 主要特征

### AI驱动工作流程

每一个主要工作流程都通过简单的斜杠命令启动，AI负责繁重的工作：

| 工作流程 | AI的功能 |
| --- | --- |
| **日常计划** | 查看昨天的进展，显示正在进行的项目，推荐重点领域，处理收件箱中的项目 |
| **项目创建** | 将粗略的想法转化为带有目标、阶段和成功指标的结构化项目 |
| **研究** | 进行深入分析，构建发现，创建原子维基条目，建立知识联系 |
| **知识解析** | 它会把无结构文本整理到你的保险库里，并进行适当的分类和链接 |
| **档案** | 识别已完成的项目并将其移至档案馆，同时保留历史背景 |

### 智能知识图谱

OrbitOS 广泛使用维基链接来构建连接的知识图谱：

- **项目** 链接至相关 **研究** 笔记以提供背景和参考
- **每日记录** 你每天参与的项目链接
- **维基条目** 是可以从任何地方引用的原子概念
- **研究笔记** 综合信息并链接到源头概念

AI在你工作时会自动建立这些联系，随着时间推移构建知识网络。

### 结构化却灵活

文件夹结构提供了清晰的组织，同时保持灵活：

```
├── 00_Inbox/          # Quick captures — the AI processes these into proper locations
├── 10_Daily/          # Daily logs (YYYY-MM-DD.md) — AI-generated each morning
├── 20_Project/        # Active projects — AI helps create and track progress
├── 30_Research/       # Deep research notes — AI-structured from your explorations
├── 40_Wiki/           # Atomic concepts — AI extracts reusable definitions
├── 50_Resources/      # Curated content — newsletters, product launches, references
├── 90_Plans/          # Execution plans — AI drafts, you approve, then archived
└── 99_System/         # System configuration
    ├── Archives/      # Historical records (organized by year/month)
    ├── Prompts/       # AI personas for different domains
    └── Templates/     # Markdown templates for consistency
```

---

## 入门指南

### 前提条件

1. **安装Obsidian** — [下载](https://obsidian.md/download) （macOS，Windows，Linux）
2. **安装AI助手** （选择一个）：
	- **Claude Code** — （ [文档）](https://docs.anthropic.com/en/docs/claude-code) `npm install -g @anthropic-ai/claude-code`)
		- **Gemini CLI** — （ [文档）](https://github.com/google-gemini/gemini-cli) `npm install -g @google/gemini-cli`)
3. 在Obsidian里打开vault文件夹，从同一个目录运行你的AI助手
4. **推荐：** 安装 [Terminal插件](https://github.com/polyipseity/obsidian-terminal) ，直接在Obsidian中运行Claude Code——这能提供无缝体验，无需切换应用

### 你的第一天

1. **捕捉你的第一个想法** ：在 。 `00_Inbox/`
	- 只要写下你想探索的想法、项目的想法
		- 不用担心格式——AI以后会帮你整理
2. **开始你的一天** ：让你的AI助手上场 `/start-my-day`
	- AI会扫描你的收件箱和表面邮件进行处理
		- 审查任何正在进行的项目（第一天就没问题，这没关系！）
		- 每天生成一份包含建议的笔记
3. **启动一个项目** ：运行将收件箱项目转换为项目 `/kickoff`
	- AI会制定计划并提出澄清问题
		- 创建具有目标、阶段和成功指标的结构化项目
4. **做些研究：** 跑 `/research <topic>`
	- 人工智能进行了彻底的调查
		- 创建结构化笔记 `30_Research/`
		- 将原子概念提取为 `40_Wiki/`
		- 自动把所有东西串联起来
5. **问个快速问题** ：跑 `/ask <question>`
	- 在不做繁琐文档的情况下，获得直接的答案
		- 也可以选择性地把有用的发现保存到你的维基

---

## 命令参考

### 核心工作流程

| 指挥 | 目的 | 使用时机 |
| --- | --- | --- |
| `/start-my-day` | AI引导的每日计划与复习 | 每天早上来定下你的注意力 |
| `/kickoff` | 将想法转化为结构化项目 | 启动任何新项目 |
| `/research` | 深度分析，自动构建知识 | 全面学习某件事 |
| `/ask` | 快速回答，无需大量笔记 | 简单的问题，事实查询 |
| `/brainstorm` | 互动式创意探索 | 概念的发展与完善 |
| `/parse-knowledge` | 将无结构文本结构化为vault | 处理笔记、文章、会议记录 |
| `/archive` | 清理已完成的物品 | 定期维护，项目完成 |

### 黑曜石特有特征

| 技能 | 目的 |
| --- | --- |
| `obsidian-markdown` | 维基链接、注解、嵌入和Obsidian风格语法 |
| `obsidian-bases` | 创建带有过滤器和公式的数据库视图（.base 文件） |
| `json-canvas` | 可视化思维导图和流程图（.canvas文件） |

### 内容策划（可选）

| 指挥 | 目的 |
| --- | --- |
| `/ai-newsletters` | 策划和总结AI通讯（简而言之：AI，The Rundown AI） |
| `/ai-products` | 在Product Hunt、HN、GitHub、Reddit上发现AI产品发布 |

---

## 项目概念

### C.A.P. 项目布局

每个项目都遵循一个统一的结构：

- **背景** ：我们想实现什么？成功是什么样子？
- **行动** ：分阶段完成任务清单
- **进展** ：带时间戳的更新链接每日笔记

### 维基链接与关联

OrbitOS 高度依赖 Obsidian 的 wikilink 语法：

```
[[NoteName]]                  # Basic link
[[NoteName|Display Text]]     # Custom display text
![[NoteName]]                 # Embed entire note
![[NoteName#Section]]         # Embed specific section
```

AI会自动创建这些链接，但你也应该大量链接——连接创造价值。

### 作为主播的每日笔记

每日笔记（）作为你的核心锚点： `10_Daily/YYYY-MM-DD.md`

- 每次项目更新都会提到工作发生的每日记录
- 收件箱的项目会根据每日笔记处理并链接
- 工作流程会自动生成这些信息 `/start-my-day`

---

## 理念

OrbitOS 基于以下原则构建：

1. **AI作为合作伙伴** ：AI不仅仅是工具——它是一个积极的协作者，理解你的系统并帮助维护它
2. **全部记录，后处理** ：收件箱存在，让你永远不会丢失任何想法;AI帮你处理事情，准备好了
3. 连接 **优先于类别** ：僵化的文件夹层级结构失效;维基链接创建灵活且可查询的知识图谱
4. **每日节奏** ：每日笔记锚定一切，形成你工作和思考的时间线
5. **渐进形式化** ：想法起初粗糙，随着AI辅助的完善逐渐形成结构化