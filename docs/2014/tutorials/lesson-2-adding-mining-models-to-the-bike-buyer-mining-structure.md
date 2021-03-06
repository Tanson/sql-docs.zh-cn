---
title: 第 2 课：向自行车购买者挖掘结构添加挖掘模型 |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 03fe44c5-6452-4ed0-95f6-9682670c0f52
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: de65fb7a85154f607cd8f266faec4621cdc41476
ms.sourcegitcommit: dfb1e6deaa4919a0f4e654af57252cfb09613dd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "56025218"
---
# <a name="lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure"></a>第 2 课：向自行车购买者挖掘结构添加挖掘模型
  在本课中，将两个挖掘模型添加到你创建的自行车购买者挖掘结构[第 1 课：创建自行车购买者挖掘结构](../../2014/tutorials/lesson-1-creating-the-bike-buyer-mining-structure.md)。 可以使用其中的一个模型浏览数据，使用另一个模型创建预测。  
  
 若要了解如何潜在客户可以按其特征分类，您将创建基于的挖掘模型[Microsoft 聚类分析算法](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md)。 在下一课中，您将研究该算法如何查找具有类似特征的客户群。 例如，您可能发现某些客户住得比较近，骑自行车上下班，并且具有类似的教育背景。 可以使用这些客户群更好地了解不同客户之间的关系，并使用此信息创建面向特定客户的营销策略。  
  
 若要预测潜在客户是否可能购买自行车，将创建基于的挖掘模型[Microsoft 决策树算法](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md)。 该算法会通查与每位潜在客户关联的信息，并查找有助于预测客户是否会购买自行车的特征。 然后将先前的自行车购买者的特征值与潜在的新客户的特征值进行比较，确定潜在的新客户是否可能购买自行车。  
  
