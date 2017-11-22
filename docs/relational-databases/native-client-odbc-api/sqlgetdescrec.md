---
title: "SQLGetDescRec |Microsoft 文档"
ms.custom: 
ms.date: 03/17/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: native-client-odbc-api
ms.reviewer: 
ms.suite: sql
ms.technology: docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: SQLGetDescRec function
ms.assetid: f3389ff2-f3be-4035-9fb5-c9ebc2f15025
caps.latest.revision: "18"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 29ce8156afcbb9d31a35e0ae727c711f82c04dfc
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2017
---
# <a name="sqlgetdescrec"></a>SQLGetDescRec
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  本主题讨论 SQLGetDescRec 功能特定于[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]本机客户端。  
  
## <a name="sqlgetdescrec-and-table-valued-parameters"></a>SQLGetDescRec 和表值参数  
 SQLGetDescRec 可用来获取的表值参数和表值参数列的属性的值。 *RecNumber* SQLGetDescRec 参数对应于*ParameterNumber* SQLBindParameter 参数。  
  
 表值参数列仅在将描述符标头字段 SQL_SOPT_SS_PARAM_FOCUS 设置为特定记录（其 SQL_DESC_TYPE 设置为 SQL_SS_TABLE）的序数时可用。 有关： SQL_SOPT_SS_PARAM_FOCUS 有关的详细信息，请参阅[SQLSetStmtAttr](../../relational-databases/native-client-odbc-api/sqlsetstmtattr.md)。  
  
 SQLGetDescRec 返回以下数据：  
  
|参数|表值参数|表值参数列和其他参数|  
|---------------|-----------------------------|----------------------------------------------------------|  
|*名称*|存储过程调用的正式参数名称；否则是长度为 0 的字符串。|表值参数列名称。|  
|*TypePtr*|SQL_DESC_TYPE。 对于表值参数，这是 SQL_SS_TABLE。|SQL_DESC_TYPE|  
|*SubTypePtr*|未定义|SQL_DESC_DATETIME_INTERVAL_CODE（对于 SQL_DATETIME 或 SQL_INTERVAL 类型的记录。）|  
|*LengthPtr*|0|SQL_DESC_OCTET_LENGTH|  
|*PrecisionPtr*|0|SQL_DESC_PRECISION|  
|*ScalePtr*|0|SQL_DESC_SCALE|  
|*NullablePtr*|1|SQL_DESC_NULLABLE|  
  
 有关表值参数的详细信息，请参阅[表值参数 &#40; ODBC &#41;](../../relational-databases/native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md)。  
  
## <a name="sqlgetdescrec-support-for-enhanced-date-and-time-features"></a>SQLGetDescRec 对日期和时间增强功能的支持  
 日期/时间类型返回以下值：  
  
||*TypePtr*|*SubTypePtr*|*LengthPtr*|*PrecisionPtr*|*ScalePtr*|  
|-|---------------|------------------|-----------------|--------------------|----------------|  
|datetime|SQL_DATETIME|SQL_CODE_TIMESTAMP|4|3|3|  
|smalldatetime|SQL_DATETIME|SQL_CODE_TIMESTAMP|8|0|0|  
|date|SQL_DATETIME|SQL_CODE_DATE|6|0|0|  
|time|SQL_SS_TIME2|0|10|0..7|0..7|  
|datetime2|SQL_DATETIME|SQL_CODE_TIMESTAMP|16|0..7|0..7|  
|datetimeoffset|SQL_SS_TIMESTAMPOFFSET|0|20|0..7|0..7|  
  
 有关详细信息，请参阅[日期和时间改进 &#40; ODBC &#41;](../../relational-databases/native-client-odbc-date-time/date-and-time-improvements-odbc.md)。  
  
## <a name="sqlgetdescrec-support-for-large-clr-udts"></a>SQLGetDescRec 对大型 CLR UDT 的支持  
 **SQLGetDescRec**支持大型 CLR 用户定义类型 (Udt)。 有关详细信息，请参阅[Large CLR User-Defined 类型 &#40; ODBC &#41;](../../relational-databases/native-client/odbc/large-clr-user-defined-types-odbc.md)。  
  
## <a name="see-also"></a>另请参阅  
 [SQLGetDescRec](http://go.microsoft.com/fwlink/?LinkId=80707)   
 [ODBC API 实现细节](../../relational-databases/native-client-odbc-api/odbc-api-implementation-details.md)  
  
  