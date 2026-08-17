---
name: newsletter-anniversary
description: Compose the RSoW or BBtn closing community and signature paragraph that ends the newsletter after the main sections.
---

# Newsletter Closing Note

Use this skill when the user wants to compose, update, or finalize the closing community and signature paragraph for RSoW or BBtn.

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
3. If the inbox contains suitable closing-note source material, verify the linked source.
4. If the inbox does not contain suitable source material, use the draft issue voice and the newsletter context to craft the final closing note.
5. Keep the signature feature in mind for BBtn: the newsletter is written in the heart of Europe, from Prague, with a European view on websites and apps.
6. End BBtn with a Prague invitation when the issue voice allows it.

If the source material cannot be interpreted, ask the human editor only when no responsible closing note can be written.

## Closing Note Selection

- Keep the closing note short, friendly, and editorially useful.
- For RSoW, mention what the team is doing or inviting readers to do next, in Czech.
- For BBtn, keep the European framing explicit and use Prague as part of the newsletter identity.
- For BBtn, include the Prague beer invitation in the final line when appropriate.
- If the issue already contains a survey, community question, or CTA, keep it concise and clear.
- Do not invent facts, offers, or event claims.

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

## Co děláme my / Co děláte vy

{{závěrečná věta nebo odstavec v češtině}}
```

### BBtn Working Output

```markdown
---
approved: waiting
---

## What we do / What you do

{{closing paragraph in English}}
```

## Paragraph Style

- Write exactly one closing paragraph.
- Keep the call to action concrete and short.
- For RSoW, use Czech naturally and keep the tone warm but direct.
- For BBtn, write in English with the European framing explicit and the Prague signature visible.
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
- Replace `{{Co děláme my / Co děláte vy}}` or `{{What we do / What you do}}` in the issue folder note with the approved paragraph.
- Remove YAML front matter before inserting the paragraph.
- Preserve links, emphasis, non-breaking spaces, and editor wording.

## Source Handling

- Work independently as much as practical.
- Do not ask the human editor to find a closing note manually if the inbox or issue voice can be inspected.
- Ask the human editor only when the target issue, publication date, or suitable closing note cannot be identified.
- After creating or updating the working output, move source files that were used from `00 Inbox/07 Anniversary` into the issue folder's `07 Anniversary` subfolder.
- Leave unused source files in their original location.
- Never archive source files from this workflow.
- At the end of the task, summarize the publication date, source used, selected closing note, created or updated files, approval state, and editor attention points.

## Style Reference

Use `reference/anniversary-examples.md` for compact examples extracted from `resources/examples/rsow/` and `resources/examples/bbtn/` only as historical guidance. For the new default layout, prefer the closing-note voice defined above.
