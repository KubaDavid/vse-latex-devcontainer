# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Critical Rule: Academic Integrity

**DO NOT write, generate, or modify any thesis content.** This includes:
- Chapter text, introductions, conclusions
- Abstracts, acknowledgments
- Bibliography annotations or descriptions
- Any academic prose in `.tex` files

The user must write all academic content themselves. AI assistance is limited to:
- LaTeX syntax help (fixing errors, formatting)
- Template configuration (metadata, structure)
- Build issues and debugging
- Explaining LaTeX commands or packages

## Project Overview

VSE LaTeX Devcontainer - a development container for writing VSE FIS thesis (bachelor/master) with AI assistance. Uses the official VSE template with APA7 citation style.

## Commands

```bash
task build          # Compile thesis to PDF (runs latexmk)
task watch          # Auto-rebuild on file changes
task clean          # Remove auxiliary files (keep PDF)
task clean-all      # Remove all generated files including PDF
task wordcount      # Count words in thesis
task wordcount-detailed  # Detailed word count by section
task bib            # Run biber for bibliography
```

## LaTeX Structure

Main file: `text/prace.tex`

| File | Purpose |
|------|---------|
| `prace.tex` | Main document - thesis metadata, structure |
| `makra.tex` | Packages, macros, formatting settings |
| `biblatex-setup.tex` | APA7 bibliography configuration (biber backend) |
| `zacatek.tex` | Title page, abstract, acknowledgments |
| `literatura.bib` | Bibliography entries |
| `czech-apa.lbx`, `slovak-apa.lbx` | APA7 localization (must stay in text/ root) |
| `prace.xmpdata` | PDF/A-2u metadata |

Chapter files: `uvod.tex`, `zaver.tex`, content chapters, `app01.tex`, `app02.tex`

## Key Configuration

- **Thesis type**: Set `\def\TypPrace{BP}` (bachelor) or `\def\TypPrace{DP}` (master) in `prace.tex`
- **Language**: Set `\def\Jazyk{cze}` (Czech), `slo` (Slovak), or `eng` (English)
- **Citations**: APA7 style via biblatex with biber backend
- **PDF standard**: PDF/A-2u compliant via `pdfx` package

## Important Notes

- `.lbx` files must remain in `text/` directory (biblatex requirement)
- Build output goes to `text/prace.pdf`
- LaTeX Workshop extension auto-builds on save (Ctrl+S)
- Grammar checking: LTeX extension (Czech + English)
