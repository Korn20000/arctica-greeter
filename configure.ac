# -*- Mode: m4; indent-tabs-mode: nil; tab-width: 4 -*-

dnl Process this file with autoconf to produce a configure script.

AC_INIT(arctica-greeter, 0.99.0.1)
AC_CONFIG_MACRO_DIR(m4)
AM_INIT_AUTOMAKE
AM_PROG_CC_C_O
AM_PROG_VALAC([0.24.0])
AM_CONFIG_HEADER(config.h)
AM_MAINTAINER_MODE
m4_ifdef([AM_SILENT_RULES], [AM_SILENT_RULES(yes)])

GLIB_GSETTINGS

dnl ###########################################################################
dnl Dependencies
dnl ###########################################################################


dnl #### removed from PKG_CHECK_MODULES: libido3-0.
PKG_CHECK_MODULES(ARCTICA_GREETER, [
    gtk+-3.0
    gdk-x11-3.0
    libayatana-ido3-0.4 >= 0.4.0
    ayatana-indicator3-0.4 >= 0.6.0
    liblightdm-gobject-1 >= 1.12.0
    freetype2
    cairo-ft
    libcanberra
    pixman-1
    x11
    xext
])

AC_DEFINE_UNQUOTED([INDICATOR_FILE_DIR], ["${prefix}/share/ayatana/indicators"], [Indicator files are searched for in this directory])

INDICATORDIR=`$PKG_CONFIG --variable=indicatordir ayatana-indicator3-0.4`
AC_SUBST(INDICATORDIR)

if $PKG_CONFIG --exists gnome-settings-daemon; then
    GSD_BINARY=`$PKG_CONFIG --variable=binary gnome-settings-daemon`
    if test -z "$GSD_BINARY"; then
        AC_MSG_NOTICE([Could not find path to gnome-settings-daemon binary])
    else
        SD_BINARY="$GSD_BINARY"
    fi

fi

if test -z "$SD_BINARY"; then
    AC_MSG_ERROR([Could not find any supported X11 settings daemon])
else
    AC_DEFINE_UNQUOTED([SD_BINARY], ["$SD_BINARY"], [Path to g-s-d])
fi

dnl ###########################################################################
dnl Internationalization
dnl ###########################################################################

IT_PROG_INTLTOOL(0.35.0)
GETTEXT_PACKAGE=arctica-greeter
AC_DEFINE_UNQUOTED(GETTEXT_PACKAGE, "$GETTEXT_PACKAGE", Gettext package)
AC_SUBST(GETTEXT_PACKAGE)

dnl ###########################################################################
dnl Files to generate
dnl ###########################################################################

AC_CONFIG_FILES([
Makefile
data/Makefile
po/Makefile.in
src/Makefile
tests/Makefile
])
AC_OUTPUT
