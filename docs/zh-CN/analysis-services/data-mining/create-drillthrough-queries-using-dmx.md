---
title: 创建钻取查询使用 DMX |Microsoft 文档
ms.date: 05/01/2018
ms.prod: sql
ms.technology: analysis-services
ms.component: data-mining
ms.topic: article
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 54183e4c9d56b67e8fd4cf966122069b7fc18ff0
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="create-drillthrough-queries-using-dmx"></a>使用 DMX 来创建钻取查询
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  对于支持钻取的所有模型，可以通过在 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] 或任何其他支持 DMX 的客户端中创建 DMX 查询来检索事例数据和结构数据。  
  
> [!WARNING]  
>  若要查看数据，必须已启用钻取，并且您必须拥有必要的权限。  
  
## <a name="specifying-drillthrough-options"></a>指定钻取选项  
 下面是通常用来检索模型事例和结构事例的语法：  
  
```  
SELECT <model column list>, StructureColumn('<structure column name') FROM <modelname>.CASES  
```  
  
 有关使用 DMX 查询返回事例数据的其它信息，请参阅 [SELECT FROM &#60;模型&#62;.CASES &#40;DMX&#41;](../../dmx/select-from-model-cases-dmx.md) 和 [SELECT FROM &#60;结构&#62;.CASES](../../dmx/select-from-structure-cases.md)。  
  
## <a name="examples"></a>示例  
 下面的 DMX 查询从时序模型返回特定产品系列的事例数据。 该查询还返回 **Amount**列，该列在挖掘结构中可用，但却未在挖掘模型中使用。  
  
```  
SELECT [DateSeries], [Model Region], Quantity, StructureColumn('Amount') AS [M200 Pacific Amount]  
FROM Forecasting.CASES  
WHERE [Model Region] = 'M200 Pacific'  
```  
  
 请注意，在此示例中，已使用别名对该结构列进行了重命名。 如果您没有为该结构列分配别名，则该列将以“Expression”名称返回。 这是所有未命名列的默认行为。  
  
## <a name="see-also"></a>另请参阅  
 [钻取查询 & #40; 数据挖掘 & #41;](../../analysis-services/data-mining/drillthrough-queries-data-mining.md)   
 [对挖掘结构的钻取](../../analysis-services/data-mining/drillthrough-on-mining-structures.md)  
  
  