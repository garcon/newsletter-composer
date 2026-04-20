---
name: newsletter-anniversary
description: Compose the RSoW or BBtn Anniversary closing paragraph by deriving the expected publication date, selecting a positive preferably round anniversary from source notes or Wikipedia day pages, and inserting it only after editor approval.
---

# Newsletter Anniversary

Use this skill when the user wants to compose, update, or finalize the closing anniversary paragraph for RSoW or BBtn.

Use `../_shared/reference/vault-structure.md`, `../_shared/reference/newsletter-context.md`, `../_shared/reference/section-map.md`, `../_shared/reference/publication-date.md`, and `../_shared/reference/approval-workflow.md` for shared vault, language, placeholder, publication-date, and approval rules.

## Inputs

- Optional source notes are in `00 Inbox/07 Anniversary`.
- The target issue folder is either `02 RSoW/rsow-###/` or `01 BBtn/bbtn-###/`.
- The target section folder is `07 Anniversary` inside the issue folder.
- The target section folder note is `_07 Anniversary.md`.
- The issue folder note is `_rsow-###.md` or `_bbtn-###.md`.

When the issue number or newsletter is ambiguous, infer it from the existing vault structure when safe. Ask the human editor only when the target issue cannot be identified.

## Publication Date

- Infer the publication date using `../_shared/reference/publication-date.md`.

## Required Reading

Before writing output:

1. Read relevant files in `00 Inbox/07 Anniversary` if present.
2. Identify the target newsletter and publication date.
3. If the inbox contains suitable anniversary source material, verify the linked source.
4. If the inbox does not contain suitable anniversary source material, open the relevant Wikipedia day page:
   - BBtn: `https://en.wikipedia.org/wiki/{{Month}}_{{day}}`, for example `https://en.wikipedia.org/wiki/March_23`.
   - RSoW: `https://cs.wikipedia.org/wiki/{{den}}._{{měsíc}}`, for example `https://cs.wikipedia.org/wiki/23._březen`.
5. Review events for the publication day.
6. Verify the selected event through its linked article or another reliable source when possible.

If the day page cannot be opened, search the web for the publication date and anniversary candidates. Ask the human editor only when no responsible candidate can be found.

## Anniversary Selection

- Prefer round anniversaries: 10, 20, 25, 30, 40, 50, 60, 75, 100, 125, 150, 200, and similar memorable numbers.
- Prefer positive, constructive, curious, cultural, scientific, technological, design, web, media, transport, or everyday-life events.
- Avoid deaths, murders, assassinations, wars, disasters, oppression, crimes, and similarly negative events.
- Avoid anniversaries that require too much grim context to explain.
- A mildly odd, charming, or surprising anniversary is welcome when it fits the newsletter voice.
- If no round positive anniversary exists, choose the best positive event and mention the exact number of years.
- Do not invent anniversary facts or dates.

## Working Output

The first output is for human editorial processing. Write it to the section folder note:

- RSoW example: `02 RSoW/rsow-112/07 Anniversary/_07 Anniversary.md`
- BBtn example: `01 BBtn/bbtn-112/07 Anniversary/_07 Anniversary.md`

Create the issue section folder and folder note if missing. This is a non-destructive structure completion.

The working output uses the same approval logic as Opinion. Add front matter:

```yaml
---
approved: waiting
---
```

### RSoW Working Output

```markdown
---
approved: waiting
---

A to je ze zpravodaje [Řekni si o web](https://reknisioweb.cz/) všechno. **{{Zmínka o výročí s odkazem}}.** Díky, že nás nejen čtete, ale také o sobě dáváte vědět. Pokud pro nás máte nějaký tip, co příště vylepšit nebo udělat jinak, těšíme se.
```

### BBtn Working Output

```markdown
---
approved: waiting
---

That’s all from the Better Button newsletter. **{{Anniversary mention including the link}}.** Thanks for reading and sharing. If you have tips for next issues, we’d love to hear them.
```

Do not add a section heading. The `{{Anniversary}}` placeholder represents the closing paragraph itself.

## Paragraph Style

- Write exactly one closing paragraph.
- Use the provided RSoW and BBtn paragraph templates unless the editor’s existing issue text clearly requires a small issue-specific variation.
- Put the anniversary mention in bold.
- Include a link in the anniversary mention.
- Keep the anniversary sentence short and readable.
- For RSoW, write Czech naturally and prefer Czech typography.
- For BBtn, write English naturally and prefer English typography.
- Do not use bullets.

## Updating Existing Working Output

If the section folder note already exists:

- Preserve human edits wherever possible.
- Do not overwrite an edited paragraph unless the user explicitly asks for a fresh rewrite.
- Preserve existing front matter.
- If front matter has no `approved` property, add `approved: waiting`.
- Keep `approved: approved`, `approved: true`, or `approved: "true"` unchanged.
- Update the paragraph only when the publication date, source material, or user request requires it.

## Final Newsletter Output

When converting the working output into the final issue newsletter:

- Read the target section folder note.
- Use the paragraph only when front matter contains `approved: approved`, `approved: true`, or `approved: "true"`.
- If `approved` is missing, `waiting`, `false`, or any other value, do not insert the paragraph into the final issue.
- Replace `{{Anniversary}}` in the issue folder note with the approved paragraph.
- Remove YAML front matter before inserting the paragraph.
- Preserve links, emphasis, non-breaking spaces, and editor wording.

## Source Handling

- Work independently as much as practical.
- Do not ask the human editor to find anniversaries manually if the inbox, Wikipedia day page, or web search can be inspected.
- Ask the human editor only when the target issue, publication date, or suitable anniversary cannot be identified.
- After creating or updating the working output, move source files that were used from `00 Inbox/07 Anniversary` into the issue folder's `07 Anniversary` subfolder.
- Leave unused source files in their original location.
- Never archive source files from this workflow.
- At the end of the task, summarize the publication date, source used, selected anniversary, rejected notable negative candidates if relevant, created or updated files, approval state, and editor attention points.

## Style Reference

Use `reference/anniversary-examples.md` for compact examples extracted from `resources/examples/rsow/` and `resources/examples/bbtn/`. Treat `resources/examples/` as the canonical source if more examples are needed.
