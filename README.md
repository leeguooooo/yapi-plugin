# yapi-plugin

Cursor plugin for YApi workflows inside Cursor.

It wraps the existing `yapi` CLI so you can use YApi without leaving the editor. The plugin checks whether `yapi` is installed, installs `@leeguoo/yapi-mcp` automatically when needed, reuses your existing `~/.yapi/config.toml`, and exposes the common query and `docs-sync` flows as Cursor skills and commands.

## What it does

- Detect and install `@leeguoo/yapi-mcp` automatically when `yapi` is missing
- Reuse `~/.yapi/config.toml` and existing `yapi login` state
- Query interfaces by keyword or ID
- List interfaces under a category
- Run `docs-sync` commands from Cursor

## Why this plugin

- Avoids re-entering YApi credentials in a second tool
- Keeps YApi discovery and docs-sync flows inside Cursor
- Gives agents a stable command surface instead of ad-hoc shell instructions
- Starts simple with `skill + commands + wrapper scripts`, without forcing MCP on day one

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

## Marketplace copy

Short description:

> Use YApi from Cursor through the local yapi CLI. Install it automatically, reuse existing login state, inspect interfaces, and run docs-sync workflows.

Primary workflows:

- Setup YApi and verify login state
- Search interfaces by keyword
- Fetch interface details by ID
- List category interfaces
- Bind and run `docs-sync`
