---
name: newsletter-opinion
description: Turn an Opinion inbox topic into researched notes, a BBtn English essay, a RSoW Czech essay, and illustration ideas, then insert approved essays into the final newsletter issue.
---

# Newsletter Opinion

Use this skill when the user wants to compose, update, or finalize the `Opinion` essay section for RSoW or BBtn.

Use `../_shared/reference/vault-structure.md`, `../_shared/reference/newsletter-context.md`, `../_shared/reference/section-map.md`, and `../_shared/reference/approval-workflow.md` for shared vault, language, placeholder, and approval rules.

## Inputs

- Source notes are in `00 Inbox/03 Opinion`.
- The inbox should contain a human-provided essay topic, brief, note, or prompt.
- The target issue folders are usually both `02 RSoW/rsow-###/` and `01 BBtn/bbtn-###/`, because the workflow produces both RSoW and BBtn outputs.
- If the user explicitly asks for only one newsletter, prepare only that target.
- The target section folder is `03 Opinion` inside the issue folder.
- The target section folder note is `_03 Opinion.md`.
- The illustration ideas file is `draw.md` inside the target section folder.
- The issue folder note is `_rsow-###.md` or `_bbtn-###.md`.

When issue numbers or newsletters are ambiguous, infer them from the existing vault structure when safe. Ask the human editor only when the target issue cannot be identified.

## Required Reading

Before writing output:

1. Read every file in `00 Inbox/03 Opinion`.
2. Identify the topic or brief that should become the essay.
3. Read any linked source in the inbox notes.
4. Run independent internet research for the topic.
5. Prefer original, primary, and recent sources, but use older sources when they are highly relevant.
6. Keep source links and citation notes for factual claims.

If a source cannot be opened, still process the topic if the remaining context is sufficient, but mark the uncertainty for editor attention in the working output.

## Editorial Base Prompt

Apply this editorial role throughout the workflow:

```plaintext
From now on, act as a professional editor working in a high-end medium, such as The Guardian, The Washington Post, CNN, or BBC. When editing texts, pay maximum attention to stylistic precision, grammatical correctness and correct use of typographic elements (e.g. quotation marks, dashes, apostrophes and other punctuation marks) according to the rules of the language. Ensure consistency, clarity and high-quality content, relying on proven sources and standards of editorial practice. If you encounter ambiguities or complex issues, point them out or express uncertainty.

Use the correct typographical rules for each language. For example, the hyphen for Czech is – and quotation marks are „“, while for English it is — and quotation marks are “”.

Use the switches to refine your procedures:

[lang] - The name or ISO code of the language you will generate text is in square brackets. For example, [cs] or [Czech] for Czech. Also, distinguish variants such as [en_US] or [en-US] for American English.

/audience - Think about what expressive devices, compositional techniques and stylistics are appropriate for the target audience and stick to this specification. Write a description of that audience and the style they want to read.

/topic - Explore the topic. Be careful and thorough. Use internet searches. Switch to English for the search to get a greater breadth of topic areas. List all available areas related to the topic in a bulleted list.

/para - Write in complete sentences and coherent paragraphs. You can just use lists only where it really makes sense.

/pyramid What would the text look like if it were written using the inverted pyramid composition method?

/style - Analyse the text provided regarding the author's style. Describe the style and continue to work with that style when writing and editing. Just analyse the style, but don't suggest any adjustments. Do not work with the text provided, nor include it in further editing. Forget the text. Use that style in your texts and revisions.

/lenght - Lengthen or shorten the text to the specified length. Unless otherwise specified, this is the number of characters. (accept /limit as the alias to /length)

/speech - The text will have an audio version created using text-to-speech. Edit the text so that it translates easily into spoken speech. Omit bulleted lists, numbered lists, bracketed text, phrases in quotation marks, and abbreviations. Avoid overusing words. Break up or shorten long sentences.

/grammar - Correct spelling and grammatical errors as if you were a Grammarly-type program in a professional paid version.

/markdown - Use markdown to format text. Put the title of the article as the first level heading. Keep intermediate headings as second-level headings, and so on. Don't add new headings if there aren't any. Add undivided spaces between words that should not be broken at the end of a line. Don't change content or structure of the text. Just the formatting.

/draw I would like to make an illustration for the article. It doesn't have to be literal, it can be a loose metaphor, irony, sarcasm, hyperbole, a joke, or a punchline. It'll be a sketch or a pencil drawing in the style of The New Yorker. Suggest 5 situations or scenes that the cartoonist could depict.

/annotation Add a brief summary at the beginning of the text in the form of a teaser, annotation or pericope up to 200 characters in total. Formulate the summary as a dictionary definition. Format it as blockquote. It the text has a title, place the annotation between the title and the text.

/fck Remember what assignments and constraints you were given and re-apply them to the text all at once.

/help - List the switches and their purpose.

Default values for switches:

/audience The creators, administrators and operators of websites and mobile apps who read my blog.

/limit 300 words
/length 300 words
```

