# -*- Mode: Automake; indent-tabs-mode: t; tab-width: 4 -*-

xgreeterdir = $(datarootdir)/xgreeters
dist_xgreeter_DATA = arctica-greeter.desktop

backgroundsdir = $(datarootdir)/backgrounds
dist_backgrounds_DATA = \
	arctica-greeter.png

dist_pkgdata_DATA = \
	a11y.svg \
	active.png \
	arrow_left.png \
	arrow_right.png \
	cof.png \
	dialog_close.png \
	dialog_close_highlight.png \
	dialog_close_press.png \
	gnome_badge.png \
	hibernate_highlight.png \
	hibernate.png \
	kde_badge.png \
	logo.png \
	lxde_badge.png \
	mate_badge.png \
	message.png \
	openbox_badge.png \
	recovery_console_badge.png \
	remote_login_help.png \
	restart_highlight.png \
	restart.png \
	shadow.png \
	shutdown_highlight.png \
	shutdown.png \
	suspend_highlight.png \
	suspend.png \
	switcher_corner.png \
	switcher_left.png \
	switcher_top.png \
	twm_badge.png \
	ubuntu_badge.png \
	unknown_badge.png \
	xfce_badge.png \
	xsession_badge.png

logo.png: logo-bare.png
	../src/logo-generator --logo logo-bare.png --text '$(VERSION)' --output logo.png

@GSETTINGS_RULES@
gsettings_SCHEMAS = \
	org.ArcticaProject.arctica-greeter.gschema.xml

dist_man1_MANS = arctica-greeter.1

EXTRA_DIST = \
	$(gsettings_SCHEMAS)

DISTCLEANFILES = \
	Makefile.in \
	logo.png
