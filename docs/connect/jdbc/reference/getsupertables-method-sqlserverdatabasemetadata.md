---
title: getSuperTables 方法 (SQLServerDatabaseMetaData) |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerDatabaseMetaData.getSuperTables
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 085461de-367b-4832-88aa-010813d2bc41
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: e74009881013dd539120cf31d6d8b7598e3023a7
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2018
ms.locfileid: "47711725"
---
# <a name="getsupertables-method-sqlserverdatabasemetadata"></a>getSuperTables 方法 (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  检索在此数据库的特定架构中定义的表层次结构的说明。  
  
> [!NOTE]  
>  [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] 目前不支持此方法。 如果使用此方法，则将始终返回一个空结果集。  
  
## <a name="syntax"></a>语法  
  
```  
  
public java.sql.ResultSet getSuperTables(java.lang.String catalog,  
                                         java.lang.String schemaPattern,  
                                         java.lang.String tableNamePattern)  
```  
  
#### <a name="parameters"></a>Parameters  
 *catalog*  
  
 一个包含目录名称的字符串。  
  
 *schemaPattern*  
  
 一个包含架构名称模式的字符串。  
  
 *tableNamePattern*  
  
 一个包含表名称模式的字符串。  
  
## <a name="return-value"></a>返回值  
 一个 [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) 对象。  
  
## <a name="exceptions"></a>异常  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 此 getSuperTables 方法由 java.sql.DatabaseMetaData 接口中的 getSuperTables 方法指定。  
  
## <a name="see-also"></a>另请参阅  
 [SQLServerDatabaseMetaData 方法](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [SQLServerDatabaseMetaData 成员](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [SQLServerDatabaseMetaData 类](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
