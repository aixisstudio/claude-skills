# Claude Skills

[English](README.md) | [Français](README.fr.md) | [Español](README.es.md) | **中文** | [日本語](README.ja.md) | [Русский](README.ru.md)

Claude 技能集 — SKILL.md 文件

_详细内容（列表、链接、描述）以英文维护 — 以下章节为你指引。_

## 🧩 What are Agent Skills?

**Skills are folders with a `SKILL.md` file** that teach an AI agent how to do a specific task — loadable context, not code. Anthropic's format: a YAML front matter (`name`, `description`) plus instructions, scripts, and resources the agent reads on demand.

This repo is a curated collection of ready-to-use skills + a guide to writing your own.

## 📚 Skill categories

### 📄 Document skills
| Skill | What it does |
|---|---|
| `docx` | Create/edit Word documents with tracked changes |
| `pdf` | Extract, split, merge, fill PDF forms |
| `pptx` | Build slide decks from outlines |
| `xlsx` | Spreadsheets with formulas, charts, pivots |

### 🛠️ Dev skills
| Skill | What it does |
|---|---|
| `webapp-testing` | Drive a browser, verify UI states |
| `mcp-builder` | Scaffold new MCP servers |
| `skill-creator` | Meta-skill: write new skills |
| `git-commit-helper` | Conventional commits, PR descriptions |

### 🎨 Creative skills
| Skill | What it does |
|---|---|
| `canvas-design` | Visual design specs → assets |
| `video-script` | Storyboard + script formatting |
| `brand-voice` | Enforce a style guide on drafts |

## 🧪 Anatomy of a SKILL.md

```markdown
---
name: pdf-form-filler
description: Fill PDF form fields. Use when the user provides a PDF with empty form fields.
---

# PDF Form Filler

## Instructions
1. Run `scripts/extract_fields.py form.pdf` to list fields
2. Ask the user for values of any ambiguous field
3. Fill with `scripts/fill_fields.py`

## Resources
- `scripts/` — helper scripts (deterministic, no LLM needed)
- `reference/field-types.md` — PDF field type reference
```

**Rules of thumb:**
- Description = trigger — it decides when the agent loads the skill
- Deterministic work goes in **scripts**, judgment work stays in instructions
- Keep SKILL.md < 500 lines; split reference material into files
- Skills compose: one skill can reference another

## 🚀 Using these skills

- **Claude.ai / Claude Code**: drop the folder in `.claude/skills/`
- **API**: attach via the skills mechanism / include in context
- **Other agents**: the format ports trivially — it's just markdown + files

---
## 贡献

欢迎提交 Pull Request，我们会审查并合并。由 [aixisstudio](https://github.com/aixisstudio) 维护，他也是开源应用防火墙 [Snitch](https://github.com/aixisstudio/Snitch) 的作者。

## 许可证: MIT
