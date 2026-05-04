---
description: Scaffold a new mode file with YAML frontmatter and prompt body
---

You are scaffolding a new mode for this suit content repo.

A **mode** is a work-shape overlay (e.g., `focused`, `design`, `ticket-writing`, `marketing`). It composes on top of an outfit at invocation time. Modes can inject a prompt body, and optionally pull in additional components via an `include:` block.

Ask the user (one question at a time):

1. **Name** — kebab-case identifier (e.g., `focused`, `design`, `triage`).
2. **Description** — one sentence describing the work-shape.
3. **Optional component overlay** — does this mode pull in specific skills/rules/hooks/agents on top of the active outfit? If yes, list them by name.
4. **Prompt body** — the instructions the mode will inject (under 4096 bytes — suit enforces this limit).

Write `modes/<name>/mode.md` with this frontmatter:

```yaml
---
name: <name>
version: 1.0.0
type: mode
description: <description>
targets: [claude-code, codex, gemini, copilot, apm, pi]
include:                   # optional — omit if mode is body-only
  skills: [<names>]
  rules: [<names>]
  hooks: [<names>]
  agents: [<names>]
  commands: [<names>]
---

<prompt body>
```

After writing, run `suit show mode <name>` to verify.
