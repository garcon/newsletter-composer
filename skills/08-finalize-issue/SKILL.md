---
name: newsletter-finalize-issue
description: Assemble a RSoW or BBtn issue by replacing template placeholders with prepared section outputs, using only approved front-matter sections and checked checklist items.
---

# Newsletter Finalize Issue

Use this skill when the user wants to assemble, finalize, or check a complete RSoW or BBtn issue from prepared section folder notes.

## Required Reading

Before editing the issue folder note:

1. Read `../_shared/reference/vault-structure.md`.
2. Read `../_shared/reference/section-map.md`.
3. Read `../_shared/reference/approval-workflow.md`.
4. Read the issue folder note, such as `_rsow-###.md` or `_bbtn-###.md`.
5. Read each section folder note that corresponds to a placeholder still present in the issue folder note.
6. Preserve human edits in both the issue folder note and section folder notes.

## Inputs

- RSoW issues are in `02 RSoW/rsow-###/`.
- BBtn issues are in `01 BBtn/bbtn-###/`.
- The final newsletter text is written in the issue folder note.
- Section folder notes are named from the section folder with a leading underscore.

When the target issue is ambiguous, infer it from the existing vault structure when safe. Ask the human editor only when the target issue cannot be identified.

## Section Insertion Rules

Use the section map for placeholders and section folders.

For checklist sections:

- `01 In a Nutshell`
- `04 Linkodrome`
- `05 Articles`

Use only checked `- [x]` items. Remove task list markers before insertion. Preserve links, emphasis, images, paragraphs, and editor wording. Do not insert unchecked items.

For direct working-output sections:

- `02 Designer’s Tip`

Insert the edited section folder note body as-is, unless the skill-specific instructions say otherwise.

For approved front-matter sections:

- `03 Opinion`
- `06 Events`
- `07 Anniversary`

Use `../_shared/reference/approval-workflow.md`. Insert only approved outputs. Remove YAML front matter before insertion.

## Placeholder Handling

- Replace only known placeholders from `../_shared/reference/section-map.md`.
- Leave unknown placeholders unchanged and report them.
- Leave unapproved approved-gated section placeholders unchanged and report them.
- After insertion, check whether any `{{...}}` placeholders remain in the issue folder note.
- Do not delete unresolved placeholders silently.

## Output Shape

- Keep section headings that are part of section outputs.
- Do not add headings for Events or Anniversary unless the section folder note already contains one.
- Keep checklist-derived Linkodrome and Articles items as paragraphs without bullets.
- Keep In a Nutshell final items on separate lines with Markdown line breaks as defined by its skill.

## Verification

After finalizing:

- Report which placeholders were replaced.
- Report which placeholders were left unresolved and why.
- Report which approved-gated sections were approved or waiting.
- Report any missing section folder notes.
- Report any remaining `{{...}}` placeholders.
