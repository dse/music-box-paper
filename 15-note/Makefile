default: 4x6-index-card-portrait.pdf letter-portrait.pdf

# hacky, I know.
INKSCAPE = $(shell \
	if [ -e "/cygdrive/c/Program Files/inkscape/inkscape.exe" ] ; then \
		echo dos '"/cygdrive/c/Program Files/inkscape/inkscape.exe"' ; \
	elif [ -e "/cygdrive/d/Program Files/inkscape/inkscape.exe" ] ; then \
		echo dos '"/cygdrive/d/Program Files/inkscape/inkscape.exe"' ; \
	else \
		echo inkscape ; \
	fi \
)

%.pdf: %.svg $(HOME)/lib/make/common.mk
	$(INKSCAPE) --without-gui --export-pdf "$@.tmp" "$<"
	mv "$@.tmp" "$@"
%.ps: %.svg $(HOME)/lib/make/common.mk
	$(INKSCAPE) --without-gui --export-ps "$@.tmp" "$<"
	mv "$@.tmp" "$@"
%.eps: %.svg $(HOME)/lib/make/common.mk
	$(INKSCAPE) --without-gui --export-eps "$@.tmp" "$<"
	mv "$@.tmp" "$@"

