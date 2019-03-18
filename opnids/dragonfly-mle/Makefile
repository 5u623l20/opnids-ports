# $FreeBSD$

PORTNAME=	dragonfly-mle
DISTVERSION= 	0.6.8
USE_GITHUB=	yes
GH_ACCOUNT=	counterflow-ai
GH_PROJECT=	dragonfly-mle
GH_TAGNAME=	v0.6.8

CATEGORIES=	opnids
#MASTER_SITES= 	GH/counterflow-ai/dragonfly-mle
#DISTFILES= 	dragonfly-mle-0.6.8.tar.gz

MAINTAINER= 	project@opnids.io
COMMENT= 	DragonFly Machine Learning Engine

LICENSE= 	GPLv2
USE_HARDENING=	pie:off relro:off

LIB_DEPENDS= libcurl.so:ftp/curl libluajit-5.1.so:lang/luajit libhiredis.so:databases/hiredis libmicrohttpd.so:www/libmicrohttpd

RUN_DEPENDS= redis-server:databases/redis lua51:lang/lua51

WRKSRC= 	${WRKDIR}/dragonfly-mle-0.6.8/src

PLIST_FILES= 	dragonfly-mle/bin/dragonfly-mle \
		dragonfly-mle/config/config.lua \
		dragonfly-mle/filter/passthrough-filter.lua \
		dragonfly-mle/filter/suricata-filter.lua \
		dragonfly-mle/www/alert.json \
		dragonfly-mle/www/nsm.json \
		dragonfly-mle/analyzer/default-analyzer.lua \
		dragonfly-mle/analyzer/dga-lr-mle.lua \
		dragonfly-mle/analyzer/dga-rf-1.ml \
		dragonfly-mle/analyzer/dga-rf-2.ml \
		dragonfly-mle/analyzer/dga-rf-3.ml \
		dragonfly-mle/analyzer/dga-rf-4.ml \
		dragonfly-mle/analyzer/dga-rf-5.ml \
		dragonfly-mle/analyzer/dga-rf-mle.lua \
		dragonfly-mle/analyzer/example-alert.lua \
		dragonfly-mle/analyzer/example-dns.lua \
		dragonfly-mle/analyzer/example-flow.lua \
		dragonfly-mle/analyzer/example-hll.lua \
		dragonfly-mle/analyzer/example-nsm.lua \
		dragonfly-mle/analyzer/example-outlier.lua \
		dragonfly-mle/analyzer/example-ranked-sum.lua \
		dragonfly-mle/analyzer/example-tls.lua \
		dragonfly-mle/analyzer/feature.lua \
		etc/rc.d/dragonfly-mle


PLIST_DIRS=	dragonfly-mle/analyzer \
		dragonfly-mle/bin \
		dragonfly-mle/config \
		dragonfly-mle/filter \
		dragonfly-mle/www \
		dragonfly-mle/log


pre-install:
	${MKDIR} ${STAGEDIR}${PREFIX}/dragonfly-mle/analyzer
	${MKDIR} ${STAGEDIR}${PREFIX}/dragonfly-mle/bin
	${MKDIR} ${STAGEDIR}${PREFIX}/dragonfly-mle/config
	${MKDIR} ${STAGEDIR}${PREFIX}/dragonfly-mle/filter
	${MKDIR} ${STAGEDIR}${PREFIX}/dragonfly-mle/www


