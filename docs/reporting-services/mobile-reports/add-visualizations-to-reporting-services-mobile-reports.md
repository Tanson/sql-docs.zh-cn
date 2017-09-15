---
title: "向 Reporting Services 移动报表添加可视化效果 |Microsoft 文档"
ms.custom: 
ms.date: 09/26/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b220b74-9ecd-4084-93fb-545208d5d7a2
caps.latest.revision: 15
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 7a6554de812f8f85c9adbd7a3338ab744555e9a0
ms.contentlocale: zh-cn
ms.lasthandoff: 08/09/2017

---
# <a name="add-visualizations-to-reporting-services-mobile-reports"></a>向 Reporting Services 移动报表添加可视化效果
图表是数据可视化效果必不可少的一部分。 了解可在 [!INCLUDE[ssRSnoversion_md](../../includes/ssrsnoversion-md.md)] 移动报表中使用的图表，这些图表可涵盖一系列方案。 

[!INCLUDE[SS_MobileReptPub_Short](../../includes/ss-mobilereptpub-long.md)] 有三种基本图表类型：时间、类别和总计。 这三种图表类型具有相应的比较图表，可用于比较两组不同的系列。  

## <a name="shared-chart-properties"></a>共享图表属性

某些属性适用于所有图表，而另一些属性则仅适用于特定的图表。 以下是一些共享属性。

### <a name="number-format"></a>数字格式
你可以向 [!INCLUDE[SS_MobileReptPub_Short](../../includes/ss-mobilereptpub-short.md)] 中的图表中的数字分配各种格式，例如，常规、带小数或不带小数的货币、带小数和不带小数的百分比等等。 在图表中，数字格式应用于轴批注以及数据点弹出窗口。 应对每个图表单独设置数字格式，而不是在移动报表上作为一个整体来设置。 

* 若要设置数字格式，请选择**布局**选项卡上，选择图表设计图面上，在**Visual 属性**窗格中选择**数字格式**。 
  
### <a name="legend"></a>图例
* 若要显示一个图表的图例，请选择**布局**选项卡上，选择图表设计图面上，在**Visual 属性**窗格集**显示图例**到**上**
  
### <a name="series"></a>系列
显示在图表中的各个值或度量值称为一个系列；多个系列可以共享（并且确实在共享）同一 X 轴和同一 Y 轴。 选择一个或多个数据表和字段即可在数据视图的数据属性面板中定义系列。 每个字段都会在图表可视化效果中生成单个系列的数据点，并呈现出自己的颜色。  

### <a name="change-aggregation"></a>更改聚合 
对于图表中的数值字段，默认聚合为总和。 你可以将其更改为平均值、计数、最小值、最大值、第一个或最后一个。

* 选择**数据**选项卡上，然后在**数据属性**，选择**选项**数值字段旁边 > 选择不同的聚合。

### <a name="set-or-clear-filters"></a>设置或清除筛选器

如果添加导航器来筛选移动报表，可以决定希望其筛选哪些图表。

1. 选择**数据**选项卡上，然后在**数据属性**，选择**选项**。

2. 下**按筛选**，请参阅导航器可以选择或清除。

了解有关 [添加导航器以筛选移动报表](../../reporting-services/mobile-reports/add-navigators-to-reporting-services-mobile-reports.md)的详细信息。
   
## <a name="time-charts"></a>时间表  
  
时间表是 [!INCLUDE[SS_MobileReptPub_Short](../../includes/ss-mobilereptpub-short.md)]中最基本的图表。 图表的时间（和日期）轴将自动设置为数据表中第一个有效的日期/时间字段。  

![mobile-report-time-chart](../../reporting-services/mobile-reports/media/mobile-report-time-chart.png)

1. 拖动**时间图**从**布局**tab 键移动到设计图面和重设其大小。

2. 默认情况下，它是堆积条形图。 你可以更改，在**系列可视化**。

3. 如果图表需要不是报表的数据时，选择**数据**选项卡 >**添加数据**到[从 Excel 或共享数据集获取数据](../../reporting-services/mobile-reports/data-for-reporting-services-mobile-reports.md)。

3. 在**数据属性**窗格中，**主系列**是**SimulatedTable**。 选择框中的箭头 > 选择你的表。

5. 如果你设置**数据结构**到**列**(上**布局**选项卡 > **Visual 属性**窗格中)，在此处**数据属性**窗格可以选择多个列的数字值。

   如果你设置**数据结构**到**行**，在此处**数据属性**窗格中，你可以选择某个**系列名称字段**的数字值和一个列。
   
