# Macau: law history in git

The law of Macau as a git history: one file per article (one file per law for the recent laws of the Legislative Assembly), one commit per version on the day in its `In-force:` trailer, and the act that made each change as the commit's author. So far every act has one version, credited to its publisher instead: `git blame` and `git log` name where each text came from; picking a date gives the text the record holds for that day.

Part of [lexifina/global-law](https://github.com/lexifina/global-law), one git history for every country's law: this is Macau's national law, which global-law reads at `macau/national/acts/`.

**What is in it now:** 64 acts, each with one version: the Basic Law (preamble and 145 articles) and its three Annexes, in Chinese; the Civil, Commercial, Penal and Criminal Procedure Codes and Lei n.º 7/2008, the Labour Relations Law, as updated texts in Portuguese; and 57 laws of the Legislative Assembly of 2018 to 2026, each as first published, in Portuguese. [`REPRODUCE.md`](REPRODUCE.md) lists every act with its version and how each was chosen.

The codes are in `code/` (`code/codigo-civil/art-001.md` is Article 1 of the Código Civil), the Assembly laws in `lei/<year>/<number>/texto.md` (`lei/2024/6/texto.md` is Lei n.º 6/2024, the Lei sindical), the Labour Relations Law in `lei-relacoes-trabalho/` (`art-046.md` is Article 46, Direito a férias), the Basic Law in `basic-law/` and its Annexes in `annexes/`. [`data/paths.json`](data/paths.json) maps each act id to its folder.

The text is in Macau's two official languages, as the sources print it: Chinese (traditional) for the Basic Law and its Annexes, Portuguese for the rest. An English translation is not part of this record.

## Questions as git commands

| Question | Command |
| --- | --- |
| Every change to Article 46 of the Labour Relations Law | `git log -p --word-diff -- lei-relacoes-trabalho/art-046.md` |
| Who is credited with each line of Article 46? | `git blame lei-relacoes-trabalho/art-046.md` |
| Every version of the Labour Relations Law, with its day | `git log --format="%h %(trailers:key=In-force,valueonly,separator=) %an" -- lei-relacoes-trabalho ':!lei-relacoes-trabalho/README.md'` |
| Article 46 as the record holds it on 1 January 2026 | `python tools/on.py 2026-01-01 lei-relacoes-trabalho art-046` |

**Outside git**, we also host this record publicly, for free:

- **[Ask Claude about Macau law](https://global-law.lexifina.com/v1/try_claude?country=macau)**: opens Claude with a first question ready.
- **[Ask ChatGPT](https://global-law.lexifina.com/v1/try_chatgpt?country=macau)**: the same question in ChatGPT.
- **[Call the API in your browser](https://global-law.lexifina.com/v1/search_law?query=f%C3%A9rias&jurisdictions=macau)**: a search of Macau law for "férias", returned as JSON. See the [documentation here](https://lexifina.com/api/global-law).

Both assistants read the record through the free Global law connector (MCP, `https://global-law.lexifina.com/mcp`); the first time, the chat gives you the link that adds it. Ask in Portuguese, in Chinese or in English.

**Host it yourself easily.** All it takes is git and Python, and the tools run on your machine:

```sh
git clone --depth 1 https://github.com/lexifina/global-law && cd global-law
python3 tools/countries.py add macau/national/acts
python3 tools/law.py show 2026-01-01 macau/national/acts/lei-relacoes-trabalho/art-046.md
```

Opened in Claude Code, Cursor, VS Code or Codex, the clone also starts a local MCP server with the same tools ([MCP.md](https://github.com/lexifina/global-law/blob/main/MCP.md)).

## Dates

Each commit is dated at noon, Asia/Macau (UTC+8), on the day in its `In-force:` trailer:

- the Basic Law: 20 December 1999, the day it was implemented; the Annexes: 30 June 2012, the latest date on the Legislative Assembly's page, which shows the 2012 amendments beside the original text;
- the four codes and Lei n.º 7/2008: the day the Boletim Oficial's page showed the updated text used (13 February to 17 September 2025). It is not the day the text took effect, since the page gives no consolidation date; each act's original publication is in `REPRODUCE.md`;
- each Assembly law: the commencement day in the Assembly's list of laws, or the law's own commencement clause where the list gives none.

Every commit is credited to its publisher as the "oldest version available": `Legislative Assembly of the Macao SAR (al.gov.mo)` for the Basic Law, the Annexes and the Assembly laws, `Imprensa Oficial da RAEM (Boletim Oficial)` for the codes and Lei n.º 7/2008. No change is yet credited to the law that made it.

## How it is checked

- `tools/check_repo.py` reads every version back from git on the day it took effect and on the day before and compares it with the corpus: 0 mismatches (see [`REPRODUCE.md`](REPRODUCE.md)).
- An Assembly law is included only while no later Assembly law published through 5 November 2026 refers to it, so its text as first published is taken as its current text; amendments and repeals are not guessed, and laws whose text or annexes need review are held back.
- Every commit's trailers parse; there are no merge commits on `main` and no commit dated after the build. No second build has been compared yet.

## What it does not show

- **Earlier versions.** Each act has one text; the codes' footnotes naming the laws that amended them are left out, and no change is credited to an amending law.
- **Most of Macau's law.** No Assembly law from before 2018 and only part of those since, no decree-law from before 1999 other than the four codes, and no administrative regulations.
- **Seven laws not yet in force** (Lei n.º 4, 7, 8, 9, 10, 14 and 15/2026, taking effect from 1 December 2026 to 1 September 2027): their folders hold only a README, without the text.
- **The other official language.** The codes and laws are here in Portuguese only, the Basic Law in Chinese only.
- **Case law.** No court decisions are part of this record.

## Sources

| Source | Kind | Past versions | Notes |
| --- | --- | --- | --- |
| [Legislative Assembly of the Macao SAR: Basic Law](https://www.al.gov.mo/zh-hant/basic-law.html) | The Basic Law and its Annexes, in Chinese | no | The Annexes with the 2012 amendments beside the original text |
| [Boletim Oficial](https://bo.io.gov.mo/) (Imprensa Oficial) | Updated texts of the four codes and Lei n.º 7/2008, in Portuguese | no, the updated text only | The site's footnotes pointing to amending laws are left out |
| [Legislative Assembly of the Macao SAR: laws](https://www.al.gov.mo/pt/law.html) | The list of laws since 1999, with each law's Boletim Oficial (I série) text | no, the text as first published | The Portuguese text; the commencement day from the list |

## Licence

See [`LICENSE`](LICENSE). The sources state no licence: the Basic Law (from the Legislative Assembly's website) and the codes and laws (from the Boletim Oficial, published by the Imprensa Oficial) are official legal texts, reproduced for reference with attribution to their publishers. The arrangement of this repository, its commit messages and tools are by Lexifina, under the Creative Commons Attribution 4.0 International licence.

No AI model wrote, translated or corrected legal text, and none runs when the history is built; the scripts were written by AI models, Claude Opus 5.5 and GPT-6 (see [`REPRODUCE.md`](REPRODUCE.md)).

## More

From [lexifina/global-law](https://github.com/lexifina/global-law):

- [FEATURES.md](https://github.com/lexifina/global-law/blob/main/FEATURES.md): every feature, and what every corpus must support (`git blame`, `law.py`, the MCP tools)
- [FAQ.md](https://github.com/lexifina/global-law/blob/main/FAQ.md): questions and answers · [CONTRIBUTING.md](https://github.com/lexifina/global-law/blob/main/CONTRIBUTING.md): proposing changes · [MCP.md](https://github.com/lexifina/global-law/blob/main/MCP.md): the MCP server · [REPRODUCE.md](https://github.com/lexifina/global-law/blob/main/REPRODUCE.md): how it was built · [CHANGELOG.md](https://github.com/lexifina/global-law/blob/main/CHANGELOG.md)
- [FRESHNESS.md](https://github.com/lexifina/global-law/blob/main/FRESHNESS.md): how current each corpus is · [Monitoring](https://github.com/lexifina/global-law/tree/main/monitoring): whether updates are running · [WATCHING.md](https://github.com/lexifina/global-law/blob/main/WATCHING.md): how each official source is watched for changes
- [performance/](https://github.com/lexifina/global-law/tree/main/performance): how fast the tools are, measured
- [visualisations/](https://github.com/lexifina/global-law/tree/main/visualisations): charts and bridges across the world's law
- [Vulnerabilities](https://github.com/lexifina/global-law/tree/main/vulnerabilities): mistakes in legislation as published
