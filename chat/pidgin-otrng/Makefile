# $NetBSD$

DISTNAME=	pidgin-otrng-0.0.0.20191201
CATEGORIES=	chat security
MASTER_SITES=	${MASTER_SITE_GITHUB:=otrv4/}
GITHUB_TAG=	232fc65e023a1013fd0df4488cc3cd1b7f2dbb58
EXTRACT_USING=	bsdtar

MAINTAINER=	fox@NetBSD.org
HOMEPAGE=	https://otr.im/
COMMENT=	Plugin for pidgin to add OTR (Off-The-Record) encryption
LICENSE=	gnu-gpl-v2

DEPENDS=	libotr-ng>=0.0.0:../../wip/libotr-ng
#		libotr-ng>=0.0.0:../../chat/libotr-ng

USE_TOOLS+=	autoreconf autoconf automake gmake intltool intltoolize m4 \
		msgfmt perl pkg-config
USE_LIBTOOL=	yes

GNU_CONFIGURE=	yes

.include "../../mk/compiler.mk"

# Supress the unknown clang pragmas warnings when using gcc
.if !empty(PKGSRC_COMPILER:Mgcc)
CFLAGS+=	-Wno-unknown-pragmas
.endif

pre-configure:
	cd ${WRKSRC} && ${SETENV} ${MAKE_ENV} intltoolize --force --copy && \
		${SETENV} ${MAKE_ENV} autoreconf -visf

.include "../../chat/pidgin/buildlink3.mk"
#.include "../../chat/libotr-ng/buildlink3.mk"
.include "../../wip/libotr-ng/buildlink3.mk"
.include "../../devel/gettext-lib/buildlink3.mk"
.include "../../devel/glib2/buildlink3.mk"
.include "../../security/libgcrypt/buildlink3.mk"
#.include "../../security/libgoldilocks/buildlink3.mk"
.include "../../wip/libgoldilocks/buildlink3.mk"
.include "../../security/libsodium/buildlink3.mk"
.include "../../x11/gtk2/buildlink3.mk"
.include "../../mk/bsd.pkg.mk"
