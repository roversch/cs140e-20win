# https://stackoverflow.com/questions/2463356/make-failure-in-subdirectory-make-not-stopping-build

PROGS := 0char-inf  1hello-inf  2hello-once

MAKEFLAGS +=  --no-print-directory

ifndef CS140E_PATH
$(error CS140E_PATH not defined!)
endif
MK = $(CS140E_PATH)/support/mk/template.one-file.mk

all clean: $(PROGS)

all: TARGET=all
clean: TARGET=clean

# recursive call to make: if you want to suppress output, get rid of the -s
$(PROGS): force
	@make -f $(MK) NAME=$@ $(TARGET)

.PHONY: force
	force :;
