# How this repository was made (Macau)

This file is written by the build on 2026-10-31, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| 澳門特別行政區立法會 (Legislative Assembly of the Macao SAR): 澳門特別行政區基本法 | <https://www.al.gov.mo/zh-hant/basic-law.html> | 2026-10-29 | no licence stated |
| Imprensa Oficial da RAEM, Boletim Oficial: Código Penal (aprovado pelo Decreto-Lei n.º 58/95/M, de 14 de Novembro) | <https://bo.io.gov.mo/bo/i/95/46/codpenpt/default.asp> | 2026-10-31 | No licence statement; official text of the law published by the Imprensa Oficial. |
| Imprensa Oficial da RAEM, Boletim Oficial: Código de Processo Penal (aprovado pelo Decreto-Lei n.º 48/96/M, de 2 de Setembro) | <https://bo.io.gov.mo/bo/i/96/36/codpropenpt/default.asp> | 2026-10-31 | No licence statement; official text of the law published by the Imprensa Oficial. |
| Imprensa Oficial da RAEM, Boletim Oficial: Lei n.º 7/2008 (Lei das relações de trabalho) | <https://bo.io.gov.mo/bo/i/2008/33/lei07.asp> | 2026-10-31 | No licence statement; official text of the law published by the Imprensa Oficial. |
| Imprensa Oficial da RAEM, Boletim Oficial: Código Civil (aprovado pelo Decreto-Lei n.º 39/99/M, de 3 de Agosto) | <https://bo.io.gov.mo/bo/i/99/31/codcivpt/default.asp> | 2026-10-31 | No licence statement; official text of the law published by the Imprensa Oficial. |
| Imprensa Oficial da RAEM, Boletim Oficial: Código Comercial (aprovado pelo Decreto-Lei n.º 40/99/M, de 3 de Agosto) | <https://bo.io.gov.mo/bo/i/99/31/codcompt/default.asp> | 2026-10-31 | No licence statement; official text of the law published by the Imprensa Oficial. |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `basic-law` | 中華人民共和國澳門特別行政區基本法 (Basic Law of the Macao SAR) | 1 | 1999-12-20 to 1999-12-20 |
| `annexes` | 基本法附件一至三 (Annexes I to III) | 1 | 2012-06-30 to 2012-06-30 |
| `codigo-penal` | Código Penal (aprovado pelo Decreto-Lei n.º 58/95/M, de 14 de Novembro) | 1 | 2025-08-16 to 2025-08-16 |
| `codigo-processo-penal` | Código de Processo Penal (aprovado pelo Decreto-Lei n.º 48/96/M, de 2 de Setembro) | 1 | 2025-08-28 to 2025-08-28 |
| `lei-relacoes-trabalho` | Lei n.º 7/2008 (Lei das relações de trabalho) | 1 | 2025-04-03 to 2025-04-03 |
| `codigo-civil` | Código Civil (aprovado pelo Decreto-Lei n.º 39/99/M, de 3 de Agosto) | 1 | 2025-02-13 to 2025-02-13 |
| `codigo-comercial` | Código Comercial (aprovado pelo Decreto-Lei n.º 40/99/M, de 3 de Agosto) | 1 | 2025-09-17 to 2025-09-17 |

The build made 7 commits:

| Commits | Kind |
| ---: | --- |
| 7 | first version of an act |
| 0 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `future`: laws not yet in force on 2026-10-31.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 0 laws in the record.
- 7 tags.

## Dates

