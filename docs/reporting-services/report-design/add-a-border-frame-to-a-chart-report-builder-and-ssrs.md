---
title: "向图表 （报表生成器和 SSRS） 添加边框 |Microsoft 文档"
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ca0c5040-40bb-4cb7-bc2b-5bcbe73858bb
caps.latest.revision: 6
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 7a14ce29863b00c01cb77f837c369256a1096f65
ms.contentlocale: zh-cn
ms.lasthandoff: 08/09/2017

---
# <a name="add-a-border-frame-to-a-chart-report-builder-and-ssrs"></a>向图表添加边框（报表生成器和 SSRS）
  若要增强图表的视觉效果，可以考虑在图表的外部周围使用边框。 可以使用 **“图表属性”** 对话框或“属性”窗格来选择边框。 图表的边框不能应用于任何其他数据区域。  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-apply-a-border-to-a-chart"></a>向图表应用边框  
  
1.  右键单击图表上的任意位置并选择“图表属性”。  
  
    > [!NOTE]  
    >  如果看不到“图表属性”，请在快捷菜单中指向“图表”，然后选择“图表属性”。  
  
2.  选择 **“边框”**，然后单击要应用于图表的边框类型。  
  
3.  （可选）选择一个值或键入一个表示边框样式的表达式。  
  
4.  （可选）指定将绘制在图表周围作为边框的线条的颜色。  
  
    > [!NOTE]  
    >  **“线条颜色”** 列表中包括常用颜色。 若要在更多颜色列表中进行选择，请在列表中单击“更多颜色”，或单击列表旁的表达式 (**fx**) 按钮以打开“表达式”编辑器。  
  
5.  （可选）指定边框的宽度。 有效值介于 0.25pt 到 20pt 之间。 可以考虑将边框的大小保持在 1pt 到 3pt 之间，以获得最佳视觉效果。  
  
6.  （可选）如果报表包含白色之外的背景色，可以考虑定义同一种颜色的页面颜色。 页面颜色是边框线外部的背景色。  
  
7.  （可选）如果选择“框架”类型，则可为该框架指定样式和颜色。 **“框架填充颜色”** 列表中包括常用颜色。  
  
## <a name="see-also"></a>另请参阅  
 [图表 &#40;报表生成器和 SSRS &#41;](../../reporting-services/report-design/charts-report-builder-and-ssrs.md)   
 [格式设置图表 &#40;报表生成器和 SSRS &#41;](../../reporting-services/report-design/formatting-a-chart-report-builder-and-ssrs.md)   
 [添加凹凸效果、 阳文和纹理样式到图表 &#40;报表生成器和 SSRS &#41;](../../reporting-services/report-design/chart-effects-add-bevel-emboss-or-texture-report-builder.md)  
  
  