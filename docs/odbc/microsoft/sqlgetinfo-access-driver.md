---
title: "SQLGetInfo （Access 驱动程序） |Microsoft 文档"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQLGetInfo function [ODBC], Access Driver
- Access driver [ODBC], SQLGetInfo
ms.assetid: c226aba7-a2f4-4b32-b640-92654b40e5a7
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 86fd194b5bdde4fad1daca185c18c9ed9fd742b5
ms.contentlocale: zh-cn
ms.lasthandoff: 09/09/2017

---
# <a name="sqlgetinfo-access-driver"></a>SQLGetInfo （Access 驱动程序）
> [!NOTE]  
>  本主题提供访问特定于驱动程序信息。 有关此函数的常规信息，请参阅下的相应主题[ODBC API 参考](../../odbc/reference/syntax/odbc-api-reference.md)。  
  
 **SQLGetInfo**支持 SQL_FILE_USAGE 信息类型。 返回的值是一个 16 位整数，指示如何驱动程序直接处理数据源中的文件：  
  
-   SQL_FILE_NOT_SUPPORTED-驱动程序不是单层驱动程序。  
  
-   SQL_FILE_TABLE-单层驱动程序将视为表中的数据源的文件。  
  
-   SQL_FILE_QUALIFIER-单层驱动程序将视为限定符数据源中的文件。  
  
 ODBC 驱动程序返回 SQL_FILE_QUALIFIER，因为每个文件是一个完整的数据库。  
  
## <a name="sqlbookmarkpersistence"></a>SQL_BOOKMARK_PERSISTENCE  
 SQL_BP_SCROLL &#124; SQL_BP_UPDATE [1]  
  
 [1] 书签在 commit 之后保留，但在回滚后将不再存在。  
  
## <a name="sqlconvertbinary"></a>SQL_CONVERT_BINARY  
 SQL_CVT_DOUBLE &#124; SQL_CVT_FLOAT &#124; SQL_CVT_INTEGER &#124; SQL_CVT_NUMERIC &#124; SQL_CVT_REAL &#124; SQL_CVT_SMALLINT &#124; SQL_CVT_VARCHAR &#124;SQL_CVT_WVARCHAR  
  
## <a name="sqlconvertchar"></a>SQL_CONVERT_CHAR  
 SQL_CVT_DOUBLE &#124; SQL_CVT_FLOAT &#124; SQL_CVT_INTEGER &#124; SQL_CVT_NUMERIC &#124; SQL_CVT_REAL &#124; SQL_CVT_SMALLINT &#124; SQL_CVT_VARCHAR &#124;SQL_CVT_WVARCHAR  
  
## <a name="sqlconvertdate"></a>SQL_CONVERT_DATE  
 SQL_CVT_DOUBLE &#124; SQL_CVT_FLOAT &#124; SQL_CVT_INTEGER &#124; SQL_CVT_NUMERIC &#124; SQL_CVT_REAL &#124; SQL_CVT_SMALLINT &#124; SQL_CVT_VARCHAR &#124;SQL_CVT_WVARCHAR  
  
## <a name="sqlconvertdouble"></a>SQL_CONVERT_DOUBLE  
 SQL_CVT_DOUBLE &#124; SQL_CVT_FLOAT &#124; SQL_CVT_INTEGER &#124; SQL_CVT_NUMERIC &#124; SQL_CVT_REAL &#124; SQL_CVT_SMALLINT &#124; SQL_CVT_VARCHAR &#124;SQL_CVT_WVARCHAR  
  
## <a name="sqlconvertfloat"></a>SQL_CONVERT_FLOAT  
 SQL_CVT_DOUBLE &#124; SQL_CVT_FLOAT &#124; SQL_CVT_INTEGER &#124; SQL_CVT_NUMERIC &#124; SQL_CVT_REAL &#124; SQL_CVT_SMALLINT &#124; SQL_CVT_VARCHAR &#124;SQL_CVT_WVARCHAR  
  
## <a name="sqlconvertinteger"></a>SQL_CONVERT_INTEGER  
 SQL_CVT_DOUBLE &#124;SQL_CVT_FLOAT &#124; SQL_CVT_INTEGER &#124; SQL_CVT_NUMERIC &#124; SQL_CVT_REAL &#124; SQL_CVT_SMALLINT &#124; SQL_CVT_VARCHAR &#124;SQL_CVT_WVARCHAR  
  
## <a name="sqlconvertlongvarbinary"></a>SQL_CONVERT_LONGVARBINARY  
 SQL_CVT_DOUBLE &#124;SQL_CVT_FLOAT &#124; SQL_CVT_INTEGER &#124; SQL_CVT_NUMERIC &#124; SQL_CVT_REAL &#124; SQL_CVT_SMALLINT &#124; SQL_CVT_VARCHAR &#124;SQL_CVT_WVARCHAR  
  
