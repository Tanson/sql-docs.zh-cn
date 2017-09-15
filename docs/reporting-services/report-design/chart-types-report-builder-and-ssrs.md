---
title: "图表类型 （报表生成器和 SSRS） |Microsoft 文档"
ms.custom: 
ms.date: 05/30/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- "10423"
ms.assetid: 57b00017-69ae-4e71-8d78-44744e208ac7
caps.latest.revision: 11
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: 7b23da886ccf8fc76cbe8e86a722e4e9a8f3e656
ms.contentlocale: zh-cn
ms.lasthandoff: 08/09/2017

---

# <a name="chart-types-report-builder-and-ssrs"></a>图表类型（报表生成器和 SSRS）

为您要呈现的数据类型选择一种适当的图表类型非常重要。 这将决定数据以图表形式呈现时对数据进行解释的好坏程度。 例如，如果数据集包含许多与图表大小有关的数据点，则使用面积图、折线图或散点图可能会更好地呈现数据集。 有关如何根据所选图表类型准备数据的讨论，请参阅 [图表（报表生成器和 SSRS）](../../reporting-services/report-design/charts-report-builder-and-ssrs.md)。  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="choosing-a-chart-type"></a>选择图表类型  
 每种图表类型都有一些独特的特征有助于使数据集可视化。 可以使用任意图表类型来显示数据，但如果使用适合您的数据的图表类型，数据将更易于阅读，至于何种图表类型适合，则取决于您尝试在报表中显示的内容。 下表总结了影响图表对特定数据集的适宜性的图表功能。  
  
 可在创建图表之后更改图表类型。 有关详细信息，请参阅[更改图表类型 &#40;报表生成器和 SSRS &#41;](../../reporting-services/report-design/change-a-chart-type-report-builder-and-ssrs.md).  
  
 许多这些类型的图表示例都可用作示例报表。 有关下载示例报表的详细信息，请参阅 [报表生成器和报表设计器示例报表](http://go.microsoft.com/fwlink/?LinkId=198283)。  
  
|图表类型|显示比率数据|显示股票数据|显示线性数据|显示多值数据|  
|----------------|------------------------|------------------------|-------------------------|-------------------------------|  
|[分区图（报表生成器和 SSRS）](../../reporting-services/report-design/area-charts-report-builder-and-ssrs.md)|||![可用](../../reporting-services/report-data/media/greencheck.gif "可用")||  
|[条形图（报表生成器和 SSRS）](../../reporting-services/report-design/bar-charts-report-builder-and-ssrs.md)|||![可用](../../reporting-services/report-data/media/greencheck.gif "可用")||  
|[数据条](../../reporting-services/report-design/sparklines-and-data-bars-report-builder-and-ssrs.md)|||![可用](../../reporting-services/report-data/media/greencheck.gif "可用")||  
|[柱形图（报表生成器和 SSRS）](../../reporting-services/report-design/column-charts-report-builder-and-ssrs.md)|||![可用](../../reporting-services/report-data/media/greencheck.gif "可用")||  
|[折线图 &#40;报表生成器和 SSRS &#41;](../../reporting-services/report-design/line-charts-report-builder-and-ssrs.md)|||![可用](../../reporting-services/report-data/media/greencheck.gif "可用")||  
|[饼图 &#40;报表生成器和 SSRS &#41;](../../reporting-services/report-design/pie-charts-report-builder-and-ssrs.md)|![可用](../../reporting-services/report-data/media/greencheck.gif "可用")||||  
|[极坐标图（报表生成器和 SSRS）](../../reporting-services/report-design/polar-charts-report-builder-and-ssrs.md)|![可用](../../reporting-services/report-data/media/greencheck.gif "可用")||||  
|[范围图（报表生成器和 SSRS）](../../reporting-services/report-design/range-charts-report-builder-and-ssrs.md)|||![可用](../../reporting-services/report-data/media/greencheck.gif "可用")|![可用](../../reporting-services/report-data/media/greencheck.gif "可用")|  
|[散点图（报表生成器和 SSRS）](../../reporting-services/report-design/scatter-charts-report-builder-and-ssrs.md)|![可用](../../reporting-services/report-data/media/greencheck.gif "可用")||![可用](../../reporting-services/report-data/media/greencheck.gif "可用")||  
|[形状图（报表生成器和 SSRS）](../../reporting-services/report-design/shape-charts-report-builder-and-ssrs.md)|![可用](../../reporting-services/report-data/media/greencheck.gif "可用")||||  
|[迷你图](../../reporting-services/report-design/sparklines-and-data-bars-report-builder-and-ssrs.md)|![可用](../../reporting-services/report-data/media/greencheck.gif "可用")|![可用](../../reporting-services/report-data/media/greencheck.gif "可用")|![可用](../../reporting-services/report-data/media/greencheck.gif "可用")|![可用](../../reporting-services/report-data/media/greencheck.gif "可用")|  
|[股价图（报表生成器和 SSRS）](../../reporting-services/report-design/stock-charts-report-builder-and-ssrs.md)||![可用](../../reporting-services/report-data/media/greencheck.gif "可用")||![可用](../../reporting-services/report-data/media/greencheck.gif "可用")|  

## <a name="next-steps"></a>后续步骤

[图表](../../reporting-services/report-design/charts-report-builder-and-ssrs.md)   
[在图中的空和 Null 数据点](../../reporting-services/report-design/empty-and-null-data-points-in-charts-report-builder-and-ssrs.md)   
[向报表添加图表](../../reporting-services/report-design/add-a-chart-to-a-report-report-builder-and-ssrs.md)  

更多问题？ [尝试的 Reporting Services 论坛](http://go.microsoft.com/fwlink/?LinkId=620231)