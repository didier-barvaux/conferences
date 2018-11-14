
ditaa = ditaa --overwrite --transparent --no-separation
pdflatex = pdflatex

images_generated = \
	images/rohc_only_headers_all.png \
	images/rohc_redundancy_one_packet.png \
	images/rohc_redundancy_one_flow.png \
	images/rohc_classification.png \
	images/rohc_wlsb.png

all: slides.pdf print.pdf

slides.pdf: slides.tex images/*.png $(images_generated)
	$(pdflatex) slides.tex
	$(pdflatex) slides.tex

print.pdf: print.tex
	$(pdflatex) print.tex
	$(pdflatex) print.tex

print.tex: slides.tex
	grep -v '\pause' slides.tex > print.tex

images/rohc_only_headers_all.png: images/rohc_only_headers_all.txt
	$(ditaa) $<

images/rohc_redundancy_one_packet.png: images/rohc_redundancy_one_packet.txt
	$(ditaa) $<

images/rohc_redundancy_one_flow.png: images/rohc_redundancy_one_flow.txt
	$(ditaa) $<

images/rohc_classification.png: images/rohc_classification.txt
	$(ditaa) $< 

images/rohc_wlsb.png: images/rohc_wlsb.txt
	$(ditaa) $< 

clean:
	$(RM) *.aux *.log *.nav *.out \
	      *.pdf *.snm *.toc *.vrb \
	      $(images_generated) print.tex

