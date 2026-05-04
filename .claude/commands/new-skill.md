---
description: Scaffold a new skill in skills/<name>/SKILL.md
---

You are scaffolding a new skill for this suit content repo.

A skill is a focused, reusable capability — a small toolkit the AI can pull in for a specific task. Skills are referenced from outfits (via `skill_include`), modes/accessories (via `include.skills`), or auto-loaded based on harness defaults.

Ask the user:

1. **Name** — kebab-case (e.g., `pdf-extract`, `csv-parse`).
2. **Description** — what does this skill do?
3. **Trigger keywords** — words that should make the AI consider invoking this skill (e.g., for `pdf-extract`: "PDF", "extract pages", "read this PDF").
4. **Body** — the skill instructions. What does the AI do when this skill is active?

Write `skills/<name>/SKILL.md` with frontmatter:

```yaml
---
name: <name>
version: 1.0.0
type: skill
description: <description>
trigger: <keywords>
---

<body>
```

After writing, run `suit list` and verify the skill appears.
