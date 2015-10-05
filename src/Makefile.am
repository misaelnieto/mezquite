## Process this file with automake to produce Makefile.in

## Created by Anjuta


uidir = $(pkgdatadir)/ui
ui_DATA = mezquite.ui


AM_CPPFLAGS = \
	-DPACKAGE_LOCALE_DIR=\""$(localedir)"\" \
	-DPACKAGE_SRC_DIR=\""$(srcdir). \
	$(libxml-2.0_CFLAGS)"\" \
	-DPACKAGE_DATA_DIR=\""$(pkgdatadir)"\" \
	$(MEZQUITE_CFLAGS)

AM_CFLAGS =\
	 -Wall\
	 -g

bin_PROGRAMS = mezquite

mezquite_SOURCES = \
	mezquite.vala config.vapi

mezquite_VALAFLAGS =  --pkg libgda-6.0  \
	--pkg gtk+-3.0 --pkg libxml-2.0


mezquite_LDFLAGS =

mezquite_LDADD = $(MEZQUITE_LIBS) \
	$(libxml-2.0_LIBS)


if PLATFORM_WIN32
mezquite_LDFLAGS += -Wl,--export-all-symbols
else
mezquite_LDFLAGS += -Wl,--export-dynamic
endif

if NATIVE_WIN32
mezquite_LDFLAGS += -mwindows
endif


EXTRA_DIST = $(ui_DATA)

# Remove ui directory on uninstall
uninstall-local:
	-rm -r $(uidir)
	-rm -r $(pkgdatadir)

