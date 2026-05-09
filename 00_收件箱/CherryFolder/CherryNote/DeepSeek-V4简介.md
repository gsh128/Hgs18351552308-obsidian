---
title: DeepSeek-V4简介
created: 2026-04-24
source: Cherry Studio
tags:
---
## 🤖 DeepSeek Chat | 深度求索

我来抓取这个URL的内容。

以下是页面内容已成功提取并整理如下：

---

# [[DeepSeek-V4 预览版：迈入百万上下文普惠时代]]

**发布日期：2026/04/24**

今天，全新系列模型 **DeepSeek-V4** 的预览版本正式上线并同步开源。

DeepSeek-V4 拥有**百万字超长上下文**，在 Agent 能力、世界知识和推理性能上均实现国内与开源领域的领先。模型按大小分为两个版本：

---

## DeepSeek-V4-Pro：性能比肩顶级闭源模型

- **Agent 能力大幅提高**：Agentic Coding 评测中达到开源模型最佳水平，使用体验优于 Sonnet 4.5，交付质量接近 Opus 4.6 非思考模式。
- **丰富的世界知识**：大幅领先其他开源模型，仅稍逊于 Gemini-Pro-3.1。
- **世界顶级推理性能**：在数学、STEM、竞赛型代码测评中超越当前所有开源模型。

---

## DeepSeek-V4-Flash：更快捷高效的经济之选

- 世界知识储备稍逊于 Pro 版，但推理能力接近。
- 因模型参数和激活更小，能提供更快捷、经济的 API 服务。
- 在简单 Agent 任务上与 Pro 旗鼓相当，高难度任务上仍有差距。

---

## 结构创新和超高上下文效率

V4 开创了全新注意力机制，在 token 维度进行压缩，结合 **DSA 稀疏注意力（DeepSeek Sparse Attention）**，实现了全球领先的长上下文能力，大幅降低了对计算和显存的需求。**1M（一百万）上下文将成为 DeepSeek 所有官方服务的标配。**

---

## Agent 能力专项优化

针对 Claude Code、OpenClaw、OpenCode、CodeBuddy 等主流 Agent 产品进行了适配和优化。

---

## API 访问

- **模型名**：`deepseek-v4-pro` 或 `deepseek-v4-flash`
- **接口**：支持 OpenAI ChatCompletions 接口与 Anthropic 接口
- **base_url** 不变
- **最大上下文长度**：1M
- 支持**非思考模式**与**思考模式**，思考模式支持 `reasoning_effort` 参数（high/max）
- **⚠️ 注意**：旧模型名 `deepseek-chat` 和 `deepseek-reasoner` 将于 **2026-07-24** 停止使用，当前阶段分别指向 `deepseek-v4-flash` 的非思考模式与思考模式。

---








## 开源权重和本地部署

- Hugging Face：https://huggingface.co/collections/deepseek-ai/deepseek-v4
- ModelScope：https://modelscope.cn/collections/deepseek-ai/DeepSeek-V4
- 技术报告：https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro/blob/main/DeepSeek_V4.pdf

---

> **「不诱于誉，不恐于诽，率道而行，端然正己。」**



