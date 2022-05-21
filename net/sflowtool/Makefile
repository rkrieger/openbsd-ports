COMMENT =		sFlow collector and sFlow-to-NetFlow conversion tool

DISTNAME =		sflowtool-3.30
PKGNAME =		${DISTNAME}

CATEGORIES =		net sysutils

HOMEPAGE =		http://www.inmon.com/technology/sflowTools.php

# InMon sFlow license; see COPYING
# Appears to allow use/reproduce/modify the software; but not sure whether
# section 2.3(i) is a condition too strict for inclusion.
PERMIT_PACKAGE_CDROM = Unsure given restrictions in section 2.3(i)
PERMIT_PACKAGE_FTP   = ${PERMIT_PACKAGE_CDROM}
PERMIT_DISTFILES_FTP = ${PERMIT_PACKAGE_CDROM}


WANTLIB =		c

MASTER_SITES =		http://www.inmon.com/bin/

SEPARATE_BUILD =	Yes
CONFIGURE_STYLE =	gnu
AUTOCONF_VERSION =	2.69

# Enable sflowtool -S option for sFlow-to-Netflow conversion
COPTS +=		-DSPOOFSOURCE

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/sflowtool
	@for i in README COPYING; do \
		${INSTALL_DATA} ${WRKSRC}/$${i} ${PREFIX}/share/doc/sflowtool/ ; \
	done

	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/sflowtool
	@for i in ipTopTalkers ipTrafficMatrix sflowRRDChart.cgi \
	  sflowRRDLoad sflowenable; do \
		${INSTALL_SCRIPT} ${WRKSRC}/scripts/$${i} \
		  ${PREFIX}/share/examples/sflowtool/ ; \
	done
	${INSTALL_DATA} ${WRKSRC}/scripts/README ${PREFIX}/share/examples/sflowtool/


.include <bsd.port.mk>
