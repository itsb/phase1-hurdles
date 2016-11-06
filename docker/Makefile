HUBFOLDER ?= itsb

all: base phase1

base:
	docker build -t $(HUBFOLDER)/sc2:$@ ./$@

phase1: base
	docker build -t $(HUBFOLDER)/sc2:$@ ./$@

.PHONY: all base phase1
