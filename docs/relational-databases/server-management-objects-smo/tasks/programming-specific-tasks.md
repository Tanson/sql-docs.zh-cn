---
title: "编程特定任务 |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: smo
ms.reviewer: 
ms.suite: sql
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- Visual Basic [SMO]
- Visual C# [SMO]
- programming [SMO]
- SQL Server Management Objects, programming
- SQL Server Management Objects, tasks
- SMO [SQL Server], programming
- SMO [SQL Server], tasks
ms.assetid: a15949ef-88d9-4205-892e-0b66588b4fcc
caps.latest.revision: "32"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 8fb3927a735f0dddfa753bb939947e8d40b6ef88
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="programming-specific-tasks"></a>编程特定的任务
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]使用 SMO 对象的特定编程的任务包括复杂主题的要点，仅将程序与特定的功能，例如备份，需要监视统计信息，复制，管理实例对象和设置配置选项。  
  
|主题|Description|  
|-----------|-----------------|  
|[在 SMO 中使用链接服务器](../../../relational-databases/server-management-objects-smo/tasks/using-linked-servers-in-smo.md)|介绍 SMO 如何使用 <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> 对象以链接 OLE-DB 服务器。|  
|[在 SMO 中配置 SQL Server](../../../relational-databases/server-management-objects-smo/tasks/configuring-sql-server-in-smo.md)|介绍如何在 SMO 中查看和修改 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 实例的配置设置。|  
|[使用表和索引分区](../../../relational-databases/server-management-objects-smo/tasks/using-table-and-index-partitioning.md)|介绍如何在 SMO 中使用索引和表分区。|  
|[使用文件组和文件存储数据](../../../relational-databases/server-management-objects-smo/tasks/using-filegroups-and-files-to-store-data.md)|介绍如何在 SMO 中使用文件组。|  
|[使用 WMI 提供程序管理服务和网络设置](../../../relational-databases/server-management-objects-smo/tasks/managing-services-and-network-settings-by-using-wmi-provider.md)|介绍使用 <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> 对象（该对象表示配置管理的 WMI 提供程序）对 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 的实例保持跟踪的若干方法。|  
|[使用数据库对象](../../../relational-databases/server-management-objects-smo/tasks/creating-altering-and-removing-database-objects.md)|介绍如何创建表示 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 实例中的对象的实例类。|  
|[管理用户、角色和登录帐户](../../../relational-databases/server-management-objects-smo/tasks/managing-users-roles-and-logins.md)|介绍如何在 SMO 中使用安全角色。|  
|[授予、撤消和拒绝权限](../../../relational-databases/server-management-objects-smo/tasks/granting-revoking-and-denying-permissions.md)|介绍如何使用 SMO 对用户或角色成员授予、撤消和拒绝权限。|  
|[使用加密](../../../relational-databases/server-management-objects-smo/tasks/using-encryption.md)|介绍如何在 SMO 中使用加密来保护数据。|  
|[在 SQL Server 代理中计划自动管理任务](../../../relational-databases/server-management-objects-smo/tasks/scheduling-automatic-administrative-tasks-in-sql-server-agent.md)|介绍如何在 SMO 中使用 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 代理以监视、报告和安排作业。|  
|[备份和还原数据库和事务日志](../../../relational-databases/server-management-objects-smo/tasks/backing-up-and-restoring-databases-and-transaction-logs.md)|介绍如何在 SMO 中备份和还原数据库和事务日志。|  
|[脚本](../../../relational-databases/server-management-objects-smo/tasks/scripting.md)|介绍如何在 SMO 中为对象编写脚本和发现对象之间的依赖关系。|  
|[传输数据](../../../relational-databases/server-management-objects-smo/tasks/transferring-data.md)|介绍如何在 SMO 中传输数据。|  
|[使用数据库邮件](../../../relational-databases/server-management-objects-smo/tasks/using-database-mail.md)|介绍 SMO 如何利用电子邮件服务。|  
|[管理 Service Broker](../../../relational-databases/server-management-objects-smo/tasks/managing-service-broker.md)|介绍如何使用 SMO 设置 Service Broker。|  
|[使用 XML 架构](../../../relational-databases/server-management-objects-smo/tasks/using-xml-schemas.md)|介绍如何在 SMO 中使用 XML 数据类型。|  
|[使用同义词](../../../relational-databases/server-management-objects-smo/tasks/using-synonyms.md)|介绍如何在 SMO 中创建同义词。|  
|[使用消息](../../../relational-databases/server-management-objects-smo/tasks/using-messages.md)|介绍如何使用系统消息，以及如何定义自己的用户定义消息。|  
|[实现全文搜索](../../../relational-databases/server-management-objects-smo/tasks/implementing-full-text-search.md)|介绍如何在 SMO 中实现全文搜索目录和索引。|  
|[实现终结点](../../../relational-databases/server-management-objects-smo/tasks/implementing-endpoints.md)|介绍如何创建端点以处理用于数据库镜像、SOAP 请求和 Service Broker 的负载。|  
|[创建和更新统计信息](../../../relational-databases/server-management-objects-smo/tasks/creating-and-updating-statistics.md)|介绍如何在 SMO 中设置和监视有关数据库的统计信息。|  
|[跟踪和重播事件](../../../relational-databases/server-management-objects-smo/tasks/tracing-and-replaying-events.md)|介绍如何使用**跟踪**和**重播**在 SMO 中跟踪和重播事件的对象。|  
  
  