# Created by: Alexey Dokuchaev <danfe@FreeBSD.org>
# $FreeBSD$

PORTNAME=	ophcrack
PORTVERSION=	3.6.1
CATEGORIES=	security
MASTER_SITES=	SF

MAINTAINER=	danfe@FreeBSD.org
COMMENT=	Windows password cracker based on rainbow tables

LICENSE=	APACHE20 GPLv2
LICENSE_COMB=	multi

LIB_DEPENDS=	libexpat.so:textproc/expat2

USES=		gmake localbase ssl tar:bzip2
GNU_CONFIGURE=	yes

PLIST_FILES=	bin/ophcrack
PORTDOCS=	AUTHORS ChangeLog README

OPTIONS_DEFINE=	X11 GRAPH DOCS
OPTIONS_DEFAULT=	X11 GRAPH

X11_DESC=	Build Qt 4 GUI frontend
GRAPH_DESC=	Enable graph rendering via Qwt

.include <bsd.port.options.mk>

.if ${PORT_OPTIONS:MX11} || ${PORT_OPTIONS:MGRAPH}
USE_QT4=	moc_build qmake_build rcc_build uic_build corelib gui
.else
CONFIGURE_ARGS+=	--disable-gui
.endif

.if ${PORT_OPTIONS:MGRAPH}
LIB_DEPENDS+=	libqwt.so:x11-toolkits/qwt5
.else
CONFIGURE_ARGS+=	--disable-graph
.endif

post-patch:
	@${REINPLACE_CMD} -E '/#include <byteswap\.h>/d ; \
		/#include/s,"bswap\.h",<machine/endian.h>, ; \
		s,bswap_([[:digit:]]+),bswap\1, ' \
			${WRKSRC}/src/samdump2/bkhive.c \
			${WRKSRC}/src/samdump2/hive.c \
			${WRKSRC}/src/samdump2/samdump2.c \
			${WRKSRC}/src/misc.h

post-install-DOCS-on:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${PORTDOCS:S,^,${WRKSRC}/,} ${STAGEDIR}${DOCSDIR}

.include <bsd.port.mk>
