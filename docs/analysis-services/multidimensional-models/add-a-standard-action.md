---
title: "添加标准操作 |Microsoft 文档"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- analysis-services/multidimensional-tabular
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ccb2928a-f75d-4acb-8ff8-fa80bb0935b2
caps.latest.revision: 7
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 8f084616a0dd548fe9ee939f5e770b1f69f125f1
ms.contentlocale: zh-cn
ms.lasthandoff: 09/01/2017

---
# <a name="add-a-standard-action"></a>添加标准操作
  您可以通过在多维数据集设计器中使用“操作”视图，向数据库添加操作。 可以从 [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]访问该“操作”视图。 在您创建了某一操作后，该操作可在您重新处理相关的多维数据集后供用户使用。 有关详细信息，请参阅 [Processing Analysis Services Objects](../../analysis-services/multidimensional-models/processing-analysis-services-objects.md)。  
  
### <a name="to-create-an-action"></a>创建操作  
  
1.  打开要为其创建操作的多维数据集，然后单击 **“操作”** 选项卡。  
  
2.  在工具栏上，单击 **“新建操作”** 图标，然后在表达式窗格中执行以下操作：  
  
    -   在 **“名称”**中，键入操作的名称。  
  
    -   从“目标类型”下拉列表中，选择要将操作附加到的对象的类型。 您在 **“目标类型”** 中选择的对象将确定可用对象以及您可在 **“目标对象”**中进行的选择的类型。 下表列出了各目标类型的有效 **“目标对象”** 选择。  
  
        |如果您选择以下目标类型|在目标对象中进行以下选择|  
        |---------------------------------------------|---------------------------------------------------|  
        |属性成员|唯一有效的选择是单个属性层次结构。 该操作的目标类型将是出现的属性的所有成员（也就是说，该操作也将适用于用户定义的层次结构）。|  
        |单元|所有单元是可用的唯一选择。 如果您选择 **“单元”** 作为目标类型，则可以在 **“条件”** 中键入一个表达式，以便限制操作与之关联的单元。|  
        |多维数据集|CURRENTCUBE 是唯一可用选择。 该操作与当前多维数据集相关联。|  
        |维度成员|选择单个维度。 该操作将与维度的所有成员相关联。|  
        |层次结构|选择单个层次结构。 该操作将仅与层次结构对象相关联。 只有在其 **AttributeHierarchyEnabled** 和 **AttributeHierarchyVisible** 属性设置为 **True**后，属性层次结构才出现在列表中。|  
        |层次结构成员|选择单个层次结构。 该操作将与所选层次结构的所有成员相关联。 只有在其 **AttributeHierarchyEnabled** 和 **AttributeHierarchyVisible** 属性设置为 **True**后，属性层次结构才出现在列表中。|  
        |级别|选择单个级别。 该操作将仅与级别对象相关联。|  
        |级别成员|选择单个级别。 该操作将与所选级别的所有成员相关联。|  
  
    -   在 **“目标对象”**中，单击文本框右侧的箭头，然后在打开的树视图中，单击要将操作附加到的对象，然后单击 **“确定”**。  
  
    -   （可选。）在 **“条件”**中，创建一个 MDX 表达式以便限制操作的目标。 您可以手动键入表达式，或者可以从 **“元数据”** 和 **“函数”** 选项卡中拖动项。  
  
    -   从“类型”下拉列表中，选择要创建的操作的类型。 下表列出了可用操作的类型：  
  
        |“类型”|Description|  
        |----------|-----------------|  
        |数据集|检索数据集。|  
        |专有|使用除此表列出的这些类型以外的其他接口执行操作。|  
        |行集|检索行集。|  
        |。|运行 OLE DB 命令。|  
        |URL|在 Internet 浏览器中显示网页。|  
  
    -   在 **“操作表达式”**中，创建定义操作的表达式。 表达式的计算结果必须为字符串。 您可以手动键入表达式，或者可以从 **“元数据”** 和 **“函数”** 选项卡中拖动项。  
  
3.  （可选。）展开 **“附加属性”**，然后执行以下步骤之一：  
  
    -   从“调用”下拉列表中，指定如何调用操作。 下表介绍用于调用操作的可用选项。  
  
        |选项|Description|  
        |------------|-----------------|  
        |交互|该操作由用户交互触发。|  
        |批处理|该操作将作为批处理操作运行。|  
        |处于打开状态|在用户打开多维数据集时该操作运行。|  
  
    -   在 **“应用程序”**中，键入与操作关联的应用程序的名称。 例如，如果您创建一个操作，该操作使用户访问某一特定网站，则与该操作相关联的应用程序应该是 Microsoft Internet Explorer 或其他 Web 浏览器。  
  
        > [!NOTE]  
        >  专有操作将不返回到服务器，除非客户端应用程序显式将架构行级限制为仅返回与“应用程序”中指定的名称匹配的操作。  
  
    -   在“操作内容”中，如果你在使用 URL 类型，则用引号括上 Internet 地址，例如 "http://www.adventure-works.com"。  
  
    -   在 **“说明”**中，键入操作的说明。  
  
    -   在 **“标题”**中，键入一个标题或计算结果为标题的 MDX 表达式。 在启动该操作时，此标题显示给最终用户。 如果未指定标题，则改用该操作的名称。  
  
    -   从“标题是 MDX”下拉列表中，指定标题是否为 MDX。 此字段指示服务器是否将 **“标题”** 的内容计算为 MDX 表达式。  
  
  