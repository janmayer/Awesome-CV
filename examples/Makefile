.PHONY: examples

LATEX = lualatex
BIBER = biber

examples: coverletter.pdf cv.pdf resume.pdf

coverletter.pdf: coverletter.tex
	$(LATEX) --interaction=nonstopmode --output-directory=build $<

%.pdf: %.tex
	$(LATEX) --interaction=nonstopmode --output-directory=build $<
	$(BIBER) build/$(basename $(notdir $<))
	$(LATEX) --interaction=nonstopmode --output-directory=build $<
	$(LATEX) --interaction=nonstopmode --output-directory=build $<

clean:
	rm -rf build
