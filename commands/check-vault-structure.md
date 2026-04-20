---
description: Check, initialize, or repair the Obsidian vault structure for the newsletter workflow.
---

Use the `newsletter-vault-structure` skill in `skills/99-vault-structure/SKILL.md`.

Inspect the current working directory as the Obsidian vault root unless `$ARGUMENTS` specifies another path. Create only missing non-destructive structure. If `$ARGUMENTS` requests a specific issue, create or repair that issue folder structure as described by the skill.

At the end, report the vault root, missing or created folders, missing or created templates, issue folders found or repaired, conflicts, skipped destructive actions, and editor-attention points.
