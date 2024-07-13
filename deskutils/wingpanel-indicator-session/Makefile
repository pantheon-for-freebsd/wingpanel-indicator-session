PORTNAME=	wingpanel-indicator-session
DISTVERSION=	2.3.1
CATEGORIES=	x11

MAINTAINER=	inucat@proton.me
COMMENT=	Wingpanel indicator of session menu
WWW=		https://github.com/elementary/wingpanel-indicator-session

LICENSE=	GPLv3

BUILD_DEPENDS=	gln:sysutils/coreutils
LIB_DEPENDS=	\
		libgee-0.8.so:devel/libgee \
		libgranite.so:x11-toolkits/granite \
		libwingpanel.so:x11/wingpanel \
		libaccountsservice.so:sysutils/accountsservice \
		libhandy-1.so:x11-toolkits/libhandy

USES=gettext-tools vala meson ninja gnome pkgconfig
MESON_ARGS=		--prefix=${PREFIX}
MESON_BUILD_DIR=	build
USE_GNOME=		glib20 gtk30 gdkpixbuf2
USE_GITHUB=		yes
GH_ACCOUNT=		elementary

do-build:
	cd ${WRKSRC} && meson setup build
	cd ${WRKSRC}/build && ninja

do-stage:
	cd ${WRKSRC}/build && DESTDIR=${WRKSRC}/../stage ninja install

.include <bsd.port.mk>
