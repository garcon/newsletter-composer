---
name: newsletter-vault-structure
description: Check, initialize, or repair the expected Obsidian vault structure for the RSoW and Better Button newsletter workflow, including top-level folders, inbox section folders, service template folders, and non-destructive folder notes.
---

# Newsletter Vault Structure

Use this skill when the user wants to check, initialize, create, repair, or audit the Obsidian vault structure used by the newsletter workflow.

Use `../_shared/reference/vault-structure.md` and `../_shared/reference/section-map.md` as the canonical runtime rules.

## Scope

This skill may create missing folders and missing empty folder notes. It may copy bundled issue templates into the vault when template files are missing.

This skill must not delete, archive, rename, overwrite, or move existing user files unless the user explicitly asks for that specific operation.

## Required Reading

Before changing anything:

1. Read `../_shared/reference/vault-structure.md`.
2. Read `../_shared/reference/section-map.md`.
3. Inspect the current working directory and treat it as the Obsidian vault root unless the user provides another path.
4. Check whether the directory appears to be an Obsidian vault. Prefer the presence of `.obsidian/`, but do not require it for an empty new vault.
5. Inventory the expected top-level folders, inbox folders, service template folder, and existing issue folders.

If the current directory is clearly not the intended vault and is not empty, ask the human editor before creating anything.

## Expected Structure

Top-level folders:

```text
00 Inbox
01 BBtn
02 RSoW
03 Archives
04 Resources
99 Service
```

Inbox folders:

```text
00 Inbox/01 In a Nutshell
00 Inbox/02 Designer’s Tip
00 Inbox/03 Opinion
00 Inbox/04 Linkodrome
00 Inbox/05 Articles
00 Inbox/06 Events
00 Inbox/07 Anniversary
```

Service template folder:

```text
99 Service/Templates
```

Service templates:

```text
99 Service/Templates/RSoW Template.md
99 Service/Templates/BBtn Template.md
```

## Folder Notes

- Folder notes use the folder name with a leading underscore.
- For top-level folders, create `_00 Inbox.md`, `_01 BBtn.md`, and so on only when the editor asks for full folder-note initialization or when the vault already uses this convention.
- For inbox section folders, create notes such as `_01 In a Nutshell.md` only when the editor asks for full folder-note initialization or when the vault already uses this convention.
- For issue folders and issue section folders, create folder notes when creating or repairing a specific issue structure.
- Never overwrite an existing folder note.

## Issue Structure Creation

If the user asks to create or repair a specific issue:

1. Identify newsletter and issue number.
2. Create `02 RSoW/rsow-###/` for RSoW or `01 BBtn/bbtn-###/` for BBtn.
3. Create the issue folder note `_rsow-###.md` or `_bbtn-###.md` if missing.
4. Create `TEMPLATE.md` in the issue folder if missing.
5. Create all section subfolders from the section map.
6. Create section folder notes with leading underscores if missing.

Use the vault service template when available. If the service template is missing, use the bundled template:

- `../00-basic-structure/rsow-template.md`
- `../00-basic-structure/bbtn-template.md`

When creating an issue folder note for the first time, copy the issue `TEMPLATE.md` content into it unless the user asks for an empty folder note.

## Service Templates

If `99 Service/Templates/RSoW Template.md` or `99 Service/Templates/BBtn Template.md` is missing, create it from the bundled template. Do not overwrite existing templates.

## Audit Output

When checking the vault, report:

- Current vault root.
- Whether `.obsidian/` was found.
- Missing top-level folders.
- Missing inbox folders.
- Missing service templates.
- Existing issue folders found.
- Any structure conflicts or suspicious paths.
- Actions taken.
- Actions skipped because they would be destructive or ambiguous.

## Safety

- Create missing directories with normal filesystem operations.
- Create missing Markdown notes only when their target path does not exist.
- Treat any path conflict, such as a file where a folder should be, as a blocker and ask the human editor.
- Do not use recursive delete, move, rename, or archive operations.
- Do not modify Obsidian configuration files unless the user explicitly asks.