了解有关 [按列或行对数据分组](../../reporting-services/mobile-reports/group-data-by-columns-or-rows-in-a-mobile-report-reporting-services.md)的详细信息。
  
## <a name="category-charts"></a>类别图表  
  
与时间表不同，在类别图表中，你将在 x 轴上按日期/时间字段以外的字段分组。 此分组称为 *类别坐标*，必须按字符串而不是数值字段分组。

![mobile-report-category-chart](../../reporting-services/mobile-reports/media/mobile-report-category-chart.png)   

1. 拖动**类别图**从**布局**到设计图面选项卡上，调整其大小，和[获取数据](../../reporting-services/mobile-reports/data-for-reporting-services-mobile-reports.md)，如果有必要。

2. 选择**数据**选项卡上，然后在**数据属性**窗格中，在**类别协调**、 选择表和字段到组上。 此字段将位于所生成图表的 x 轴上。

3. 下**主系列**，选择要聚合的每个类别的数据表和数值字段。 
  
## <a name="totals-charts"></a>总计图表  

![mobile-report-totals-chart](../../reporting-services/mobile-reports/media/mobile-report-totals-chart.png)
  
总计图表可实现两个不同的目的： 
* 它不显示多个系列，而只显示所定义的主系列的总和或总计。 
* 它允许按列或行对数据分组。 在处理平展数据时，按列分组可能非常有用。 按列分组时，仅主系列属性可用，因为类别列是按为主系列属性选择的字段数自动确定的。  

了解有关 [按列或行对数据分组](../../reporting-services/mobile-reports/group-data-by-columns-or-rows-in-a-mobile-report-reporting-services.md)的详细信息。 
  
## <a name="comparison-charts"></a>比较图  
  
时间表、类别图表和总计图表也可用作 *比较图*。 在比较图中，不仅可以指定主系列，还可以另外指定一个比较系列。 主系列和比较系列可以用三种不同的方式显示。

![mobile-report-comparison-time-chart](../../reporting-services/mobile-reports/media/mobile-report-comparison-time-chart.png)

1. 拖动其中一个**比较图**（时间、 类别或总计） 从**布局**到设计图面选项卡上，调整其大小，和[获取数据](../../reporting-services/mobile-reports/data-for-reporting-services-mobile-reports.md)，如果有必要。

2. 在**Visual 属性**窗格中，请在**系列可视化**，选择以下项之一： 
   * 条形图与细条形图
   * 折线图与条形图
   * 条形图与分段面积图 

在比较图中，可以选择对某个系列中的主值和比较值使用相同的图表颜色。

* 在**Visual 属性**窗格中，设置**重复使用颜色在比较系列上的**到**上**。

   如果设置为**上**、 调色板的重新启动之间绘制主和比较系列，在主因此相关的值和比较系列是相同的。 

   如果设置为**关闭**之后比较系列，防止可能令人误解的颜色协调错误系列的两个集之间, 绘制主系列时，调色板会继续按正常方式轮换。  
  
## <a name="pie-and-funnel-charts"></a>饼图和漏斗图  
  
饼图和漏斗图带给你最简单的可视化效果。 你可以按行或按列构造数据。 
* **移动报表中的** 饼图 [!INCLUDE[ssRSnoversion_md](../../includes/ssrsnoversion-md.md)] 可以是饼形、环形或中间为总计的环形。 饼图可用于显示一个整体的不同部分的相对大小。 切片过多的话会难以理解。
* **漏斗图** 通常用于显示某个过程的各个阶段，例如销售。

![mobile-report-funnel-chart](../../reporting-services/mobile-reports/media/mobile-report-funnel-chart.png)

### <a name="structure-pie-and-funnel-chart-data-by-rows-or-by-columns"></a>按行或按列构造饼图和漏斗图数据
1. 拖动**饼图**或**漏斗图**从**布局**到设计图面选项卡上，调整其大小，和[获取数据](../../reporting-services/mobile-reports/data-for-reporting-services-mobile-reports.md)，如果有必要。
2. 在“视觉对象属性”窗格的“数据结构”下面，选择以下选项之一：
   * **按列**
   * **按行**
