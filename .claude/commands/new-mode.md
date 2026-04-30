---
description: Scaffold a new mode file with YAML frontmatter and prompt body
---

You are scaffolding a new mode for this suit content repo.

Ask the user:

1. **Name** — kebab-case identifier (e.g., `focused`, `design`, `triage`).
2. **Description** — one sentence describing the mood or constraint.
3. **Prompt body** — the actual instructions the mode will inject. Keep it under 4096 bytes (suit enforces this limit).

Write `modes/<name>/mode.md` with this frontmatter:

```yaml
---
name: <name>
version: 1.0.0
type: mode
description: <description>
---

<prompt body>
```

After writing, run `suit show mode <name>` to verify.
