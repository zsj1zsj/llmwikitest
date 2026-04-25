# LLM Wiki — Schema & Workflow

This is the configuration file for Claude Code acting as wiki maintainer. Read this at the start of every session.

## Vault structure

```
llmwiki/
├── CLAUDE.md          ← this file (schema/config)
├── raw/               ← immutable source documents (you add, LLM only reads)
│   ├── articles/
│   ├── papers/
│   ├── clippings/
│   ├── notes/
│   └── assets/        ← 图片等媒体文件统一存放于此
└── wiki/              ← LLM-maintained knowledge base
    ├── index.md       ← master catalog of all wiki pages
    ├── log.md         ← append-only activity log
    ├── overview.md    ← high-level synthesis of everything
    ├── sources/       ← one summary page per raw source
    ├── concepts/      ← concept/topic pages
    ├── entities/      ← person, org, product pages
    └── analyses/      ← comparisons, syntheses, answers filed back
```

## Page conventions

Every wiki page must have YAML frontmatter:

```yaml
---
type: source | concept | entity | analysis | overview
created: YYYY-MM-DD
updated: YYYY-MM-DD
sources: [list of raw source filenames that informed this page]
tags: [relevant tags]
---
```

- Use `[[wikilinks]]` for all cross-references between wiki pages
- Link to raw sources as `[[raw/articles/filename]]`
- Keep pages focused — split when a page exceeds ~500 words on a single subtopic

## Operations

### Ingest
When user says "ingest <path>":
1. Read the raw source file
2. Discuss key takeaways with user
3. Create `wiki/sources/<slug>.md` — summary page with key points, quotes, metadata
4. Update `wiki/index.md` — add entry under Sources
5. Update relevant `wiki/concepts/` and `wiki/entities/` pages — add new info, note contradictions with existing claims
6. Update `wiki/overview.md` if the source shifts the big picture
7. Append to `wiki/log.md`: `## [YYYY-MM-DD] ingest | <title>`

### Query
When user asks a question:
1. Read `wiki/index.md` to identify relevant pages
2. Read those pages
3. Synthesize answer with citations to wiki pages
4. If the answer is valuable, offer to file it as `wiki/analyses/<slug>.md`
5. If filed, update `wiki/index.md` and append to `wiki/log.md`

### Batch Ingest
When user says "ingest <directory>":
1. Glob all files under that directory
2. Read `wiki/sources/*.md` frontmatter to collect already-ingested filenames (from `sources:` fields)
3. Skip any file whose filename already appears in an existing source page — report skipped files to user
4. For each remaining file, run the standard Ingest steps (read → summarize → create source page → update concepts/entities → update index/overview)
5. Append one log entry per newly ingested file; add a single summary line listing skipped files

### Lint
When user says "lint":
1. Read `wiki/index.md` and scan all pages
2. Report: orphan pages, missing cross-references, contradictions, stale claims, concepts without pages
3. Fix issues or flag for user review
4. Append to `wiki/log.md`: `## [YYYY-MM-DD] lint | <summary>`

## Style rules
- Write wiki pages in clear, direct prose — no filler
- Flag contradictions explicitly: `> **Contradiction:** This conflicts with [[other-page]] which says...`
- When a new source supersedes an old claim, update the old page and note the revision
- Never delete from `wiki/log.md` — it is append-only
- Always update `wiki/index.md` when creating or significantly updating a page
