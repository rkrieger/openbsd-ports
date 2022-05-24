COMMENT =		NTLM authentication support for python-requests

MODPY_EGG_VERSION =	1.1.0
DISTNAME =		requests_ntlm-${MODPY_EGG_VERSION}
PKGNAME =		py-${DISTNAME}
CATEGORIES =		www

HOMEPAGE =		https://github.com/requests/requests-ntlm/

# MIT
PERMIT_PACKAGE =	Yes

MODULES =		lang/python

MODPY_PI =		Yes
MODPY_SETUPTOOLS =	Yes
MODPY_PYTEST =		Yes

FLAVORS =		python3
FLAVOR =		python3

RUN_DEPENDS =		security/py-cryptography${MODPY_FLAVOR} \
			security/py-ntlm-auth${MODPY_FLAVOR} \
			www/py-requests${MODPY_FLAVOR} \

TEST_DEPENDS =		security/py-cryptography${MODPY_FLAVOR} \
			www/py-flask${MODPY_FLAVOR} \
			www/py-requests${MODPY_FLAVOR} \
			devel/py-test${MODPY_FLAVOR} \
			devel/py-test-cov${MODPY_FLAVOR} \
			devel/py-wheel${MODPY_FLAVOR}
#			devel/py-test-pep8${MODPY_FLAVOR} \

.include <bsd.port.mk>
