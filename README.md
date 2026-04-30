# suit-template

A starter content repo for [suit](https://github.com/danmestas/suit), the multi-harness AI agent configurator. Fork this repo, customize the personas/modes/skills to your taste, and point `suit init` at your fork.

## Use this template

Click **Use this template** at the top of this repo, or:

```bash
gh repo create my-suit-config --template danmestas/suit-template --public
```

Then point suit at your fork:

```bash
suit init https://github.com/your-username/my-suit-config
suit list personas
suit claude --persona default
```

## What's in here

- `personas/` — `default` (generic) and `code` (code-focused). Personas are YAML-frontmatter markdown files that filter which skills your harness sees.
- `modes/` — `general` (default) and `focused` (deep-work, minimal interruptions). Modes inject a system prompt into the harness session.
- `skills/` — empty. Your skills go here. Use the `/new-skill` slash command in Claude Code to scaffold one.
- `.suit/default.yaml` — when you run `suit claude` with no flags, this is the default persona+mode that gets applied.
- `.claude/commands/` — Claude Code slash commands for AI-assisted scaffolding: `/new-persona`, `/new-mode`, `/new-skill`, `/new-plugin`. Each drives the AI to write the right files for you.
- `TAXONOMY.md` — the canonical category taxonomy that personas can reference. Add your own categories here as you create them.

## License

MIT
