# Created by: Eric Anholt <anholt@FreeBSD.org>
# $FreeBSD$

PORTNAME=	chromium-bsu
PORTVERSION=	0.9.16.1
PORTREVISION=	1
CATEGORIES=	games
MASTER_SITES=	SF/${PORTNAME}/Chromium%20B.S.U.%20source%20code/

MAINTAINER=	amdmi3@FreeBSD.org
COMMENT=	Arcade-style, top-scrolling space shooter

LICENSE=	ART10
LICENSE_FILE=	${WRKSRC}/COPYING

LIB_DEPENDS=	libGLC.so:graphics/quesoglc

GNU_CONFIGURE=	yes
USES=		gmake gettext-tools localbase pkgconfig
USE_SDL=	sdl2 image2
USE_GL=		gl glu
CONFIGURE_ARGS=	--disable-sdl \
		--disable-sdlmixer \
		--disable-sdlimage \
		--disable-ftgl \
		--disable-glut \
		--disable-glpng
LLD_UNSAFE=	yes
MAKE_ARGS=	LDFLAGS="${LDFLAGS}"

INSTALLS_ICONS=	yes

PORTDOCS=	*
PORTDATA=	*

OPTIONS_DEFINE=	NLS DOCS
OPTIONS_SINGLE=	AUDIO
OPTIONS_SINGLE_AUDIO=	OPENAL SDL_MIXER
OPTIONS_DEFAULT=	OPENAL
OPTIONS_SUB=	yes

AUDIO_DESC=	Audio output selection
OPENAL_DESC=	Use OpenAL for audio
SDL_MIXER_DESC=	Use SDL_mixer for audio

SDL_MIXER_USE=		SDL=mixer2
SDL_MIXER_CONFIGURE_ENABLE=sdl2mixer
OPENAL_USES=		openal:al,alut
OPENAL_CONFIGURE_ENABLE=openal
NLS_USES=		gettext
NLS_CONFIGURE_ENABLE=	nls

.include <bsd.port.mk>
