# $Id$

bin_PROGRAMS = file
#CLEANFILES =

#CPPFLAGS +=
CFLAGS += -D_GNU_SOURCE -D_BSD_SOURCE -std=gnu99
CFLAGS += -fstack-protector-all
if IS_PIE
CFLAGS += -fPIE
LDFLAGS += -pie
endif
if IS_DEBUG
CFLAGS += -O0 -g
CFLAGS += -Wno-long-long -Wall -W -Wnested-externs -Wformat=2
CFLAGS += -Wmissing-prototypes -Wstrict-prototypes -Wmissing-declarations
CFLAGS += -Wwrite-strings -Wshadow -Wpointer-arith -Wsign-compare
CFLAGS += -Wundef -Wbad-function-cast -Winline -Wcast-align
CFLAGS += -Wdeclaration-after-statement -Wno-pointer-sign
CPPFLAGS += -DDEBUG
else !IS_DEBUG
CFLAGS += -O2
endif

dist_man1_MANS = file.1
dist_man5_MANS = magic.5

dist_file_SOURCES = \
	file.c \
	file.h \
	magic.h \
	magic-dump.c \
	magic-load.c \
	magic-test.c \
	magic-common.c \
	text.c \
	xmalloc.c \
	xmalloc.h
if PRCTL
dist_file_SOURCES += seccomp-sandbox.c
endif

nodist_file_SOURCES =
if NO_STRLCAT
nodist_file_SOURCES += compat/strlcat.c
endif
if NO_STRLCPY
nodist_file_SOURCES += compat/strlcpy.c
endif
if NO_REALLOCARRAY
nodist_file_SOURCES += compat/reallocarray.c
endif
if NO_VIS
nodist_file_SOURCES += compat/vis.c
endif
