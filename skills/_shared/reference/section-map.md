# Section Map

Use this as the canonical mapping between inbox folders, issue section folders, headings, placeholders, and skills.

The default newsletter layout now uses `Perex`, `Mikro-intro`, `Opinion`, `Signály a šumy` / `Signals and noise`, `Linkodrom` / `Linkodrome`, `Kde se potkáme` / `Where we'll meet`, and a final closing note. `Perex`, `Mikro-intro`, and `Servis` are template-level blocks, not inbox sections.

| Order | Inbox and issue folder | RSoW heading | BBtn heading | RSoW placeholder | BBtn placeholder | Skill |
| --- | --- | --- | --- | --- | --- | --- |
| 01 | `01 In a Nutshell` | `Signály a šumy` | `Signals and noise` | `{{Signály a šumy}}` | `{{Signals and noise}}` | `newsletter-in-a-nutshell` |
| 02 | `03 Opinion` | `Opinion` | `Opinion` | `{{Opinion}}` | `{{Opinion}}` | `newsletter-opinion` |
| 03 | `04 Linkodrome` | `Linkodrom` | `Linkodrome` | `{{Linkodrom}}` | `{{Linkodrome}}` | `newsletter-linkodrome` |
| 04 | `06 Events` | `Kde se potkáme` | `Where we'll meet` | `{{Kde se potkáme}}` | `{{Where we'll meet}}` | `newsletter-events` |
| 05 | `07 Anniversary` | `Co děláme my / Co děláte vy` | `What we do / What you do` | `{{Co děláme my / Co děláte vy}}` | `{{What we do / What you do}}` | `newsletter-anniversary` |

Optional legacy blocks that remain available for special editions:

- `02 Designer’s Tip` / `Designer’s Tip` placeholder: `{{Designérský tip}}` or `{{Designer’s Tip}}`, skill `newsletter-design-tip`
- `05 Articles` / `Published on BBtn` / `Vyšlo na ŘSoW` placeholder: `{{Published on BBtn}}` or `{{Vyšlo na ŘSoW}}`, skill `newsletter-articles`

Folder notes use the folder name with a leading underscore, for example `_04 Linkodrome.md`.
