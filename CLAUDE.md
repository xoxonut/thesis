# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

Reply in zh-tw
Reply in zh-tw
Reply in zh-tw


## Repository purpose

This is a thesis-writing and presentation-preparation repository, not a software project. There is no build system, package manifest, or test suite. The thesis topic is AP-side hidden-node risk-aware RTS threshold control for Wi-Fi, using AoA estimation (MUSIC) from AP-side multi-antenna CSI.

## Project structure

- Root-level topic notes hold research material, e.g. `MUSIC vs ESPRIT.md`, `paper for hidden node finding.md`.
- `rts/cts paper.md` — RTS/CTS-related literature notes (inside the `rts/` directory).
- `slide storyline review.md` — storyline review of `thesis_new_template.pptx` with proposed slide-order fixes.
- `bak/` — backups of previous artifacts (e.g. an earlier `thesis_filled.pptx`). Do not treat these as current.
- `thesis_new_template.pptx`, `template.pptx` — slide decks. `thesis_new_template.pptx` is the current working deck. See PPTX rule below.
- `outline.md` (the former chapter-by-chapter thesis outline) has been removed; there is currently no standalone outline file. The section structure of `thesis_new_template.pptx` (Introduction, Background, AoA-Assisted Dynamic RTS Threshold Adaptation, Evaluation, Conclusion) is the closest reference for thesis structure.

Many notes are written in Traditional Chinese mixed with English technical terms; match the existing language of a note when editing it.

## Working with PPTX files

**Do not modify PPTX files directly.** Only read them and output their text content; ask the user before making any change, and let the user (or an explicit follow-up instruction) perform the actual edit.

## Writing conventions

- Keep notes as concise Markdown with descriptive headings; prefer short paragraphs and bullet lists.
- Use exact technical terms consistently: `RTS/CTS`, `CSI`, `AoA`, `MUSIC`, `hidden node`.
- Use readable, topic-based filenames (e.g. `paper for hidden node finding.md`), not vague names like `notes.md`.
- Keep new research notes near related existing notes rather than introducing new top-level structure.

## Validating changes

There are no automated tests. Validate changes by reopening affected Markdown or presentation files and confirming the content is readable, complete, and technically consistent with the current deck structure. For any PPTX-adjacent work, verify slide count, visible text, and layout integrity before reporting completion (per the no-direct-modification rule above).

## Git workflow

- Before and after edits, run `git status --short` and `git diff --stat` to confirm what changed.
- Commit messages should be short, descriptive, and imperative/descriptive (e.g. `add picture of steering vector`), not date-only (avoid messages like `7/9`).
- PR descriptions should summarize the thesis content changed, list affected files, and mention any PPTX visual-review steps performed.
- If a sandbox helper fails before Git can run, rerun the read-only checks (`git status --short`, `git diff --stat`) outside the sandbox with approval before committing.