## <a name="sqlconvertlongvarchar"></a>SQL_CONVERT_LONGVARCHAR  
 SQL_CVT_DOUBLE &#124;SQL_CVT_FLOAT &#124; SQL_CVT_INTEGER &#124; SQL_CVT_NUMERIC &#124; SQL_CVT_REAL &#124; SQL_CVT_SMALLINT &#124; SQL_CVT_VARCHAR &#124;SQL_CVT_WVARCHAR  
  
## <a name="sqlconvertnumeric"></a>SQL_CONVERT_NUMERIC  
 SQL_CVT_DOUBLE &#124;SQL_CVT_FLOAT &#124; SQL_CVT_INTEGER &#124; SQL_CVT_NUMERIC &#124; SQL_CVT_REAL &#124; SQL_CVT_SMALLINT &#124; SQL_CVT_VARCHAR &#124;SQL_CVT_WVARCHAR  
  
## <a name="sqlconvertreal"></a>SQL_CONVERT_REAL  
 SQL_CVT_DOUBLE &#124;SQL_CVT_FLOAT &#124; SQL_CVT_INTEGER &#124; SQL_CVT_NUMERIC &#124; SQL_CVT_REAL &#124; SQL_CVT_SMALLINT &#124; SQL_CVT_VARCHAR &#124;SQL_CVT_WVARCHAR  
  
## <a name="sqlconvertsmallint"></a>SQL_CONVERT_SMALLINT  
 SQL_CVT_DOUBLE &#124;SQL_CVT_FLOAT &#124; SQL_CVT_INTEGER &#124; SQL_CVT_NUMERIC &#124; SQL_CVT_REAL &#124; SQL_CVT_SMALLINT &#124; SQL_CVT_VARCHAR &#124;SQL_CVT_WVARCHAR  
  
## <a name="sqlconverttime"></a>SQL_CONVERT_TIME  
 SQL_CVT_DOUBLE &#124;SQL_CVT_FLOAT &#124; SQL_CVT_INTEGER &#124; SQL_CVT_NUMERIC &#124; SQL_CVT_REAL &#124; SQL_CVT_SMALLINT &#124; SQL_CVT_VARCHAR &#124;SQL_CVT_WVARCHAR  
  
## <a name="sqlconverttimestamp"></a>SQL_CONVERT_TIMESTAMP  
 SQL_CVT_DOUBLE &#124;SQL_CVT_FLOAT &#124; SQL_CVT_INTEGER &#124; SQL_CVT_NUMERIC &#124; SQL_CVT_REAL &#124; SQL_CVT_SMALLINT &#124; SQL_CVT_VARCHAR &#124;SQL_CVT_WVARCHAR  
  
## <a name="sqlconverttinyint"></a>SQL_CONVERT_TINYINT  
 SQL_CVT_DOUBLE &#124;SQL_CVT_FLOAT &#124; SQL_CVT_INTEGER &#124; SQL_CVT_NUMERIC &#124; SQL_CVT_REAL &#124; SQL_CVT_SMALLINT &#124; SQL_CVT_VARCHAR &#124;SQL_CVT_WVARCHAR  
  
## <a name="sqlconvertvarbinary"></a>SQL_CONVERT_VARBINARY  
 SQL_CVT_DOUBLE &#124;SQL_CVT_FLOAT &#124; SQL_CVT_INTEGER &#124; SQL_CVT_NUMERIC &#124; SQL_CVT_REAL &#124; SQL_CVT_SMALLINT &#124; SQL_CVT_VARCHAR &#124;SQL_CVT_WVARCHAR  
  
## <a name="sqlconvertvarchar"></a>SQL_CONVERT_VARCHAR  
 SQL_CVT_DOUBLE &#124;SQL_CVT_FLOAT &#124; SQL_CVT_INTEGER &#124; SQL_CVT_NUMERIC &#124; SQL_CVT_REAL &#124; SQL_CVT_SMALLINT &#124; SQL_CVT_VARCHAR &#124;SQL_CVT_WVARCHAR  
  
## <a name="sqlunion"></a>SQL_UNION  
 SQL_U_UNION_ALL &#124;SQL_U_UNION  
  
## <a name="sqldbmsver"></a>SQL_DBMS_VER  
  
|ISAM|版本|版本号的格式|  
|----------|-------------|-------------------------------|  
|Microsoft Access|2.0|02.00.0000|  
||3.0|03.00.0000|  
||3.5|03.50.0000|  
||4.0|04.00.0000|  
  
> [!NOTE]  
>  不支持 1.0 和 1.1 版。 此外，没有任何区别中的 Microsoft Access 版本 3.0、 7.0 和 97 数据格式。  
  
## <a name="sqlddlindex"></a>SQL_DDL_INDEX  
 SQL_DL_CREATE_INDEX  
  
 SQL_DL_DROP_INDEX  
  
