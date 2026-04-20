# Ongoing Rules

- Keep development instructions concise, reusable, and easy to scan.
- Put runtime workflow rules in `SKILL.md` files or `skills/_shared/reference/`.
- Put only plugin-development documentation in `instructions/`.
- Preserve the distinction between the Czech RSoW context and the English/global-European BBtn context.
- For checklist-based working outputs, preserve human edits and checked states; final issue assembly uses only checked items.
- Never archive or delete source notes unless the user explicitly asks for archiving. Moving used source notes into an issue section folder is not archiving.
- After making changes, always check whether `plugin.json` is still current and update it if needed.
- After changing Claude Code command aliases or metadata, check whether `.claude-plugin/plugin.json`, `commands/`, and `hooks/hooks.json` are still current.
- If a skill or agent needs an MCP server, keep `.mcp.json` current.
- If a runtime rule is useful to more than one skill, prefer a shared reference over copying it into each skill.
- Use the `99-` prefix for service workflow skills that support the vault or plugin operation rather than a newsletter section.
