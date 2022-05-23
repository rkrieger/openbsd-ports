COMMENT =		NTLM authentication support for python-requests

V =			1.1.0
MODPY_EGG_VERSION =	${V}
DISTNAME =		requests_ntlm-${MODPY_EGG_VERSION}
PKGNAME =		py-${DISTNAME}
CATEGORIES =		www

HOMEPAGE =		https://github.com/requests/requests-ntlm/

GH_ACCOUNT =		requests
GH_PROJECT =		requests-ntlm
GH_TAGNAME =		v${V}

# MIT
PERMIT_PACKAGE =	Yes

MODULES =		lang/python
MODPY_SETUPTOOLS =	Yes
MODPY_PYTEST =		Yes

FLAVORS =		python3
FLAVOR =		python3

RUN_DEPENDS =		www/py-requests${MODPY_FLAVOR} \
			security/py-ntlm-auth${MODPY_FLAVOR} \
			security/py-cryptography${MODPY_FLAVOR}

TEST_DEPENDS =		devel/py-test${MODPY_FLAVOR} \
			devel/py-test-cov${MODPY_FLAVOR} \
			devel/py-wheel${MODPY_FLAVOR} \
			www/py-flask${MODPY_FLAVOR} \
			www/py-requests${MODPY_FLAVOR} \
			security/py-cryptography${MODPY_FLAVOR}
#			devel/py-test-pep8${MODPY_FLAVOR} \

.include <bsd.port.mk>
