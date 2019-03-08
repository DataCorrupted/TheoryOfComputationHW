ifeq ($(OS),Windows_NT)
	PDFVIEWER=acrobat
else
	PDFVIEWER=xdg-open
endif

TARGET = hw1

.PHONY : clean all

all : $(patsubst %,%.pdf,$(TARGET)) clean

clean :
	for i in aux log bbl blg bcf out run.xml; do \
		rm -f $(patsubst %,%.$$i,$(TARGET)); \
	done
	-rm -f *~

# You may append other dependencies
%.pdf : %.tex
	$(eval basename = $(patsubst %.tex,%,$<))
	xelatex $(basename)
	$(PDFVIEWER) $(TARGET).pdf &