---
name: newsletter-articles
description: Compose the RSoW Vyšlo na ŘSoW or BBtn Published on BBtn section by listing articles published on the relevant site since the previous newsletter and summarizing them in the Linkodrom/Linkodrome style without inline headings or author mentions.
---

# Newsletter Articles

Use this skill when the user wants to compose, update, or finalize the `Vyšlo na ŘSoW` section for RSoW or the `Published on BBtn` section for BBtn.

Use `instructions/publication-date.md` for the previous/current issue date interval and `instructions/section-map.md` for canonical placeholders and folder names.

## Inputs

- Source notes or article overviews are in `00 Inbox/05 Articles`.
- RSoW article sources are published on `https://www.reknisioweb.cz/`.
- BBtn article sources are published on `https://better-button.com/`.
- The target issue folder is either `02 RSoW/rsow-###/` or `01 BBtn/bbtn-###/`.
- The target section folder is `05 Articles` inside the issue folder.
- The target section folder note is `_05 Articles.md`.
- The issue folder note is `_rsow-###.md` or `_bbtn-###.md`.

When the issue number or newsletter is ambiguous, infer it from the existing vault structure when safe. Ask the human editor only when the target issue cannot be identified.

## Required Reading

Before writing output:

1. Read every file in `00 Inbox/05 Articles`, including Markdown notes, CSV exports, feed snapshots, and non-Markdown asset notes when possible.
2. Identify the target newsletter and current issue.
3. Identify the previous published newsletter issue for the same site.
4. List all articles published on the relevant site in the interval `(previous_issue_published, current_issue_published]`.
5. Open every article URL using an available browsing tool, MCP server, local feed export, CSV export, or local computer tool.
6. Use the article itself as the primary factual basis for the summary.
7. For profile articles, find the original article illustration and include it before the profile summary.

If the publication range cannot be identified from local files, inspect the website, RSS feed, archive page, or any available export. Ask the human editor only when the date range or target issue cannot be resolved responsibly.

Preferred sources for determining the publication range and article list:

1. Current and previous issue folder note front matter, especially `published`.
2. Local exports such as `resources/examples/*/posts.csv` or inbox CSV files.
3. Site RSS feeds, archive pages, or article indexes.
4. Direct website inspection or web search.

## Article Selection

- Include every article published on the relevant site after the previous newsletter issue and on or before the current issue publication date.
- Exclude newsletter issues themselves.
- Exclude drafts, unpublished items, events, or social posts unless they are published as regular site articles.
- If an article was updated after the previous newsletter but originally published earlier, include it only when the update is editorially substantial and clearly relevant.
- If no articles were published in the period, create the working output with the section heading and an editor note explaining that no matching articles were found.

## Article Types And Ordering

Order selected articles in this sequence:

1. Profiles of people.
2. Expert terms, glossary entries, principles, methods, or concepts.
3. Tools, utilities, products, resources, or practical services.

Within each group, prefer editorial importance and usefulness over strict chronology. Keep closely related items together when it helps readability.

## Summary Style

- Create summaries in the style of Linkodrom/Linkodrome, but without a bold inline heading.
- Do not mention article authors.
- Ideal summary length is about 250 characters.
- Maximum summary length is 450 characters.
- Start with the expression that best identifies the article.
- The opening expression is usually a person’s name, expert term, glossary term, method, tool name, or product name.
- Link that opening expression to the article.
- For person profiles, italicize the linked name, for example `*[Lucy Suchman](https://www.reknisioweb.cz/p/lucy-suchman)*`.
- For glossary terms and tools, link the term or tool name at the start.
- Write in complete sentences after the linked opening expression.
- Do not create a bold inline heading.
- Do not add author names.
- Do not use emoji bullets.
- Do not invent facts, categories, or publication dates.

## Images

- Before the first person profile, include the illustration image from the original profile article.
- If more than one person profile is included, include each profile’s original illustration before that profile unless the editor’s existing output already uses a different arrangement.
- Preserve useful alt text from the original article.
- If the original article has an image but no useful alt text, create a concise descriptive alt text.
- Use the image URL from the original article unless the local workflow already stores article images in an `assets` folder.
- Do not add images for glossary terms or tools unless the source article’s structure clearly requires it.
- If no person profile is included, do not add an image solely for decoration.

