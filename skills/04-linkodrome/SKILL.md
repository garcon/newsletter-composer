---
name: newsletter-linkodrome
description: Compose the RSoW Linkodrom or BBtn Linkodrome section from Obsidian inbox notes, verify linked sources and authors, prepare an editorial checklist, and later convert accepted items into the final newsletter format.
---

# Newsletter Linkodrome

Use this skill when the user wants to compose, update, or finalize the `Linkodrom` section for RSoW or the `Linkodrome` section for BBtn.

Use `../_shared/reference/vault-structure.md`, `../_shared/reference/newsletter-context.md`, and `../_shared/reference/section-map.md` for shared vault, language, placeholder, and folder rules.

## Inputs

- RSoW source notes are in `00 Inbox/04 Linkodrome`.
- BBtn source notes are in `00 Inbox/04 Linkodrome`.
- The target issue folder is either `02 RSoW/rsow-###/` or `01 BBtn/bbtn-###/`.
- The target section folder is `04 Linkodrome` inside the issue folder.
- The target section folder note is `_04 Linkodrome.md`.
- The issue folder note is `_rsow-###.md` or `_bbtn-###.md`.

When the issue number or newsletter is ambiguous, infer it from the existing vault structure when safe. Ask the human editor only when the target issue cannot be identified.

## Required Reading

Before writing output:

1. Read every file in `00 Inbox/04 Linkodrome`, including Markdown notes and non-Markdown asset notes when possible.
2. Extract every URL from every source file.
3. Open every extracted URL using an available browsing tool, MCP server, or local computer tool.
4. Use the linked source as the primary factual basis for the summary.
5. Try to identify the author or authors of each summarized source.
6. Keep a source link for every summary item.

If a URL cannot be opened, still process the note if it contains enough context, but mark the item for editor attention in the working output. If the author cannot be identified after reasonable effort, omit the author rather than inventing one.

## Source Handling

- Work independently as much as practical.
- Do not ask the human editor to read links or summarize source material.
- Ask the human editor only when a source file cannot be interpreted, when link access fails and the note has insufficient context, or when a file in the inbox has no clear relation to the section.
- After creating or updating the working output, move the source files that were used from `00 Inbox/04 Linkodrome` into the issue folder's `04 Linkodrome` subfolder.
- Leave unused source files in their original location.
- Never archive source files from this workflow.

## Language

- For RSoW, write summaries in Czech.
- For BBtn, write summaries in English.
- For BBtn, omit items that are only relevant to Czech readers and have no useful value for an international audience.

## Summary Style

- Each item summarizes one linked source or one tightly related source bundle.
- Ideal summary length is about 250 characters.
- Maximum summary length is 450 characters.
- Start with an inline heading in bold.
- The first bold phrase does not have to be a complete sentence.
- When there is a good editorial reason, only the strongest part of the first sentence may be bold.
- After the bold opening, write a concise explanatory summary in complete sentences.
- Try to mention the author or authors in the summary when they can be identified.
- Italicize names of people, companies, products, services, and brands.
- Keep source links on the most relevant words.
- Choose link text that makes sense even when read on its own.
- Use dry humor and mild snark when it helps, but never be mean, cruel, or malicious.
- Do not invent facts, author names, dates, or source claims.
- Do not use emoji as bullets in this section.

## Ordering

Order the list by editorial importance:

1. Most important information first.
2. Newsletter context first, especially Czech context for RSoW.
3. UX, web business, digital product, and internet business items above general technology items.
4. Fun or curiosity items near the end.
5. Quotes, memes, and image-only items may be interleaved when they improve the rhythm of the section.

## Working Output

The first output is for human editorial processing. Write it to the section folder note:

- RSoW example: `02 RSoW/rsow-112/04 Linkodrome/_04 Linkodrome.md`
- BBtn example: `01 BBtn/bbtn-112/04 Linkodrome/_04 Linkodrome.md`

Create the issue section folder and folder note if missing. This is a non-destructive structure completion.

Use a checked Markdown task list. Items are checked by default. The human editor may rewrite summaries, change links, reorder items, add text, or uncheck items. Unchecked items must not be copied into the final issue text.

### RSoW Working Output

```markdown
## Linkodrom

- [x] **{{tučný inline nadpis}}** {{shrnutí s autorem/autorkou a odkazy}}
- [x] **{{tučný inline nadpis}}** {{shrnutí s autorem/autorkou a odkazy}}
- [x] **{{tučný inline nadpis}}** {{shrnutí s autorem/autorkou a odkazy}}
```

### BBtn Working Output

```markdown
## Linkodrome

- [x] **{{bold inline heading}}** {{summary with author and links}}
- [x] **{{bold inline heading}}** {{summary with author and links}}
- [x] **{{bold inline heading}}** {{summary with author and links}}
```

## Updating Existing Working Output

If the section folder note already exists:

- Preserve human edits wherever possible.
- Keep existing checked and unchecked states.
- Do not overwrite rewritten summaries.
- Add newly discovered items as checked items unless there is a clear reason to mark them for editor attention.
- Preserve editor ordering unless the user explicitly asks for reordering.
- Remove an item only when its source file is no longer relevant and removal is clearly requested.

## Final Newsletter Output

When converting the editorial checklist into the final issue newsletter:

- Use only checked `- [x]` items.
- Remove task list markers.
- Put every item in its own paragraph.
- Preserve bold inline headings, links, italics, quotes, images, and editor wording.
- Do not add bullets.
- Do not add emoji bullets.
- Remove unchecked items.
- Replace `{{Linkodrom}}` in RSoW issue templates with the complete edited `## Linkodrom` section.
- Replace `{{Linkodrome}}` in BBtn issue templates with the complete edited `## Linkodrome` section.

Final item example:

```markdown
**Nápady jsou levné, provedení je také levné.** *Dave Kiss* píše, že v éře LLM nástrojů už není rozhodující umět kódovat, ale rychle iterovat, mít vkus a umět vybrat správný problém.
```

## Style Reference

Use `reference/linkodrome-examples.md` for compact examples extracted from `resources/examples/rsow/` and `resources/examples/bbtn/`. Treat `resources/examples/` as the canonical source if more examples are needed.
