---
title: sys.dm_pdw_network_credentials (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql
ms.technology: data-warehouse
ms.reviewer: ''
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: d4fee3ad-6285-4ea5-8513-5e6eb617abb0
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: '>= aps-pdw-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: 7d9e18284ac4d97efaa217802682fe79ebb2dfc5
ms.sourcegitcommit: dfb1e6deaa4919a0f4e654af57252cfb09613dd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "56041518"
---
# <a name="sysdmpdwnetworkcredentials-transact-sql"></a>sys.dm_pdw_network_credentials (Transact-SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md.md)]

  返回的所有网络凭据的列表存储在[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]所有的目标服务器的设备。 控制节点和每个计算节点列出结果。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|pdw_node_id|**int**|与节点关联的唯一数字 id。|  
|target_server_name|**nvarchar(32)**|目标服务器的 IP 地址的[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]将访问通过使用用户名和密码凭据。|  
|username|**nvarchar(32)**|该密码存储的用户名。|  
|last_modified|**datetime**|上次修改凭据的操作的日期时间。|  
  
## <a name="permissions"></a>权限  
 需要 VIEW SERVER STATE。  
  
## <a name="general-remarks"></a>一般备注  
 此动态管理视图的键是*pdw_node_id*加上*target_server_name*。  
  
## <a name="see-also"></a>请参阅  
 [SQL 数据仓库和并行数据仓库动态管理视图&#40;Transact SQL&#41;](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)  
  
  