## Language

- For RSoW, write summaries in Czech.
- For BBtn, write summaries in English.
- For BBtn, omit articles that are only relevant to Czech readers and have no useful value for an international audience only when the BBtn site did not publish them. If the relevant BBtn site published the article, include it.

## Working Output

The first output is for human editorial processing. Write it to the section folder note:

- RSoW example: `02 RSoW/rsow-112/05 Articles/_05 Articles.md`
- BBtn example: `01 BBtn/bbtn-112/05 Articles/_05 Articles.md`

Create the issue section folder and folder note if missing. This is a non-destructive structure completion.

Use a checked Markdown task list for article summaries. Items are checked by default. Images are not task-list items; place them directly before the related checked profile item. The human editor may rewrite summaries, change links, reorder items, add text, or uncheck items. Unchecked items must not be copied into the final issue text.

### RSoW Working Output

```markdown
## Vyšlo na ŘSoW

![{{ALT text}}]({{profile image URL}})

- [x] *[{{Jméno osobnosti}}]({{URL článku}})* {{shrnutí profilu}}
- [x] [{{odborný termín}}]({{URL článku}}) {{shrnutí termínu}}
- [x] [{{název nástroje}}]({{URL článku}}) {{shrnutí nástroje}}
```

### BBtn Working Output

```markdown
## Published on BBtn

![{{Alt text}}]({{profile image URL}})

- [x] *[{{Person name}}]({{article URL}})* {{profile summary}}
- [x] [{{expert term}}]({{article URL}}) {{term summary}}
- [x] [{{tool name}}]({{article URL}}) {{tool summary}}
```

If there is no profile article, omit the image and begin with the first checked item.

## Updating Existing Working Output

If the section folder note already exists:

- Preserve human edits wherever possible.
- Keep existing checked and unchecked states.
- Do not overwrite rewritten summaries.
- Add newly discovered articles as checked items unless there is a clear reason to mark them for editor attention.
- Preserve editor ordering unless the user explicitly asks for reordering.
- Remove an item only when its source article is outside the publication range and removal is clearly requested.
- Preserve profile images already chosen by the editor.

## Final Newsletter Output

When converting the editorial checklist into the final issue newsletter:

- Use only checked `- [x]` items.
- Remove task list markers.
- Put every summary item in its own paragraph.
- Preserve profile images immediately before their related profile summaries.
- Preserve links, italics, images, alt text, and editor wording.
- Do not add bullets.
- Do not add emoji bullets.
- Remove unchecked items.
- Replace `{{Vyšlo na ŘSoW}}` in RSoW issue templates with the complete edited `## Vyšlo na ŘSoW` section.
- Replace `{{Published on BBtn}}` in BBtn issue templates with the complete edited `## Published on BBtn` section.

Final examples:

```markdown
![George A. Miller, AI-generated drawing based on photographs.](https://substack-post-media.s3.amazonaws.com/public/images/8c34088c-8760-4c97-b302-0c561265c6ba_1536x1024.webp)

*[George A. Miller](https://better-button.com/p/george-miller)* was an American cognitive psychologist who changed how we think about human limits in design. He is known for the magical number 7±2 and emphasised that design must respect how people think, remember and understand the world.

[Core Web Vitals](https://better-button.com/p/core-web-vitals) are Google’s standard for measuring real user experience: when the main content appears, how quickly the interface responds and how stable the layout is.
```

## Source Handling

- Work independently as much as practical.
- Do not ask the human editor to list articles manually if the site, feed, archive, CSV export, or local notes can be inspected.
- Ask the human editor only when the publication range or relevant site cannot be identified.
- After creating or updating the working output, move source files that were used from `00 Inbox/05 Articles` into the issue folder's `05 Articles` subfolder.
- Leave unused source files in their original location.
- Never archive source files from this workflow.
- At the end of the task, summarize the date range, included articles, skipped articles if any, created or updated files, and any editor attention points.

## Style Reference

Use `reference/articles-examples.md` for compact examples extracted from `resources/examples/rsow/` and `resources/examples/bbtn/`. Treat `resources/examples/` as the canonical source if more examples are needed.
