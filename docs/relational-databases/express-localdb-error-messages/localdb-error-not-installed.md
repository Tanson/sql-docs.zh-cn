---
title: "LOCALDB_ERROR_NOT_INSTALLED |Microsoft 文档"
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: localdb
ms.reviewer: 
ms.suite: sql
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: e7912885-1c14-409b-9022-83ad4c36f3bd
caps.latest.revision: "10"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 65fa20a9c43ef69cb29214ef2b631713d67b7760
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="localdberrornotinstalled"></a>LOCALDB_ERROR_NOT_INSTALLED
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|SQL Server|  
|事件 ID|278|  
|事件源|SQL Server 本地数据库运行时 12.0|  
|组件|本地数据库运行时 API|  
|消息正文|注意： 消息文本为空，因为此消息意味着整个 LocalDB API （包括将 HRESULT 映射到消息文本的 FormatMessage 函数） 不可用。|  
  
## <a name="explanation"></a>解释  
 计算机上没有安装本地数据库运行时。  
  
## <a name="user-action"></a>用户操作  
 安装本地数据库运行时，然后重试操作。  
  
  