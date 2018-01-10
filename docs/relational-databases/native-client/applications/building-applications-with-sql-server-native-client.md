---
title: "使用 SQL Server Native Client 构建应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 03/16/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: native-client|applications
ms.reviewer: 
ms.suite: sql
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- data access [SQL Server Native Client], building applications
- SQLNCLI, building applications
- applications [SQL Server Native Client]
- SQL Server Native Client, building applications
ms.assetid: 254a2b48-f0e3-43b5-a48d-3d666c2a779f
caps.latest.revision: "21"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: e1cd3cda7249c3ac85ca0672547fb973b7692e24
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="building-applications-with-sql-server-native-client"></a>使用 SQL Server Native Client 生成应用程序
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../../includes/snac-deprecated.md)]

  开发使用 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 库的应用程序时，会出现很多问题。 本节中的主题讨论了多个此类问题，包括如何从 MDAC 升级到 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client，如何使用 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 头文件和库文件，以及可用于 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 的各种连接字符串的概述。  
  
## <a name="in-this-section"></a>本节内容  
 [安装 SQL Server Native Client](../../../relational-databases/native-client/applications/installing-sql-server-native-client.md)  
 讨论如何安装 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client，各种组件安装到的位置以及如何卸载 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client。  
  
 [SQL Server Native Client 的组件](../../../relational-databases/native-client/applications/components-of-sql-server-native-client.md)  
 讨论组成 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 的组件，包括库、资源、帮助和头文件。  
  
 [将连接字符串关键字用于 SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md)  
 讨论通过 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 连接到数据库时可以使用的各种类型的连接字符串。  
  
 [使用 SQL Server Native Client 头文件和库文件](../../../relational-databases/native-client/applications/using-the-sql-server-native-client-header-and-library-files.md)  
 讨论如何在应用程序中使用 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 头文件和库文件。  
  
 [将应用程序从 MDAC 更新到 SQL Server Native Client](../../../relational-databases/native-client/applications/updating-an-application-to-sql-server-native-client-from-mdac.md)  
 讨论 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 和 MDAC 之间的区别，以及从 MDAC 升级到 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 时应考虑的问题。  
  
 [从 SQL Server 2005 Native Client 更新应用程序](../../../relational-databases/native-client/applications/updating-an-application-from-sql-server-2005-native-client.md)  
 讨论从 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] Native Client 升级到 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 中的 [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] Native Client 时应该考虑的问题。  
  
 [将 ADO 用于 SQL Server Native Client](../../../relational-databases/native-client/applications/using-ado-with-sql-server-native-client.md)  
 讨论 ADO 如何使用 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 访问和使用 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 功能。  
  
 [SQL Server Native Client 的支持策略](../../../relational-databases/native-client/applications/support-policies-for-sql-server-native-client.md)  
 讨论如何将各种数据访问组件与不同版本的 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 一起使用。  
  
 [使用 SQL Server Native Client 连接到 Windows Azure SQL 数据库](../../../relational-databases/native-client/applications/connecting-to-a-windows-azure-sql-database-using-sql-server-native-client.md)  
 讨论如何使用 [!INCLUDE[ssSDS](../../../includes/sssds-md.md)] Native Client 连接到 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]。  
  
## <a name="see-also"></a>另请参阅  
 [SQL Server Native Client 编程](../../../relational-databases/native-client/sql-server-native-client-programming.md)   
 [ODBC 操作指南主题](../../../relational-databases/native-client-odbc-how-to/odbc-how-to-topics.md)   
 [OLE DB 操作指南主题](../../../relational-databases/native-client-ole-db-how-to/ole-db-how-to-topics.md)  
  
  