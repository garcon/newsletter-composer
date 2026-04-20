# Newsletter Composer

Newsletter Composer je plugin pro přípravu zpravodajů Řekni si o web a Better Button z podkladů uložených v Obsidian vaultu. Funguje v GitHub Copilot CLI i v Claude Code.

Plugin slouží lidskému editorovi: vezme podklady z `00 Inbox`, připraví pracovní výstupy v podsložkách aktuálního vydání, přesune použité zdroje a nakonec vloží schválené sekce do výsledné šablony vydání. Sdílené skilly a agenti tvoří společné jádro; platformní soubory zpřístupňují stejné workflow v Copilot CLI i Claude Code.

## Co Plugin Umí

Plugin obsahuje agenty a skilly pro tyto části zpravodajů:

| Agent | Skill | Sekce |
| --- | --- | --- |
| `vault-structure` | `newsletter-vault-structure` | kontrola a vytvoření struktury Obsidian vaultu |
| `in-a-nutshell` | `newsletter-in-a-nutshell` | RSoW/BBtn `In a Nutshell` |
| `design-tip` | `newsletter-design-tip` | RSoW `Designérský tip`, BBtn `Designer’s Tip` |
| `opinion` | `newsletter-opinion` | RSoW/BBtn `Opinion` |
| `linkodrome` | `newsletter-linkodrome` | RSoW `Linkodrom`, BBtn `Linkodrome` |
| `articles` | `newsletter-articles` | RSoW `Vyšlo na ŘSoW`, BBtn `Published on BBtn` |
| `events` | `newsletter-events` | RSoW/BBtn odstavec s akcemi |
| `anniversary` | `newsletter-anniversary` | RSoW/BBtn závěrečný odstavec s výročím |
| `finalize-issue` | `newsletter-finalize-issue` | sestavení výsledného vydání |

## Požadavky

- Nainstalovaný a přihlášený GitHub Copilot CLI, Claude Code, nebo obojí.
- Přístup ke Git repozitáři s tímto pluginem.
- Node.js a `npx`, protože plugin používá Playwright MCP.
- Obsidian vault se strukturou popsanou níže, případně prázdný vault, který může Copilot připravit.

Rychlá kontrola:

```shell
copilot version
copilot login
claude --version
node --version
npx --version
```

## Instalace Do GitHub Copilot CLI

Plugin nainstalujte z GitHub repozitáře `garcon/newsletter-composer`:

```shell
copilot plugin install garcon/newsletter-composer
```

Stejný repozitář lze nainstalovat také přes Git URL:

```shell
copilot plugin install https://github.com/garcon/newsletter-composer.git
```

Pokud instalujete fork nebo kopii pluginu z podsložky jiného repozitáře, použijte odpovídající název repozitáře a cestu:

```shell
copilot plugin install OWNER/REPO:PATH/TO/newsletter-composer
```

Po instalaci spusťte Copilot CLI:

```shell
copilot
```

V interaktivním režimu ověřte, že se plugin načetl:

```text
/plugin list
/agent
/skills list
/env
```

Měli byste vidět plugin `newsletter-composer`, newsletterové agenty a newsletterové skilly.

Po změnách plugin aktualizujete příkazem:

```shell
copilot plugin update newsletter-composer
```

## Použití V Claude Code

Plugin obsahuje také kompatibilní vrstvu pro Claude Code:

```text
.claude-plugin/plugin.json
commands/
hooks/hooks.json
```

Claude Code může plugin používat lokálně přímo z této složky. Při vývoji nebo testování spusťte Claude Code z kořene pluginu:

```shell
claude --plugin-dir .
```

Pokud chcete plugin používat z GitHub checkoutu, nejdřív si repozitář stáhněte a spusťte Claude Code ve stažené složce:

```shell
git clone https://github.com/garcon/newsletter-composer.git
cd newsletter-composer
claude --plugin-dir .
```

Po spuštění ověřte, že se plugin načetl:

```text
/plugin list
/help
/agents
```

