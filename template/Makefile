OUT_DIR=out/

all:	clean cv resume coverletter postgen-clean
	
cv:
	rm -f $(OUT_DIR)/CV.pdf 
	latexmk  -bibtex -pdf -outdir=out -interaction=nonstopmode CV
	make postgen-clean

resume:
	rm -f $(OUT_DIR)/resume.pdf 
	latexmk  -bibtex -pdf -outdir=out -interaction=nonstopmode resume
	make postgen-clean

coverletter:
	rm -f $(OUT_DIR)/CoverLetter.pdf
	latexmk  -bibtex -pdf -outdir=out -interaction=nonstopmode CoverLetter
	make postgen-clean

to-docx:
	rm -rf ../to_share/docx
	mkdir ../to_share/docx
	pandoc -s Research.tex --mathjax -o ../to_share/docx/Research.docx
	pandoc -s Teaching.tex --mathjax -o ../to_share/docx/Teaching.docx
	pandoc -s Diversity.tex --mathjax -o ../to_share/docx/Diversity.docx
	pandoc -s CV.tex --mathjax -o ../to_share/docx/CV.docx
	pandoc -s CoverLetter.tex --mathjax -o ../to_share/docx/CoverLetter.docx

clean:
	rm -vf *.aux *.log *.out *concordance.tex $(OUT_DIR)/*.pdf 
	
postgen-clean:
	rm -vf \
		$(OUT_DIR)/*.aux \
		$(OUT_DIR)/*.log \
		$(OUT_DIR)/*.out \
		$(OUT_DIR)/*concordance.tex \
		$(OUT_DIR)/*.fdb_latexmk \
		$(OUT_DIR)/*.fls \
		$(OUT_DIR)/*.xml \
		$(OUT_DIR)/*.bbl \
		$(OUT_DIR)/*.bcf \
		$(OUT_DIR)/*.blg \
		