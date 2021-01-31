AC_PREREQ([2.61])
AC_INIT([dsynth], [1.0.2], [tuxillo@quantumachine.net])

AC_CONFIG_AUX_DIR(config)
AC_CONFIG_MACRO_DIRS([m4])

AM_INIT_AUTOMAKE

AC_PROG_LIBTOOL
AC_PROG_MAKE_SET

LT_PREREQ([2.2])
LT_INIT

AC_LANG(C)

AC_ARG_WITH([md],
      AC_HELP_STRING([--with-md],
         [Enable libmd. This disables the OpenSSL check.]))

BUILD_PLATFORM=unknown

AC_MSG_CHECKING([for build platform])
# https://stackoverflow.com/questions/38898591/how-to-check-the-os-with-automake
case "${host_os}" in
	freebsd*)
		BUILD_PLATFORM=FreeBSD
		;;
	dragonfly*)
		BUILD_PLATFORM=DragonFly
		;;
	*)
		AC_MSG_ERROR(["Unsupported OS $host_os"])
		;;
esac
AC_MSG_RESULT([$BUILD_PLATFORM])

AC_CONFIG_SRCDIR(src/dsynth.c)
AC_CONFIG_FILES([Makefile src/Makefile])

AS_IF([test "x${with_md}" = xyes],
	[AC_CHECK_LIB([md], [MD5Data],
			    [AC_DEFINE([HAVE_MD], [1], [Have libmd]) have_md=true],
			    [AC_MSG_ERROR([libmd was not found in the system])]
			    )],
	[PKG_CHECK_MODULES(openssl, openssl)])

AM_CONDITIONAL([USE_LIBMD], [test  x$have_md = xtrue])


AC_CHECK_LIB([ncurses],
	[initscr],
	[AC_DEFINE([HAVE_BASE_NCURSES], [1], [Have base ncurses lib]) have_base_ncurses=true],
	[PKG_CHECK_MODULES(ncurses, ncurses)]
)

AM_CONDITIONAL([USE_BASE_NCURSES], [test  x$have_base_ncurses = xtrue])

AC_PROG_CC

AC_OUTPUT

