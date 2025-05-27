# LaTeX Paper Build System

This repository contains a Makefile to streamline building and maintaining your LaTeX paper project. It includes commands for compiling the paper, cleaning auxiliary files, and managing images and ACM-related templates.

## 📁 Project Structure

* `main.tex` – Main LaTeX file
* `images/` – Directory containing all image files
* `sections/` – Subfiles for organizing the paper (optional)
* `references.bib` – Bibliography file
* `Makefile` – Automation commands

## 🛠️ Available Commands

Run these using `make <target>`:

### `make` or `make all`

Compile the paper into a PDF (`main.pdf`) using `latexmk`. Cleans up auxiliary files after compilation.

### `make pdf`

Only compiles the paper to PDF (uses `bibtex` for bibliography).

### `make tidy`

Removes LaTeX auxiliary files to keep the directory clean:

```
*.aux *.log *.blg *.bbl *.dvi *.fdb_latexmk *.fls *.out *.synctex.gz *.cut
```

### `make clean-images`

Finds and deletes image files in the `images/` folder that are **not referenced** in any `.tex` file.
Helpful to reduce clutter and remove unused assets.

### `make acm`

Initializes the project using the **ACM LaTeX template** (as provided by [Overleaf's official ACM template](https://www.overleaf.com/latex/templates/acm-conference-proceedings-primary-article-template/wbvnghjbzwpc)):

* Renames `sample-sigconf-authordraft.tex` to `main.tex`
* Deletes other sample/template files (e.g., `sample-*`, `.bbx`, `.bst`, `.cbx`, etc.)
* Creates a blank `references.bib`
* Sets up empty `figures/` and `sections/` folders for organization

Use this when starting a new ACM paper project based on the Overleaf template.

## 🧠 Notes

* This Makefile assumes you are using `latexmk` and `bibtex`. Make sure both are installed.
* Image cleanup is conservative—only images not mentioned *exactly by name* (e.g., `fig1.pdf`) are removed.

## ✅ Requirements

* `latexmk`
* `bibtex`
* `grep`, `find`, `basename` (standard Unix tools)
