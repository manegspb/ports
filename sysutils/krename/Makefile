# $FreeBSD$

PORTNAME=	krename
PORTVERSION=	5.0.1
CATEGORIES=	sysutils kde
MASTER_SITES=	KDE/stable/${PORTNAME}/${PORTVERSION}/src

MAINTAINER=	kde@FreeBSD.org
COMMENT=	Powerful batch file renamer for KDE

LICENSE=	GPLv2+
LICENSE_FILE=	${WRKSRC}/COPYING

LIB_DEPENDS=	libtag.so:audio/taglib \
		libexiv2.so:graphics/exiv2 \
		libpodofo.so:graphics/podofo \
		libfreetype.so:print/freetype2

USES=		cmake compiler:c++11-lang gettext kde:5 pkgconfig qt:5 tar:xz
USE_KDE=	auth bookmarks codecs completion config configwidgets \
		coreaddons crash i18n iconthemes itemviews jobwidgets \
		kio service solid widgetsaddons windowsystem xmlgui
USE_QT=		concurrent core dbus declarative gui network xml widgets \
		buildtools_build qmake_build

.include <bsd.port.mk>
