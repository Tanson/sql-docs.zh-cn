---
title: "创建链接的报表 |Microsoft 文档"
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
helpviewer_keywords:
- linked reports [Reporting Services], creating
ms.assetid: 12be8341-cb57-45e8-a421-2bf66b50234d
caps.latest.revision: 44
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 232e24ef08c24d5c6a2c9799094fc492305eea46
ms.contentlocale: zh-cn
ms.lasthandoff: 08/09/2017

---
# <a name="create-a-linked-report"></a>创建链接报表
  链接报表是提供对现有报表的访问点的报表服务器项。 从概念上说，它与用于运行程序或打开文件的程序快捷方式类似。  
  
 链接报表是从现有报表派生的，保留原始报表的报表定义。 链接报表始终会继承原始报表的报表布局和数据源属性。 所有其他属性和设置都可以与原始报表不同，其中包括安全性、参数、位置、订阅和计划。  
  
 如果希望创建现有报表的其他版本，则可以创建链接报表。 例如，可以使用一个区域销售额报表来为所有销售区域创建区域特定的报表。  
  
 虽然链接报表通常基于参数化报表，但并不一定需要使用参数化报表。 每当您想使用不同的设置部署现有报表时，都可以创建链接报表。  
  
### <a name="to-create-a-linked-report"></a>创建链接报表  
  
1.  在报表管理器中，导航到包含想要链接到的报表的文件夹，然后打开选项菜单并单击 **“创建链接报表”**。  
  
2.  键入新链接报表的名称。 根据需要，可以键入说明。  
  
3.  若要为报表选择不同的文件夹，请单击 **“更改位置”**。 单击要使用的文件夹，或者在 **“位置”** 框中键入文件夹名称。 [!INCLUDE[clickOK](../../includes/clickok-md.md)]如果不选择其他文件夹，（其中存储它所基于的报表） 的当前文件夹中创建链接的报表。  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]链接的报表将打开。  
  
     链接报表的图标与报表服务器管理的其他项不同。 下面的图标表示链接报表：  
  
     ![链接报表图标](../../reporting-services/report-server/media/hlp-16linked.gif "链接报表图标")  
  
## <a name="see-also"></a>另請參閱  
 [打开和关闭报表 &#40;报表管理器 &#41;](../../reporting-services/reports/open-and-close-a-report-report-manager.md)   
 [新链接的报表页 &#40;报表管理器 &#41;](http://msdn.microsoft.com/library/fefb46e8-6901-4d50-a3f8-7c49ad72e7b1)   
 [选择项位置页 &#40;报表管理器 &#41;](http://msdn.microsoft.com/library/4a53a1a8-d1e1-47ef-b1fc-63352ece7d3c)   
 [属性常规页、 报表 &#40;报表管理器 &#41;](http://msdn.microsoft.com/library/66c99d28-ab41-45f0-bf02-ed560293595d)   
 [Reporting Services 概念 &#40;SSRS &#41;](../../reporting-services/reporting-services-concepts-ssrs.md)   
 [报表管理器 &#40;SSRS 本机模式 &#41;](http://msdn.microsoft.com/library/80949f9d-58f5-48e3-9342-9e9bf4e57896)  
  
  