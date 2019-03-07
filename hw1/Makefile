# You may override this variable from the command line. E.g.:
# make target=foo
# make clean target=foo
target = hw1

.PHONY : clean all

all : $(patsubst %,%.pdf,$(target)) clean

clean :
	for i in aux log bbl blg bcf out run.xml; do \
		rm -f $(patsubst %,%.$$i,$(target)); \
	done
	-rm -f *~

# You may append other dependencies
%.pdf : %.tex
	$(eval basename = $(patsubst %.tex,%,$<))
	xelatex $(basename)
	acrobat $(target).pdf &