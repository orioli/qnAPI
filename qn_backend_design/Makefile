PICTURES=$(wildcard images/*) $(wildcard graphviz_images/*)

DOT_DEFINITIONS=$(wildcard dot/*.dot)
DOT_GRAPHS=$(patsubst %.dot,%.pdf,$(DOT_DEFINITIONS))

FDP_DEFINITIONS=$(wildcard fdp/*.dot)
FDP_GRAPHS=$(patsubst %.dot,%.pdf,$(FDP_DEFINITIONS))

all: Makefile qualnotes_backend_design.pdf qualnotes_backend_design.docx


qualnotes_backend_design.pdf: README.md $(PICTURES) $(DOT_GRAPHS) $(FDP_GRAPHS)
	pandoc -s  -N --toc --toc-depth=2 \
	-o $@ $< 

qualnotes_backend_design.docx: README.md $(PICTURES) $(DOT_GRAPHS) $(FDP_GRAPHS)
	pandoc -s  -N --toc --toc-depth=2 \
	-o $@ $< 

dot/%.pdf:dot/%.dot
	dot -Tpdf -o $@  $< 

fdp/%.pdf:fdp/%.dot
	fdp -Tpdf -o $@  $< 
