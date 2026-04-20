---
description: Assemble the current RSoW or BBtn issue from prepared and approved section outputs.
---

Use the `newsletter-finalize-issue` skill in `skills/08-finalize-issue/SKILL.md`.

Finalize the current issue by replacing known placeholders with prepared section outputs. Use only checked checklist items and only approved front-matter sections. If `$ARGUMENTS` specifies a newsletter, issue, target folder, placeholder subset, or constraint, honor it.

At the end, report replaced placeholders, unresolved placeholders, unapproved or waiting sections, missing section folder notes, and remaining `{{...}}` placeholders.
