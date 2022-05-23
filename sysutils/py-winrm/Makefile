COMMENT =		Python library for Windows Remote Management (WinRM)

V =			0.4.3
MODPY_EGG_VERSION =	${V}
DISTNAME =		winrm-${MODPY_EGG_VERSION}
PKGNAME =		py-${DISTNAME}
CATEGORIES =		sysutils

HOMEPAGE =		https://github.com/diyan/pywinrm/

GH_ACCOUNT =		diyan
GH_PROJECT =		pywinrm
GH_TAGNAME =		v${V}

# MIT
PERMIT_PACKAGE =	Yes

MODULES =		lang/python
MODPY_SETUPTOOLS =	Yes
MODPY_PYTEST =		Yes

FLAVORS =		python3
FLAVOR =		python3

RUN_DEPENDS =		devel/py-six${MODPY_FLAVOR} \
			security/py-ntlm-auth${MODPY_FLAVOR} \
			security/py-cryptography${MODPY_FLAVOR} \
			textproc/py-xmltodict${MODPY_FLAVOR} \
			www/py-requests${MODPY_FLAVOR} \
			www/py-requests_ntlm${MODPY_FLAVOR} \

TEST_DEPENDS =		devel/py-test${MODPY_FLAVOR} \
			devel/py-test-cov${MODPY_FLAVOR} \
			devel/py-wheel${MODPY_FLAVOR} \
			www/py-flask${MODPY_FLAVOR} \
			www/py-requests${MODPY_FLAVOR} \
			security/py-cryptography${MODPY_FLAVOR}
#			devel/py-test-pep8${MODPY_FLAVOR} \

.include <bsd.port.mk>
