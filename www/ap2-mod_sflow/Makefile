# $OpenBSD$

SHARED_ONLY =		Yes

COMMENT =		Log Apache traffic to an sFlow collector

V =			1.0.4
DISTNAME =		mod-sflow-${V}
PKGNAME =		ap2-mod_sflow-${V}

# for any port that creates shared libraries.
# both libtool and cmake handle this automatically.
# for libtool-based ports, have a look at WRKBUILD/shared_libs.log
#SHARED_LIBS =		???

# the category used in the directory name, /usr/ports/<category>/portname,
# must be included and listed first.
CATEGORIES =		www

HOMEPAGE =		https://code.google.com/p/mod-sflow/

# InMon sFlow license
# Appears to allow use/reproduce/modify the software; but not sure whether
# section 2.3(i) is a condition too strict for inclusion.
PERMIT_PACKAGE_CDROM = Unsure given restrictions in section 2.3(i)
PERMIT_PACKAGE_FTP   = ${PERMIT_PACKAGE_CDROM}
PERMIT_DISTFILES_FTP = ${PERMIT_PACKAGE_CDROM}

# "make port-lib-depends-check" can help
#WANTLIB =		???


# where the source files and patches can be fetched
#
MASTER_SITES =		https://mod-sflow.googlecode.com/files/

RUN_DEPENDS =		www/apache-httpd
BUILD_DEPENDS =		${RUN_DEPENDS}

#MAKE_FLAGS =		???
#MAKE_ENV =		???
#FAKE_FLAGS =		???
#TEST_FLAGS =		???

# build/configuration variables
#
#SEPARATE_BUILD =	Yes (build in a directory other than WRKSRC)
#SEPARATE_BUILD =	flavored (distinct flavors may share a common WRKSRC)
#USE_GMAKE =		Yes
#USE_GROFF =		Yes
# Programs that require GNU libtool to build instead of the OpenBSD one
# should use this option.
#USE_LIBTOOL=		gnu
# Set CONFIGURE_STYLE to value corresponding to some standard configuration
# 	  perl [modbuild]: perl's MakeMaker Makefile.PL (modbuild: perl's
#	  Module::Build Build.PL)
# 	  gnu [autoconf] [old] [dest]: gnu style configure (old: no
# 	  sysconfdir), (dest: add DESTDIR, does not handle it),
# 	  (autoconf: needed by port, implies gnu)
# 	XXX: cygnus products do NOT use autoconf for making the main
# 		configure from configure.in
# 	  imake [noman]: port uses imake for configuration.
#	  (noman: no man page installation)
# 	  simple: port has its own configure script
#CONFIGURE_STYLE =	
#CONFIGURE_SCRIPT =	??? (if other than configure)
#CONFIGURE_ARGS +=	${CONFIGURE_SHARED}
#CONFIGURE_ENV =	???

# for gnu stuff
#AUTOCONF_VERSION =	??? (defaults to 2.13)
#AUTOMAKE_VERSION =	??? (defaults to 1.4)
# config.guess and others are copied here
#MODGNU_CONFIG_GUESS_DIRS = ??? (defaults to ${WRKSRC})

# Is the build automagic or is it interactive
#
#IS_INTERACTIVE =		Yes
#TEST_IS_INTERACTIVE =		Yes



# Overrides for default values
#
#LDFLAGS =		???
#MAKE_FILE =		???
#PKG_ARCH =		??? (* for arch-independent packages)
#WRKDIST =		??? if other than ${WRKDIR}/${DISTNAME}
#WRKSRC =		??? if other than ${WRKDIST}
#WRKBUILD =		??? if other than ${WRKSRC}
#WRKCONF =		??? if other than ${WRKBUILD}

#ALL_TARGET =		???
#INSTALL_TARGET =	???
#TEST_TARGET =		???

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


.include <bsd.port.mk>
