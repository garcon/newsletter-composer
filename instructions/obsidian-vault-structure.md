# Obsidian Vault Structure

The `00-basic-structure` skill should assume the Obsidian vault uses these top-level folders:

- `00 Inbox` - source notes and inputs for composing newsletters.
- `01 BBtn` - issues of the Better Button newsletter.
- `02 RSoW` - issues of the Rekni si o web newsletter.
- `03 Archives` - notes postponed for archiving. Archiving is initiated only by a live editor and must never happen without explicit permission from a human operator.
- `04 Resources` - shared resources for all newsletter issues. The plugin may use this folder to store resources useful across newsletter editions.
- `99 Service` - service folder for templates and operational notes. The plugin may use this folder to store service files intended for live editors.

## `00 Inbox` Structure

The `00 Inbox` folder contains source material for newsletter sections. Its subfolders map to RSoW and BBtn sections as follows:

- Files and folders may also be stored directly in `00 Inbox`, not only in its listed subfolders. These can include newsletter assets such as meme images, email headers, footers, and other supporting material.
- If the agent does not know how to use a file stored directly in `00 Inbox`, it should ask the human editor about the appropriate use.
- `01 Telegraph` - source material for `RSoW/Telegraficky` and `BBtn/Telegraph`.
- `02 Designer's tip` - source material for `RSoW/Designérský tip` and `BBtn/Designer's tip`.
- `03 Opinion` - source material for essays inserted into `RSoW/Opinion` and `BBtn/Opinion`.
- `04 Linkodrome` - source material for `RSoW/Linkodrom` and `BBtn/Linkodrome`.
- `05 Articles` - overview of published articles for `RSoW/Vyšlo na ŘSoW` and `BBtn/Published on BBtn`.
- `06 Events` - source material for planned events in `RSoW/Events` and `BBtn/Events`.
- `07 Anniversary` - source material for current anniversaries in `RSoW/Anniversary` and `BBtn/Anniversary`.

## Newsletter Issue Folders

- Individual RSoW issues are stored in `02 RSoW`.
- Individual BBtn issues are stored in `01 BBtn`.
- Each issue has its own subfolder.
- RSoW issue folders are named `rsow-###`, where `###` is the issue number.
- BBtn issue folders are named `bbtn-###`, where `###` is the issue number.
- Each folder has a folder note. The folder note filename matches the folder name with a leading `_`.
- The final newsletter text is written in the folder note of the issue folder.
- Example: RSoW issue 100 is stored in `02 RSoW/rsow-100/_rsow-100.md`.
- Each issue folder contains subfolders matching the same structure as `00 Inbox`.
- Skills move source notes used for composing an issue into the matching subfolders inside that issue folder.
- Source notes that are not used remain in their original location.
- All subfolders also have folder notes.
- Folder note naming is always consistent: folder name with a leading `_`.

## Newsletter Templates

- Each issue folder stores the template used for writing that issue as `TEMPLATE.md`.
- Issue templates are derived from templates stored in `99 Service/Templates/`.
- The RSoW vault template is `99 Service/Templates/RSoW Template.md`.
- The BBtn vault template is `99 Service/Templates/BBtn Template.md`.
- If the expected vault template is missing, derive the issue template from the template bundled with the skill.
- In the plugin file structure, the bundled RSoW template is named `rsow-template.md`.
- In the plugin file structure, the bundled BBtn template is named `bbtn-template.md`.
- Template derivation rules belong in the relevant skill, and agents must follow them.

## Vault Structure Handling

- If the vault folder structure does not match the expected basic structure, the agent must notify the human editor.
- If the vault is empty, the agent may create the basic structure without asking for permission, because this is considered a non-destructive action. Afterward, it must inform the human editor and summarize what it created.
- If any item from the basic vault structure is missing, the agent may add it without asking for permission, because this is considered a non-destructive action. Afterward, it must inform the human editor and summarize what it added.
- Agents should work as independently as practical and should not request human editor intervention unnecessarily.
- Agents may proceed independently when creating missing structure, provided the action is non-destructive.
- After any autonomous structure creation or repair, the agent must summarize the completed changes for the human editor.

## Obsidian Plugin Requirements

The basic vault setup should include at least these Obsidian community plugins:

- Dataview, with JavaScript queries and inline queries enabled. Plugin URL: `obsidian://show-plugin?id=dataview`.
- Definition list. Plugin URL: `obsidian://show-plugin?id=definition-list`.
- Folder notes, configured so folder note filenames start with an underscore `_`. Plugin URL: `obsidian://show-plugin?id=folder-notes`.
- Local REST API, so Obsidian can be used as a server. Plugin URL: `obsidian://show-plugin?id=obsidian-local-rest-api`.
- QuickAdd, for quickly creating notes. Plugin URL: `obsidian://show-plugin?id=quickadd`.
- Regex Find/Replace, for convenient replacements using regular expressions. Plugin URL: `obsidian://show-plugin?id=obsidian-regex-replace`.
- Templater, for more advanced templates. Plugin URL: `obsidian://show-plugin?id=templater-obsidian`.

The Obsidian core plugins Publish and Sync should be disabled.
The vault may have other plugins enabled unless they are explicitly forbidden.
