# Repository Guidelines

## Project Structure & Module Organization

This repository supports thesis writing and presentation preparation. Root-level Markdown files hold research notes and outline material, such as `outline.md`, `MUSIC vs ESPRIT.md`, and `Spatial Spectrum Estimation to MUSIC.md`. The `rts/` directory contains RTS/CTS-related reading notes. The `bak/` directory is used for backups or previous artifacts. The main slide deck is `thesis_filled.pptx`.

There is no conventional application source tree, package manifest, or test directory in this repository. Keep new research notes near related existing notes, and use clear topic-based filenames.

## Build, Test, and Development Commands

No build or runtime command is required for the current repository contents. Useful maintenance commands:

```powershell
git status --short
git diff --stat
Get-ChildItem -Force
```

Use `git status --short` before and after edits to confirm the changed files. Use `git diff --stat` to summarize text-file changes.

## Writing Style & Naming Conventions

Write notes in concise Markdown with descriptive headings. Prefer short paragraphs and bullet lists for technical explanations. Use exact technical terms consistently, for example `RTS/CTS`, `CSI`, `AoA`, `MUSIC`, and `hidden node`.

For filenames, prefer readable topic names already used in the repository, such as `paper for hidden node finding.md`. Avoid vague names like `notes.md` when adding new files.

## Testing Guidelines

There are no automated tests. Validate changes by reopening affected Markdown or presentation files and checking that the content is readable, complete, and technically consistent. For PPTX work, verify slide count, visible text, and layout integrity before reporting completion.

## Commit & Pull Request Guidelines

Recent commit messages are short and descriptive, for example `add picture of steering vector` and `add CSI, hidden node, rts/cts info`. Use a concise imperative or descriptive subject. Avoid date-only messages such as `7/9`.

Pull requests should summarize the thesis content changed, list affected files, and mention any PPTX or visual-review steps performed.

## Agent-Specific Instructions

Preserved project instructions:

- This is repo for thesis
- DO NOT MODIFY PPTX, just read and output the text and ask me for modification