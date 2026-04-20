# Translation Skill: Czech → British English

Description
- Reusable skill document describing rules and steps for translating Markdown files from Czech (resources\examples\rsow\) into British English and saving results to resources\examples\bbtn\.

Scope
- Translate all .md files under: resources\examples\rsow\*.md
- Do NOT modify or translate posts.csv, posts.xlsx, or non-markdown files.

Preservation rules
- Preserve YAML frontmatter keys exactly. Translate visible frontmatter *values* (title, description) only.
- Preserve code fences (```), inline code (`code`), raw URLs, links (URLs and targets), and image file paths unchanged.
- Preserve block metadata and any non-translatable tokens (e.g., placeholders like {{var}}).

Translation rules
- Translate headings, body text, list items, image alt text and captions, and visible frontmatter values into British English.
- Keep punctuation and markdown structure intact.
- Maintain sentence breaks; do not merge or split paragraphs arbitrarily.

Localisation rules
- Use British English spelling (organisation, recognise, behaviour, colour, travelled, etc.).
- Format dates in long-form UK style (e.g., "1 February 2026").
- Use decimal point "." and thousands separator "," (e.g., 1,234.56).

Global substitutions (apply across all files)
- "ŘSoW" → "BBtn"
- "Řekni si o web" → "Better Button"
- "reknisioweb.cz" → "better-button.com"
- "rsow.cz" → "bbtn.io"

Overwrite policy
- When running the batch translation, overwrite any existing files in resources\examples\bbtn\ unconditionally (user authorized this).
- Keep original Czech files in resources\examples\rsow\ unchanged.

Usage / Repeatability
- To re-run the translation in future, follow these steps:
  1. Ensure .github/skills/translation-skill.md exists (this file).
  2. For each .md in resources\examples\rsow\, read YAML and body, translate visible text using these rules, and write output to resources\examples\bbtn\ with the same filename, overwriting.
  3. Validate results for YAML integrity and that code blocks/links were preserved.

Notes
- This document codifies the agreed rules. If additional global substitutions are required, update the "Global substitutions" list before re-running.
- posts.csv and posts.xlsx are out of scope and will not be modified.

Created-by: translation-skill
