# Replace ??? with appropriate values
# Remove extraneous comments before commit
# Use /usr/ports/infrastructure/bin/portcheck

# Reasons why the port/package shouldn't be built
#
# Only tested for amd64
#ONLY_FOR_ARCHS =	amd64

COMMENT =	metadata client for Triton/SmartOS guests

V = 20200116
DISTNAME =	mdata-client-${V}

GH_ACCOUNT =	joyent
GH_PROJECT =	mdata-client
GH_COMMIT =	dbb3fdec26373f8e86c9ea0057ebba48581ff476

CATEGORIES =	sysutils

HOMEPAGE =	https://github.com/joyent/mdata-client


# MIT
PERMIT_PACKAGE = 	Yes

WANTLIB +=		c

# build/configuration variables
#SEPARATE_BUILD =	Yes (build in a directory other than WRKSRC)
USE_GMAKE =		Yes

NO_TEST=        Yes

do-install:
.for prog in mdata-list mdata-get mdata-put mdata-delete
	${INSTALL_PROGRAM} ${WRKBUILD}/${prog} ${PREFIX}/sbin
	sed -i -e 's/__SECT__/8/g' ${WRKDIST}/man/man1m/${prog}.1m
	${INSTALL_MAN} ${WRKDIST}/man/man1m/${prog}.1m ${PREFIX}/man/man8/${prog}.8
.endfor





.include <bsd.port.mk>
