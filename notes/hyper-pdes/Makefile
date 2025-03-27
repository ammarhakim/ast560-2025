all: hyper-pdes.pdf hw-hyper-pdes.pdf

hyper-pdes.pdf: hyper-pdes.tex
	pdflatex -shell-escape hyper-pdes
	pdflatex -shell-escape hyper-pdes
	pdflatex -shell-escape hyper-pdes
	cp hyper-pdes.pdf ../../source/_static

hw-hyper-pdes.pdf: hw-hyper-pdes.tex
	pdflatex -shell-escape hw-hyper-pdes
	pdflatex -shell-escape hw-hyper-pdes
	pdflatex -shell-escape hw-hyper-pdes
	cp hw-hyper-pdes.pdf ../../source/_static

clean:
	rm -rf hyper-pdes.pdf *~ hyper-pdes.aux hyper-pdes.bbl hyper-pdes.blg hyper-pdes.log
	rm -rf hw-hyper-pdes.pdf *~ hw-hyper-pdes.aux hw-hyper-pdes.bbl hw-hyper-pdes.blg hw-hyper-pdes.log
