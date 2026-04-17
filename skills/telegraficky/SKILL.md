---
name: telegraficky
description: Generate Telegraficky section from URLs in Obsidian
---

Goal:
Create a "Telegraficky" section from a list of URLs stored in Obsidian.

Steps:

1. Load the file:
   03 Projects/ŘSoW newsletter/ŘSoW{{issue}}/Resources/Telegraficky.md
   where {{issue}} is the number of newsletter issue 
   using the command-line

2. Extract all URLs from the file.

3. For each URL:
   a) fetch content using MCP or cURL 
   b) extract main article content
   c) create a summary

Summary rules:
- max 80 characters
- 1 or 2 sentences
- highlight the key insight
- no filler words
- neutral, factual tone

4. Format output:

Start with header: `## Telegraficky`

Each item:
- start with exactly one emoji (contextual, not random)
- short summary
- include clickable link
- use the appropriate typography aacording to the language

Example:

🏗️ [Vláda odsunula digitalizaci stavebního zákona](URL) na roky 2030–2031.

5. At the end, append:

`Sledujte nás také přes [RSS feed](https://www.reknisioweb.cz/feed?sectionId=130962), [Bluesky](https://bsky.app/profile/www.reknisioweb.cz) nebo [Linkedin](https://www.linkedin.com/company/reknisioweb/).`