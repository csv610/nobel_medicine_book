# The Nobel Prize in Physiology or Medicine

A comprehensive LaTeX book documenting every Nobel laureate in Physiology or Medicine from 1901 to 2025.

## Overview

This book covers all 116 Nobel Prizes in Physiology or Medicine awarded between 1901 and 2025. It documents 232 laureates across medical and physiological science; prizes were not awarded in nine years because of World Wars and other circumstances.

- **Chapters:** 116 (one per awarded prize year; chapters with multiple laureates group them together)
- **Laureates documented:** 232 individuals
- **Years covered:** 1901–2025
- **Years without prize:** 1915, 1916, 1917, 1918, 1921, 1925, 1940, 1941, 1942
- **GitHub:** https://github.com/csv610/nobel_medicine_book

## Structure

```
nobel_medicine.tex          — master document (book class, 12pt a4paper)
README.md                   — this file
chapters/                   — 116 chapter source files
    1901_Behring.tex
    1902_Ross.tex
    ...
    2025_Brunkow_Ramsdell_Sakaguchi.tex
```

Each chapter covers a single award year and may include one, two, or three laureates. The master file includes an overview table and an index, then inputs all chapters in chronological order.

## Chapter Structure

Every chapter follows the same pattern:

- `\chapter[short]{full}` with a label for cross-referencing
- `\section*{Main Contribution}` — a one-sentence summary of the Nobel-winning work
- `\section{Official Citation}` — the exact Nobel citation text
- `\section{Background and Historical Context}` — era, scientific climate, and personal biography
- `\section{The Discovery/Contribution}` — detailed account of the research and its experimental basis
- `\section{Impact and Legacy}` — how the work shaped modern medicine and science
- `\index{}` entries for key people, diseases, techniques, and terms

## Contents

The book includes:

- A chronological overview table listing every year, laureate name(s), and key contribution
- 116 individual chapters, each covering one Nobel Prize year
- A back-of-book index (122 entries) for navigating by person, disease, and concept
- Nobel citation text for every award and laureate group

## Building

```bash
pdflatex --jobname=nobel_medicine nobel_medicine.tex
makeindex nobel_medicine
pdflatex --jobname=nobel_medicine nobel_medicine.tex
pdflatex --jobname=nobel_medicine nobel_medicine.tex
```

The master file uses `makeidx` for the back-of-book index and sets `\hbadness=10000`, `\vbadness=10000`, `\hfuzz=3pt`, `\vfuzz=2pt`, and `\tolerance=10000` to suppress overfull-box warnings for a clean compilation.

### Incremental builds

To compile only a subset of chapters during development, wrap the input section with:

```latex
\includeonly{chapters/1901_Behring,chapters/2024_Ambros_Ruvkun}
```

Remove the line or comment it out for a full build.

## Tools & Dependencies

- LaTeX (TeX Live 2024+)
- `makeidx` for index generation
- `hyperref` for clickable cross-references and links
- `booktabs`, `longtable` for tables
- `amsmath` for mathematical notation
- `microtype` for typographic refinement
- `geometry` for page layout

## Recent Work

- Expanded early chapters (Finsen, Koch, Fibiger, Behring) with clinical details, historical context, and global impact
- Added index entries across all chapters (122 entries total)
- Removed boilerplate language from chapter prose
- Fixed formatting issues (Unicode characters, double backslashes, bare `\item` outside itemize)

## License

All content is authored by csv610 and licensed under the MIT License unless otherwise noted.
