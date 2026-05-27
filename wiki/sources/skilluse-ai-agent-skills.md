---
type: source
created: 2026-05-27
updated: 2026-05-27
sources: [SkillUse — Manage AI Agent Skills with Ease.md]
tags: [科技/AI, AI Agent, 开发工具, 开源]
---

# SkillUse：AI Agent 技能管理工具

**来源：** [[raw/articles/SkillUse — Manage AI Agent Skills with Ease|skilluse.dev, 2026-04-05]]

## 核心功能

SkillUse 是一个基于 GitHub 的 **AI Agent 技能注册中心**——发现、安装、发布 AI 编码助手的 skill 文件。

支持的 Agent：Claude Code、Cursor、Windsurf 等。

## 工作原理

```
GitHub 仓库（技能注册中心）
    ├── 公共社区仓库
    ├── 公司私有仓库
    └── 个人私有仓库
         ↓
      skilluse CLI
         ↓
    ┌────┼────┐
    ↓    ↓    ↓
~/.claude/  ~/.cursor/  ~/.codex/
  skills/    skills/     skills/
```

技能文件放入 Agent 目录后立即生效，无需重启或配置。

## 快速上手

```bash
npm install -g skilluse
skilluse auth login        # GitHub 认证
skilluse repo add skilluse/skilluse   # 添加仓库
skilluse skill install commit         # 安装技能
```

需要 Node.js 18+。

## 与现有生态关系

- 类似 npm/pip 包管理，但面向 AI Agent 的 prompt/skill 文件
- 与 Claude Code 的 `/skill` 机制配合
