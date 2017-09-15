---
title: "交互式排序、 文档结构图和链接 （报表生成器和 SSRS） |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc6ef408-4a76-408a-9d3f-033481fe21cf
caps.latest.revision: 7
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: f60696e601bc48d20384d9037f4e5f7a1b35d749
ms.contentlocale: zh-cn
ms.lasthandoff: 08/09/2017

---
# <a name="interactive-sort-document-maps-and-links-report-builder-and-ssrs"></a>交互式排序、文档结构图和链接（报表生成器和 SSRS）
  在基于 Web 的环境中，您可以添加许多让用户与报表进行交互的功能。 用户可以更改报表中值的排序顺序，在报表中显示或隐藏某些项，或者单击其中的链接以访问其他报表或网页。 还可以添加目录或文档结构图。 报表用户只需单击目录或文档结构图中的项，即可跳至报表内的相应区域。  
  
 报表生成器和报表设计器支持三种类型的链接，它们分别执行以下操作：  
  
-   **书签链接** 跳至报表中的其他区域。  
  
-   **超链接** 跳至用于指定网页地址的 URL 或使用 URL 访问跳至报表服务器上的报表。  
  
-   **钻取报表链接** 跳至同一报表服务器上的其他报表。 有关详细信息，请参阅[钻取报表（报表生成器和 SSRS）](../../reporting-services/report-design/drillthrough-reports-report-builder-and-ssrs.md)。  
  
> [!NOTE]  
>  绑定到数据集字段的链接容易被篡改。 有关详细信息，请参阅 msdn.microsoft.com 上 [联机丛书](../../reporting-services/security/secure-reports-and-resources.md) 中的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][保护报表和资源](http://go.microsoft.com/fwlink/?LinkId=154888) 。  
  
 您还可以设计包含排序、筛选器和可见性参数引用的表达式，让用户控制报表的显示和内容。 有关详细信息，请参阅[报表参数（报表生成器和报表设计器）](../../reporting-services/report-design/report-parameters-report-builder-and-report-designer.md)、[对数据进行筛选、分组和排序（报表生成器和 SSRS）](../../reporting-services/report-design/filter-group-and-sort-data-report-builder-and-ssrs.md)和[添加数据集筛选器、数据区域筛选器和组筛选器（报表生成器和 SSRS）](../../reporting-services/report-design/add-dataset-filters-data-region-filters-and-group-filters.md)。  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="in-this-section"></a>本節內容  
 [交互式排序 &#40;报表生成器和 SSRS &#41;](../../reporting-services/report-design/interactive-sort-report-builder-and-ssrs.md)  
 介绍如何将交互排序按钮添加到列标题。  
  
 [创建文档结构图 &#40;报表生成器和 SSRS &#41;](../../reporting-services/report-design/create-a-document-map-report-builder-and-ssrs.md)  
 介绍如何添加目录以支持在大型报表中导航。  
  
 [将书签添加到报表 &#40;报表生成器和 SSRS &#41;](../../reporting-services/report-design/add-a-bookmark-to-a-report-report-builder-and-ssrs.md)  
 说明如何添加书签以在报表内创建链接。  
  
 [将超链接添加到 URL &#40;报表生成器和 SSRS &#41;](../../reporting-services/report-design/add-a-hyperlink-to-a-url-report-builder-and-ssrs.md)  
 说明如何添加从报表指向 URL 的链接。  
  
## <a name="see-also"></a>另请参阅  
 [钻取、 深化、 子报表和嵌套的数据区域和 #40;报表生成器和 SSRS &#41;](../../reporting-services/report-design/drillthrough-drilldown-subreports-and-nested-data-regions.md)  
  
  