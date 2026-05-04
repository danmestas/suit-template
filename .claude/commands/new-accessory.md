---
description: Scaffold a new accessory (small named overlay bundle) under accessories/<name>/
---

You are scaffolding a new accessory for this suit content repo.

An **accessory** is a small, named, repeatable add-on layered onto an outfit + mode at invocation time. Examples: a `tracing` accessory that pulls in observability skills + a tracing hook; a `pr-policy` accessory that adds one rules file; an `oncall` accessory that bundles a few escalation skills.

Use accessories for piecemeal composition. For larger role-shaped bundles (like "backend dev"), use outfits instead.

Ask the user (one question at a time):

1. **Name** — kebab-case (e.g., `tracing`, `pr-policy`, `oncall`).
2. **Description** — one sentence. What does this accessory add?
3. **Target harnesses** — claude-code, codex, gemini, copilot, apm, pi. Default: all six.
4. **Components to include** — names of existing skills/rules/hooks/agents in the wardrobe. Each is force-included (overrides outfit category-based filtering).

Once you have answers, write `accessories/<name>/accessory.md`:

```yaml
---
name: <name>
version: 1.0.0
type: accessory
description: <description>
targets: [<targets>]
include:
  skills: [<names>]
  rules: [<names>]
  hooks: [<names>]
  agents: [<names>]
  commands: [<names>]
---

(optional body — most accessories don't need one)
```

After writing, verify with:

```bash
suit list accessories
suit show accessory <name>
```

Strict-include rule: if any referenced component doesn't exist in the wardrobe, suit will fail at prelaunch with a precise error. Make sure each name in `include:` matches an existing component before saving.
