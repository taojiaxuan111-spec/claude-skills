# AI热点采集工具

基于 Claude Code Skill 的 AI 热点自动采集工具。每天一句话触发，Claude 自动搜索多个来源，整理当日最值得关注的 AI 动态，直接输出到对话框。

---

## 效果预览

```
📰 今日AI热点 · 2026-06-30

🧑‍💻 Vibe Coding / AI编程

1. Claude Code 6月重磅更新：嵌套子 Agent + Artifacts
   来源：Anthropic 官方
   要点：支持最多3层嵌套子 Agent，Artifacts 可生成可分享的实时网页

2. Cursor vs Claude Code vs Codex：2026 选哪个？
   来源：viblo.asia
   要点：主流建议混合用法——Cursor 负责日常编辑速度，Claude Code 做复杂任务规划

🚀 AI新产品

1. Databox MCP：将业务数据直接接入 Claude
   来源：Product Hunt
   要点：通过 MCP 协议把 Databox 数据喂给 Claude，分析报告自动化

🤖 模型动态

1. Anthropic 秘密递交 IPO 注册文件，估值近 $1T
   来源：CNBC
   要点：完成 $65B Series H 后估值 $965B，超过 OpenAI

⏱ 采集时间：2026-06-30 | 范围：近24小时
```

---

## 功能特点

- **一句话触发**：说"采集热点"即可，无需任何参数
- **多源聚合**：同时搜索 Twitter/X、Product Hunt、Hacker News、Reddit、官方博客
- **严格时效**：只采集过去 24 小时内的内容，不混入旧新闻
- **智能过滤**：每个分类最多 3 条，自动去重，过滤纯学术论文
- **聚焦方向**：专注 Vibe Coding、AI 新产品、模型动态三个方向

---

## 采集来源

| 分类 | 来源 |
|------|------|
| 🧑‍💻 Vibe Coding / AI编程 | Twitter/X、个人博客、技术社区 |
| 🚀 AI新产品 | Product Hunt、Hacker News Show HN、独立开发者 |
| 🤖 模型动态 | Anthropic / OpenAI / Google 官方博客、CNBC、VentureBeat |

**重点关注账号**：@AnthropicAI、@kaborsk1（Claude Code 作者）、@swyx、@simonw、@levelsio

---

## 安装

### 前提条件

- 已安装 [Claude Code](https://claude.ai/code)

### 一键安装

```bash
mkdir -p ~/.claude/skills/topic-collector
curl -sL https://raw.githubusercontent.com/taojiaxuan111-spec/claude-skills/main/skills/topic-collector/SKILL.md \
  > ~/.claude/skills/topic-collector/SKILL.md
```

重启 Claude Code 后生效。

---

## 使用方法

安装完成后，在 Claude Code 对话框中直接输入触发词：

| 说什么 | 效果 |
|--------|------|
| `采集热点` | 完整采集三个分类 |
| `今日AI热点` | 同上 |
| `开始今日选题` | 同上 |
| `帮我采集` | 同上 |
| `只看 Vibe Coding 热点` | 只采集 Vibe Coding 分类 |
| `只看模型动态` | 只采集模型动态分类 |

---

## 工作原理

这是一个 [Claude Code Skill](https://docs.claude.ai/en/docs/claude-code/skills)——一个放在 `.claude/skills/` 目录下的 `SKILL.md` 文件。Claude Code 检测到触发词后自动加载该 Skill，使用 WebSearch 工具依次搜索各分类，整理后输出到对话框。

整个流程无需 API Key、无需服务器，完全在本地 Claude Code 环境中运行。

---

## License

MIT
