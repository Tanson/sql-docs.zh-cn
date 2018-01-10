---
title: "错误接口中的信息 |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: native-client-ole-db-errors
ms.reviewer: 
ms.suite: sql
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- IErrorRecords interface
- IErrorInfo interface
- OLE DB error handling, error interfaces
- ISQLErrorInfo interface
- errors [OLE DB], error interfaces
ms.assetid: 4620f03f-1193-43e7-ba19-ad022737d300
caps.latest.revision: "31"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 88299f51849de357fd1b5bc4d728dbaccb298dd4
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="information-in-error-interfaces"></a>错误接口中的信息
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB 提供程序报告的 OLE DB 定义的错误接口中的某些错误和状态信息**IErrorInfo**， **IErrorRecords**，和**ISQLErrorInfo**.  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB 提供程序支持**IErrorInfo**成员函数，如下所示。  
  
|成员函数|Description|  
|---------------------|-----------------|  
|**GetDescription**|错误消息说明性字符串。|  
|**GetGUID**|定义错误的接口的 GUID。|  
|**GetHelpContext**|不提供支持。 始终返回零。|  
|**GetHelpFile**|不提供支持。 始终返回 NULL。|  
|**GetSource**|“Microsoft SQL Server Native Client”字符串。|  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB 提供程序支持使用者可用**IErrorRecords**成员函数，如下所示。  
  
|成员函数|Description|  
|---------------------|-----------------|  
|**GetBasicErrorInfo**|使用有关错误的基本信息填充 ERRORINFO 结构。 ERRORINFO 结构包含标识错误的 HRESULT 返回值的成员、访问接口和该错误适用的接口。|  
|**GetCustomErrorObject**|在接口上返回的引用**ISQLErrorInfo，**和[ISQLServerErrorInfo](http://msdn.microsoft.com/library/a8323b5c-686a-4235-a8d2-bda43617b3a1)。|  
|**GetErrorInfo**|在返回的引用**IErrorInfo**接口。|  
|**GetErrorParameters**|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB 提供程序不会返回使用者通过参数**GetErrorParameters**。|  
|**GetRecordCount**|可用错误记录的计数。|  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB 提供程序支持**ISQLErrorInfo::GetSQLInfo** ，如下所示的参数。  
  
|参数|Description|  
|---------------|-----------------|  
|*pbstrSQLState*|返回错误的 SQLSTATE 值。 SQLSTATE 值在 SQL-92、ODBC 和 ISO SQL 以及 API 规范中定义。 既不[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]也不[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Native Client OLE DB 提供程序定义特定于实现的 SQLSTATE 值。|  
|*plNativeError*|返回[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]错误号**master.dbo.sysmessages**时可用。 本机错误后提供成功尝试初始化[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Native Client OLE DB 提供程序数据源。 之前尝试， [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB 提供程序始终返回零。|  
  
## <a name="see-also"></a>另请参阅  
 [错误](../../relational-databases/native-client-ole-db-errors/errors.md)  
  
  