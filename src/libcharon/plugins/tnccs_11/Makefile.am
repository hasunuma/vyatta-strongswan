
INCLUDES = -I$(top_srcdir)/src/libstrongswan -I$(top_srcdir)/src/libhydra \
	-I$(top_srcdir)/src/libcharon -I$(top_srcdir)/src/libtls ${xml_CFLAGS}

AM_CFLAGS = -rdynamic

libstrongswan_tnccs_11_la_LIBADD = ${xml_LIBS}

if MONOLITHIC
noinst_LTLIBRARIES = libstrongswan-tnccs-11.la
else
plugin_LTLIBRARIES = libstrongswan-tnccs-11.la
endif

libstrongswan_tnccs_11_la_SOURCES = \
	tnccs_11_plugin.h tnccs_11_plugin.c tnccs_11.h tnccs_11.c \
	batch/tnccs_batch.h batch/tnccs_batch.c \
	messages/tnccs_msg.h messages/tnccs_msg.c \
	messages/imc_imv_msg.h messages/imc_imv_msg.c \
	messages/tnccs_error_msg.h messages/tnccs_error_msg.c \
	messages/tnccs_preferred_language_msg.h messages/tnccs_preferred_language_msg.c \
	messages/tnccs_reason_strings_msg.h messages/tnccs_reason_strings_msg.c \
	messages/tnccs_recommendation_msg.h messages/tnccs_recommendation_msg.c \
	messages/tnccs_tncs_contact_info_msg.h messages/tnccs_tncs_contact_info_msg.c

libstrongswan_tnccs_11_la_LDFLAGS = -module -avoid-version

