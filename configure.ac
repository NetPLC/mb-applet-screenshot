AC_PREREQq(2.53)
AC_INIT(screenshot, 0.3, [yocto@yoctoproject.org])
AM_INIT_AUTOMAKE()
AC_CONFIG_SRCDIR(screenshot-utils.c)
AM_CONFIG_HEADER(config.h)

m4_ifdef([AM_SILENT_RULES], [AM_SILENT_RULES([yes])])

AM_DISABLE_STATIC
AC_ISC_POSIX
AC_PROG_CC
AC_STDC_HEADERS
AC_PROG_LIBTOOL

PKG_CHECK_MODULES(DEPS, x11 gdk-x11-3.0 gtk+-3.0)

MB_APPLET="yes"

AC_ARG_WITH(applet,
     AC_HELP_STRING([--without-applet], [disable building of matchbox applet]),
     [
	if test "x$withval" = "xno"; then
	   MB_APPLET="no"
	else
	   PKG_CHECK_MODULES(MBAPP, matchbox-panel)
	fi
     ],
     [PKG_CHECK_MODULES(MBAPP, matchbox-panel)])

AM_CONDITIONAL(WITH_MB_APPLET, test "x$MB_APPLET" = "xyes")

dnl appletdir=$(pkg-config --variable=appletdir matchbox-panel)

APPLETDIR=$()
AC_OUTPUT([
Makefile
])
