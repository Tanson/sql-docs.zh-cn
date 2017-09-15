---
title: "透视 (SSAS 表格) |Microsoft 文档"
ms.custom: 
ms.date: 04/10/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- analysis-services/multidimensional-tabular
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f78c3a1-ce2c-4e7f-a277-71a657692bea
caps.latest.revision: 12
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: a9c1ad93e5c4af1736721436f4ce5116ac279934
ms.contentlocale: zh-cn
ms.lasthandoff: 09/01/2017

---
# <a name="perspectives"></a>透视
  在表格模型中，透视定义模型的可查看子集，借此您可以将注意力集中在该模型中的特定业务或特定应用上。  
  
##  <a name="bkmk_understanding"></a> 优势  
 表格模型可为非常复杂的对象，以使用户进行浏览。 单个模型可以表示完整的数据仓库内容，可具有多个表、度量值和维度。 用户可能只需要与模型的一小部分进行交互即可满足其商业智能和报表要求，因此，这样的复杂性会令用户感到过于复杂。  
  
 在透视中，表、列和度量值（包括 KPI）定义为字段对象。 可为每个透视选择可查看字段。 例如，单个模型可以包含产品、销售、财务、员工和地理数据。 在销售部要求产品、销售、促销和地理数据时，他们可能不需要员工和财务数据。 同样，人力资源部门不需要与销售促销和地理有关的数据。  
  
 在用户使用定义的透视连接到模型（作为数据源）时，该用户可以选择要使用的透视。 例如，当在 Excel 中连接到某一模型数据时，人力资源部门的用户可以在数据连接向导的“选择表和视图”页上选择人力资源透视。 只有为人力资源透视定义的字段（表、列和度量值）将在数据透视表字段列表中可见。  
  
 透视的用途不是为了作为一种安全机制，而是作为一个可为用户提供更好体验的工具。 特定透视的所有安全性都从基础模型继承。 透视无法让用户访问该用户尚未拥有访问权的模型对象。 必须先解决模型数据库的安全性，然后才能通过透视访问模型中的对象。 安全角色可用于保护模型元数据和数据。 有关详细信息，请参阅[角色](../../analysis-services/tabular-models/roles-ssas-tabular.md)。  
  
##  <a name="bkmk_testpersp"></a> Testing perspectives  
 在创作模型时，可以使用模型设计器中的“在 Excel 中分析”功能来测试已定义的透视的效用。 从模型设计器中的 **“模型”** 菜单中，当您单击 **“在 Excel 中分析”**时，在打开 Excel 之前，将会出现 **“选择凭据和透视”** 对话框。 在此对话框中，您可以指定当前用户名、其他用户、角色和一个用于连接作为数据源的模型工作区数据库的透视以及视图数据。  
  
##  <a name="bkmk_related_tasks"></a> Related tasks  
  
|主题|Description|  
|-----------|-----------------|  
|[创建和管理透视](../../analysis-services/tabular-models/create-and-manage-perspectives-ssas-tabular.md)|描述如何使用模型设计器中的“透视”对话框创建和管理透视。|  
  
## <a name="see-also"></a>另请参阅  
 [角色](../../analysis-services/tabular-models/roles-ssas-tabular.md)   
 [层次结构](../../analysis-services/tabular-models/hierarchies-ssas-tabular.md)  
  
  