Claude Code používá namespacované příkazy podle názvu pluginu. Editor může použít například:

```text
/newsletter-composer:prepare-in-a-nutshell
/newsletter-composer:check-vault-structure
/newsletter-composer:prepare-design-tip
/newsletter-composer:prepare-opinion
/newsletter-composer:prepare-linkodrome
/newsletter-composer:prepare-articles
/newsletter-composer:prepare-events
/newsletter-composer:prepare-anniversary
/newsletter-composer:finalize-issue
```

Za příkaz lze doplnit upřesnění:

```text
/newsletter-composer:prepare-events RSoW issue 112, publication date 2026-04-27
```

Claude Code vrstva používá stejné skilly, agenty, `.mcp.json` a obsahové instrukce jako GitHub Copilot CLI plugin. GitHub Copilot CLI instalace tím není dotčená.

Pokud se příkazy nezobrazují, spusťte v Claude Code:

```text
/reload-plugins
/help
```

Pokud se plugin stále nenačte, zkontrolujte, že Claude Code spouštíte ze složky, která obsahuje `.claude-plugin/plugin.json`.

## Očekávaná Struktura Obsidian Vaultu

Copilot CLI spouštějte z kořene Obsidian vaultu, ne ze složky pluginu:

```shell
cd PATH/TO/OBSIDIAN/VAULT
copilot
```

Vault má mít tyto hlavní složky:

```text
00 Inbox
01 BBtn
02 RSoW
03 Archives
04 Resources
99 Service
```

Servisní workflow, která neodpovídají konkrétní newsletterové sekci, používají také prefix `99-`. Skill pro kontrolu struktury vaultu je proto uložený jako `skills/99-vault-structure/`.

Podklady patří do sekčních složek v `00 Inbox`:

```text
00 Inbox/
├── 01 In a Nutshell
├── 02 Designer’s Tip
├── 03 Opinion
├── 04 Linkodrome
├── 05 Articles
├── 06 Events
└── 07 Anniversary
```

Vydání jsou uložená ve složkách `01 BBtn` a `02 RSoW`:

```text
01 BBtn/bbtn-111/_bbtn-111.md
02 RSoW/rsow-111/_rsow-111.md
```

Každé vydání má vlastní složku, složkovou poznámku a odpovídající podsložky pro jednotlivé sekce. Pokud některá bezpečně vytvořitelná část struktury chybí, agent ji může doplnit a na konci shrne, co vytvořil.

## Základní Postup

1. Vložte podklady pro sekci do odpovídající podsložky v `00 Inbox`.
2. Pokud vault zakládáte nebo si nejste jistí strukturou, spusťte agenta `vault-structure`.
3. Otevřete terminál v kořeni Obsidian vaultu a spusťte `copilot`.
4. Spusťte odpovídajícího agenta přes `/agent`, nebo Copilotu napište, který skill má použít.
5. Agent připraví pracovní výstup v podsložce aktuálního vydání.
6. Zkontrolujte a upravte pracovní výstup v Obsidianu.
7. Až je sekce připravená, změňte `approved: waiting` na `approved: approved` nebo `approved: true`.
8. Spusťte agenta `finalize-issue`, který vloží schválené sekce do šablony vydání.

## Spouštění Agentů

V interaktivním Copilot CLI použijte:

```text
/agent
```

Vyberte newsletterového agenta a popište úkol. Příklady:

```text
Check the Obsidian vault structure and create missing non-destructive folders.
```

```text
Prepare the In a Nutshell section for the current BBtn issue.
```

```text
Prepare the RSoW Designérský tip from the inbox source material.
```

```text
Research and prepare the Opinion section for the next issue.
```

```text
Finalize the current RSoW issue using only approved section outputs.
```

Skill můžete vyvolat také běžnou větou:

```text
Use the newsletter-linkodrome skill to prepare Linkodrome for the current issue.
```

```text
Use the newsletter-finalize-issue skill to assemble the BBtn issue.
```

