---
title: 成员 (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- leaf members [Master Data Services]
- consolidated members [Master Data Services]
- consolidated members [Master Data Services], about consolidated members
- members [Master Data Services], about members
- leaf members [Master Data Services], about leaf members
- members [Master Data Services]
ms.assetid: 0fda32b9-677d-4ba2-bb28-f76f2383a30f
caps.latest.revision: 10
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 934dbb8ff42bfbb3c334131f77e33d44d8542223
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37307974"
---
# <a name="members-master-data-services"></a>成员 (Master Data Services)
  在 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]中，成员是物理主数据。 例如，成员可以是 Product 实体中的 Road-150 自行车或 Customer 实体中的特定客户。  
  
## <a name="how-members-relate-to-other-model-objects"></a>成员如何与其他模型对象关联  
 可以将成员看作一个表中的行。 相关成员包含在一个实体中，每个成员由属性值进行定义。  
  
 在此示例中，该表表示实体，表中的行表示成员，表中的列表示属性。 每个单元表示特定成员的属性值。  
  
 ![表示为表的 Master Data Services 实体](../../2014/master-data-services/media/mds-conc-entity-table.gif "Master Data Services Entity Represented as Table")  
  
## <a name="member-types"></a>成员类型  
 存在三种类型的成员：叶成员、合并成员和集合成员。  
  
 叶成员是实体中的默认成员。  
  
-   在派生层次结构中，叶成员是唯一的成员类型。 来自一个实体的叶成员用作来自其他实体的叶成员的父级。  
  
-   在显式层次结构中，叶成员位于最低级别并且不能具有子级。  
  
 只有为实体启用显式层次结构和集合时，合并成员才存在。  
  
-   派生层次结构不包含合并成员。  
  
-   在显式层次结构中，合并成员可以是层次结构中其他成员的父级，也可以是子级。  
  
## <a name="use-hierarchies-and-collections-to-organize-members"></a>使用层次结构和集合组织成员  
 层次结构和集合可用于分组成员便于报告或分析。 有关详细信息，请参阅[层次结构&#40;Master Data Services&#41; ](hierarchies-master-data-services.md)并[集合&#40;Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md)。  
  
## <a name="member-example"></a>成员示例  
 在下面的示例中，每个成员均包含 Name、Code、Subcategory、StandardCost、ListPrice 和 FilePhoto 属性值。  
  
 ![自行车产品实体表](../../2014/master-data-services/media/mds-conc-entity-table-w-data.gif "Bike Product Entity Table")  
  
## <a name="related-tasks"></a>Related Tasks  
  
|任务说明|主题|  
|----------------------|-----------|  
|创建新的叶成员。|[创建叶成员&#40;Master Data Services&#41;](../../2014/master-data-services/create-a-leaf-member-master-data-services.md)|  
|创建新的合并成员。|[创建合并的成员&#40;Master Data Services&#41;](../../2014/master-data-services/create-a-consolidated-member-master-data-services.md)|  
|删除现有成员或集合。|[删除成员或集合&#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md)|  
|重新激活已删除的成员或集合。|[重新激活成员或集合&#40;Master Data Services&#41;](../../2014/master-data-services/reactivate-a-member-or-collection-master-data-services.md)|  
|更新成员的属性值。|[更改属性类型&#40;MDS add-in for Excel&#41;](microsoft-excel-add-in/change-the-attribute-type-mds-add-in-for-excel.md)|  
|在层次结构中移动成员。|[层次结构中移动成员&#40;Master Data Services&#41;](../../2014/master-data-services/move-members-within-a-hierarchy-master-data-services.md)|  
  
## <a name="related-content"></a>相关内容  
  
-   [Master Data Services 概述](master-data-services-overview-mds.md)  
  
-   [实体 (Master Data Services)](../../2014/master-data-services/entities-master-data-services.md)  
  
-   [属性&#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md)  
  
-   [层次结构&#40;Master Data Services&#41;](hierarchies-master-data-services.md)  
  
-   [集合&#40;Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md)  
  
-   [叶权限&#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md)  
  
-   [合并的权限&#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md)  
  
-   [筛选器运算符&#40;Master Data Services&#41;](../../2014/master-data-services/filter-operators-master-data-services.md)  
  
  