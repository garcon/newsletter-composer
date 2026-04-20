# Vault Structure

Use this shared structure for every newsletter skill that reads inbox material, creates issue folders, moves source notes, or writes section folder notes.

## Top-Level Folders

- `00 Inbox` - source notes and inputs for composing newsletters.
- `01 BBtn` - Better Button issues.
- `02 RSoW` - Řekni si o web issues.
- `03 Archives` - postponed notes. Archive only after an explicit human editor request.
- `04 Resources` - shared resources for all newsletter issues.
- `99 Service` - templates and operational notes for editors.

## Inbox Folders

- `01 In a Nutshell`
- `02 Designer’s Tip`
- `03 Opinion`
- `04 Linkodrome`
- `05 Articles`
- `06 Events`
- `07 Anniversary`

Files may also be stored directly in `00 Inbox`. If a directly stored file has no clear use, ask the human editor before moving or changing it.

## Issue Folders

- RSoW issues are stored in `02 RSoW/rsow-###/`.
- BBtn issues are stored in `01 BBtn/bbtn-###/`.
- Each issue folder has a folder note named with a leading underscore, for example `_rsow-112.md` or `_bbtn-112.md`.
- The final newsletter text is written in the issue folder note.
- Each issue folder contains section subfolders matching the inbox folder names.
- Section folder notes also use the folder name with a leading underscore, for example `_04 Linkodrome.md`.
- Skills move used source notes into the matching issue section folder.
- Unused source notes remain in their original location.
- Never archive or delete source notes unless the human editor explicitly asks for archiving.

## Structure Repair

- If the vault is empty, create the basic structure without asking; this is non-destructive.
- If a required folder or folder note is missing, create it when needed; this is non-destructive.
- If existing structure conflicts with the expected structure in a way that could lose or misplace content, stop and ask the human editor.
- After creating or repairing structure, summarize what changed.

## Templates

- Issue templates normally come from `99 Service/Templates/`.
- RSoW template: `99 Service/Templates/RSoW Template.md`.
- BBtn template: `99 Service/Templates/BBtn Template.md`.
- If a vault template is missing, use the bundled templates in `skills/00-basic-structure/`.
