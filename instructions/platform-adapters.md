# Platform Adapters

This repository supports multiple assistant plugin surfaces from the same core skills.

## Shared Core

- `skills/*/SKILL.md` contains section workflows.
- `skills/_shared/reference/` contains runtime rules shared by multiple skills.
- `agents/*.agent.md` contains agent entry points that GitHub Copilot CLI and Claude Code can discover.
- `.mcp.json` contains shared MCP server configuration.

Keep workflow behavior in the shared core whenever possible. Adapter files should point to the shared core instead of duplicating workflow rules.

## GitHub Copilot CLI Adapter

- Manifest: `plugin.json`.
- Agents: `agents/`.
- Skills: explicit `skills` list in `plugin.json`.
- Hooks: `hooks.json`.
- MCP: `.mcp.json`.

When adding or removing a skill, update the explicit `skills` list in `plugin.json`.

## Claude Code Adapter

- Manifest: `.claude-plugin/plugin.json`.
- Slash command aliases: `commands/*.md`.
- Hooks: `hooks/hooks.json`.
- Skills: default `skills/` discovery.
- Agents: default `agents/` discovery.
- MCP: `.mcp.json`.

Claude Code commands are namespaced by the plugin name, for example `/newsletter-composer:prepare-opinion`. Commands should stay thin: invoke the relevant shared skill and pass through `$ARGUMENTS`.

When adding a new section workflow:

- Add or update the shared skill.
- Add or update the Copilot agent when needed.
- Add a Claude command alias in `commands/` when the workflow should be manually invokable.
- Update `.claude-plugin/plugin.json` only when plugin metadata changes.
- Update `README.md` for editor-facing usage changes.
