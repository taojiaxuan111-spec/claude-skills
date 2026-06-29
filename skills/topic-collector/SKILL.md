---
name: topic-collector
description: AI热点采集工具。从Twitter/X、Product Hunt、Reddit、Hacker News等采集AI相关热点，直接在对话框输出结果。聚焦领域：Vibe Coding/AI编程、AI新产品/创业、AI模型动态。当用户说"开始今日选题"、"采集热点"、"看看今天有什么新闻"、"今日AI热点"、"帮我采集"时触发。
icon: 📰
---

# Topic Collector - AI热点采集

## 使用流程

当用户触发热点采集时，按以下步骤执行：

### 第一步：确认今日日期

获取当前日期（今天是 {{currentDate}}），所有搜索必须限制在过去 24 小时内。

### 第二步：执行搜索

使用 **WebSearch** 工具，依次执行以下搜索查询：

#### 🧑‍💻 Vibe Coding / AI编程
- `"Claude Code" tips tricks site:twitter.com OR site:x.com`
- `"Cursor" OR "Claude Code" vibe coding tutorial`
- `Claude Code new feature update`
- `AI coding agent workflow 2026`

#### 🚀 AI新产品/创业
- `site:producthunt.com AI tools today`
- `Hacker News "Show HN" AI`
- `new AI tool launch startup`

#### 🤖 AI模型动态
- `Claude OR GPT OR Gemini model update release`
- `Anthropic OR OpenAI OR Google AI announcement`
- `new LLM benchmark release`

### 第三步：整理内容

每条热点提取以下信息：
- **标题**：简洁的中文标题（20字以内）
- **来源**：平台 + 账号/作者
- **链接**：原文 URL
- **要点**：1-2句话说明为什么值得关注

过滤规则：
- 只保留 24 小时内的内容
- 每个分类最多 3 条，取最有价值的
- 重复内容合并
- 纯学术论文（无实际应用讨论的）跳过

### 第四步：在对话框输出结果

直接以 Markdown 格式输出，格式如下：

```
📰 **今日AI热点 · {{日期}}**

---

### 🧑‍💻 Vibe Coding / AI编程

**1. [标题](链接)**
来源：@xxx
要点：说明

...

---

### 🚀 AI新产品

...

---

### 🤖 模型动态

...

---
⏱ 采集时间：{{日期}} | 范围：近24小时
```

---

## 聚焦内容说明

### 🧑‍💻 Vibe Coding / AI编程（最高优先级）
优先关注：
- Claude Code 新功能、技巧、最佳实践
- Cursor 使用心得和新特性
- AI Agent 工作流（n8n、Make 等）
- 实操教程和案例（能直接用的）

**重点关注账号**：@AnthropicAI、@kaborsk1（Claude Code作者）、@swyx、@simonw、@levelsio

### 🚀 AI新产品/创业
优先关注：
- Product Hunt 当日 AI 分类 Top 5
- 独立开发者发布的 AI 工具
- Hacker News Show HN 中的 AI 项目
- 融资/收购大事件

### 🤖 AI模型动态
优先关注：
- Anthropic Claude 系列更新
- OpenAI GPT/o系列更新
- Google Gemini 更新
- 重要 benchmark 结果

---

## 常见触发词

| 用户说 | 执行操作 |
|--------|----------|
| "开始今日选题" | 完整采集流程，对话框输出 |
| "采集热点" | 完整采集流程，对话框输出 |
| "今日AI热点" | 完整采集流程，对话框输出 |
| "帮我采集" | 完整采集流程，对话框输出 |
| "只看 Vibe Coding 热点" | 只搜索 Vibe Coding 分类，对话框输出 |
| "只看模型动态" | 只搜索模型动态分类，对话框输出 |

---

## 注意事项

- **时间严格限制 24 小时**，不采集旧内容
- 每次搜索前告诉用户"正在搜索 X 分类..."让用户知道进度
- 如果某分类搜索结果为空，跳过该分类，不要填充旧内容
- 链接必须是原文直链，不要用重定向或聚合页链接
