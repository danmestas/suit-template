---
description: Scaffold a new plugin (multi-component package) under plugins/<name>/
---

You are scaffolding a new plugin for this suit content repo.

A plugin is a bundled set of related skills, hooks, and configuration. Plugins are how you ship cohesive multi-skill capabilities (e.g., a "data-pipeline" plugin with skills for ingest, transform, load).

Ask the user:

1. **Name** — kebab-case (e.g., `data-pipeline`).
2. **Description** — what does this plugin do collectively?
3. **Components** — list of skills/hooks the plugin includes. We'll create stubs for each.

Write `plugins/<name>/plugin.json`:

```json
{
  "name": "<name>",
  "version": "1.0.0",
  "description": "<description>",
  "components": [...]
}
```

For each component, scaffold a stub file (skill, hook, etc.) under `plugins/<name>/<component>/`.

After writing, run `suit list` to confirm the plugin's components are discovered.
