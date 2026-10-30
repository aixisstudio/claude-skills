# Claude Skills

[English](README.md) | [Français](README.fr.md) | [Español](README.es.md) | **中文** | [日本語](README.ja.md) | [Русский](README.ru.md)

Claude 技能集 — SKILL.md 文件

□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□

**Skills是带有`SKILL.md`文件**的文件夹,教AI代理如何完成特定任务——可装入上下文,而不是代码. Anthropic格式:一个YAML前置物质(`name`,`description`)加上指令,脚本,以及代理商按要求读取的资源.

这部Repo是一款整理的现成技能集+自写指南.

□ 技能类别

* 文件技能
技术 它会做什么?
|---|---|
`docx` 创建/编辑 有跟踪更改的文字文档 QQ
`pdf` 提取、拆分、合并、填充 PDF 表格
`pptx` 从大纲中创建幻灯片甲板
`xlsx` 带有公式、图表、 pivots 的电子表格

=============================================================================================================================================================================
技术 它会做什么?
|---|---|
QQ `webapp-testing` 驱动浏览器, 验证UI 状态 QQ
`mcp-builder` 脚手架新MCP服务器
=====================================================================================================================================================================================
`git-commit-helper` 常规承诺、公关说明

创造能力
技术 它会做什么?
|---|---|
`canvas-design` 视觉设计规格 → 资产
`video-script` 故事板 + 脚本格式化
`brand-voice` 执行关于草稿的样式指南

□ 解剖一个SKILL.MD

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

** 拇指规则:**
- 描述=触发——它决定代理人何时装载技能
- 定型工作用**语录**,判决工作用说明书。
- 保留 SKILL.md < 500行;将参考资料分割成文件
- 技能构成:一种技能可以参考另一种技能

□ 利用这些技能

- ** Claude.ai / Claude代码**: 将文件夹放入 `.claude/skills/`
- ** API**:通过技能机制附加/包括上下文
- **其他代理**:格式端口微乎其微——只是标记下+文件

---
## 贡献

欢迎提交 Pull Request，我们会审查并合并。由 [aixisstudio](https://github.com/aixisstudio) 维护，他也是开源应用防火墙 [Snitch](https://github.com/aixisstudio/Snitch) 的作者。

## 许可证: MIT
