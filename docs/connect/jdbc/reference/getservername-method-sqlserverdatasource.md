---
title: getServerName 方法 (SQLServerDataSource) |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerDataSource.getServerName
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 3004ed22-5d69-4dd0-8761-d39f0b7dde13
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 76ff04ce4b2a56387a573f7409b1e56c93fdedff
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2018
ms.locfileid: "47833897"
---
# <a name="getservername-method-sqlserverdatasource"></a>getServerName 方法 (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  返回 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 实例的名称。  
  
## <a name="syntax"></a>语法  
  
```  
  
public java.lang.String getServerName()  
```  
  
## <a name="return-value"></a>返回值  
 一个包含服务器名称的字符串；如果未设置值，则为 Null。  
  
## <a name="remarks"></a>Remarks  
 服务器名称为正在运行 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 的目标计算机的主机名。 如果未设置 getServerName 属性，getServerName 则将返回默认值 Null。  
  
## <a name="see-also"></a>另请参阅  
 [SQLServerDataSource 成员](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource 类](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
