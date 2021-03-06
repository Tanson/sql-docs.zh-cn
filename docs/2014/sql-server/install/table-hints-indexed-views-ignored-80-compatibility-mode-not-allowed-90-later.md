---
title: 中的表提示索引视图定义在 80 兼容模式下将被忽略，不允许在 90 模式下或更高版本 |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
helpviewer_keywords:
- query hints [SQL Server]
- indexed views [SQL Server], query hints
ms.assetid: 405dfcff-a3a6-4e6d-a53a-ed77bbacdd13
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: bf4f8e5c3ea23b1ab52199c884c2980bf52bc983
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2018
ms.locfileid: "48160047"
---
# <a name="table-hints-in-indexed-view-definitions-are-ignored-in-80-compatibility-mode-and-are-not-allowed-in-90-mode-or-later"></a>在 80 兼容模式中将忽略索引视图定义中的表提示且在 90 或更高的模式中不允许表提示
  在 90 或更高的兼容模式中，不允许索引视图定义中的表提示。 有关详细信息，请参阅 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 联机丛书中的以下主题：“设计索引视图”、“创建索引视图”和“查询提示 ([!INCLUDE[tsql](../../includes/tsql-md.md)])”。  
  
## <a name="component"></a>组件  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a>纠正措施  
 必须从索引视图的定义中删除表提示。 不管使用哪种兼容模式，我们建议您测试应用程序。 通过测试应用程序，可以确保在创建、更新和访问索引视图时（包括当索引视图与查询匹配时），程序按预期运行。  
  
## <a name="see-also"></a>请参阅  
 [数据库引擎升级问题](../../../2014/sql-server/install/database-engine-upgrade-issues.md)   
 [SQL Server 2014 升级顾问&#91;新&#93;](/sql/2014/sql-server/install/sql-server-2014-upgrade-advisor)  
  
  
