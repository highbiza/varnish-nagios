# $Id$
libexec_PROGRAMS = check_varnish

check_varnish_SOURCES = check_varnish.c

check_varnish_CFLAGS = -include config.h ${VARNISHAPI_CFLAGS}

check_varnish_LDADD = ${VARNISHAPI_LIBS}

EXTRA_DIST = LICENSE autogen.sh

nagios-plugin-varnish_${PACKAGE_VERSION}_amd64.deb: check_varnish
	-fpm -s dir -t deb -n nagios-plugin-varnish -v ${PACKAGE_VERSION} check_varnish=/usr/lib/nagios/plugins/check_varnish

pkg: check_varnish nagios-plugin-varnish_${PACKAGE_VERSION}_amd64.deb
