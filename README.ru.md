# Claude Skills

[English](README.md) | [Français](README.fr.md) | [Español](README.es.md) | [中文](README.zh-CN.md) | [日本語](README.ja.md) | **Русский**

Скиллы для Claude — SKILL.md

###Что такое агентские навыки?

** Навыки - это папки с файлом `SKILL.md`**, которые учат агента ИИ выполнять определенную задачу - загружаемый контекст, а не код. Формат Anthropic: передняя часть YAML (`name`, `description`) плюс инструкции, сценарии и ресурсы, которые агент читает по требованию.

Это репо - кураторская коллекция готовых к использованию навыков + руководство по написанию собственного.

##  categories Навыки

###  skills Навыки работы с документами
Навыки, навыки Что он делает
|---|---|
`docx` Создание/редактирование Документы Word с отслеживаемыми изменениями
| `pdf` | Экстракт, разделение, слияние, заполнение форм PDF |
| `pptx` | Построить слайд-палубы из контуров |
| `xlsx` | Электронные таблицы с формулами, диаграммами, поворотами |

###  ️ Навыки
Навыки, навыки Что он делает
|---|---|
| `webapp-testing` | Управлять браузером, проверять состояния пользовательского интерфейса |
| `mcp-builder` | Новые MCP-серверы
| `skill-creator` | Мета-навык: напишите новые навыки |
| `git-commit-helper` | Обычные обязательства, описания PR |

### Творческие способности
Навыки, навыки Что он делает
|---|---|
| `canvas-design` | Спецификации визуального дизайна → активы |
| `video-script` | Раскадровка + форматирование сценариев |
| `brand-voice` | Составьте руководство по стилю на черновиках |

Анатомия SKILL.md

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

** Правила большого пальца: **
Описание = триггер - решает, когда агент загружает навык
Детерминистская работа идет в **скриптах **, работа суждения остается в инструкциях
Сохраните SKILL.md < 500 строк; разделите справочный материал на файлы
Навыки составления: один навык может ссылаться на другой

###Использование этих навыков

**Claude.ai/Claude Code**: опустить папку в `.claude/skills/`
**API**: подключать через механизм навыков / включать в контекст
**Другие агенты**: порты формата тривиально — это просто разметка + файлы

---
## Участие

Pull request'ы приветствуются — открой PR, он будет проверен и принят. Ведёт [aixisstudio](https://github.com/aixisstudio), автор [Snitch](https://github.com/aixisstudio/Snitch) — open-source application firewall.

## Лицензия: MIT
