# Created by: Rob Farmer <rfarmer@predatorlabs.net>
# $FreeBSD$

PORTNAME=	tumble
PORTVERSION=	0.36
DISTVERSIONPREFIX=	v
CATEGORIES=	graphics print

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Creates a PDF file from image files

LICENSE=	GPLv2
LICENSE_FILE=	${WRKSRC}/COPYING

BROKEN_FreeBSD_13=	ld: error: duplicate symbol: blank_handler
BROKEN_FreeBSD_14=	ld: error: duplicate symbol: blank_handler
NOT_FOR_ARCHS=		powerpc sparc64
NOT_FOR_ARCHS_REASON=	Only works on little endian systems

LIB_DEPENDS=	libtiff.so:graphics/tiff \
		libnetpbm.so:graphics/netpbm

USES=		bison gmake jpeg localbase:ldflags

USE_GITHUB=	yes
GH_ACCOUNT=	brouhaha

CFLAGS+=	-I${LOCALBASE}/include/netpbm

PORTDOCS=	README
PLIST_FILES=	bin/tumble

OPTIONS_DEFINE=	DOCS

post-patch:
	@${REINPLACE_CMD} -e \
		's|^\(CFLAGS\) =.*|\1 := $$(CFLAGS)| ; \
		 s|^\(LDFLAGS\) =.*|\1 := $$(LDFLAGS)| ; \
		 s|-O3|| ; \
		 s|-lpbm|-lnetpbm| ; \
		 s|strip|true|' ${WRKSRC}/Makefile

do-install:
	(cd ${WRKSRC} && ${INSTALL_PROGRAM} tumble \
		${STAGEDIR}${PREFIX}/bin)

do-install-DOCS-on:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	(cd ${WRKSRC} && ${INSTALL_DATA} README \
		${STAGEDIR}${DOCSDIR})

.include <bsd.port.mk>