Each commit is dated at noon (Asia/Macau) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: The Basic Law was adopted on 31 March 1993 and implemented from 20 December 1999 (the date stated at the head of the published text). https://www.al.gov.mo/zh-hant/basic-law.html

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `5c6a8f367ca2b94a0f815990995036e3627379bfa3c4957d70d7a7f460352e94` (2815637 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `a4faa25af85facb64b956b372f6b528aafdd7ec1`, `check.py` `3d00541d258745461ab52b1b0cb4e1716a27a95d`, `on.py` `644a6c0857fbcc72562032b58d57aa113fee0641`.
- Python 3.12.10; git version 2.46.0.windows.1.

## Checks

7 versions of 7 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

A second build from the same corpus into an empty folder gave identical hashes for all 7 history commits and 7 tags (history tip `c77fa003c42cfe699e6f137f2c068d03103304e4`).

## Decisions made by hand

- Chinese (traditional) is built: the Basic Law is authentic in Chinese and Portuguese; the Legislative Assembly page gives the Chinese text.
- Two acts: the Basic Law itself (dated 1999-12-20, when it was implemented) and the Annexes, which the source shows with the 2012 amendments beside the original text (dated 2012-06-30, the latest date on the page). No earlier versions are online at the source.
- Chapter and section headings are kept at the start of the article that follows them.
- Código Penal (aprovado pelo Decreto-Lei n.º 58/95/M, de 14 de Novembro): one version, the updated text as the Imprensa Oficial page showed it on 2025-08-16, credited to the Imprensa Oficial as "oldest version available". It is not an in-force date: the act is Decreto-Lei n.º 58/95/M, published in Boletim Oficial n.º 46/1995 (I série) of 14 November 1995; in force 1 January 1996 (art. 12.º), and the page gives no consolidation date.
- Código Penal (aprovado pelo Decreto-Lei n.º 58/95/M, de 14 de Novembro): Portuguese, one of the two official languages of Macau; the Chinese text is not built. One unit per article (art-NNN, added articles as art-NNN-a); book, part, title, chapter and section headings are kept at the start of the article that follows them, like the Basic Law. The site's footnote lines and asterisk markers that point to amending laws are left out; a number whose text the site marks as revoked keeps only its number, and runs of revoked articles that the site shows by number only (for example "Artigo 289.º e Artigo 290.º") are left out.
- Código de Processo Penal (aprovado pelo Decreto-Lei n.º 48/96/M, de 2 de Setembro): one version, the updated text as the Imprensa Oficial page showed it on 2025-08-28, credited to the Imprensa Oficial as "oldest version available". It is not an in-force date: the act is Decreto-Lei n.º 48/96/M, published in Boletim Oficial n.º 36/1996 (I série) of 2 September 1996; the page notes that its content was republished by Despacho do Chefe do Executivo n.º 354/2013, and the page gives no consolidation date.
- Código de Processo Penal (aprovado pelo Decreto-Lei n.º 48/96/M, de 2 de Setembro): Portuguese, one of the two official languages of Macau; the Chinese text is not built. One unit per article (art-NNN, added articles as art-NNN-a); book, part, title, chapter and section headings are kept at the start of the article that follows them, like the Basic Law. The site's footnote lines and asterisk markers that point to amending laws are left out; a number whose text the site marks as revoked keeps only its number, and runs of revoked articles that the site shows by number only (for example "Artigo 289.º e Artigo 290.º") are left out.
- Lei n.º 7/2008 (Lei das relações de trabalho): one version, the updated text as the Imprensa Oficial page showed it on 2025-04-03, credited to the Imprensa Oficial as "oldest version available". It is not an in-force date: the act is Lei n.º 7/2008, published in Boletim Oficial n.º 33/2008 (I série) of 18 August 2008; in force 1 January 2009 (art. 97.º); the page notes that its content was republished by Despacho do Chefe do Executivo n.º 134/2020, and the page gives no consolidation date.
- Lei n.º 7/2008 (Lei das relações de trabalho): Portuguese, one of the two official languages of Macau; the Chinese text is not built. One unit per article (art-NNN, added articles as art-NNN-a); book, part, title, chapter and section headings are kept at the start of the article that follows them, like the Basic Law. The site's footnote lines and asterisk markers that point to amending laws are left out; a number whose text the site marks as revoked keeps only its number, and runs of revoked articles that the site shows by number only (for example "Artigo 289.º e Artigo 290.º") are left out.
- Código Civil (aprovado pelo Decreto-Lei n.º 39/99/M, de 3 de Agosto): one version, the updated text as the Imprensa Oficial page showed it on 2025-02-13, credited to the Imprensa Oficial as "oldest version available". It is not an in-force date: the act is Decreto-Lei n.º 39/99/M, published in Boletim Oficial n.º 31/1999 of 3 August 1999, and the page gives no consolidation date.
- Código Civil (aprovado pelo Decreto-Lei n.º 39/99/M, de 3 de Agosto): Portuguese, one of the two official languages of Macau; the Chinese text is not built. One unit per article (art-NNN, added articles as art-NNN-a); book, part, title, chapter and section headings are kept at the start of the article that follows them, like the Basic Law. The site's footnote lines and asterisk markers that point to amending laws are left out; a number whose text the site marks as revoked keeps only its number, and runs of revoked articles that the site shows by number only (for example "Artigo 289.º e Artigo 290.º") are left out.
- Código Comercial (aprovado pelo Decreto-Lei n.º 40/99/M, de 3 de Agosto): one version, the updated text as the Imprensa Oficial page showed it on 2025-09-17, credited to the Imprensa Oficial as "oldest version available". It is not an in-force date: the act is Decreto-Lei n.º 40/99/M, published in Boletim Oficial n.º 31/1999 of 3 August 1999, and the page gives no consolidation date.
- Código Comercial (aprovado pelo Decreto-Lei n.º 40/99/M, de 3 de Agosto): Portuguese, one of the two official languages of Macau; the Chinese text is not built. One unit per article (art-NNN, added articles as art-NNN-a); book, part, title, chapter and section headings are kept at the start of the article that follows them, like the Basic Law. The site's footnote lines and asterisk markers that point to amending laws are left out; a number whose text the site marks as revoked keeps only its number, and runs of revoked articles that the site shows by number only (for example "Artigo 289.º e Artigo 290.º") are left out.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- Claude Code wrote the parser; it did not write or alter any legal text. 0 model calls at data-build time.
- none
- none
- none
- none
- none
