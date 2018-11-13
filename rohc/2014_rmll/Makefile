
all: slides.pdf

slides.pdf: slides.tex images/*.png
	pdflatex slides.tex
	pdflatex slides.tex

clean:
	$(RM) *.aux *.log *.nav *.out \
	      *.pdf *.snm *.toc

