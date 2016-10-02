# $OpenBSD$

COMMENT=	privilege-separated letsencrypt client

V=		0.1.11
GH_ACCOUNT=	kristapsdz
GH_PROJECT=	acme-client
GH_TAGNAME=	VERSION_${V:S/./_/g}
DISTNAME=	acme-client-$V

CATEGORIES=	security security/letsencrypt

HOMEPAGE =	https://kristaps.bsd.lv/acme-client/

# ISC
PERMIT_PACKAGE_CDROM=	Yes

# uses pledge()
WANTLIB += c crypto ssl tls

NO_TEST=	Yes

ALL_TARGET=	acme-client
#FAKE_FLAGS=	PREFIX=${WRKINST}${PREFIX}

.include <bsd.port.mk>
