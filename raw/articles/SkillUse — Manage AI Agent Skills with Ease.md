---
created: 2026-04-05
tags:
  - ai/skill
source: https://skilluse.dev/
---

## Introduction

```
▗▄▄▖▗▖ ▗▖▗▄▄▄▖▗▖   ▗▖   ▗▖ ▗▖ ▗▄▄▖▗▄▄▄▖
▐▌   ▐▌▗▞▘  █  ▐▌   ▐▌   ▐▌ ▐▌▐▌   ▐▌
 ▝▀▚▖▐▛▚▖   █  ▐▌   ▐▌   ▐▌ ▐▌ ▝▀▚▖▐▛▀▀▘
▗▄▄▞▘▐▌ ▐▌▗▄█▄▖▐▙▄▄▖▐▙▄▄▖▝▚▄▞▘▗▄▄▞▘▐▙▄▄▖
```

SkillUse is a **registry for AI agent skills** based on GitHub. Discover, install, and publish skills across your teams and coding agents — Claude Code, Cursor, Windsurf, and more. [Star on GitHub](https://github.com/skilluse/skilluse).

Install a skill once, use it everywhere. Share skills across your team. Publish your own skills to any GitHub repository so others can discover and install them.

## How it works

GitHub repositories act as skill registries — public community repos, private company repos, or personal repos. SkillUse pulls skills from any of them and installs them into the directory your AI agent watches.

```
┌─────────────────────────────────────────────────────────────────┐
│           GitHub Repositories (Skill Registries)                │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐           │
│  │ Public Repo  │  │ Company Repo │  │Personal Repo │           │
│  │ (community)  │  │  (private)   │  │  (private)   │           │
│  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘           │
│         └─────────────────┼─────────────────┘                   │
│                           ▼                                     │
│                    ┌────────────┐                               │
│                    │  skilluse  │                               │
│                    └─────┬──────┘                               │
│                          │                                      │
│         ┌────────────────┼────────────────┐                     │
│         ▼                ▼                ▼                     │
│  ~/.claude/skills  ~/.cursor/skills  ~/.codex/skills            │
└─────────────────────────────────────────────────────────────────┘
```

Once a skill file lands in the agent directory, it becomes available as a slash command immediately — no restart, no configuration needed.

## Installation

Install the SkillUse CLI globally using your preferred package manager:

```bash
npm install -g skilluse
```

Or with pnpm:

```bash
pnpm add -g skilluse
```

Verify the installation:

```bash
skilluse --version
```

SkillUse requires Node.js 18 or later. It stores skills in your home directory under `~/.claude/skills/` for Claude Code, with support for other agents coming soon.

## Quick start

Get up and running in three steps:

**1\. Authenticate** — log in with your GitHub account to enable installing and publishing skills:

```bash
skilluse auth login
```

**2\. Add a skill repository** — point SkillUse at a GitHub repo containing skills:

```bash
skilluse repo add skilluse/skilluse
```

**3\. Install a skill** — browse and install skills from the repo:

```bash
skilluse skill install commit
```

Once installed, the skill appears as a slash command in your AI agent. In Claude Code, type `/commit` to use it.

## Commands

SkillUse is organized into four command groups: `auth`, `repo`, `skill`, and `publish`.

| Command | Description |  |
| --- | --- | --- |
| skilluse auth | Manage authentication with GitHub |  |
| skilluse repo | Manage skill repositories |  |
| skilluse skill | Install, remove, and list skills |  |
| skilluse publish | Publish skills to a repository |  |

## auth

The `auth` command handles GitHub OAuth authentication. SkillUse uses GitHub to identify users and to read from (and optionally write to) skill repositories.

```bash
# Log in via GitHub OAuth
skilluse auth login

# Check current auth status
skilluse auth status

# Log out
skilluse auth logout
```

Authentication is required for installing skills from private repositories and for publishing skills. Public repositories can be browsed without logging in.

## repo

Skill repositories are GitHub repos that follow the SkillUse format. The `repo` command manages which repos SkillUse knows about.

```bash
# Add a repository
skilluse repo add <owner>/<repo>

# List configured repositories
skilluse repo list

# Remove a repository
skilluse repo remove <owner>/<repo>

# Set a repository as the default for publishing
skilluse repo default <owner>/<repo>
```

You can add multiple repositories. When installing a skill by name, SkillUse searches all configured repos in the order they were added.

## skill

The `skill` command is the core of SkillUse. Install skills from repositories, list what's installed, and remove skills you no longer need.

```bash
# Install a skill by name
skilluse skill install <skill-name>

# Install from a specific repo
skilluse skill install <owner>/<repo>/<skill-name>

# List all installed skills
skilluse skill list

# Remove a skill
skilluse skill remove <skill-name>

# Show details about a skill
skilluse skill info <skill-name>
```

Skills are installed into the appropriate directory for your AI agent. For Claude Code, skills land in `~/.claude/skills/` and become available as `/skill-name` slash commands immediately — no restart required.

## publish

Share your skills with others by publishing them to a GitHub repository. The `publish` command handles versioning and pushing your skill files.

```bash
# Publish a skill from the current directory
skilluse publish

# Publish to a specific repository
skilluse publish --repo <owner>/<repo>

# Publish with a specific version
skilluse publish --version 1.2.0
```

Publishing requires authentication (`skilluse auth login`) and write access to the target repository. The repository must follow the SkillUse directory structure.

## Creating skills

A skill is a folder containing a `SKILL.md` file and optional reference documents. Create a new skill by making a directory with the skill name:

```bash
mkdir my-skill && cd my-skill
touch SKILL.md
```

The skill name (the folder name) becomes the slash command. A skill named `commit` becomes `/commit` in Claude Code.

To publish your skill, push the folder to a GitHub repository following the SkillUse structure, then run `skilluse publish`.

## Skill format

Each skill lives in a folder and must have a `SKILL.md` file — the prompt that gets injected into the AI agent when the skill is invoked.

```
my-skill/
├── SKILL.md          # Required — the skill prompt
└── references/       # Optional — supporting docs
    ├── guide.md
    └── examples.md
```

Write `SKILL.md` as a plain Markdown instruction prompt. Describe what the skill does, what inputs it expects, and how the agent should behave.

```bash
# SKILL.md example

Generate a Conventional Commits 1.0.0 compliant commit message.

## Instructions

1. Read all staged changes with \`git diff --cached\`
2. Summarize the changes in 72 characters or less
3. Use the format: \`<type>(<scope>): <description>\`
4. Valid types: feat, fix, docs, style, refactor, test, chore

## Output

Run: git commit -m "<message>"
```

Files in `references/` are automatically loaded alongside `SKILL.md` when the skill is invoked, giving the agent additional context without cluttering the main prompt.

A skill repository has one folder per skill at the top level:

```
my-skill-repo/
├── commit/
│   ├── SKILL.md
│   └── references/
│       └── conventional-commits.md
├── review-pr/
│   └── SKILL.md
└── deploy/
    ├── SKILL.md
    └── references/
        └── deploy-guide.md
```

## Supported agents

SkillUse supports 8 agents. Skills are installed globally by default, or locally (project-level) with the `--local` flag.

Agent support

| Agent | Global path | Local path |
| --- | --- | --- |
| Claude Code | ~/.claude/skills/ | .claude/skills/ |
| Cursor | — (project only) | .cursor/skills/ |
| VS Code + Copilot | — (project only) | .github/skills/ |
| Goose | ~/.config/goose/skills/ | .goose/skills/ |
| Codex CLI | ~/.codex/skills/ | .codex/skills/ |
| OpenCode | ~/.config/opencode/skill/ | .opencode/skill/ |
| Letta | ~/.letta/skills/ | .letta/skills/ |
| Other (portable) | — (project only) | .skills/ |

Specify the agent with the `--agent` flag, or let SkillUse auto-detect based on config files present in your project:

```bash
# Auto-detect agent
skilluse skill install commit

# Specify agent explicitly
skilluse skill install commit --agent cursor

# Install locally (project-level)
skilluse skill install commit --local
```

Questions or feedback? [Open an issue on GitHub](https://github.com/skilluse/skilluse/issues) or reach out on [X/Twitter](https://x.com/JiweiYuan).


# 摘录

# 单词

# 总结
>总结的目的是主要是为了培养自己对文章的理解能力， 目标是能够在不丢失主要信息的前提下复述文章