COMMENT =		creates NTLM authentication structures

V =			1.5.0
MODPY_EGG_VERSION =	${V}
DISTNAME =		ntlm-auth-${MODPY_EGG_VERSION}
PKGNAME =		py-${DISTNAME}
CATEGORIES =		security

HOMEPAGE =		https://github.com/jborean93/ntlm-auth/

GH_ACCOUNT =		jborean93
GH_PROJECT =		ntlm-auth
GH_TAGNAME =		v${V}

# MIT
PERMIT_PACKAGE =	Yes

MODULES =		lang/python
MODPY_SETUPTOOLS =	Yes
MODPY_PYTEST =		Yes

FLAVORS =		python3
FLAVOR =		python3

RUN_DEPENDS =		security/py-cryptography${MODPY_FLAVOR}

TEST_DEPENDS =		devel/py-test${MODPY_FLAVOR} \
			devel/py-test-cov${MODPY_FLAVOR} \
			www/py-requests${MODPY_FLAVOR} \
			security/py-cryptography${MODPY_FLAVOR}
#			devel/py-test-pep8${MODPY_FLAVOR} \

.include <bsd.port.mk>
