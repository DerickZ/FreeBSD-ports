# Created by: Juergen Lock <nox@FreeBSD.org>
# $FreeBSD$

PORTNAME=	cxxtools
PORTVERSION=	2.2.1
PORTREVISION=	3
CATEGORIES=	devel
MASTER_SITES=	http://www.tntnet.org/download/

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Collection of general-purpose C++ classes

LICENSE=	LGPL21+
LICENSE_FILE=	${WRKSRC}/COPYING

BROKEN_aarch64=		does not configure: error: check for atomictype failed
BROKEN_armv6=		does not compile: string_view:204:5: error: static_assert failed "Character type of basic_string_view must be a POD"
BROKEN_armv7=		does not compile: string_view:204:5: error: static_assert failed "Character type of basic_string_view must be a POD"
BROKEN_mips=		does not configure: in section .data.rel.ro of csvdeserializer-test.o: defined in discarded section
BROKEN_mips64=		does not configure: in section .data.rel.ro of csvdeserializer-test.o: defined in discarded section
BROKEN_sparc64=		does not configure

USES=		cpe iconv libtool localbase pathfix
CPE_VENDOR=	tntnet
USE_CSTD=	gnu89
GNU_CONFIGURE=	yes
INSTALL_TARGET=	install-strip
USE_LDCONFIG=	yes

.include <bsd.port.pre.mk>

.if ${ARCH} == amd64
PLIST_SUB+=	X86_64_ONLY=""
.else
PLIST_SUB+=	X86_64_ONLY="@comment "
.endif

.if ${ARCH} == i386
PLIST_SUB+=	I386_ONLY=""
.else
PLIST_SUB+=	I386_ONLY="@comment "
.endif

.if (${ARCH} == amd64) || (${ARCH} == i386)
PLIST_SUB+=	X86_ONLY=""
.else
PLIST_SUB+=	X86_ONLY="@comment "
.endif

.if ${ARCH} == arm || ${ARCH} == armv6 || ${ARCH} == armv7
PLIST_SUB+=	ARM_ONLY=""
.else
PLIST_SUB+=	ARM_ONLY="@comment "
.endif

.if ${ARCH} == mips || ${ARCH} == mips64
PLIST_SUB+=	MIPS_ONLY=""
.else
PLIST_SUB+=	MIPS_ONLY="@comment "
.endif

.if ${ARCH} == powerpc || ${ARCH} == powerpc64
PLIST_SUB+=	PPC_ONLY=""
.else
PLIST_SUB+=	PPC_ONLY="@comment "
.endif

.include <bsd.port.post.mk>