## Author Style Reference

Use this text only as style reference. Analyse its voice, rhythm, composition, and typographic habits, then forget its content and do not reuse the example story.

```markdown
# Propast realizace a propast vyhodnocení

> Propast realizace a vyhodnocení – Jak snadno zjistit, jak lze věc použít a co se s ní po použití stalo.

Jedeme autem po dálnici a jedné z dcer sedících na zadním sedadle se vybila sluchátka: _„Půjč si moje,“_ říkám zpoza volantu a ukazuju na svá sluchátka, ale je mi naprosto jasné, že tak snadné to nebude. Cítím ve vzduchu příležitost sledovat propast realizace ve zpětném zrcátku.

**Propast realizace** (anglicky [Gulf of Execution](https://en.wikipedia.org/wiki/The_Design_of_Everyday_Things#Gulf_of_execution)) je úsilí, které musí člověk vynaložit na to, aby zjistil, jakým způsobem lze věc použít.

Dcera zapne moje sluchátka a zjistí, že se k jejímu telefonu nepřipojila. Jsou to přeci moje sluchátka. V mobilu zobrazí zařízení s bluetooth: _„Tati, já v telefonu ty tvoje sluchátka nevidím a nevidím je ani v nespárovaných zařízeních.“_ Některá zařízení nejsou pro ostatní viditelná, dokud je nepřepnete do párovacího módu. Telefon vám to ale v nastavení bluetooth nepřipomene. Sluchátka se v mezičase připojila k mému telefonu. Sluchátka nijak neukazují, že je možné je dlouhým podržením spínače přepnout do párovacího režimu. Ukázkový příklad pro jev zvaný propast realizace. V tomhle případě je ta propast bez externího doplnění znalostí nepřekonatelná.

**Propast vyhodnocení** (anglicky [Gulf of Evaluation](https://en.wikipedia.org/wiki/The_Design_of_Everyday_Things#Gulf_of_evaluation)) je naopak úsilí, které musí člověk vynaložit, aby poznal, co se s věcí po použití stalo.

Když sluchátka zapnete, začnou hledat spárovaná zařízení a blikají rychle modře. Pokud se připojí ke spárovanému zařízení, začnou blikat modře pomalu. Při přepnutí do párovacího módu bliká střídavě modrá a červená dioda. Pokud tyhle signály neznáte, nejspíš nepoznáte, co se se sluchátky děje. Chytrá sluchátka proto vydávají i zvuky, což má na uživatele dost podobný efekt jako diody. Ta nejchytřejší sluchátka na vás rovnou promluví. Pokud nechcete spadnout do propasti vyhodnocení, pořiďte si sluchátka, která vám řeknou třeba: _„paring“_ nebo _„low battery“_.

Termíny propast realizace a propast vyhodnocení pocházejí z knihy Dona Normana [Design of Everyday Things](https://www.goodreads.com/book/show/18012365-the-design-of-everyday-things). Koncept propastí je zásadní pro porozumění tomu, jak navrhovat produkty a systémy, které jsou intuitivní a uživatelsky přívětivé. Cílem designérů je propasti zmenšovat, aby lidé mohli efektivně a bez zbytečné frustrace používat věci, jak potřebují.
```

## Workflow

Run the workflow in order. Unless the user asks for only one newsletter, create both the RSoW and BBtn working outputs.

### 1. Research Notes

Use this prompt with the topic from the inbox:

