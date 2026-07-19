# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

Reply in zh-tw


## Repository purpose

This repository contains implementation, presentation, and experiment artifacts for the thesis on AP-side hidden-node risk-aware RTS threshold control for Wi-Fi, using AoA estimation (MUSIC) from AP-side multi-antenna CSI. It currently has no build system, package manifest, or automated test suite.

Research questions, literature synthesis, meeting notes, decisions, project status, and task tracking are canonical in the [Obsidian thesis project](https://github.com/xoxonut/OB/blob/master/10%20Projects/Thesis%20-%20Hidden%20Node%20and%20MUSIC/Thesis%20-%20Hidden%20Node%20and%20MUSIC.md).

## Project structure

- `thesis proposal 7_17.pptx` — current working proposal deck.
- `template.pptx` — presentation template, not the current deck.
- `slide draft - proposed main deck.md` — proposed 15-slide content associated with the deck.
- `slide storyline review.md` — review of an earlier 26-slide proposal deck; use its storyline guidance, not its slide numbers, for the current deck.
- `papers/` — source PDFs retained with the artifact repository; literature synthesis belongs in Obsidian.
- `bak/` — previous presentation artifacts. Do not treat these as current.
- `skills/` — repository-specific workflows for presentation work.

Many notes are written in Traditional Chinese mixed with English technical terms; match the existing language of a note when editing it.

## Knowledge and artifact boundary

- Add literature notes, research ideas, meeting notes, decisions, project status, and TODOs to the Obsidian project.
- Add code, figures, datasets, raw or processed results, decks, and reproduction instructions to this repository.
- For an experiment, keep the complete setup and outputs here. Add only the conclusion and a link to the relevant Git commit to Obsidian.
- Markdown in this repository must be artifact-adjacent, such as a slide draft, an experiment README, or code documentation. Do not start a second literature notebook here.

## Working with PPTX files

**Do not modify PPTX files directly.** Only read them and output their text content; ask the user before making any change, and let the user (or an explicit follow-up instruction) perform the actual edit.

## Writing conventions

- Keep notes as concise Markdown with descriptive headings; prefer short paragraphs and bullet lists.
- Use exact technical terms consistently: `RTS/CTS`, `CSI`, `AoA`, `MUSIC`, `hidden node`.
- Use readable, artifact-based filenames, not vague names like `notes.md`.
- Link to canonical Obsidian notes instead of copying research synthesis into this repository.

## Validating changes

There are no automated tests. Validate Markdown by reopening affected files and confirming the content is readable, complete, and consistent with the current deck. For any PPTX-adjacent work, verify slide count, visible text, and layout integrity before reporting completion (per the no-direct-modification rule above).

## Git workflow

- Before and after edits, run `git status --short` and `git diff --stat` to confirm what changed.
- Commit messages should be short, descriptive, and imperative/descriptive (e.g. `add picture of steering vector`), not date-only (avoid messages like `7/9`).
- PR descriptions should summarize the thesis content changed, list affected files, and mention any PPTX visual-review steps performed.
- If a sandbox helper fails before Git can run, rerun the read-only checks (`git status --short`, `git diff --stat`) outside the sandbox with approval before committing.
