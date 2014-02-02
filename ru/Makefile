all: main.pdf

%.pdf: %.tex $(wildcard *.tex) $(addsuffix .ps,$(basename $(wildcard *.dot)))
	xelatex $< || rm $@
	xelatex $< || rm $@

open: main.pdf
	xdg-open $<

%.ps: %.dot
	dot -Tps:cairo -o$@ $<

clean:
	$(RM) *.ps *.pdf *.aux *.log *.toc *.nav *.snm *.out

.PHONY: all open clean
