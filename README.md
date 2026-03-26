# yapi-plugin

Cursor plugin for working with YApi through the existing `yapi` CLI.

## What it does

- Detect and install `@leeguoo/yapi-mcp` automatically when `yapi` is missing
- Reuse `~/.yapi/config.toml` and existing `yapi login` state
- Query interfaces by keyword or ID
- List interfaces under a category
- Run `docs-sync` commands from Cursor

## Layout

- `.cursor-plugin/plugin.json`: marketplace metadata
- `skills/yapi/SKILL.md`: YApi routing and URL handling guidance
- `commands/`: setup, login, query, and docs-sync command prompts
- `scripts/`: local Node wrappers around the `yapi` CLI

## Local development

```bash
npm test
npm run validate
```

## Runtime assumptions

- `node` and `npm` are available locally
- global npm install is permitted
- YApi authentication is still managed by `yapi login`
