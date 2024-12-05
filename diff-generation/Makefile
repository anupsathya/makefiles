# Author: Anup Sathya
# Created: 12-05-2024

# Default target
.PHONY: all
all: install diff clean

# Installation
.PHONY: install
install:
	@echo "This tool requires homebrew. Make sure you have homebrew installed."
	@sleep 2
	@echo "Installing latexpand..."
	@echo "Downloading..." 
	cd original && curl -O https://mirrors.rit.edu/CTAN/support/latexpand/latexpand;
	cd revised && curl -O https://mirrors.rit.edu/CTAN/support/latexpand/latexpand;
	@brew install latexdiff
	@echo "Installation completed."

# Generating the diff file
.PHONY: diff
diff:
	cd original && perl latexpand original.tex > original-temp.tex;
	cp original/original-temp.tex revised/original-temp.tex;
	cd revised && perl latexpand revised.tex > revised-temp.tex;
	cd revised && latexdiff original-temp.tex revised-temp.tex > changes-marked.tex;
	cp revised/changes-marked.tex changes-marked.tex;

# Cleaning up temporary files
.PHONY: clean
clean:
	rm original/original-temp.tex;
	rm revised/revised-temp.tex;