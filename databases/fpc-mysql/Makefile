# Created by: John Merryweather Cooper
# $FreeBSD$

PORTREVISION=	2
CATEGORIES=	databases lang
PKGNAMESUFFIX=	-mysql

COMMENT=	Free Pascal interface to MySQL

USES=		fpc

MASTERDIR=	${.CURDIR}/../../lang/fpc
WRKUNITDIR=	${FPCSRCDIR}/packages/${PKGNAMESUFFIX:S/-//}
EXTRACTUNITDIR=	${WRKUNITDIR}

OPTIONS_DEFINE=	MYSQL
MYSQL_DESC=	Install MySQL client
OPTIONS_DEFAULT=	MYSQL

MYSQL_USES=	mysql

.include "${MASTERDIR}/Makefile"