## <a name="alter-mining-structure-statement"></a>ALTER MINING STRUCTURE 语句  
 为了向挖掘结构添加挖掘模型，可以使用[ALTER MINING STRUCTURE &#40;DMX&#41; ](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016)语句。 可以将语句中的代码分为下列几部分：  
  
-   标识挖掘结构  
  
-   命名挖掘模型  
  
-   定义键列  
  
-   定义输入列和可预测列  
  
-   标识算法和参数更改  
  
 下面是 ALTER MINING MODEL 语句的一般示例：  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
ADD MINING MODEL [<mining model name>]  
(  
    [<key column>],  
    <mining model columns>,  
) USING <algorithm name>( <algorithm parameters> )  
WITH FILTER (<expression>)  
```  
  
 代码的第一行标识将向其添加挖掘模型的现有挖掘结构：  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
```  
  
 代码的第二行对将要添加到挖掘结构中的挖掘模型进行命名：  
  
```  
ADD MINING MODEL [<mining model name>]  
```  
  
 有关命名 DMX 中的对象的信息，请参阅[标识符&#40;DMX&#41;](/sql/dmx/identifiers-dmx)。  
  
 代码的接下来的各行定义挖掘结构中将由挖掘模型使用的各列：  
  
```  
[<key column>],  
<mining model columns>  
```  
  
 您只能使用挖掘结构中现有的各列，列表中的第一列必须是挖掘结构中的键列。  
  
 代码的下一行定义生成挖掘模型的挖掘算法以及可以对算法设置的算法参数：  
  
```  
) USING <algorithm name>( <algorithm parameters> )  
```  
  
 您可以调整的算法参数的详细信息，请参阅[Microsoft 决策树算法](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md)并[Microsoft 聚类分析算法](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md)。  
  
 您可以使用以下语法指定将挖掘模型中的一列用于预测：  
  
```  
<mining model column> PREDICT  
```  
  
 代码的最后一行是可选的，用于定义在定型和测试模型时应用的筛选器。 有关如何向挖掘模型应用筛选器的详细信息，请参阅[挖掘模型的筛选器&#40;Analysis Services-数据挖掘&#41;](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md)。  
  
## <a name="lesson-tasks"></a>课程任务  
 在本课程中，将执行以下任务：  
  
-   使用 [!INCLUDE[msCoName](../includes/msconame-md.md)] 决策树算法向自行车购买者结构中添加决策树挖掘模型  
  
-   使用 [!INCLUDE[msCoName](../includes/msconame-md.md)] 聚类分析算法向自行车购买者结构中添加聚类分析挖掘模型  
  
-   因为您想查看所有事例的结果，所以不向任何一个模型中添加筛选器。  
  
## <a name="adding-a-decision-tree-mining-model-to-the-structure"></a>向结构中添加决策树挖掘模型  
 第一步是基于 [!INCLUDE[msCoName](../includes/msconame-md.md)] 决策树算法添加挖掘模型。  
  
#### <a name="to-add-a-decision-tree-mining-model"></a>添加决策树挖掘模型  
  
1.  在**对象资源管理器**，右键单击该实例的[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]，依次指向**新查询**，然后单击**DMX**若要打开查询编辑器和一个新的空白查询。  
  
2.  将 ALTER MINING STRUCTURE 语句的一般示例复制到空白查询中。  
  
3.  将  
  
    ```  
    <mining structure name>   
    ```  
  
     使用：  
  
    ```  
    [Bike Buyer]  
    ```  
  
4.  将  
  
    ```  
    <mining model name>   
    ```  
  
     使用：  
  
    ```  
    Decision Tree  
    ```  
  
5.  将  
  
    ```  
    <mining model columns>,  
    ```  
  
     使用：  
  
    ```  
    (  
       CustomerKey,  
       [Age],  
       [Bike Buyer] PREDICT,  
       [Commute Distance],  
       [Education],  
       [Gender],  
       [House Owner Flag],  
       [Marital Status],  
       [Number Cars Owned],  
       [Number Children At Home],  
       [Occupation],  
       [Region],  
       [Total Children],  
       [Yearly Income]  
    ```  
  
     在本例中，`[Bike Buyer]` 列被指定为 PREDICT 列。  
  
6.  将  
  
    ```  
    USING <algorithm name>( <algorithm parameters> )   
    ```  
  
     使用：  
  
    ```  
    Using Microsoft_Decision_Trees  
    WITH DRILLTHROUGH  
    ```  
  
     通过 WITH DRILLTHROUGH 语句，您可以浏览用于生成挖掘模型的事例。  
  
     现在，结果语句应该如下所示：  
  
    ```  
    ALTER MINING STRUCTURE [Bike Buyer]  
    ADD MINING MODEL [Decision Tree]  
    (  
       CustomerKey,  
       [Age],  
       [Bike Buyer] PREDICT,  
       [Commute Distance],  
       [Education],  
       [Gender],  
       [House Owner Flag],  
       [Marital Status],  
       [Number Cars Owned],  
       [Number Children At Home],  
       [Occupation],  
       [Region],  
       [Total Children],  
       [Yearly Income]  
    ) USING Microsoft_Decision_Trees  
    WITH DRILLTHROUGH  
    ```  
  
7.  上**文件**菜单上，单击**另存 dmxquery1.dmx 另存为**。  
  
8.  在中**另存为**对话框中，浏览到相应的文件夹，并将文件命名`DT_Model.dmx`。  
  
9. 在工具栏上，单击**Execute**按钮。  
  
## <a name="adding-a-clustering-mining-model-to-the-structure"></a>向结构中添加聚类分析挖掘模型  
 现在可以基于 [!INCLUDE[msCoName](../includes/msconame-md.md)] 聚类分析算法向自行车购买者挖掘结构添加挖掘模型。 由于聚类分析挖掘模型将使用挖掘结构中定义的所有列，因此，可以省略定义挖掘列，使用快捷方式向结构中添加模型。  
  
#### <a name="to-add-a-clustering-mining-model"></a>添加聚类分析挖掘模型  
  
1.  在**对象资源管理器**，右键单击该实例的[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]，依次指向**新查询**，然后单击**DMX**以打开查询编辑器和一个新的空白查询。  
  
2.  将 ALTER MINING STRUCTURE 语句的一般示例复制到空白查询中。  
  
3.  将  
  
    ```  
    <mining structure name>   
    ```  
  
     使用：  
  
    ```  
    [Bike Buyer]  
    ```  
  
4.  将  
  
    ```  
    <mining model>   
    ```  
  
     使用：  
  
    ```  
    Clustering Model  
    ```  
  
5.  删除以下内容：  
  
    ```  
    (  
        [<key column>],  
        <mining model columns>,  
    )  
    ```  
  
6.  将  
  
    ```  
    USING <algorithm name>( <algorithm parameters> )  
    ```  
  
     使用：  
  
    ```  
    USING Microsoft_Clustering  
    ```  
  
     现在，完整的语句应该如下所示：  
  
    ```  
    ALTER MINING STRUCTURE [Bike Buyer]  
    ADD MINING MODEL [Clustering]  
    USING Microsoft_Clustering   
    ```  
  
7.  上**文件**菜单上，单击**另存 dmxquery1.dmx 另存为**。  
  
8.  在中**另存为**对话框中，浏览到相应的文件夹，并将文件命名`Clustering_Model.dmx`。  
  
9. 在工具栏上，单击**Execute**按钮。  
  
 在下一课中，您将处理模型和挖掘结构。  
  
## <a name="next-lesson"></a>下一课  
 [第 3 课：处理自行车购买者挖掘结构](../../2014/tutorials/lesson-3-processing-the-bike-buyer-mining-structure.md)  
  
  
