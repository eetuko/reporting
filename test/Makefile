
# Convert all files in this directory that have a .md suffix
SOURCE_DOCS := $(wildcard *.md)

EXPORTED_DOCS=\
 $(SOURCE_DOCS:.md=.html)


PANDOC=/usr/local/bin/pandoc
RM=/bin/rm

# Define table of content title
TOC_TITLE='Table of contents'
export TOC_TITLE
PANDOC_OPTIONS=-f markdown+emoji -s --self-contained --toc -V toctitle:$(TOC_TITLE)

# Define document title
TITLE='Title to be defined'
export TITLE
PANDOC_TITLE=-M title=$(TITLE)

PANDOC_HTML_OPTIONS=--to html5 -c ../css/style.css --template='../templates/custom.html5'

%.html : %.md
	$(PANDOC) $(PANDOC_OPTIONS) $(PANDOC_TITLE) $(PANDOC_HTML_OPTIONS) -o $@ $<
        
all : $(EXPORTED_DOCS)

clean:
	- $(RM) $(EXPORTED_DOCS)
