AC_PREREQ([2.61])
AC_INIT([dsynth], [1.0.2], [tuxillo@quantumachine.net])

AC_CONFIG_AUX_DIR(config)
AM_INIT_AUTOMAKE

AC_CONFIG_MACRO_DIRS([m4])

AC_PROG_LIBTOOL
AC_PROG_MAKE_SET

LT_PREREQ([2.2])
LT_INIT

AC_LANG(C)

AC_CONFIG_SRCDIR(src/dsynth.c)
AC_CONFIG_FILES([Makefile src/Makefile])

PKG_CHECK_MODULES(openssl, openssl)
PKG_CHECK_MODULES(ncurses, ncurses)

AC_PROG_CC

AC_OUTPUT

