---
title: "用户角色属性 (Management Studio) | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.swb.reportserver.userroleproperties.f1
ms.assetid: c8b22236-a8b1-4e15-b1ff-4e1909b602d3
caps.latest.revision: 27
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 76bd80e1fc470d9cdb998d23834d0a3473d411fe
ms.contentlocale: zh-cn
ms.lasthandoff: 08/09/2017

---
# <a name="user-role-properties-management-studio"></a>用户角色属性 (Management Studio)
  使用此页，可以查看项级角色定义中所包含的任务， 还可以更改任务列表或修改角色说明。  
  
 项级角色定义是用户相对于特定项（即文件夹、报表、资源或共享数据源）所执行的一组指定任务。 角色定义将分配给用户或组，以便在报表管理器中创建角色分配。 角色定义中的任务描述用户或组可以执行的任务。  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]包括多种你可以使用的预定义的项级角色定义。 可以通过更改每个角色定义的任务列表来修改角色定义。 对角色定义进行编辑将影响包括角色定义的所有角色分配。  
  
> [!NOTE]  
>  用户角色分配仅适用于在本机模式下运行的报表服务器。 如果将报表服务器配置为 SharePoint 集成，则该页显示有关在 SharePoint 站点上定义的角色和权限级别的只读信息。  
  
## <a name="options"></a>选项  
 **名称**  
 指定角色定义的名称。  
  
 **Description**  
 显示角色定义的说明。 在 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]中，该说明仅在此页上可见。 在报表管理器中，该说明可帮助用户确定是否在角色分配中使用该角色。  
  
 **任务**  
 列出可为此角色定义选择的所有项级任务。 可以在预定义任务列表中添加或删除项，以定义用户通过此角色访问给定项的方式。 不能创建新任务，也不能修改现有任务。 只有 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]中才显示角色定义的任务列表。  
  
 **任务说明**  
 提供每个任务的有关信息。 不能修改任务说明。  
  
## <a name="see-also"></a>另请参阅  
 [项级任务](../../reporting-services/security/tasks-and-permissions-item-level-tasks.md)   
 [角色定义](../../reporting-services/security/role-definitions.md)   
 [Management Studio F1 帮助中的报表服务器](../../reporting-services/tools/report-server-in-management-studio-f1-help.md)   
 [任务和权限](../../reporting-services/security/tasks-and-permissions.md)   
 [预定义的角色](../../reporting-services/security/role-definitions-predefined-roles.md)  
  
  