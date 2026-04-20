---
name: newsletter-events
description: Compose the RSoW or BBtn Events paragraph by selecting relevant events from the site event overview for the seven days starting on the newsletter publication date, then insert it only after editor approval.
---

# Newsletter Events

Use this skill when the user wants to compose, update, or finalize the `Events` paragraph for RSoW or BBtn.

Use `instructions/publication-date.md` for publication-date inference, `instructions/approval-workflow.md` for approval semantics, and `instructions/section-map.md` for canonical placeholders and folder names.

## Inputs

- Optional source notes are in `00 Inbox/06 Events`.
- RSoW event overview is linked from the RSoW home page with link text containing `Konference a akce`.
- BBtn event overview is linked from the BBtn home page with link text containing `Events`.
- The target issue folder is either `02 RSoW/rsow-###/` or `01 BBtn/bbtn-###/`.
- The target section folder is `06 Events` inside the issue folder.
- The target section folder note is `_06 Events.md`.
- The issue folder note is `_rsow-###.md` or `_bbtn-###.md`.

When the issue number or newsletter is ambiguous, infer it from the existing vault structure when safe. Ask the human editor only when the target issue cannot be identified.

## Publication Date

- Infer the publication date using `instructions/publication-date.md`.
- The event selection window starts on the publication date and covers seven calendar days including the publication date.
- Use the local timezone of the newsletter workflow, Europe/Prague, unless the source event explicitly states a different timezone.

## Required Reading

Before writing output:

1. Read relevant files in `00 Inbox/06 Events` if present.
2. Identify the target newsletter and publication date.
3. Open the relevant home page.
4. For RSoW, find a home-page link whose text contains `Konference a akce`.
5. For BBtn, find a home-page link whose text contains `Events`.
6. Open the event overview page.
7. Extract events whose dates fall within the seven-day selection window.
8. Open event detail pages when needed to verify date, language, location, and topic.

If the home-page link cannot be found, inspect the site navigation, archive, RSS feed, local resources, or existing examples. Ask the human editor only when the event overview cannot be identified responsibly.

## Event Selection

- For RSoW, prefer events in Czechia and Slovakia.
- For RSoW, include online events when they are relevant to Czech and Slovak readers.
- For BBtn, prefer events in English.
- For BBtn, include international, online, and nearby European events when useful to an international audience.
- Prioritize web, UX, product, accessibility, frontend, design, content, analytics, AI, digital business, and related community events.
- Prefer events with clear date, location or online format, and a useful link.
- Omit events outside the seven-day window unless the user explicitly asks for a broader overview.
- If there are too many eligible events, choose the most relevant mix and point to the full overview at the end.
- If no suitable events are found, write a short approved-gated note saying that no relevant events were found for the seven-day window and link to the overview when available.

## Working Output

The first output is for human editorial processing. Write it to the section folder note:

- RSoW example: `02 RSoW/rsow-112/06 Events/_06 Events.md`
- BBtn example: `01 BBtn/bbtn-112/06 Events/_06 Events.md`

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

{{jeden odstavec s vybranými akcemi v češtině}}
```

### BBtn Working Output

```markdown
---
approved: waiting
---

{{one paragraph with selected events in English}}
```

Do not add a section heading unless the existing issue format explicitly uses one. The `{{Events}}` placeholder represents the paragraph itself.

## Paragraph Style

- Write one concise paragraph.
- Match the style of event paragraphs in `resources/examples/`.
- Mention relative days when natural: today, tomorrow, on Wednesday, ve středu, zítra.
- Link event names or the most descriptive phrase.
- End with a link to the full event overview when useful.
- For RSoW, write Czech naturally and prefer Czech typography.
- For BBtn, write English naturally and prefer English typography.
- Do not use bullets.
- Do not list every possible event when a curated paragraph reads better.

## Updating Existing Working Output

If the section folder note already exists:

- Preserve human edits wherever possible.
- Do not overwrite an edited paragraph unless the user explicitly asks for a fresh rewrite.
- Preserve existing front matter.
- If front matter has no `approved` property, add `approved: waiting`.
- Keep `approved: approved`, `approved: true`, or `approved: "true"` unchanged.
- Update the paragraph only when the publication date, event overview, or user request requires it.

## Final Newsletter Output

When converting the working output into the final issue newsletter:

- Read the target section folder note.
- Use the paragraph only when front matter contains `approved: approved`, `approved: true`, or `approved: "true"`.
- If `approved` is missing, `waiting`, `false`, or any other value, do not insert the paragraph into the final issue.
- Replace `{{Events}}` in the issue folder note with the approved paragraph.
- Remove YAML front matter before inserting the paragraph.
- Preserve links, emphasis, and editor wording.

## Source Handling

- Work independently as much as practical.
- Do not ask the human editor to list events manually if the overview can be inspected.
- Ask the human editor only when the target issue, publication date, or event overview cannot be identified.
- After creating or updating the working output, move source files that were used from `00 Inbox/06 Events` into the issue folder's `06 Events` subfolder.
- Leave unused source files in their original location.
- Never archive source files from this workflow.
- At the end of the task, summarize the publication date, seven-day window, selected events, skipped edge cases if any, created or updated files, approval state, and editor attention points.

## Style Reference

Use `reference/events-examples.md` for compact examples extracted from `resources/examples/rsow/` and `resources/examples/bbtn/`. Treat `resources/examples/` as the canonical source if more examples are needed.
