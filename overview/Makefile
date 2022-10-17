.PHONY: all
all: notes.pdf slides.pdf

LATEXFLAGS+=	-shell-escape

SRC+=		preamble.tex
SRC+=		abstract.tex contents.tex

notes.pdf: notes.tex
notes.pdf: ${SRC}

slides.pdf: slides.tex
slides.pdf: ${SRC}
#slides.pdf: ltxobj/slides-incomplete.pdf

ltxobj/slides-incomplete.pdf: ${SRC} ${DEPENDS}
ltxobj/slides-incomplete.pdf: slides.tex
	${COMPILE.tex}
	mv ltxobj/slides.pdf ltxobj/slides-incomplete.pdf
	mv ltxobj/slides.snm ltxobj/slides-incomplete.snm


.PHONY: clean
clean:
	${RM} notes.pdf slides.pdf


INCLUDE_MAKEFILES=../makefiles
include ${INCLUDE_MAKEFILES}/tex.mk
