---
description: Scaffold a new outfit file with YAML frontmatter and prompt body
---

You are scaffolding a new outfit for this suit content repo.

Ask the user (one question at a time, multiple-choice when possible):

1. **Name** — kebab-case identifier (e.g., `backend`, `data-eng`). Used as filename and reference key.
2. **Description** — one sentence. What kind of work does this outfit suit?
3. **Target harnesses** — claude-code, codex, gemini, copilot, apm, pi. Default: all six.
4. **Categories** — pick from `TAXONOMY.md` at the repo root. At least one required.
5. **Skill includes/excludes** — optional. Names of skills to force-include or force-exclude.

Once you have answers, write `outfits/<name>/outfit.md` with this frontmatter:

```yaml
---
name: <name>
version: 1.0.0
type: outfit
description: <description>
targets: [<targets>]
categories: [<categories>]
skill_include: [<optional>]
skill_exclude: [<optional>]
---
```

Followed by a one-paragraph prompt body that frames the outfit's role and priorities.

After writing, show the user the file path and run `suit show outfit <name>` to verify it loads.
