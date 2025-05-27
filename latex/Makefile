TEX_FILES := $(shell find . -name '*.tex')
IMAGE_DIR := images
IMAGE_FILES := $(shell find $(IMAGE_DIR) -type f \( -name '*.pdf' -o -name '*.png' -o -name '*.jpg' \))

tidy:
	rm -f *.dvi *.aux *.log *.blg *.bbl *.fdb_latexmk *.fls *.out *.synctex.gz *.cut

clean-images:
	@echo "Checking for unused images..."
	@for img in $(IMAGE_FILES); do \
		name=$$(basename $$img); \
		ref=$$(grep -F "$$name" $(TEX_FILES)); \
		if [ -z "$$ref" ]; then \
			echo "Deleting unused image: $$img"; \
			rm $$img; \
		fi \
	done

acm:
	rm -f *.bbx *.bst *.png *.pdf *.bib *.cbx *.cls *.dbx *.txt
	cp sample-sigconf-authordraft.tex main.tex
	rm -f sample-*
	touch references.bib
	mkdir figures
	mkdir sections
