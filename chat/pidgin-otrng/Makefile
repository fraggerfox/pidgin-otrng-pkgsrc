# $NetBSD$

DISTNAME=	pidgin-otrng-0.0.0.20190803
CATEGORIES=	chat security
MASTER_SITES=	${MASTER_SITE_GITHUB:=otrv4/}
GITHUB_TAG=	0145537dcd0b5349bf0d0cf54573642f99ff1fbb
EXTRACT_USING=	bsdtar

MAINTAINER=	fox@NetBSD.org
HOMEPAGE=	https://otr.im/
COMMENT=	Plugin for pidgin to add OTR (Off-The-Record) encryption
LICENSE=	gnu-gpl-v2

DEPENDS=	libotr-ng>=0.0.0:../../wip/libotr-ng
#		libotr-ng>=0.0.0:../../chat/libotr-ng

USE_TOOLS+=	autoconf automake gmake intltool intltoolize m4 msgfmt \
		perl pkg-config
USE_LIBTOOL=	yes

GNU_CONFIGURE=	yes

.include "../../mk/compiler.mk"

# Supress the unknown clang pragmas warnings when using gcc
.if !empty(PKGSRC_COMPILER:Mgcc)
CFLAGS+=	-Wno-unknown-pragmas
.endif

pre-configure:
	cd ${WRKSRC} && intltoolize --force --copy && autoreconf -visf

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
