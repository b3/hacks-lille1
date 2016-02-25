all: modele-presentation-lille1.pdf modele-cours-lille1.pdf modele-presentation.pdf

%.pdf: %.tex
	pdflatex $<
	pdflatex $<

%.pdf: %.md tex-friendly-zone.jpg
	./md2beamer $^

modele-cours-lille1.pdf: modele-cours-lille1.tex $(wildcard ??-*.tex)

.PHONY: clean
clean:
	-rm *~ *.aux *.log *.nav *.out *.snm *.toc *.vrb
