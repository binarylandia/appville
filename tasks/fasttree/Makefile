SHELL = /bin/bash

CC      ?= gcc
CFLAGS  ?= -O3 -finline-functions -funroll-loops -Wall
LDFLAGS ?= -lm
STRIP   ?= strip
prefix  ?= /usr/local
build_dir ?= .build

EXE_SUFFIX := $(if $(findstring mingw,$(CC)),.exe,)

TARGETS = $(addsuffix $(EXE_SUFFIX),$(build_dir)/FastTree $(build_dir)/FastTreeDbl $(build_dir)/FastTreeMP $(build_dir)/FastTreeDblMP)

.PHONY: all install clean

all: $(TARGETS)

install: $(TARGETS)
	@$(foreach exe,$(TARGETS),\
		install -D -m 755 -s --strip-program=$(STRIP) $(exe) $(prefix)/bin/$(notdir $(exe));)

clean:
	@rm -fv $(TARGETS)

$(TARGETS): $(build_dir)
	$(CC) $(CFLAGS) -o $@ FastTree.c $(LDFLAGS)

$(build_dir)/FastTreeDbl$(EXE_SUFFIX) $(build_dir)/FastTreeDblMP$(EXE_SUFFIX): CFLAGS += -DUSE_DOUBLE
$(build_dir)/FastTreeMP$(EXE_SUFFIX) $(build_dir)/FastTreeDblMP$(EXE_SUFFIX): CFLAGS += -DOPENMP -fopenmp

$(build_dir):
	@mkdir -p $@
