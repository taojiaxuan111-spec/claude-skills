# Claude Code Skills

我的 Claude Code 自定义 Skill 合集，持续更新。

## 什么是 Claude Code Skill？

Skill 是放在 `.claude/skills/<name>/SKILL.md` 里的指令文件，Claude Code 会在对话中按需加载，赋予 AI 特定领域的知识和工作流。

## Skills 列表

### 📰 [topic-collector](skills/topic-collector/SKILL.md)

AI 热点采集工具。每天一句话触发，自动搜索并整理当日 AI 热点，直接输出到对话框。

**聚焦领域：**
- 🧑‍💻 Vibe Coding / AI 编程（Claude Code、Cursor、AI Agent）
- 🚀 AI 新产品 / 创业（Product Hunt、Hacker News）
- 🤖 AI 模型动态（Anthropic、OpenAI、Google）

**触发词：** "采集热点"、"今日AI热点"、"开始今日选题"

## 安装使用

```bash
# 安装 topic-collector
mkdir -p ~/.claude/skills/topic-collector
curl -sL https://raw.githubusercontent.com/taojiaxuan111-spec/claude-skills/main/skills/topic-collector/SKILL.md \
  > ~/.claude/skills/topic-collector/SKILL.md
```

安装后重启 Claude Code，直接对话触发即可。

## License

MIT
