SHELL = /bin/sh

.PHONY : proposal pdf clean tar

proposal : proposal.ps
pdf : proposal.pdf
tar : proposal.tar.gz

TEXFILES = proposal.tex introduction.tex atca-rce-cob.tex author_list.tex bibl.tex conclusions.tex lbne-implementation.tex schedule-budget.tex
FIGURES  = 

proposal.dvi : $(TEXFILES) $(FIGURES)

proposal.tar.gz : $(TEXFILES) $(FIGURES)
	tar zcvf $@ $(TEXFILES) $(FIGURES) GNUmakefile

clean :
	rm -f proposal.ps *.dvi *.aux *.log *.bak *.lof *.lot *.toc *gz *~

%.pdf : %.ps
	ps2pdf $<

%.ps : %.dvi
	dvips -P pdf -t letter $<

%.dvi : %.tex
	latex $<
	latex $<

