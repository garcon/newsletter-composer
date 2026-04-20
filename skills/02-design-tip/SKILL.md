---
name: newsletter-design-tip
description: Compose the RSoW Designérský tip or BBtn Designer’s Tip section from one text input and one image input, prepare a working section for human editing, and later copy the accepted section into the final newsletter issue.
---

# Newsletter Design Tip

Use this skill when the user wants to compose, update, or finalize the `Designérský tip` section for RSoW or the `Designer’s Tip` section for BBtn.

Use `../_shared/reference/vault-structure.md`, `../_shared/reference/newsletter-context.md`, and `../_shared/reference/section-map.md` for shared vault, language, placeholder, and folder rules.

## Inputs

- RSoW source notes are in `00 Inbox/02 Designer’s Tip`.
- BBtn source notes are in `00 Inbox/02 Designer’s Tip`.
- The inbox should contain one text source and usually one image source for the section.
- The target issue folder is either `02 RSoW/rsow-###/` or `01 BBtn/bbtn-###/`.
- The target section folder is `02 Designer’s Tip` inside the issue folder.
- The target section folder note is `_02 Designer’s Tip.md`.
- The issue folder note is `_rsow-###.md` or `_bbtn-###.md`.

When the issue number or newsletter is ambiguous, infer it from the existing vault structure when safe. Ask the human editor only when the target issue cannot be identified.

## Required Reading

Before writing output:

1. Read every file in `00 Inbox/02 Designer’s Tip`.
2. Identify the text source and the image source.
3. Inspect the image when an available local image tool, MCP server, browser tool, or vision-capable model can open it.
4. Extract every URL from the text source and image-adjacent notes.
5. Open every extracted URL using an available browsing tool, MCP server, or local computer tool.
6. Use source links as the primary factual basis for claims in the section.

If a URL cannot be opened, still process the source if it contains enough context, but mark the item for editor attention in the working output.

## Source Handling

- Work independently as much as practical.
- Do not ask the human editor to read links or summarize source material.
- Ask the human editor only when the text source cannot be interpreted, an image alt text cannot be produced independently, link access fails and the note has insufficient context, or a file in the inbox has no clear relation to the section.
- After creating or updating the working output, move the source files that were used from `00 Inbox/02 Designer’s Tip` into the issue folder's `02 Designer’s Tip` subfolder.
- Move any generated or downloaded `assets` folder together with the section folder content whenever moving the working output or source bundle between folders.
- Leave unused source files in their original location.
- Never archive source files from this workflow.
- At the end of the task, summarize what sources were used, what files were moved or created, what image asset was saved, and any remaining editor attention points.

## Language

- For RSoW, write the section in Czech.
- For BBtn, write the section in English.
- For BBtn, localize Czech-only context for an international audience or omit it when it has no useful value.

## Section Style

- Preserve the practical design advice from the text source.
- Keep the section concise, concrete, and editorially useful.
- Reformat the tip into the required working-output template even when the source is not already written that way.
- Start with the image when an image is available.
- Use one short bold opening recommendation followed by its explanation in the same paragraph.
- Include one incorrect result and one desired result.
- Include two user benefits.
- End with one short sentence that states the result of applying the tip.
- Use dry humor and mild snark only when it helps, but never be mean, cruel, or malicious.
- Italicize names of people, companies, products, services, and brands.
- Keep source links on the most relevant words.
- Do not invent facts, examples, or claims not supported by the text source, image, or linked sources.
- Avoid generic design platitudes unless the input specifically supports them.

## Image Handling

