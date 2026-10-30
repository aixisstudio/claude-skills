# Claude Skills

[English](README.md) | **Français** | [Español](README.es.md) | [中文](README.zh-CN.md) | [日本語](README.ja.md) | [Русский](README.ru.md)

Agent Skills pour Claude — des SKILL.md qui enseignent de vraies compétences

Qu'est-ce que les compétences des agents ?

**Les compétences sont des dossiers avec un fichier `SKILL.md`** qui enseignent à un agent d'IA comment effectuer une tâche spécifique — contexte chargeable, pas code. Format de l'anthropique : une matière avant YAML (`name`, `description`) plus instructions, scripts et ressources que l'agent lit sur demande.

Cette repo est une collection curated de compétences prêtes à l'emploi + un guide pour écrire votre propre.

Catégories de compétences

Compétences documentaires
Compétence Ce qu'il fait
|---|---|
Créer/éditer Documents Word avec changements suivis
`pdf`?Extrait, partage, fusion, remplir les formulaires PDF?
Construisez des ponts coulissants à partir de contours
`xlsx`=Feuilles de calcul avec formules, graphiques, pivots=

Compétences du Dev
Compétence Ce qu'il fait
|---|---|
Conduire un navigateur, vérifier les états de l'interface utilisateur
`mcp-builder`
`skill-creator`: Meta-skill: écrire de nouvelles compétences
`git-commit-helper`: commits conventionnels, descriptions PR

Compétences créatives
Compétence Ce qu'il fait
|---|---|
`canvas-design`=Spécifications visuelles → actifs
`video-script`
`brand-voice`: Appliquer un guide de style sur les projets

Anatomie d'un SKILL.md

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

**Règles du pouce:**
- Description = déclencheur — il décide quand l'agent charge l'habileté
- Le travail déterministe va dans **scripts**, le travail de jugement reste dans les instructions
- Conserver SKILL.md < 500 lignes; diviser le matériel de référence en fichiers
- Les compétences composent : une compétence peut en faire une autre

Utilisation de ces compétences

- **Claude.ai / Claude Code** : déposez le dossier dans `.claude/skills/`
- **API**: attacher via le mécanisme des compétences / inclure dans le contexte
- **Autres agents**: les ports format trivially — c'est juste balisage + fichiers

---
## Contribuer

Les pull requests sont les bienvenues : ouvre une PR, elle sera relue et fusionnée. Maintenu par [aixisstudio](https://github.com/aixisstudio), auteur de [Snitch](https://github.com/aixisstudio/Snitch), pare-feu applicatif open source.

## Licence: MIT
