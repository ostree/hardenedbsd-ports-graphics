# Created by: Ulrich Spoerlein <uspoerlein@gmail.com>
# $FreeBSD$

PORTNAME=	wmwifi
PORTVERSION=	0.4
DISTVERSIONSUFFIX=-bsd
PORTREVISION=	4
CATEGORIES=	net
MASTER_SITES=	http://digitalssg.net/debian/ \
		LOCAL/uqs

MAINTAINER=	uqs@FreeBSD.org
COMMENT=	Dockapp displaying the signal strength of WiFi connection

GNU_CONFIGURE=	yes
USE_XORG=	x11 xpm
USES=		gmake

NOPIE_PORTS=	yes

CPPFLAGS+=	-I${LOCALBASE}/include

PLIST_FILES=	bin/wmwifi

.include <bsd.port.mk>
