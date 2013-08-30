PANDOC = pandoc -s --webtex 
MD0 = $(patsubst %.md0,%.md,$(wildcard *.md0))
HTML = $(patsubst %.md,%.html,$(wildcard *.md)) $(patsubst %.md0,%.html,$(wildcard *.md0))
PARG = -c ../css/pmag.css -B header.htm -A footer.htm --base-header-level=1 
RM = rm -f

.PHONY: all

all: $(HTML) 

html: $(MD0) $(HTML)

shtm: 
	$(PANDOC) $(MD) -o ../book/pmag.html $(PARG)

md0: $(MD0)
    
%.md0 : 
	node md0.js $*.md0 $*.md
    
%.md: %.md0
	node md0.js $< $@

%.html: %.md
	$(PANDOC) $< reflink.md9 -o ../htm/$@ $(PARG)
	
clean: 
	${RM} ../htm/*.*
	${RM} ../book/*.*
	${RM} ../timg/*.*
	${RM} $(MD0)

    
# $?�G�N���w�Q��s�� dependencies ���ȡC�]�N�O dependencies ���A�� targets �ٷs���ȡC
# $@�G�N�� targets ���ȡC
# $<�G�N���Ĥ@�� dependencies ���ȡC
# $* : �N�� targets �ҫ��w���ɮסA�����]�t���ɦW�C