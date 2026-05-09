---
aliases: [AI工具, AI使用]
category: AI工具
created: 2025-10-01
modified: 2026-04-04
tags: [AI工具, CherryStudio, MCP, 网页提取]
title: AI使用总结
type: learning
---
# Ai使用总结

## 一、日常使用模型

- **DeepSeek**
	- 2026年4月余额：92.24元
- **kimi**
	- 2026年4月余额：58.26元
- **智谱**
	-  2026年4月余额：5.80元
	- 资源包：
		- glm-4.5-air模型（赠送） 2026年4月余2,522,527 token
		- glm-4.7模型（付费） 2026年4月余68,978,721 tokens 
- **MiniMax**
	- 2026年4月代金券可用余额：15元
- **Cherry Studio**
	- 2026年4月余额：6.99美元
- **火山引擎**
	- 2026年4月余额：19.93元
- **硅基流动**
	- 2026年4月余额：9.97元
	- 开工福利券：
		- 剩余额度：16.5639元
		- 有效期至：2026-04-13 23:59:59
	- 开工福利券：
		- 剩余额度：18.0000元
		- 有效期至：2026-04-20 23:59:59
	- 认证奖励券：
		- 剩余额度：16.0000元
		- 有效期至：2026-09-10 23:59:59
- **ModelScope**
- **百灵大模型**
	- 2026年4月余额：10元  浪费不能调用

## 二、关于Ai的使用

### 1.obsidian中Ai插件

- **KHoj**
	- Khoj 是一个开源的个人人工智能 
	- 你可以和它聊任何话题。它会用你分享的文件回复，只要有需要。它还能访问公共互联网的信息。 
	- 快速利用自然语言查找相关笔记和文档 
	- 它支持PDF、纯文本、markdown、组织模式文件和Notion页面。 
	- 您可以通过您的Emacs、Obsidian、Khoj桌面应用或任何网页浏览器访问 
	- 使用我们的云实例随时随地访问您的Khoj，并在消费级硬件上自托管以保障隐私
- **Claudian**
- **Copilot**
- **Generate Text**
- **Smart composer chat**
### 2.Custom Frames中的Ai小程序

- **豆包**
- **千问**
- **Coze**
- **DeepSeek**

### 3.ima.copilot知识库

- **过程中对此知识库中的内容进行学习并应用！**
- **ima.copilot知识库**检索功能较强

## 三、CherryStudio中的MCP

### 1.@cherry/mcp-auto-install

- 自动安装 MCP 服务（测试版）
- 感受不到他的直接效果，没有启动使用

### 2.@cherry/filesystem

- 实现文件系统操作的模型上下文协议（MCP）的 Node.js 服务器
- 环境变量：`WORKSPACE_ROOT=目录路径地址（可选）`
- 如果没有配置环境变量，需要在模型对话的时候输入路径地址

- **复制的文件地址** D:\HgsFiles\Vs_Ob_TyFiles\OneFiles\Learn
- **MCP中输入的参数地址** D:/HgsFiles/Vs_Ob_TyFiles/OneFiles/Learn  
- **可用工具**：
	- **glob**这是一个快速找文件的工具，不管项目文件多还是少，都能飞快找到。 核心功能。 **glob = 按规则快速找文件 （总结）**
		- 规则简单：* 任意字、** 任意文件夹 
		- 不带 / 全项目找，带 / 指定文件夹找 
		- 返回最新修改的文件，最多 100 个 
		- 不填路径默认从项目根目录找
	- `ls`这就是个**列文件 / 文件夹的工具**，相当于你在电脑里打开文件夹看里面有啥，专门给 AI 用的版本。`s` = 给 AI 用的「文件夹内容查看器」
		- 能看当前 / 指定文件夹里的文件和文件夹
		- 自动过滤没用的文件夹和隐藏文件，最多列 100 个
		- 加参数能深入子文件夹，最多 5 层
		- 不填路径默认看项目根目录
	- `grep`这是一个**在文件内容里搜关键词 / 找文本的神器**，相当于你在整个项目里「全局搜索」，专门给 AI 用的增强版，不管项目多大都能飞快搜完。`grep` = 给 AI 用的「项目全局内容搜索器」
		- 搜的是文件里的文本，不是文件名
		- 支持正则，能做超级精准的复杂搜索
		- 自动过滤没用的文件，只给你有用的结果
		- 直接返回「文件 + 行号 + 内容」，定位问题超快
	- `read` 是一个**读取本地文件内容的工具**，相当于你用编辑器打开文件看内容，专门给 AI 用的版本，用来获取项目里文件的完整 / 部分内容。`read` = 给 AI 用的「文件阅读器」
		- 只能读项目内的文本文件，默认读前 2000 行
		- 支持自定义读取范围，带行号返回
		- 自动过滤二进制文件，安全可靠
	- `edit` 这是一个**精准修改文件内容的工具**，相当于你在编辑器里「精准替换指定文本」，是修改已有文件的首选安全工具，专门给 AI 用的版本。edit = 给 AI 用的「精准文件编辑器」
		- 只改指定内容，不碰其他部分，比 write 安全 100 倍
		- 必须先读再改，缩进严格对齐，避免格式错乱
		- 支持批量替换，适合修改已有代码 / 配置文件
	- `write` 是一个向本地文件系统写入文件的工具，**相当于你用编辑器「新建 / 覆盖保存文件」**，专门给 AI 用的版本，用来创建或修改项目内的文件。write = 给 AI 用的「文件写入器」 
		- 能新建文件，也能覆盖已有文件（高危，必须先读再写） 
		- 优先用 edit 改已有文件，禁止主动建文档 
		- 自动补全不存在的父目录，只允许操作项目内文件
		- **全量写入器（高危操作，谨慎使用）**
	- `delete` 是一个**删除文件 / 文件夹的高危工具**，相当于你在电脑里「永久删除文件」，删除后**无法撤销恢复**，是所有工具中风险最高的操作。`delete` = 给 AI 用的「永久删除工具」
		- 能删文件，也能删文件夹（非空文件夹必须加递归参数）
		- **删除不可逆，是最高危操作**，必须严格验证路径后再执行
