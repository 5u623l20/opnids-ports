# $FreeBSD$

PORTNAME=       redis-ml
DISTVERSION=    0.99.1
USE_GITHUB= 	yes
GH_ACCOUNT=	counterflow-ai
GH_PROJECT=	redis-ml
GH_TAGNAME=	0.99.1

CATEGORIES=     opnids
#MASTER_SITES=   GH/counterflow-ai/redis-ml
#DISTFILES=      redis-ml-0.99.1.tar.gz


MAINTAINER=     project@opnids.io
COMMENT=        redis-ml for Dragonfly MLE 

LICENSE=        APACHE20

LIB_DEPENDS= libopenblas.so:math/openblas libcblas.so:math/cblas

#RUN_DEPENDS=

#WRKSRC=         ${WRKDIR}/redis-ml-0.99.1/

PLIST_FILES=    /usr/local/lib/redis-ml.so 

#PLIST_DIRS=

#pre-install:

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/src/redis-ml.so ${STAGEDIR}/${PREFIX}/lib/redis-ml.so

#post-install:

.include <bsd.port.mk>