do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/dragonfly-mle ${STAGEDIR}/${PREFIX}/dragonfly-mle/bin
	${INSTALL_SCRIPT} ${WRKDIR}/dragonfly-mle-0.6.8/src/config/config.lua ${STAGEDIR}/${PREFIX}/dragonfly-mle/config/
	${INSTALL_SCRIPT} ${WRKDIR}/dragonfly-mle-0.6.8/src/filter/passthrough-filter.lua ${STAGEDIR}/${PREFIX}/dragonfly-mle/filter/
	${INSTALL_SCRIPT} ${WRKDIR}/dragonfly-mle-0.6.8/src/filter/suricata-filter.lua ${STAGEDIR}/${PREFIX}/dragonfly-mle/filter/
	${INSTALL_DATA} ${WRKDIR}/dragonfly-mle-0.6.8/src/www/alert.json ${STAGEDIR}/${PREFIX}/dragonfly-mle/www/
	${INSTALL_DATA} ${WRKDIR}/dragonfly-mle-0.6.8/src/www/nsm.json ${STAGEDIR}/${PREFIX}/dragonfly-mle/www/
	${INSTALL_SCRIPT} ${WRKDIR}/dragonfly-mle-0.6.8/src/analyzer/default-analyzer.lua ${STAGEDIR}/${PREFIX}/dragonfly-mle/analyzer/
	${INSTALL_SCRIPT} ${WRKDIR}/dragonfly-mle-0.6.8/src/analyzer/dga-lr-mle.lua ${STAGEDIR}/${PREFIX}/dragonfly-mle/analyzer/
	${INSTALL_SCRIPT} ${WRKDIR}/dragonfly-mle-0.6.8/src/analyzer/dga-rf-1.ml ${STAGEDIR}/${PREFIX}/dragonfly-mle/analyzer/
	${INSTALL_SCRIPT} ${WRKDIR}/dragonfly-mle-0.6.8/src/analyzer/dga-rf-2.ml ${STAGEDIR}/${PREFIX}/dragonfly-mle/analyzer/
	${INSTALL_SCRIPT} ${WRKDIR}/dragonfly-mle-0.6.8/src/analyzer/dga-rf-3.ml ${STAGEDIR}/${PREFIX}/dragonfly-mle/analyzer/
	${INSTALL_SCRIPT} ${WRKDIR}/dragonfly-mle-0.6.8/src/analyzer/dga-rf-4.ml ${STAGEDIR}/${PREFIX}/dragonfly-mle/analyzer/
	${INSTALL_SCRIPT} ${WRKDIR}/dragonfly-mle-0.6.8/src/analyzer/dga-rf-5.ml ${STAGEDIR}/${PREFIX}/dragonfly-mle/analyzer/
	${INSTALL_SCRIPT} ${WRKDIR}/dragonfly-mle-0.6.8/src/analyzer/dga-rf-mle.lua ${STAGEDIR}/${PREFIX}/dragonfly-mle/analyzer/
	${INSTALL_SCRIPT} ${WRKDIR}/dragonfly-mle-0.6.8/src/analyzer/example-alert.lua ${STAGEDIR}/${PREFIX}/dragonfly-mle/analyzer/
	${INSTALL_SCRIPT} ${WRKDIR}/dragonfly-mle-0.6.8/src/analyzer/example-dns.lua ${STAGEDIR}/${PREFIX}/dragonfly-mle/analyzer/
	${INSTALL_SCRIPT} ${WRKDIR}/dragonfly-mle-0.6.8/src/analyzer/example-flow.lua ${STAGEDIR}/${PREFIX}/dragonfly-mle/analyzer/
	${INSTALL_SCRIPT} ${WRKDIR}/dragonfly-mle-0.6.8/src/analyzer/example-hll.lua ${STAGEDIR}/${PREFIX}/dragonfly-mle/analyzer/
	${INSTALL_SCRIPT} ${WRKDIR}/dragonfly-mle-0.6.8/src/analyzer/example-nsm.lua ${STAGEDIR}/${PREFIX}/dragonfly-mle/analyzer/
	${INSTALL_SCRIPT} ${WRKDIR}/dragonfly-mle-0.6.8/src/analyzer/example-outlier.lua ${STAGEDIR}/${PREFIX}/dragonfly-mle/analyzer/
	${INSTALL_SCRIPT} ${WRKDIR}/dragonfly-mle-0.6.8/src/analyzer/example-ranked-sum.lua ${STAGEDIR}/${PREFIX}/dragonfly-mle/analyzer/
	${INSTALL_SCRIPT} ${WRKDIR}/dragonfly-mle-0.6.8/src/analyzer/example-tls.lua ${STAGEDIR}/${PREFIX}/dragonfly-mle/analyzer/
	${INSTALL_SCRIPT} ${WRKDIR}/dragonfly-mle-0.6.8/src/analyzer/feature.lua ${STAGEDIR}/${PREFIX}/dragonfly-mle/analyzer/
	${INSTALL_SCRIPT} ${WRKDIR}/dragonfly-mle-0.6.8/rc/freebsd/dragonfly-mle ${STAGEDIR}/${PREFIX}/etc/rc.d


post-install:
	${MKDIR} ${STAGEDIR}${PREFIX}/dragonfly-mle/log

.include <bsd.port.mk>