**使用中**
### 3.filesystem+MCP -shell

- 对指定文件夹管理
- 功能等同@cherry/filesystem
- 操作文件路径D:/HgsFiles/Vs_Ob_TyFiles/OneFiles/Clippings
- hyper-mcp-shell 
	- 定位：MCP 服务器 → 连接 AI 客户端 ↔ 本地 Shell
- `@modelcontextprotocol/server-filesystem`：
	- **MCP 官方标准文件系统服务器**
	- 让 AI 读取 / 写入 / 列出你电脑上的文件
**使用中**

### 4.obsidian-mcp

[建睿通/黑曜石MCP：增强版黑曜石MCP服务器——25个高级AI工具](https://github.com/jianruidutong/obsidian-mcp)

Obsidian MCP服务器是一款强大的模型上下文协议（MCP）服务器，旨在实现AI模型与Obsidian知识库之间的无缝集成。提供25种强大的工具，用于智能知识管理、自动化内容分析和智能链接功能。
✨ 核心功能
	🔗 Obsidian 无缝集成：通过 MCP 协议直接访问 Obsidian 知识库
	📝 完整的笔记管理：通过高级文本替换功能阅读、创建、更新和删除笔记
	📁 文件夹操作：创建、重命名、移动和删除支持完整层级结构的文件夹
	🔍 智能搜索：涵盖所有文件类型的全文搜索，并支持智能评分
	🤖 人工智能分析：利用TF-IDF框架带来革命性的战略洞察
	🔗 自动反向链接生成：革命性的智能笔记名称检测及维基链接转换
	⚡ 精准编辑：高级PATCH操作，包含航向和区块级定位
	🚀 双API策略：结合Obsidian REST API与文件系统备份以实现最大可靠性
	🎯 上下文优化：用于大型语言模型上下文长度管理的智能内容摘要
	📊 批量处理：高效的批量操作并跟踪进度
✨ 新功能
	🧠 15个新的人工智能增强智能内容分析工具
	🔗 智能自动链接与先进模式识别
	📊 用于可视化笔记关系的知识图谱生成
	🏷️ 带智能建议的高级标签管理
	📝 用于一致创建笔记的模板系统
	🔍 使用TF-IDF和余弦相似度的内容相似性分析
	📈 发现隐藏联系的关系分析
🛠️ 完整工具套件（25个工具）
	📚 核心笔记管理（10个工具）
		📄 注释操作
		📁 文件夹与组织
	🏷️ 标签管理系统（3个工具）
	📝 模板系统（4个工具）
	🧠 人工智能内容分析（4个工具）
	📊 知识图谱与分析（4个工具）

### 5.@cherry/fetch

- 用于获取 URL 网页内容的 MCP 服务器
- `fetch_html` **人话翻译**：「帮我把这个网页的**原始HTML代码**完整抓下来给我」 
	 - 作用：获取网页最原始的源码，包含所有标签、样式、脚本，适合需要分析网页结构、提取完整页面信息的场景。
	 - 举个例子：你让AI分析某个网站的页面结构，它就用这个工具抓完整HTML源码。 
 - `fetch_markdown` **人话翻译**：「帮我把这个网页的内容，**转成干净的Markdown格式**给我」
	 - 作用：自动把网页里的广告、导航、冗余代码都去掉，只保留正文内容，并且转成Markdown（标题、列表、链接都保留格式），直接就能复制到笔记里用。
	 - 举个例子：你让AI把一篇公众号文章/博客文章转成Markdown笔记，就用这个工具。 
 - `fetch_txt` **人话翻译**：「帮我把这个网页的内容，**只提取纯文本**给我」
	 - 作用：把网页里所有格式都去掉，只留下纯文字内容，没有任何标签、样式、格式，适合只需要文字内容、不需要排版的场景。
	 - 举个例子：你让AI提取网页里的文字做摘要，就用这个工具抓纯文本。
  - `fetch_json` **人话翻译**：「帮我把这个URL里的**JSON数据**完整抓下来给我」
	  - 作用：专门用来获取接口返回的JSON数据（比如API接口、JSON文件），适合需要处理结构化数据、接口数据的场景。
	  - 举个例子：你让AI分析某个天气API返回的JSON数据，就用这个工具。
  
  📊 **一张表看懂区别** 
 
| 工具名              | 输出格式       | 核心特点        | 适用场景         |
| ---------------- | ---------- | ----------- | ------------ |
| `fetch_html`     | 原始HTML     | 完整源码，保留所有标签 | 网页结构分析、爬虫开发  |
| `fetch_markdown` | 干净Markdown | 去冗余，保留排版格式  | 文章转笔记、内容归档   |
| `fetch_txt`      | 纯文本        | 无格式，只留文字    | 文本提取、摘要生成    |
| `fetch_json`     | 原始JSON     | 结构化数据，完整保留  | API数据获取、接口调试 |
  
 💡 补充小知识： 这四个工具本质都是「HTTP请求工具」，只是对返回内容做了不同的处理，是AI联网能力的核心工具之一，常见于Claude的MCP（Model Context Protocol）服务器配置里。 要不要我给你一份这四个工具的**完整JSON配置示例**，可以直接复制到Claude的MCP配置里用？

---
- 调取与模型有关，用glm-4.5时没结果
- 用kimi k2.5时效果明显
- 对新闻头条、微信公众号没有效果

### 6.AliyunBailianMCP_WebSearch

- 基于通义实验室Text-Embedding，GTE-reRank，Query 改写，搜索判定等多种检索模型及语义理解，串接专业搜索工程框架及各类型实时信息检索工具，提供实时互联网全栈信息检索，提升LLM回答准确性及时效性。

### 7.amap-maps+caiyun-weather

- 高德地图+彩云天气
- 查询某地的天气、出行、景点及美食

### 8.@cherry/sequentialthinking

- 一个MCP服务器实现，提供了通过结构化思维过程进行动态和反思性问题解决的工具

## 四、网页提取

- **cherrystudio中**
	- @cherry/fetch
		- 用于获取 URL 网页内容的 MCP 服务器
	- WebParse
		- 网页解析(WebParser)MCP服务，一个专用于网页内容解析的工具包。
		- 适合微信公众号
- **浏览器中**
	- Obsidian Web Clipper扩展**
		- 全文提取
- **obsidian中**
	- 插件claude技能defuddle
		- 提取总结
	- 插件TextGenerator的文本提取**
		- 可提取内容

## 五、Ai会话中的联网功能

### CherryStudio中的联网功能

- [Tavily API Platform](https://app.tavily.com/home#)
	- 2000点/月（免费）
- [Querit.ai | Search Smarter, Build Faster](https://www.querit.ai/en/dashboard/home)
	- 1000点/月（免费）
	- 效果没有Tavily好

## 六、obsidian中的Ai插件

### 1.Smart Composer
- **Chat  聊天**
	- Chat model   聊天模型
		- Choose the model you want to use for chat.   
		- 选择您想用于聊天的模型。
	- Apply model  应用模型
		- Choose the model you want to use for apply feature.  
		- 选择您想用于应用功能的模型。
	- System prompt  系统提示
		- This prompt will be added to the beginning of every chat.  
		- 此提示将添加到每次聊天的开头。
	- Include current file  包含当前文件
		- Automatically include the content of your current file in chats.
		- 自动将当前文件的内容包含在聊天中。
	- Enable tools 启用工具 
		- Allow the AI to use MCP tools. 
		- 允许AI使用MCP工具。
	- Max auto tool requests  最大自动工具请求次数
		- Maximum number of consecutive tool calls that can be made automaticallywithout user confirmation. Higher values can significantly increase costs as eachtool call consumes additional tokens.
	- 在无需用户确认的情况下，可自动执行的连续工具调用的最大次数。较高的值会显著增加成本，因为每次工具调用都会消耗额外的令牌。
