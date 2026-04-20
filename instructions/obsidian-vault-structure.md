# Obsidian Vault Structure

This is a development note. Runtime vault rules live in `skills/_shared/reference/vault-structure.md`.

When changing vault layout, folder names, template names, or source-movement behavior:

- Update `skills/_shared/reference/vault-structure.md`.
- Update `skills/_shared/reference/section-map.md` if section folder names change.
- Update the affected section skills when their input or output paths change.
- Update `README.md` so human editors see the new structure.
- Keep destructive operations out of automated workflows unless the human editor explicitly asks for them.

Obsidian community plugin recommendations belong in editor-facing documentation unless a skill needs them to execute a task.
