---
title: "报表服务器 Web 服务进行建模方法--|Microsoft 文档"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
ms.assetid: d3e658c9-bb22-480b-a3d5-bcde8f537ab2
caps.latest.revision: 4
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: a6aab5e722e732096e9e4ffdf458ac25088e09ae
ms.openlocfilehash: 6f95a5e6d379d9f0a998cb58cbf32c00be980884
ms.contentlocale: zh-cn
ms.lasthandoff: 08/12/2017

---
# <a name="model-methods---report-server-web-service"></a>模型方法的报表服务器 Web 服务
  可以使用这些方法来管理模型。  
  
|方法|操作|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.GenerateModel%2A>|在共享数据源上生成默认模型。|  
|<xref:ReportService2010.ReportingService2010.GetModelItemPermissions%2A>|检索与模型项相关联的用户权限。|  
|<xref:ReportService2010.ReportingService2010.GetModelItemPolicies%2A>|检索与模型项关联的策略。|  
|<xref:ReportService2010.ReportingService2010.GetUserModel%2A>|返回当前用户的模型的语义段。|  
|<xref:ReportService2010.ReportingService2010.InheritModelItemParentSecurity%2A>|删除与模型项关联的策略并导致模型项从其父项继承策略。|  
|<xref:ReportService2010.ReportingService2010.ListModelDrillthroughReports%2A>|列出与模型中实体关联的钻取报表。|  
|<xref:ReportService2010.ReportingService2010.ListModelItemChildren%2A>|返回模型项子元素的数组。|  
|<xref:ReportService2010.ReportingService2010.ListModelItemTypes%2A>|返回支持的模型项类型的列表。|  
|<xref:ReportService2010.ReportingService2010.ListModelPerspectives%2A>|列出模型和透视可供用户。|  
|<xref:ReportService2010.ReportingService2010.RegenerateModel%2A>|基于对数据源架构的更改更新现有模型。|  
|<xref:ReportService2010.ReportingService2010.RemoveAllModelItemPolicies%2A>|删除与指定模型中的模型项相关联的所有策略。|  
|<xref:ReportService2010.ReportingService2010.SetModelDrillthroughReports%2A>|将一组以及模型的钻取报表相关联。|  
|<xref:ReportService2010.ReportingService2010.SetModelItemPolicies%2A>|设置模型项的安全策略。|  
  
## <a name="see-also"></a>另请参阅  
 [使用 Web 服务和.NET Framework 构建应用程序](../../../reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)   
 [报表服务器 Web 服务](../../../reporting-services/report-server-web-service/report-server-web-service.md)   
 [报表服务器 Web 服务方法](../../../reporting-services/report-server-web-service/methods/report-server-web-service-methods.md)   
 [技术参考 &#40;SSRS &#41;](../../../reporting-services/technical-reference-ssrs.md)  
  
  