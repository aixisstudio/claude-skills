# Claude Skills

[English](README.md) | [Français](README.fr.md) | **Español** | [中文](README.zh-CN.md) | [日本語](README.ja.md) | [Русский](README.ru.md)

Skills de agente para Claude

¿Cuáles son las habilidades del agente?

**Las habilidades son carpetas con un archivo `SKILL.md`** que enseñan a un agente de AI cómo hacer una tarea específica — contexto cargable, no código. Formato de Antrópico: una materia frontal YAML (`name`, `description`) más instrucciones, scripts y recursos que el agente lee bajo demanda.

Este repo es una colección curada de habilidades listas para usar + una guía para escribir su propio.

## 📚 Categorías de la habilidad

#### 📄 Document skills
Esquía permanente Lo que hace
|---|---|
Silencio `docx` Silencio Crear / editar Documentos de palabras con cambios rastreados
← `pdf` Silencio Extract, split, merge, fill PDF forms ←
Silencio `pptx` Silencio Construir cubiertas de diapositivas de contornos Silencio
← `xlsx` Silencioso hojas de cálculo con fórmulas, diagramas, pivotes

### ## 🛠ف Destrezas Dev
Esquía permanente Lo que hace
|---|---|
← `webapp-testing` Silencio Conducir un navegador, verificar los estados de la UI
← `mcp-builder` ← Nuevos servidores MCP
Silencio `skill-creator` Silencio Meta-skill: escribir nuevas habilidades ←
Silencio `git-commit-helper` Silenciocomunicación, descripciones de las relaciones sexuales

#### ## ## ### ### #### ## ### ### ######################################################################################################################################################################################################################################
Esquía permanente Lo que hace
|---|---|
← `canvas-design` ← Diseño visual specs → assets ←
TEN `video-script` TENIDO Storyboard + script formatear
Silencio `brand-voice` Silencio Hacer cumplir una guía de estilo sobre los proyectos

## 🧪 Anatomía de un SKILL.md

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

**Ruinas de pulgar:**
- Descripción = disparador - decide cuando el agente carga la habilidad
- El trabajo determinista va en **scriptos**, el trabajo de juicio permanece en instrucciones
- Mantener SKILL.md 0 500 líneas; dividir material de referencia en archivos
- Composicion de habilidades: una habilidad puede hacer referencia a otra

## 🚀 Usando estas habilidades

- **Claude.ai / Código Claude**: suelte la carpeta en `.claude/skills/`
**API**: adjuntar a través del mecanismo de habilidades / incluir en el contexto
- **Otros agentes**: los puertos de formato trivialmente - es sólo marcado + archivos

---
## Contribuir

Los pull requests son bienvenidos: abre una PR y será revisada y fusionada. Mantenido por [aixisstudio](https://github.com/aixisstudio), autor de [Snitch](https://github.com/aixisstudio/Snitch), firewall de aplicaciones open source.

## Licencia: MIT
