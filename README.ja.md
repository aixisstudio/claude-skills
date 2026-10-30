# Claude Skills

[English](README.md) | [Français](README.fr.md) | [Español](README.es.md) | [中文](README.zh-CN.md) | **日本語** | [Русский](README.ru.md)

Claude スキル集 — SKILL.md

## 🧩 エージェントスキルとは?

**Skillsは、特定のタスクを実行する方法AIエージェントを教える`SKILL.md`ファイル**を持つフォルダです。ロード可能なコンテキストは、コードではありません。 Anthropic のフォーマット: YAML の前部問題(`name`、`description`)プラスの指示、スクリプトおよび代理店は要求で読みました。

このレポは、既設のスキル + 自分で書くためのガイドのキュレーションコレクションです。

## スキルカテゴリ

#### ドキュメントスキル
| スキル | お問い合わせ |
|---|---|
| `docx` | 作成・編集 変更を追跡したWord文書 |
| `pdf` | 抽出・分割・合併・充填PDFフォーム |
| `pptx` | 概要からスライドデッキを造る |
| `xlsx` | 仕様書・チャート・ピボットのスプレッドシート |

#### ############################################################################################################################################################################################################################################################
| スキル | お問い合わせ |
|---|---|
| `webapp-testing` | ブラウザをドライブし、UIの状態を検証 |
| `mcp-builder` | 新MCPサーバーの足場 |
| `skill-creator` | メタスキル | 新卒採用 |
| `git-commit-helper` | 慣習的なコミット、PR 説明 |

#### クリエイティブスキル
| スキル | お問い合わせ |
|---|---|
| `canvas-design` | ビジュアルデザイン仕様 → アセット |
| `video-script` | ストーリーボード+スクリプトのフォーマット |
| `brand-voice` | ドラフトのスタイルガイド |

## 🧪 SKILL.mdの解剖学

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

**親指のルール:**
- 説明 = トリガー — エージェントがスキルをロードしたときに決定
- 決定的な仕事は**scripts**で行きます、判断の仕事は指示にとどまります
- SKILL.md <500行> 参照材料をファイルに分割する
- スキルコンポーズ: 1つのスキルは別のスキルを参照することができます

## これらのスキルを使用する

- **Claude.ai/Claudeコード**:`.claude/skills/`のフォルダをドロップ
-**API**:スキルのメカニズム/コンテキストに含める
-**その他のエージェント**:フォーマットポートは一意に-それは単なるマークダウン+ファイルです

---
## 貢献

プルリクエストを歓迎します。レビューしてマージします。[aixisstudio](https://github.com/aixisstudio) による管理 — オープンソースのアプリケーションファイアウォール [Snitch](https://github.com/aixisstudio/Snitch) の作者です。

## ライセンス: MIT
