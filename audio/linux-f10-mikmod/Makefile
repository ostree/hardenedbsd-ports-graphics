# Created by: bsam
# $FreeBSD$

PORTNAME=	mikmod
PORTVERSION=	3.2.0
CATEGORIES=	audio linux
DISTNAME=	lib${PORTNAME}-${PORTVERSION}-${RPMVERSION}

MAINTAINER=	emulation@FreeBSD.org
COMMENT=	MikMod Sound Library (Linux Fedora 10)

CONFLICTS=	linux-mikmod-[0-9]* linux-f8-mikmod-[0-9]*

USES=		linux:f10
USE_LINUX_RPM=	yes

RPMVERSION=	3.beta2.fc9
LINUX_NAME=	lib${PORTNAME}
USE_LDCONFIG=	yes

PLIST_FILES=	usr/lib/libmikmod.so.3 usr/lib/libmikmod.so.3.0.0
DOCSDIR=	${PREFIX}/usr/share/doc/${LINUX_NAME}-${PORTVERSION}
PORTDOCS=	AUTHORS COPYING.LESSER COPYING.LIB NEWS README TODO
DESCR=		${.CURDIR}/../${PORTNAME}/pkg-descr

.include <bsd.port.mk>
