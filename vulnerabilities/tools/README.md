# Tools

The scripts behind this Macau-only run of global-law's vulnerability detectors. They run inside a copy of
[global-law/vulnerabilities/scripts](https://github.com/lexifina/global-law/tree/main/vulnerabilities/scripts) (Python 3.11+,
`pip install duckdb pyarrow`), with a bare clone of this repository at `sources/corpus/macau-law.git`, a blobless bare
clone of global-law at `sources/global-law.git`, and a `pins.json` that names only macau-law and its commit (language
`pt`). `build_vulns.py`, `flags_chart.py`, `late_ext_select.py` and `late_ext_rebut.py` sit two folders above the scripts,
next to `config.json`.

| Script | What it does |
| --- | --- |
| `run.sh` | Indexes the history and texts, maps paths to the folders since the move (`map_moved.py`), adds this repository's history rows, and runs the detectors (`bash run.sh <shards>`) |
| `map_moved.py` | Rewrites the paths in the history table to each act's folder since the move of 10 November 2026 (`data/paths.json`, for example `lei-10-2018/` to `lei/2018/10/` and `codigo-civil/` to `code/codigo-civil/`), so that an act's history is not split in two at the move; `run.sh` runs it after the history is indexed |
| `add_root.py` | Builds the history rows from this repository's own commits (global-law replays it only up to an earlier commit), so the history detectors read every change |
| `run_triage.sh` | The model review: the 40 strongest flags per category, the 40 strongest lapsed time limits in law texts, and the empty periods (here 4 lapsed time limits, reviewed in both passes, and no empty periods) |
| `late_ext_select.py` | Chooses the empty periods for global-law's review of that category (there were none here) |
| `late_ext_rebut.py` | Adds the second, arguing-against pass to the empty-period review, as `triage.py` does for the other categories |
| `build_vulns.py` | Builds `data/flags.csv`, `data/reviewed.csv` and `data/by_category.csv` from the findings and the model review |
| `flags_chart.py` | Draws the chart at the top of the READMEs, in Portuguese and English, light and dark |
| `config.json` | The repository, the Portuguese category names, the files that are not law, and the chart's labels |
| `patch_detectors.py` | Fixes blind spots found in runs on several country repositories in the copy of global-law's scripts (`python -X utf8 patch_detectors.py <scripts dir>`) |
| `patch_detectors_vi.py`, `patch_es.py`, `patch_ca.py`, `patch_en.py`, `patch_de.py`, `patch_en_et.py`, `patch_co.py`, `patch_sv.py`, `patch_pt.py`, `patch_ru.py`, `patch_r18.py` | The same for the Vietnamese, Spanish, Catalan, English (two rounds), German, Colombian, Salvadoran, Brazilian Portuguese and Russian blind spots found by other runs, and a later round for several languages; this run's copy carries them all. `patch_pt.py` applies here, the corpus being Portuguese (dates such as "1º de janeiro", references such as "art. 3º-A" and "arts. 4º a 7º", repeal clauses); `patch_mo.py` adds the forms Macau writes differently |
| `patch_mo.py` | The fixes for Portuguese as written in Macau, below (`python -X utf8 patch_mo.py <scripts dir>`; each change carries a `patch_mo` marker, and one already in place is skipped) |
| `apply_patches.py` | Applies every patch above once, in order, recording each in `.kit_patches.json` in the scripts folder (`python -X utf8 apply_patches.py <scripts dir>`); `patch_mo.py` is last in its list |
| `redo.py` | Runs `apply_patches.py`, then again only the scans and detectors the fixes change, the model review of lapsed time limits, references to deleted provisions and empty periods, and the build (`python -X utf8 redo.py <run folder> [--keep-reviews] [--full]`; `--full` runs every step again through `run.sh`; `EMBED_FONTS` names the script that embeds the chart's fonts). Before the build it runs the kit's `patch_build_r7.py`, whose fixes this copy of `build_vulns.py` already has; not needed here, as every fix was in place before the run whose results are published |

The model review needs `LLM_BASE_URL`, `LLM_API_KEY`, `LLM_MODEL` and `LLM_AUTH` set for an OpenAI-compatible Responses API.
It was run as `bash run_triage.sh '^(data/|tools/|README|REPRODUCE|LICENSE|jurisdiction)'`; every law is under `basic-law/`,
`annexes/`, `code/`, `lei-relacoes-trabalho/` or `lei/`, so the review of lapsed time limits in law texts drew the same 4
flags as the review of all of them, and `build_vulns.py` keeps the later review of each flag.

The detectors in this copy already carried every fix of the kit's patches. Changes made for this repository:

- `pins.json` names the corpus language as `pt` (global-law's list of corpora gave none): the codes, Law 7/2008 and the
  Assembly's laws are in Portuguese; the Basic Law and its Annexes, in Chinese, are not read by the time-limit search, and
  their dates were read by hand.
- `add_root.py` is unchanged: the 64 commits that make a version carry `Kind: publisher` (each act's single version,
  credited to the Legislative Assembly or the Imprensa Oficial as the oldest version available), which the kit already
  counts as law. The two commits that moved the act folders and taught `tools/on.py` the new layout (`Kind: documentation`)
  are left out, as are the 13 commits with no `In-force` trailer (the READMEs, tables, tools and `REPRODUCE.md`).
- `patch_mo.py`, time limits (`ingest/textscan.py`): "até ao dia 30 de Junho de 2027" (European Portuguese puts "ao"
  between "até" and "dia") was not read; and the Slavic "do" (until) read the Portuguese "do" (of the), so that "produz
  efeitos a partir do dia 1 de Janeiro de 2021" and "Do dia 1 de Julho de 2026 até ..." were read as rules ending on that
  day. In a Portuguese corpus a match that opens with "do" is now skipped. Lapsed time limits went from 7 to 4 (4 gone, 1 new).
- `patch_mo.py`, references (`ingest/refscan.py`): "artigo 5.º" (the ordinal sign after a full stop, as Macau and Portugal
  write it) left ".º" after the number, so "artigos 7.º a 9.º" was read as article 7 alone, "artigo 3.º-A" lost its letter,
  and "artigo 26.º do Código Civil" was read as the act's own article 26. The number now takes ".º" with it. No count
  changed: no article has ever been removed here and none is held as a "(Revogado)" placeholder.
- `patch_mo.py`, duplicate numbering (`detectors/dup_labels.py`): a line that begins with a reference, where the text wraps
  ("artigo 71.º da Lei Básica da Região Administrativa Especial de"), was read as an article heading; a heading never
  begins with a lower-case letter. Duplicate numbering went from 8 to 0.
- `config.json` counts as not law `data/`, `tools/`, the root files and every `README.md` (each act's list of its files,
  and all that the folders of the seven 2026 laws not yet in force hold).
- There are no amounts in a dead currency to read: every amount is in patacas, and no text names the escudo.
