---
title: 创建和更改对象 (XMLA) |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
helpviewer_keywords:
- objects [XML for Analysis]
- subordinate objects [XML for Analysis]
- XML for Analysis, objects
- modifying objects
- removing objects
- deleting objects
- XMLA, objects
ms.assetid: a2080867-e130-440c-92eb-f768869f34a8
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 3d4249f12e062659778eb9bcf3ce562f92465f01
ms.sourcegitcommit: 334cae1925fa5ac6c140e0b2c38c844c477e3ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2018
ms.locfileid: "53354065"
---
# <a name="creating-and-altering-objects-xmla"></a>创建和更改对象 (XMLA)
  可以单独创建、更改和删除主要对象。 主要对象包括以下对象：  
  
-   服务器  
  
-   “数据库”  
  
-   维度  
  
-   多维数据集  
  
-   度量值组  
  
-   “度量值组”  
  
-   透视  
  
-   挖掘模型  
  
-   角色  
  
-   与服务器或数据库关联的命令  
  
-   数据源  
  
 您使用[创建](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla)的实例上创建主要对象命令[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]，和[Alter](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla)命令更改实例上的现有主要对象。 这两个命令使用运行[Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute)方法。  
  
## <a name="creating-objects"></a>创建对象  
 使用 `Create` 方法创建对象时，必须首先标识包含要创建的 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 对象的父对象。 通过提供中的对象引用来标识父对象[ParentObject](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla)属性的`Create`命令。 每一个对象引用都包含为 `Create` 命令唯一标识父对象时所需的对象标识符。 有关对象引用的详细信息，请参阅[定义和标识对象&#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects)。  
  
 例如，若要为某一多维数据集创建新的度量值组，则必须提供对该多维数据集的对象引用。 `ParentObject` 属性中多维数据集的对象引用同时包含数据库标识符和多维数据集标识符，因为同一多维数据集标识符可能用于不同的数据库上。  
  
 [ObjectDefinition](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/objectdefinition-element-xmla)元素包含定义要创建的主要对象的 Analysis Services 脚本语言 (ASSL) 元素。 有关 ASSL 的详细信息，请参阅[使用 Analysis Services 脚本语言进行开发&#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md)。  
  
 如果将 `AllowOverwrite` 命令的 `Create` 属性设置为 True，则会覆盖具有指定标识符的现有主要对象。 否则，如果具有指定标识符的主要对象仍存在于父对象中，则会发生错误。  
  
 有关详细信息`Create`命令，请参阅[创建元素&#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla)。  
  
### <a name="creating-session-objects"></a>创建会话对象  
 会话对象是一些临时对象，它们仅可用于客户端应用程序所使用的显式或隐式会话，且在会话结束后会删除这些会话对象。 您可以通过设置创建会话对象`Scope`的属性`Create`命令*会话*。  
  
> [!NOTE]  
>  使用时*会话*设置，`ObjectDefinition`元素只能包含[维度](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl)，[多维数据集](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl)，或[MiningModel](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) ASSL元素。  
  
## <a name="altering-objects"></a>更改对象  
 通过修改对象时`Alter`方法，必须首先标识要修改通过提供中的对象引用的对象[对象](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla)属性的`Alter`命令。 每一个对象引用都包含为 `Alter` 命令唯一标识该对象时所需的对象标识符。 有关对象引用的详细信息，请参阅[定义和标识对象&#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects)。  
  
 例如，若要修改某一多维数据集的结构，必须提供对该多维数据集的对象引用。 `Object` 属性中多维数据集的对象引用同时包含数据库标识符和多维数据集标识符，因为同一多维数据集标识符可能用于不同的数据库上。  
  
 `ObjectDefinition` 元素包含用于定义要修改的主要对象的 ASSL 元素。 有关 ASSL 的详细信息，请参阅[使用 Analysis Services 脚本语言进行开发&#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md)。  
  
 如果将 `AllowCreate` 命令的 `Alter` 属性设置为 True，则当指定的主要对象不存在时，会创建该对象。 否则，如果指定的主要对象尚不存在，则会出现错误。  
  
### <a name="using-the-objectexpansion-attribute"></a>使用 ObjectExpansion 属性  
 如果您要更改仅主要对象的属性并不重新定义主要对象所包含的次要对象，则可以设置`ObjectExpansion`的属性`Alter`命令*ObjectProperties*。 这样，`ObjectDefinition` 属性便只需包含该主要对象的属性的元素，并且 `Alter` 会将与该主要对象关联的次要对象保持不变。  
  
 若要重新定义的主要对象的次要对象，必须设置`ObjectExpansion`归于*ExpandFull*和对象定义必须包含该主要对象包含的所有次要对象。 如果 `ObjectDefinition` 命令的 `Alter` 属性未显式包含该主要对象所包含的某一次要对象，则会删除未包含的该次要对象。  
  
### <a name="altering-session-objects"></a>更改会话对象  
 若要修改所创建的会话对象`Create`命令，设置`Scope`的属性`Alter`命令*会话*。  
  
> [!NOTE]  
>  使用时*会话*设置，`ObjectDefinition`元素只能包含[维度](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl)，[多维数据集](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl)，或[MiningModel](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) ASSL元素。  
  
## <a name="creating-or-altering-subordinate-objects"></a>创建或更改从属对象  
 尽管 `Create` 或 `Alter` 命令创建或更改的只是一个最顶层的主要对象，但要创建或修改的主要对象可在包含它的 `ObjectDefinition` 属性中包含从属于该主要对象的其他主要对象和次要对象的定义。 例如，定义某个多维数据集时，可在 `ParentObject` 中指定父数据库，再在 `ObjectDefinition` 的多维数据集定义中定义该多维数据集的度量值组，然后在该度量值组中定义每一个度量值组的分区。 次要对象只能在其所属的主要对象下定义。 有关主要和次要对象的详细信息，请参阅[数据库对象&#40;Analysis Services-多维数据&#41;](../multidimensional-models/olap-logical/database-objects-analysis-services-multidimensional-data.md)。  
  
## <a name="examples"></a>示例  
  
### <a name="description"></a>Description  
 下面的示例创建引用的关系数据源[!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)]示例[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]数据库。  
  
### <a name="code"></a>代码  
  
```  
<Create xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <ParentObject>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
    </ParentObject>  
    <ObjectDefinition>  
        <DataSource xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RelationalDataSource">  
            <ID>AdventureWorksDW2012</ID>  
            <Name>AdventureWorksDW2012</Name>  
            <ConnectionString>Data Source=localhost;Initial Catalog=AdventureWorksDW2008R2;Integrated Security=True</ConnectionString>  
            <ImpersonationInfo>  
                <ImpersonationMode>ImpersonateServiceAccount</ImpersonationMode>  
            </ImpersonationInfo>  
            <ManagedProvider>System.Data.SqlClient</ManagedProvider>  
            <Timeout>PT0S</Timeout>  
        </DataSource>  
    </ObjectDefinition>  
</Create>  
```  
  
### <a name="description"></a>Description  
 下面的示例对上例中创建的关系数据源进行了更改：将该数据源的查询超时设置为 30 秒。  
  
### <a name="code"></a>代码  
  
```  
<Alter ObjectExpansion="ObjectProperties" xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <DataSourceID>AdventureWorksDW2012</DataSourceID>  
    </Object>  
    <ObjectDefinition>  
        <DataSource xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RelationalDataSource">  
            <ID>AdventureWorksDW2012</ID>  
            <Name>AdventureWorksDW2012</Name>  
            <ConnectionString>Data Source=fr-dwk-02;Initial Catalog=AdventureWorksDW2008R2;Integrated Security=True</ConnectionString>  
            <ManagedProvider>System.Data.SqlClient</ManagedProvider>  
            <Timeout>PT30S</Timeout>  
        </DataSource>  
    </ObjectDefinition>  
</Alter>  
```  
  
### <a name="comments"></a>注释  
 `ObjectExpansion`的属性`Alter`命令设置为*ObjectProperties*。 此设置允许[ImpersonationInfo](https://docs.microsoft.com/bi-reference/assl/properties/impersonationinfo-element-assl)元素中，次要对象，若要从数据源中定义排除`ObjectDefinition`。 因此，该数据源的模拟信息仍设置为在第一个示例中所指定的服务帐户。  
  
## <a name="see-also"></a>请参阅  
 [执行方法&#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute)   
 [使用 Analysis Services 脚本语言 (ASSL) 开发](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md)   
 [在 Analysis Services 中使用 XMLA 开发](developing-with-xmla-in-analysis-services.md)  
  
  
