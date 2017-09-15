---
title: "创建多服务器环境 | Microsoft Docs"
ms.custom: 
ms.date: 01/30/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQL Server Agent, multiserver environments
- master servers [SQL Server], about master servers
- target servers [SQL Server], about target servers
- multiserver environments [SQL Server]
ms.assetid: edc2b60d-15da-40a1-8ba3-f1d473366ee6
caps.latest.revision: 6
author: stevestein
ms.author: sstein
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: cd9eee1cd80634bd3472bcf4e948658eed3a60f2
ms.contentlocale: zh-cn
ms.lasthandoff: 06/22/2017

---
# <a name="create-a-multiserver-environment"></a>创建多服务器环境
多服务器管理需要设置一个主服务器 (MSX) 以及一个或多个目标服务器 (TSX)。 首先在主服务器上定义将在所有目标服务器上处理的作业，然后将这些作业下载到目标服务器。  
  
默认情况下，将为主服务器和目标服务器之间的连接启用完全安全套接字层 (SSL) 加密和证书验证。 有关详细信息，请参阅 [在目标服务器上设置加密选项](../../ssms/agent/set-encryption-options-on-target-servers.md)  
  
如果您具有大量目标服务器，应避免通过其他 [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 功能在具有重大性能要求的生产服务器上定义主服务器，因为目标服务器通信量可能会降低生产服务器的性能。 如果还将事件转发到专用的主服务器，则可以在一台服务器上集中管理。 有关详细信息，请参阅 [管理事件](../../ssms/agent/manage-events.md)。  
  
> [!NOTE]  
> 若要使用多服务器作业处理， [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 代理服务帐户必须是主服务器上 **msdb** 数据库角色 **TargetServersRole** 的成员。 “主服务器向导”将服务帐户自动添加到此角色，以作为登记过程的一部分。  
  
## <a name="considerations-for-multiserver-environments"></a>多服务器环境的注意事项  
  
创建多服务器环境时，考虑下列问题：  
  
-   使用最新版作为主服务器。 支持当前版本和前两个版本。

-   每台目标服务器只向一台主服务器报告。 必须将目标服务器从一台主服务器上脱离，才能将其登记在其他服务器上。  
  
-   更改目标服务器的名称时，必须在更改名称之前将其脱离并在更改后重新登记。  
  
-   若要取消多服务器配置，必须使所有目标服务器脱离主服务器。  
  
-   SQL Server Integration Services 仅支持版本与主服务器版本相同或更高的目标服务器。  
  
## <a name="related-tasks"></a>相关任务  
以下主题介绍创建多服务器环境的常见任务：  
  
|Description|主题|  
|---------------|---------|  
|描述如何创建主服务器。|[设置主服务器](../../ssms/agent/make-a-master-server.md)|  
|描述如何创建目标服务器。|[设置目标服务器](../../ssms/agent/make-a-target-server.md)|  
|描述如何将目标服务器登记到主服务器。|[将目标服务器登记到主服务器](../../ssms/agent/enlist-a-target-server-to-a-master-server.md)|  
|描述如何使目标服务器从主服务器脱离。|[将目标服务器从主服务器脱离](../../ssms/agent/defect-a-target-server-from-a-master-server.md)|  
|描述如何使多台目标服务器脱离主服务器。|[将多台目标服务器从主服务器脱离](../../ssms/agent/defect-multiple-target-servers-from-a-master-server.md)|  
|描述如何检查目标服务器的状态。|[sp_help_targetserver (Transact-SQL)](http://msdn.microsoft.com/en-us/f841d3bd-901a-4980-ad0b-1c6eeba3f717)<br /><br />[sp_help_targetservergroup (Transact-SQL)](http://msdn.microsoft.com/en-us/ec3a4a68-b591-431c-9518-053ede522d0c)|  
  
## <a name="see-also"></a>另请参阅  
[排除使用代理的多服务器作业的故障](../../ssms/agent/troubleshoot-multiserver-jobs-that-use-proxies.md)  
  
