SRC = Presentation.tex
PDF = Presentation.pdf
AUX = Presentation.aux
TEXC := latexmk
TEXC_OPTS += -shell-escape -xelatex -pdf -silent -interaction=nonstopmode -synctex=1
TEXMFHOME = $(shell kpsewhich -var-value=TEXMFHOME)
INSTALL_DIR = $(TEXMFHOME)/tex/latex/mtheme

.PHONY: clean install

all: $(PDF)

$(AUX):
		$(TEXC) $(TEXC_OPTS) $(SRC)

$(PDF): beamerthemem.sty $(AUX) $(SRC)
		$(TEXC) $(TEXC_OPTS) $(SRC)

continuous:
	$(TEXC) $(TEXC_OPTS) -pvc $(SRC)

clean:
		@rm -f $(PDF)

install:
		mkdir -p $(INSTALL_DIR)
		cp *.sty $(INSTALL_DIR)


