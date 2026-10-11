# skills-public

Public Claude Code and Codex skills for Python work: code review, exploratory
data analysis, local data inspection, verified literature reviews, dependency
management with uv, tutorials and Obsidian notes.

## Layout

One directory per skill under `skills/`, each with a `SKILL.md` entry point and
any supporting `references/` or `scripts/` next to it:

```text
skills/<skill-name>/SKILL.md
```

## Skills

| Skill | Description |
| --- | --- |
| [code-review](skills/code-review/SKILL.md) | Python code review: architecture, security, quality, testing, docs |
| [code-review-loop](skills/code-review-loop/SKILL.md) | Iterative review, fix and re-review loop over Python changes |
| [dataset-inspector](skills/dataset-inspector/SKILL.md) | Inspect local Parquet, CSV, JSON, or JSONL files |
| [do-literature-review](skills/do-literature-review/SKILL.md) | Verified literature reviews with citation audit trails |
| [eda](skills/eda/SKILL.md) | Exploratory analysis for tabular datasets |
| [lazy-imports](skills/lazy-imports/SKILL.md) | Defer Python imports to cut module and CLI startup time |
| [obsidian-create-note](skills/obsidian-create-note/SKILL.md) | Import a local Markdown file as a note in an Obsidian vault |
| [tutorial-expand](skills/tutorial-expand/SKILL.md) | Expand or annotate official tutorials for Python data and ML libraries |
| [uv-deps](skills/uv-deps/SKILL.md) | Manage dependencies in uv projects and workspaces |

## Installation

With [skillden](https://github.com/argythana/skillden), declare this repo as a
source in your catalog and scope each skill globally or to projects. The
repository URL is `https://github.com/argythana/skills-public.git` and each
skill's path is `skills/<skill-name>`.

Without skillden, copy or symlink a skill directory into `~/.claude/skills/`
for Claude Code or `~/.agents/skills/` for Codex.

## Validation

```bash
scripts/validate-skills-frontmatter            # validate working tree
scripts/validate-skills-frontmatter --staged   # validate staged index
scripts/install-hooks                          # validate staged skills on commit
```

The validator enforces exact `name` and `description` keys, folded
descriptions, `name` matching the skill directory, and `description` under
1024 characters, which is Codex's hard limit. Requires Ruby. CI runs it on
every push and pull request.
