AM_LDFLAGS = -lpthread -lutil

bin_PROGRAMS = dsynth
dsynth_SOURCES = \
	build.c \
	bulk.c \
	config.c \
	dsynth.c \
	dsynth.h \
	html.c \
	icrc32.c \
	monitor.c \
	mount.c \
	ncurses.c \
	pkglist.c \
	repo.c \
	runstats.c \
	status.c \
	subs.c

man1_MANS = dsynth.1
dist_man1_MANS = dsynth.1

if USE_LIBMD
CRYPTO_CFLAGS =
CRYPTO_LDADD = -lmd
else
CRYPTO_CFLAGS = $(openssl_CFLAGS)
CRYPTO_LDADD = $(openssl_LIBS)
endif

if USE_BASE_NCURSES
EXTRA_CFLAGS =
EXTRA_LDADD = -lcurses
else
EXTRA_CFLAGS = $(ncurses_CFLAGS)
EXTRA_LDADD = $(ncurses_LIBS)
endif

dsynth_CFLAGS = $(AM_CFLAGS) $(EXTRA_CFLAGS) $(CRYPTO_CFLAGS)
dsynth_LDADD = $(AM_LDADD) $(EXTRA_LDADD) $(CRYPTO_LDADD)

AUTOMAKE_OPTIONS = subdir-objects
