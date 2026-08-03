# The Nobel Prize in Physiology or Medicine

A comprehensive LaTeX book documenting every Nobel laureate in Physiology or Medicine from 1901 to 2025.

## Overview

- **Chapters:** 115 (one per year, some years have multiple laureates in a single chapter)
- **Pages:** 715
- **Size:** 2.16 MB
- **Index entries:** 122
- **GitHub:** <https://github.com/csv610/nobel_medicine_book>

## Structure

```
nobel_medicine.tex          — master file (AMS book class, 12pt a4paper)
chapters/*.tex              — 115 chapter source files (one per laureate/year)
nobel_medicine.pdf          — compiled output
```

## Building

```bash
pdflatex --jobname=nobel_medicine nobel_medicine.tex
bibtex nobel_medicine          # if bibliography present
pdflatex --jobname=nobel_medicine nobel_medicine.tex
pdflatex --jobname=nobel_medicine nobel_medicine.tex
makeidx nobel_medicine         # rebuild index
```

The master file uses `makeidx` for the back-of-book index and `\hbadness=10000` / `\vbadness=10000` to suppress overfull-box warnings.

## Contents

The book includes an overview table (year, laureate(s), key contribution) and individual chapters for each laureate, covering:

- Biography and education
- Research methodology
- Nobel citation and awarded year
- Legacy and impact on modern medicine

Chapters are named `YYYY_LastName{.tex}` and sorted chronologically.

## Tools

- LaTeX (TeX Live 2026)
- `makeidx` for index generation
- `hyperref` for clickable links
- `booktabs`, `longtable`, `amsmath`

## Tests

```bash
pytest
```

## Recent Work

- Expanded early chapters (Finsen, Koch, Fibiger, Behring) with clinical details, historical context, and global impact
- Added index entries across chapters (122 entries total)
- Removed boilerplate language from chapter prose
- Fixed formatting issues (Unicode, double backslashes, bare `\item`)
