
INCLUDES = -I$(top_srcdir)/src/libstrongswan -I$(top_srcdir)/src/libhydra \
	-I$(top_srcdir)/src/libcharon ${nm_CFLAGS}

AM_CFLAGS = -rdynamic \
  -DNM_CA_DIR=\"${nm_ca_dir}\"

if MONOLITHIC
noinst_LTLIBRARIES = libstrongswan-nm.la
else
plugin_LTLIBRARIES = libstrongswan-nm.la
endif

libstrongswan_nm_la_SOURCES = \
	nm_plugin.h nm_plugin.c \
	nm_service.h nm_service.c \
	nm_creds.h nm_creds.c \
	nm_handler.h nm_handler.c

libstrongswan_nm_la_LDFLAGS = -module -avoid-version
libstrongswan_nm_la_LIBADD  = ${nm_LIBS}
