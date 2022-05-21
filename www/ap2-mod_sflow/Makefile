SHARED_ONLY =		Yes

COMMENT =		Log Apache traffic to an sFlow collector

V =			1.0.4
DISTNAME =		mod-sflow-${V}
PKGNAME =		ap2-mod_sflow-${V}

CATEGORIES =		www

HOMEPAGE =		https://code.google.com/p/mod-sflow/

# InMon sFlow license
# Appears to allow use/reproduce/modify the software; but not sure whether
# section 2.3(i) is a condition too strict for inclusion.
PERMIT_PACKAGE_CDROM = Unsure given restrictions in section 2.3(i)
PERMIT_PACKAGE_FTP   = ${PERMIT_PACKAGE_CDROM}
PERMIT_DISTFILES_FTP = ${PERMIT_PACKAGE_CDROM}

MASTER_SITES =		https://mod-sflow.googlecode.com/files/

RUN_DEPENDS =		www/apache-httpd
BUILD_DEPENDS =		${RUN_DEPENDS}

APXS	= ${LOCALBASE}/sbin/apxs2

do-build:
	rm -f `${APXS} -q LIBEXECDIR`/mod_sflow.so
	cd ${WRKSRC} && ${APXS} -Wc,"${CFLAGS}" -c -o ${WRKBUILD}/mod_sflow.so \
		mod_sflow.c sflow_api.c

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/lib/apache2
	${INSTALL_PROGRAM} ${WRKBUILD}/.libs/mod_sflow.so \
		${PREFIX}/lib/apache2

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/apache2/mod/mod_sflow
	${INSTALL_DATA} ${WRKBUILD}/README \
		${PREFIX}/share/doc/apache2/mod/mod_sflow/
	${INSTALL_DATA} ${FILESDIR}/hsflowd.auto ${PREFIX}/share/doc/apache2/mod/mod_sflow/


.include <bsd.port.mk>