## Poznámky K Jednotlivým Sekcím

### Struktura Vaultu

Agent `vault-structure` zkontroluje očekávané složky Obsidian vaultu, vytvoří chybějící nedestruktivní strukturu, doplní servisní šablony a může připravit strukturu konkrétního vydání. Nikdy nemaže, nearchivuje ani nepřepisuje existující soubory bez výslovného zadání.

### In a Nutshell

Podklady s odkazy vložte do `00 Inbox/01 In a Nutshell`. Agent ověří zdroje a připraví stručná editoriální shrnutí.

### Designérský Tip / Designer’s Tip

Textové a obrázkové podklady vložte do `00 Inbox/02 Designer’s Tip`. Pokud je k dispozici obrázek, agent ho uloží do složky `assets` v aktuální podsložce vydání. Pokud chybí ALT text, agent se ho pokusí vytvořit.

### Opinion

Námět na esej vložte do `00 Inbox/03 Opinion`. Agent udělá rešerši, připraví anglickou verzi pro BBtn, českou verzi pro RSoW a náměty na ilustrace do souboru `draw.md`.

### Linkodrome

Odkazy vložte do `00 Inbox/04 Linkodrome`. Shrnutí mají mít ideálně kolem 250 znaků, nejvýše 450 znaků.

### Articles

Agent `articles` vypíše články vydané na odpovídajícím webu od posledního zpravodaje a připraví shrnutí pro `Vyšlo na ŘSoW` nebo `Published on BBtn`.

### Events

Agent `events` připraví jeden odstavec s akcemi pro sedm dní od očekávaného data vydání zpravodaje.

### Anniversary

Agent `anniversary` připraví závěrečný odstavec s výročím. Pokud nejsou podklady v Inboxu, použije události z odpovídající stránky Wikipedie a vybírá přednostně pozitivní kulatá výročí.

## Schvalování Výstupů

Některé pracovní výstupy se do výsledného vydání nesmí vložit bez schválení editorem. Mají proto ve front matteru:

```yaml
---
approved: waiting
---
```

Finalizace vloží jen sekce s některou z těchto hodnot:

```yaml
approved: approved
approved: true
approved: "true"
```

Všechny ostatní hodnoty znamenají, že sekce není schválená. Finalizační agent nechá její placeholder v šabloně beze změny a upozorní na to editora.

Při vložení schváleného textu agent odstraní front matter, ale zachová editorovy formulace, odkazy, obrázky, zvýraznění a strukturu odstavců.

## Užitečné Příkazy V Copilot CLI A Claude Code

GitHub Copilot CLI:

```text
/plugin list
/agent
/skills list
/skills info newsletter-opinion
/mcp show
/diff
/env
```

Claude Code:

```text
/plugin list
/reload-plugins
/help
/agents
/newsletter-composer:check-vault-structure
/newsletter-composer:prepare-opinion
/newsletter-composer:finalize-issue
```

Příkaz `/diff` v Copilot CLI nebo běžný `git diff` v terminálu použijte po práci agenta, pokud chcete zkontrolovat změny v souborech.

## Řešení Potíží

Pokud se plugin nezobrazuje, zkontrolujte instalaci:

```shell
copilot plugin list
```

V Claude Code zkontrolujte, že plugin spouštíte nebo instalujete ze složky s `.claude-plugin/plugin.json`, a použijte:

```text
/reload-plugins
/plugin list
```

Pokud chybí agenti nebo skilly, restartujte Copilot CLI po instalaci nebo aktualizaci pluginu.

Pokud se nespustí Playwright MCP, ověřte, že máte dostupné Node.js a `npx`. MCP server je nastavený v `.mcp.json`.

Pokud Copilot nenajde newsletterové složky, ověřte, že jste `copilot` spustili z kořene Obsidian vaultu.

Pokud se sekce nevloží do výsledného vydání, zkontrolujte front matter ve složkové poznámce sekce a po lidské kontrole nastavte `approved` na schválenou hodnotu.