3. 如果选择了“按列”，则选择“数据”选项卡，并在“数据属性”窗格的“主系列”下面，选择表以及需要在饼图或漏斗图中聚合的所有字段。 将使用字段名称来标记所生成图表的每个区域。

   如果你选择**行**，选择**数据**选项卡上，然后在**数据属性**窗格中，在**类别列**，选择表和列，其值要用于分组和标签在饼图中的。 在“主系列”列下面，为图表中的值选择一个数值字段。

了解有关 [按列或行对数据分组](../../reporting-services/mobile-reports/group-data-by-columns-or-rows-in-a-mobile-report-reporting-services.md)的详细信息。 

## <a name="treemaps"></a>树状图  
  
树状图在显示指标时，会将其值应用于矩形网格中图块的大小和颜色。 

![mobile-report-group-treemap](../../reporting-services/mobile-reports/media/mobile-report-group-treemap.png)

1. 拖动**树状图**从**布局**到设计图面选项卡上，调整其大小，和[获取数据](../../reporting-services/mobile-reports/data-for-reporting-services-mobile-reports.md)，如果有必要。
2.  选择**数据**选项卡上，然后在**数据属性**窗格中： 

     * 下**大小表示**选择磁贴的大小的数值字段。
     * 在“颜色表示”下面为图块颜色选择一个数值字段。 
     * [可选] **自定义中间值**：可视化类型为 HeatMapWithCustomCenterValue 时，只能使用 **自定义中间值** 。
     
         中间值用于决定框的颜色。 与中间值相比，指标越好，颜色越绿。 指标越差，颜色越红。
     
     * [可选]若要在查看器选择网格中的某个图块时显示弹出窗口，请在“弹出式标签”下面选择一个或多个字段。 树状图弹出窗口可以同时显示文本和数值字段。  

默认情况下，树状图采用分层结构，先按类别，然后按大小和颜色对图块分组。
* 也可以在**数据**选项卡上，在**分组依据**选择表和字段。

可以关闭分组，以便仅按大小和颜色排列图块。 

* 择“布局”选项卡并将“两级树状图”设置为“关闭”。   

## <a name="waterfall-charts"></a>瀑布图

瀑布图显示在值增加或减少时的动态总值。 它可用于理解一系列积极和消极变化如何影响初始值（例如，净收益）。

颜色编码为绿色的列表示增加，为红色的列表示减少，通过这些列，可以快速理解增减情况。 初始值和最终值列通常从零开始，而中间值则是浮动列。 从外观上而言，瀑布图也称为网图。

### <a name="when-to-use-a-waterfall-chart"></a>什么情况下使用瀑布图

在以下情况下，瀑布图是不错的选择：
* 跨时序或不同的类别更改度量值以审核影响总值的主要变化。
* 通过显示各种收入源并得出总利润（或亏损）绘制公司的年利润。
* 显示一年开始和结束时公司的员工总数。
* 直观呈现每月的收支情况以及帐户的动态平衡。 

### <a name="create-a-waterfall-chart"></a>创建瀑布图

1. 拖动**瀑布图**从**布局**到设计图面选项卡上，调整其大小，和[获取数据](../../reporting-services/mobile-reports/data-for-reporting-services-mobile-reports.md)，如果有必要。

    ![mobile-report-waterfall-chart-icon](../../reporting-services/mobile-reports/media/mobile-report-waterfall-chart-icon.png)
    
2.  选择**数据**选项卡上，然后在**数据属性**窗格中，选择一个类别字段中的数据**类别协调**，和的数值字段**主系列**: 

    ![mobile-report-waterfall-data](../../reporting-services/mobile-reports/media/mobile-report-waterfall-data.png)
    
3. 选择**布局**选项卡以查看预览中的瀑布图。

   ![mobile-report-waterfall-chart](../../reporting-services/mobile-reports/media/mobile-report-waterfall-chart.png)
   
   亏损月（如 2 月、6 月和 7 月）呈现红色。 
   盈利月（如 9 月、10 月和 11 月）呈现绿色。 

## <a name="see-also"></a>另请参阅 
* [Maps in Reporting Services mobile reports](../../reporting-services/mobile-reports/maps-in-reporting-services-mobile-reports.md)
* [Reporting Services 移动报表中的导航器](../../reporting-services/mobile-reports/add-navigators-to-reporting-services-mobile-reports.md)
* [Reporting Services 移动报表中的数据网格](../../reporting-services/mobile-reports/add-data-grids-to-mobile-reports-reporting-services.md)
* [Reporting Services 移动报表中的仪表](../../reporting-services/mobile-reports/add-gauges-to-mobile-reports-reporting-services.md)
  

