# Edge cases

[Português](EDGE-CASES.md) · **English**

The 4 flags, each checked by hand, and what the 12 flags the fixes for Portuguese as written in Macau removed were. None survived the model review. Back to [the vulnerabilities README](README.en.md).

## Spent (2)

| Act | What the record says | Why it is harmless now |
| --- | --- | --- |
| [Law 22/2024](https://github.com/lexifina/macau-law/blob/92c2f4c3ee8fb6bd124b1c7f723069cbe5e9cf1d/lei/2024/22/texto.md) (hawkers' management regime), Article 20(4) and (7) | the holders of a hawker licence who chose to keep it may keep it valid "até 31 de Dezembro de 2025" (until 31 December 2025) if they lodge the deposit referred to in Article 7 within 90 days of the law's entry into force; so may the residents of Wanzai who already hold a licence (paragraph 7) | A transitional rule for the licences that existed when the law took effect, on 1 March 2025 (Article 30); it ran out as written. This repository holds Assembly laws only while no later Assembly law published by 5 November 2026 refers to them, so no law in it extended the date. |

## Misread by a detector (2)

| Act | What the record says | What happened |
| --- | --- | --- |
| [Law 10/2018](https://github.com/lexifina/macau-law/blob/92c2f4c3ee8fb6bd124b1c7f723069cbe5e9cf1d/lei/2018/10/texto.md) (special tax benefit for the purchase of motor vehicles), Article 2(1) | "damaged vehicles" are motor vehicles whose registration was cancelled at a request filed with the Transport Bureau (DSAT) "até 18 de Setembro de 2017" (by 18 September 2017) and which the DSAT confirms were flooded or crushed in Macau during Typhoon Hato | The date fixes which vehicles the benefit covers, not the end of a rule. The law took effect on 14 August 2018, after the date, and its benefit covers new vehicles bought from 23 August 2017 to two years after that (Article 2(4)). |
| [Law 10/2018](https://github.com/lexifina/macau-law/blob/92c2f4c3ee8fb6bd124b1c7f723069cbe5e9cf1d/lei/2018/10/texto.md), Article 5(2) | the period of use of a damaged vehicle runs from its first registration "até ao dia 23 de Agosto de 2017" (up to 23 August 2017) | The law's day for Typhoon Hato (the vehicle's owner on that day, Article 2(2); new vehicles bought from that day, Article 2(4)): the end point of the period of use on which the benefit is calculated (the annex's table of rates by period of use, Article 4(1)), not a time limit. This flag is new: the time-limit search did not read "até ao dia" before the fix. |

## The other flags

- **Lapsed time limits before the fix:** 7, of which 4 were the Portuguese "do" (of the) read as the Slavic "do" (until): Article 7(2) of [Law 15/2018](https://github.com/lexifina/macau-law/blob/92c2f4c3ee8fb6bd124b1c7f723069cbe5e9cf1d/lei/2018/15/texto.md) (repeal of the offshore regime), "O artigo 6.º produz efeitos a partir do dia 1 de Janeiro de 2021" (Article 6 takes effect from 1 January 2021), and Articles 65(2), 66(2) and 67(1) of [Law 12/2025](https://github.com/lexifina/macau-law/blob/92c2f4c3ee8fb6bd124b1c7f723069cbe5e9cf1d/lei/2025/12/texto.md) (supervision of medical devices), whose transitional periods run "Do dia 1 de Julho de 2026 até ao dia 30 de Junho de 2027" (from 1 July 2026 to 30 June 2027) and the like. The start of a period was read as its end. The 3 other flags are among the 4 above; after the fix, all the periods of Law 12/2025 end in 2027 or later.
- **Duplicate numbering before the fix:** 8, none a real duplicate. In the Assembly's laws, held as one text with the lines as the Boletim Oficial breaks them, a line that begins with a reference was read as an article heading: "artigo 71.º da Lei Básica da Região Administrativa Especial de" twice in Laws 17/2018, 4/2020, 9/2024, 7/2025 and 11/2026, in each law's enacting formula and in that of the law it republishes in an annex, "artigo 26.º" twice in Law 13/2020, "artigo 5.º" three times in Law 9/2023 and "artigo 33.º da Lei Eleitoral para a Assembleia Legislativa" in Law 7/2025. After the fix, none.
- **Repeal gaps, same-day conflicts, retroactive dates, empty periods, stale amounts, references to deleted provisions:** none. Each act has one version, credited to its publisher, so no provision's text changes in the history and there is nothing to compare. The repository says so itself: no change is yet credited to the law that made it.
- **References to repealed placeholders, dead fines:** none. No provision's text is only "(Revogado)"; the two Commercial Code articles that the Boletim Oficial marks as repealed keep their text (see the README).
- **Dead currencies, publisher notes:** none. The amounts are in patacas, the currency in use, and no text names the escudo; the detector found no note that an amendment could not be carried out.
