# Repository Guidelines

## Project Structure & Module Organization

This repository is an Obsidian-style Markdown knowledge base.

- `raw/` contains immutable source material. Add new inputs under `raw/articles/`, `raw/papers/`, `raw/clippings/`, or `raw/notes/`; keep media in `raw/assets/`.
- `wiki/` contains maintained knowledge pages. Use `wiki/sources/` for source summaries, `wiki/entities/` for people and organizations, `wiki/concepts/` for topics, and `wiki/analyses/` for synthesis.
- `wiki/index.md`, `wiki/overview.md`, and `wiki/log.md` are coordination files. Update the index when adding pages and append to the log for ingest or lint work.
- `CLAUDE.md` defines the vault schema and workflow; follow it for page format and wiki maintenance tasks.

## Build, Test, and Development Commands

There is no application build step or test runner in this repository. Validate changes with lightweight repository checks:

- `git status --short` shows modified and untracked files.
- `rg --files wiki raw` lists tracked knowledge-base content.
- `rg '\[\[' wiki` helps inspect Obsidian wikilinks.

For content operations, use the documented workflow language, such as `ingest raw/articles/example.md` or `lint`.

## Coding Style & Naming Conventions

Write pages in clear, direct Markdown. Wiki pages should include YAML frontmatter:

```yaml
---
type: source | concept | entity | analysis | overview
created: YYYY-MM-DD
updated: YYYY-MM-DD
sources: []
tags: []
---
```

Use `[[wikilinks]]` for internal cross-references and `[[raw/articles/filename]]` for raw-source links. Keep pages focused; split a page when one subtopic grows beyond about 500 words. Prefer descriptive Chinese or English filenames that match the subject, for example `wiki/entities/宋孝武帝刘骏.md`.

## Testing Guidelines

Content review is the main quality gate. Before committing, check that new wiki pages have valid frontmatter, relevant `sources`, and useful cross-links. Confirm newly created pages are listed in `wiki/index.md`. Treat `wiki/log.md` as append-only.

## Commit & Pull Request Guidelines

Recent commits use short, imperative summaries, often in Chinese, with optional prefixes such as `ingest:`, `lint:`, `cleanup:`, or `merge:`. Examples: `ingest 杨惠之考...` and `lint: 补入四幅地图...`.

Pull requests should describe the sources added or pages changed, note index/log updates, and mention any unresolved contradictions or missing cross-links. Include screenshots only when visual assets or Obsidian rendering behavior are relevant.

## Agent-Specific Instructions

Do not modify files under `raw/` unless the user explicitly asks; treat them as source records. When new material contradicts existing wiki claims, preserve the older context and add an explicit contradiction note rather than silently replacing it.