- If the source contains an image, download or copy it into an `assets` subfolder inside the target section folder.
- If the target section folder is `02 RSoW/rsow-112/02 Designer’s Tip`, save image assets under `02 RSoW/rsow-112/02 Designer’s Tip/assets/`.
- Reference saved images with standard Markdown image syntax, for example `![{{ALT text}}](assets/{{image-name.png}})`.
- If the image is already a remote Markdown image, download it to the local `assets` folder and update the Markdown image URL to the local asset path.
- Keep useful alt text when it exists.
- If the image source is missing, prepare the working output without an image and briefly mention this in the final summary to the human editor.
- If the image needs alt text and none is provided, create concise descriptive alt text in the working output based on the examples in `reference/rsow-design-tip-examples.md`.
- To create missing alt text, first inspect the image directly or use an available MCP server or vision-capable model that can understand the image.
- If no local or MCP vision route is available, the agent may open ChatGPT in a browser and ask for alt text in a temporary chat.
- Ask the human editor for alt text only as the last resort.
- Do not edit or generate image assets unless the user explicitly asks for that.

## Working Output

The first output is for human editorial processing. Write it to the section folder note:

- RSoW example: `02 RSoW/rsow-112/02 Designer’s Tip/_02 Designer’s Tip.md`
- BBtn example: `01 BBtn/bbtn-112/02 Designer’s Tip/_02 Designer’s Tip.md`

Create the issue section folder and folder note if missing. This is a non-destructive structure completion.

The human editor may rewrite the text, change links, replace the image, or otherwise edit the working output. Preserve those edits when updating existing working output.

### RSoW Working Output

```markdown
## Designérský tip

![{{ALT text}}]({{adresa obrázku}})

**{{Hlavní tip}}** {{Vysvětlení tipu}}

❌ {{Chybný výsledek}}\
✅ {{Požadovaný výsledek}}

👉 {{Benefit pro uživatele}}\
👉 {{Další benefit}}

{{Výsledek uplatnění tipu}}
```

If the source image is missing, omit the image line:

```markdown
## Designérský tip

**{{Hlavní tip}}** {{Vysvětlení tipu}}

❌ {{Chybný výsledek}}\
✅ {{Požadovaný výsledek}}

👉 {{Benefit pro uživatele}}\
👉 {{Další benefit}}

{{Výsledek uplatnění tipu}}
```

### BBtn Working Output

```markdown
## Designer’s Tip

![{{Alt text}}]({{image URL}})

**{{Main tip}}** {{Explanation of the tip}}

❌ {{Incorrect result}}\
✅ {{Desired result}}

👉 {{User benefit}}\
👉 {{Additional benefit}}

{{Result of applying the tip}}
```

Older BBtn examples in `resources/examples/bbtn/` may use the heading `From The Designer`. Treat them as historical style references only. New BBtn working and final outputs use `Designer’s Tip`.

If the source image is missing, omit the image line:

```markdown
## Designer’s Tip

**{{Main tip}}** {{Explanation of the tip}}

❌ {{Incorrect result}}\
✅ {{Desired result}}

👉 {{User benefit}}\
👉 {{Additional benefit}}

{{Result of applying the tip}}
```

## Updating Existing Working Output

If the section folder note already exists:

- Preserve human edits wherever possible.
- Do not overwrite rewritten copy.
- Do not replace the image or its `assets` entry unless the source image changed or the user asks for it.
- Keep the local asset path stable when possible.
- Add editor notes only when a source is missing, ambiguous, or unverifiable.
- Remove content only when its source file is no longer relevant and removal is clearly requested.

## Final Newsletter Output

When converting the edited working section into the final issue newsletter:

- Copy the edited section from the section folder note into the issue folder note.
- Replace `{{Designérský tip}}` in RSoW issue templates with the complete edited `## Designérský tip` section.
- Replace `{{Designer’s Tip}}` in BBtn issue templates with the complete edited `## Designer’s Tip` section.
- Preserve Markdown image syntax, links, paragraphs, emphasis, and editor wording.
- Preserve local `assets` paths and make sure the referenced image remains in the issue section folder's `assets` subfolder.
- Remove internal editor notes before inserting the section into the final issue.
- Do not translate or rewrite the human-edited working output unless the user explicitly asks for that.

## Style Reference

Use `reference/rsow-design-tip-examples.md` for compact Czech examples extracted from `resources/examples/rsow/`. Treat `resources/examples/` as the canonical source if more examples are needed. For BBtn, translate the same structure into natural English under `## Designer’s Tip`.
