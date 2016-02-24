all: modele-presentation-lille1.pdf modele-cours-lille1.pdf 

%.pdf: %.tex
	pdflatex $<
	pdflatex $<

modele-cours-lille1.pdf: modele-cours-lille1.tex $(wildcard ??-*.tex)

.PHONY: clean
clean:
	-rm *~ *.aux *.log *.nav *.out *.snm *.toc *.vrb
