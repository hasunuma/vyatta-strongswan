EXTRA_DIST = ext/dumm.c ext/README \
  ext/lib/dumm.rb ext/lib/dumm/guest.rb

lib_LTLIBRARIES = libdumm.la
ipsec_PROGRAMS = dumm irdumm

libdumm_la_SOURCES = dumm.c dumm.h guest.c guest.h iface.c iface.h \
  bridge.c bridge.h mconsole.c mconsole.h cowfs.h cowfs.c
dumm_SOURCES = main.c
irdumm_SOURCES = irdumm.c

libdumm_la_LIBADD = $(top_builddir)/src/libstrongswan/libstrongswan.la \
  -lbridge -lfuse -lutil
dumm_LDADD = libdumm.la ${gtk_LIBS}
irdumm_LDADD = libdumm.la -lruby1.8

INCLUDES = -I$(top_srcdir)/src/libstrongswan ${gtk_CFLAGS} \
  ${RUBYINCLUDE}
AM_CFLAGS = -D_FILE_OFFSET_BITS=64

all-local: ext

clean-local:
	(test -f ext/Makefile && cd ext && $(MAKE) clean && rm Makefile || true)

install-data-local:
	(test -f ext/Makefile && cd ext && $(MAKE) install)

ext:	libdumm.la
	(cd ext && $(RUBY) extconf.rb && $(MAKE))

.PHONY: ext
