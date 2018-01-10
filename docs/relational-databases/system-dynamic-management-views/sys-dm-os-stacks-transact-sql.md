---
title: "sys.dm_os_stacks (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 03/13/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: dmv's
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- dm_os_stacks
- dm_os_stacks_TSQL
- sys.dm_os_stacks
- sys.dm_os_stacks_TSQL
dev_langs: TSQL
helpviewer_keywords: sys.dm_os_stacks dynamic management view
ms.assetid: a69b06c4-28f0-4535-8fa1-9f132db4d916
caps.latest.revision: "23"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 9e3e292fbafbee9586d377f133af7f9d3ee520d5
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2017
---
# <a name="sysdmosstacks-transact-sql"></a>sys.dm_os_stacks (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  此动态管理视图供 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 内部使用以执行下列操作：  
  
-   跟踪调试数据（例如，未完成的分配）。  
  
-   在组件认为已经进行一个调用的地方，假定或验证由 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 组件使用的逻辑。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**stack_address**|**varbinary （8)**|是该堆栈分配的唯一地址。 不可为 null。|  
|**frame_index**|**int**|每行代表一个函数调用，当按帧为特定的索引以升序排序**stack_address**，返回的完整调用堆栈。 不可为 null。|  
|**frame_address**|**varbinary （8)**|函数调用的地址。 不可为 null。|  
  
## <a name="remarks"></a>注释  
 **sys.dm_os_stacks**要求的服务器和其他组件的符号必须存在于服务器以正确显示的信息。  
  
## <a name="permissions"></a>Permissions  
上[!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)]，需要`VIEW SERVER STATE`权限。   
上[!INCLUDE[ssSDS_md](../../includes/sssds-md.md)]高级层，需要`VIEW DATABASE STATE`数据库中的权限。 上[!INCLUDE[ssSDS_md](../../includes/sssds-md.md)]标准版和基本层，需要**服务器管理员**或**Azure Active Directory 管理员**帐户。  
  

## <a name="see-also"></a>另请参阅  
  [SQL Server 操作系统相关的动态管理视图 &#40;Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/sql-server-operating-system-related-dynamic-management-views-transact-sql.md)  
  
  