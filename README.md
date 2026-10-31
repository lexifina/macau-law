# Macau: law history in git

The law of Macau as a git history: one file per provision, and the law that made each change as the commit's author, so `git blame` names the law behind every line.

It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law), which places it at `mo/`.

**What is in it now (first build retrieved 2026-10-29; codes added 2026-10-31)**

| Folder | Law | Versions | Language |
| --- | --- | ---: | --- |
| `basic-law/` | Basic Law of the Macao SAR (preamble and Articles 1 to 145), implemented 20 December 1999 | 1 | Chinese (traditional); the Basic Law is authentic in Chinese and Portuguese |
| `annexes/` | Annexes I to III, with the 2012 amendments shown beside the original text | 1 | Chinese (traditional) |
| `codigo-penal/` | Código Penal (Decreto-Lei n.º 58/95/M), updated text as published by the Imprensa Oficial in the Boletim Oficial pages, as shown on 16 August 2025 | 1 | Portuguese, an official language of Macau |
| `codigo-processo-penal/` | Código de Processo Penal (Decreto-Lei n.º 48/96/M), updated text as published by the Imprensa Oficial in the Boletim Oficial pages, as shown on 28 August 2025 | 1 | Portuguese |
| `lei-relacoes-trabalho/` | Lei n.º 7/2008, Lei das relações de trabalho (labour relations law), updated text as published by the Imprensa Oficial in the Boletim Oficial pages, as shown on 3 April 2025 | 1 | Portuguese |
| `codigo-civil/` | Código Civil (Decreto-Lei n.º 39/99/M), updated text as published by the Imprensa Oficial in the Boletim Oficial pages, as shown on 13 February 2025 | 1 | Portuguese |
| `codigo-comercial/` | Código Comercial (Decreto-Lei n.º 40/99/M), updated text as published by the Imprensa Oficial in the Boletim Oficial pages, as shown on 17 September 2025 | 1 | Portuguese |

Sources: the Legislative Assembly of the Macao SAR website (Basic Law, in Chinese) and the Boletim Oficial of the Imprensa Oficial (codes and laws, in Portuguese). Each code or law is the updated text the Imprensa Oficial shows, with its footnotes pointing to amending laws left out; there is no dated history yet, and the Chinese texts of the codes are not built.

This is a first, small build, not the whole statute book. It has no dated history: each act is one "oldest version available" commit, dated from the source's own date and credited to the publisher. Texts are in the official language shown above; the English is a translation where marked, and the original governs.

Sources and terms are in `LICENSE`; how it was built is in `REPRODUCE.md`. Not legal advice; for anything that matters, read the original.
