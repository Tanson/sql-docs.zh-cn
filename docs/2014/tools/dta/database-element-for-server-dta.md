---
title: 服务器 (DTA) 数据库元素 |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Database element
ms.assetid: 5cd9a87a-af4b-45f3-8c18-f7fd7e7d3064
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 9b23e8d7f68cca0722691863a2c5c8d5e095c33c
ms.sourcegitcommit: ceb7e1b9e29e02bb0c6ca400a36e0fa9cf010fca
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2018
ms.locfileid: "52782889"
---
# <a name="database-element-for-server-dta"></a>服务器的数据库元素 (DTA)
  指定特定服务器上要优化的数据库。  
  
## <a name="syntax"></a>语法  
  
```  
  
<Server>  
...code removed here...  
    <Database>...</Database>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|Description|  
|--------------------|-----------------|  
|数据类型和长度|无。|  
|默认值|无。|  
|出现次数|对于每个 `Server` 元素需要使用一次或多次。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|--------------|  
|父元素|[服务器元素 (DTA)](server-element-dta.md)|  
|子元素|[数据库的名称元素 (DTA)](name-element-for-database-dta.md)<br /><br /> [数据库的架构元素 (DTA)](schema-element-for-database-dta.md)|  
  
## <a name="remarks"></a>备注  
 在数据库引擎优化顾问 XML 架构中，此元素的名称为 **DatabaseDetailsTypecomplexType** 。 请不要将此 `Database` 元素与根级父元素为 `Configuration` 元素的元素相混淆。 有关详细信息，请参阅[用于配置的数据库元素 (DTA)](database-element-for-configuration-dta.md)。  
  
## <a name="example"></a>示例  
 有关用法示例`Database`元素，请参阅[服务器元素&#40;DTA&#41;](server-element-dta.md)。  
  
## <a name="see-also"></a>请参阅  
 [XML 输入文件引用（数据库引擎优化顾问）](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
