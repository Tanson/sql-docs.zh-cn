---
title: isValid 方法 (SQLServerConnection) |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 3b0a8bbf-9369-4456-9ab8-1434ccacdd7e
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 855a2fc8c6ff5a1cb9cee1db7504e0dd309113b0
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2018
ms.locfileid: "47727445"
---
# <a name="isvalid-method-sqlserverconnection"></a>isValid 方法 (SQLServerConnection)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  指示此 [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) 对象是否已关闭以及是否仍然有效。  
  
## <a name="syntax"></a>语法  
  
```  
  
public boolean isValid(int timeout)  
```  
  
#### <a name="parameters"></a>Parameters  
 *timeout*  
  
 一个指定为验证连接而等待的秒数的整数。  
  
## <a name="return-value"></a>返回值  
 如果连接有效，则为 true；如果连接无效或在超时之前无法确定连接是否有效，则为 false。  
  
## <a name="exceptions"></a>异常  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 此 isValid 方法由 java.sql.Connection 接口中的 isValid 方法指定。  
  
## <a name="see-also"></a>另请参阅  
 [SQLServerConnection 成员](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [SQLServerConnection 类](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  
