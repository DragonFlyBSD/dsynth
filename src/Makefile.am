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

dsynth_CFLAGS = $(openssl_CFLAGS) $(ncurses_CFLAGS)
dsynth_LDADD = $(openssl_LIBS) $(ncurses_LIBS)

AUTOMAKE_OPTIONS = subdir-objects