```plaintext
The topic is: {{námět z inboxu}}.

Run your own research. No constraints on the type of source or its language. Write well-sourced notes with strict academic style citations. Prefer recent sources, but if they are highly relevant, use the older ones too. Prefer original sources over secondary sources. The output is a Markdown document in English. It will serve as preparation for writing a popular article for webmasters, web designers, website owners, and maintainers.
```

Write the result to `research.md`.

### 2. English Article Draft

Use this prompt:

```plaintext
Based on your own research, write an article in /para on /topic "{{námět z inboxu}}" for my default /audience in my /style. Do not address the target audience literally. Write in British English.
```

Use the research notes from `research.md`. This is an intermediate draft only.

### 3. BBtn Working Output

Use this prompt:

```plaintext
Rewrite the article as an inverted /pyramid. Add title. Keep /length under 200 words.
```

Use this output for BBtn. Write it to the BBtn section folder note with front matter:

```markdown
---
approved: waiting
---

# {{English title}}

> {{English annotation}}

{{English essay under 200 words}}
```

### 4. RSoW Working Output

Use this prompt:

```plaintext
Translate the article into [cs], including the title and annotation. Adapt it for /speech in enhanced /grammar.
```

Use this output for RSoW. Write it to the RSoW section folder note with front matter:

```markdown
---
approved: waiting
---

# {{Český titulek}}

> {{Česká anotace}}

{{Česká esej upravená pro mluvené čtení}}
```

### 5. Illustration Ideas

Use this prompt:

```plaintext
/draw (Navrhni náměty pro ilustraci k eseji)
```

Write the result to `draw.md` in each target section folder that receives an essay. Include five illustration ideas. The ideas may be metaphorical, ironic, sarcastic, exaggerated, funny, or punchline-driven. Aim for a pencil sketch or New Yorker-style cartoon brief.

## Working Output

Create the target section folder and folder note if missing. This is a non-destructive structure completion.

Write the relevant working essays to:

- RSoW example: `02 RSoW/rsow-112/03 Opinion/_03 Opinion.md`
- BBtn example: `01 BBtn/bbtn-112/03 Opinion/_03 Opinion.md`

Also write in each target section folder that receives an essay:

- `research.md` with English research notes and citations.
- `draw.md` with illustration ideas.

After creating the working outputs, preserve the used inbox source notes with the outputs:

- If only one newsletter is prepared, move the used source notes from `00 Inbox/03 Opinion` into that issue folder's `03 Opinion` subfolder.
- If both RSoW and BBtn are prepared, copy the used source notes into both target `03 Opinion` subfolders, then remove the originals from `00 Inbox/03 Opinion`.
- Leave unused source files in their original location.
- Never archive source files from this workflow.

## Updating Existing Working Output

If the section folder note already exists:

- Preserve human edits wherever possible.
- Do not overwrite an edited essay unless the user explicitly asks for a fresh rewrite.
- Preserve existing front matter.
- If front matter has no `approved` property, add `approved: waiting`.
- Keep `approved: approved`, `approved: true`, or `approved: "true"` unchanged.
- Update `research.md` or `draw.md` only when new research, a changed topic, or a user request requires it.

## Final Newsletter Output

When converting the working output into the final issue newsletter:

- Read the target section folder note.
- Use the essay only when front matter contains `approved: approved`, `approved: true`, or `approved: "true"`.
- If `approved` is missing, `waiting`, `false`, or any other value, do not insert the essay into the final issue.
- Replace `{{Opinion}}` in each issue folder note with the approved essay body for that newsletter.
- Remove YAML front matter before inserting the essay.
- Preserve the title, annotation, paragraphs, links, and editor wording.
- Do not include `research.md` or `draw.md` in the final issue unless the user explicitly asks for that.

## Language

- For BBtn, write the final working essay in British English.
- For RSoW, write the final working essay in Czech.
- Use correct typographic conventions for the language.
- Czech uses en dashes and Czech quotation marks: `–`, `„“`.
- English uses em dashes and English quotation marks: `—`, `“”`.

## Source Handling

- Work independently as much as practical.
- Do not ask the human editor to read links, summarize sources, or run research.
- Ask the human editor only when the topic cannot be interpreted, the target issue cannot be identified, or a factual ambiguity cannot be responsibly resolved.
- At the end of the task, summarize the topic, key research sources, created files, approval state, and any editor attention points.
