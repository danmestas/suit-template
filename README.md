# suit-template

A starter content repo for [suit](https://github.com/danmestas/suit), the multi-harness AI agent configurator. Fork this repo, customize the outfits/modes/accessories/skills to your taste, and point `suit init` at your fork.

## Use this template

Click **Use this template** at the top of this repo, or:

```bash
gh repo create my-suit-config --template danmestas/suit-template --public
```

Then point suit at your fork:

```bash
suit init https://github.com/your-username/my-suit-config
suit list outfits
suit claude --outfit default
suit claude --outfit code --mode focused --accessory <name>
```

## What's in here

- `outfits/` — `default` (generic) and `code` (code-focused). Outfits are YAML-frontmatter markdown files that bundle a configuration set for a role-shaped session.
- `modes/` — `general` (default) and `focused` (deep-work, minimal interruptions). Modes overlay a work-shape on top of an outfit; they can inject a prompt body and/or pull in additional components.
- `accessories/` — empty. Accessories are small, named, repeatable add-ons applied via `--accessory <name>`. Use `/new-accessory` to scaffold one.
- `skills/` — empty. Your skills go here. Use `/new-skill` to scaffold one.
- `.suit/default.yaml` — when you run `suit claude` with no flags, this is the default outfit+mode that gets applied.
- `.claude/commands/` — Claude Code slash commands for AI-assisted scaffolding: `/new-outfit`, `/new-mode`, `/new-skill`, `/new-accessory`. Each drives the AI to write the right files for you.
- `TAXONOMY.md` — the canonical category taxonomy that outfits can reference. Add your own categories here as you create them.

## Composition model

```
suit claude --outfit <name> --mode <name> --accessory <a> --accessory <b>
```

1. **Outfit** seeds the baseline configuration (skills + rules + hooks + agents).
2. **Mode** overlays work-shape (focused, design, ticket-writing, …) — can inject a prompt body and/or pull in additional components.
3. **Accessories** layer on piecemeal — each `--accessory` is a small named bundle applied in CLI order.

See suit's ADR-0010 for full resolution semantics.

## License

MIT