## <a name="sqlgetdataextensions"></a>SQL_GETDATA_EXTENSIONS  
 SQL_GD_ANY_ORDER &#124;SQL_GD_ANY_COLUMN &#124;SQL_GD_BLOCK &#124;SQL_GD_BOUND  
  
## <a name="sqlkeywords"></a>SQL_KEYWORDS  
 字母数字  
  
 AUTOINCREMENT  
  
 BINARY  
  
 BOOLEAN  
  
 BYTE  
  
 计数器  
  
 货币  
  
 DATABASE  
  
 DATABASENAME  
  
 DATETIME  
  
 不允许  
  
 DISTINCTROW  
  
 DOUBLEFLOAT  
  
 FLOAT4  
  
 FLOAT8  
  
 GENERAL  
  
 IEEEDOUBLE  
  
 IEEESINGLE  
  
 IGNORE  
  
 IMAGE  
  
 INTEGER1  
  
 INTEGER2  
  
 INTEGER4  
  
 逻辑  
  
 LOGICAL1  
  
 LONG  
  
 长二进制  
  
 LONGCHAR  
  
 长文本  
  
 备注  
  
 MONEY  
  
 注意  
  
 NUMBER  
  
 OLEOBJECT  
  
 所有者访问  
  
 PARAMETERS  
  
 PERCENT  
  
 PIVOT  
  
 短  
  
 单个  
  
 SINGLEFLOAT  
  
 STDEV  
  
 STDEVP  
  
 字符串  
  
 TABLEID  
  
 TEXT  
  
 返回页首  
  
 转换  
  
 UNSIGNEDBYTE  
  
 VAR  
  
 VARBINARY  
  
 VARP  
  
 YESNO  
  
## <a name="sqlnumericfunctions"></a>SQL_NUMERIC_FUNCTIONS  
 SQL_FN_NUM_ABS &#124;SQL_FN_NUM_ATAN &#124;SQL_FN_NUM_CEILING &#124;SQL_FN_NUM_COS &#124;SQL_FN_NUM_EXP &#124;SQL_FN_NUM_FLOOR &#124;SQL_FN_NUM_LOG &#124;SQL_FN_NUM_MOD &#124;SQL_FN_NUM_POWER &#124;SQL_FN_NUM_RAND &#124;SQL_FN_NUM_SIGN &#124;SQL_FN_NUM_SIN &#124;SQL_FN_NUM_SQRT &#124;SQL_FN_NUM_TAN  
  
## <a name="sqlojcapabilities"></a>SQL_OJ_CAPABILITIES  
 SQL_OJ_LEFT SQL_OJ_RIGHT SQL_OJ_NOT_ORDERED SQL_OJ_INNER SQL_OJ_ALL_COMPARISON_OPS  
  
## <a name="sqlcatalogusage"></a>SQL_CATALOG_USAGE  
 SQL_QU_DML_STATEMENTS &#124;SQL_QU_TABLE_DEFINITION &#124;SQL_QU_INDEX_DEFINITION &#124;SQL_QU_PROCEDURE_INVOCATION  
  
## <a name="sqlscrolloptions"></a>SQL_SCROLL_OPTIONS  
 SQL_SO_FORWARD_ONLY &#124;SQL_SO_STATIC &#124;SQL_SO_KEYSET_DRIVEN  
  
## <a name="sqlstringfunctions"></a>SQL_STRING_FUNCTIONS  
 SQL_FN_STR_ASCII &#124;SQL_FN_STR_CHAR &#124;SQL_FN_STR_CONCAT &#124; SQL_FN_STR_LCASE &#124; SQL_FN_STR_LEFT &#124; SQL_FN_STR_LENGTH &#124; SQL_FN_STR_LOCATE &#124;SQL_FN_STR_LOCATE_2 SQL_FN_STR_LTRIM &#124; SQL_FN_STR_RIGHT &#124; SQL_FN_STR_RTRIM &#124; SQL_FN_STR_SPACE &#124;SQL_FN_STR_SUBSTRING &#124; SQL_FN_STR_UCASE  
  
## <a name="sqlsubqueries"></a>SQL_SUBQUERIES  
 SQL_SQ_COMPARISON &#124;SQL_SQ_EXISTS &#124;SQL_SQ_IN &#124;SQL_SQ_QUANTIFIED &#124;SQL_SQ_CORRELATED_SUBQUERIES  
  
## <a name="sqltimedatefunctions"></a>SQL_TIMEDATE_FUNCTIONS  
 SQL_FN_TD_CURDATE &#124; SQL_FN_TD_CURTIME &#124; SQL_FN_TD_DAYOFMONTH &#124; SQL_FN_TD_DAYOFWEEK &#124;SQL_FN_TD_DAYOFYEAR &#124; SQL_FN_TD_HOUR &#124;SQL_FN_TD_MINUTE &#124;SQL_FN_TD_MONTH &#124; SQL_FN_TD_NOW &#124;SQL_FN_TD_SECOND &#124;SQL_FN_TD_WEEK &#124;SQL_FN_TD_YEAR