# Section Map

This is a development note. Runtime section mapping lives in `skills/_shared/reference/section-map.md`.

When changing a section folder, heading, placeholder, or skill name:

- Update `skills/_shared/reference/section-map.md`.
- Update affected `SKILL.md` files and examples.
- Update `skills/00-basic-structure/*-template.md` if placeholders change.
- Update `plugin.json` keywords when public section names change.
- Update `README.md` if editor-facing names change.

The `newsletter-vault-structure` skill is intentionally not listed in the section map because it does not correspond to a newsletter placeholder. Keep service workflows outside the section numbering and use the `99-` prefix, for example `skills/99-vault-structure/`.
