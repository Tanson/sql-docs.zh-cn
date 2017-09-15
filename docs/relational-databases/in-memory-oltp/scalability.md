---
title: "可伸缩性 | Microsoft Docs"
ms.custom: 
ms.date: 08/27/2015
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine-imoltp
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4891c57-56bb-49f4-9bb5-f11b745279e5
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 5ab43ba6b6a27fa46b5214a60063c5df3f5496f4
ms.contentlocale: zh-cn
ms.lasthandoff: 06/22/2017

---
# <a name="scalability"></a>可伸缩性
  SQL Server 2016 包含内存优化表磁盘存储的可伸缩性增强功能。  
  
-   **要保留内存优化表的多个线程**  
  
     在以前版本的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]中，存在单个脱机检查点线程以扫描内存优化表更改的事务日志并将其保存在检查点文件（如数据和差异文件）中。 具有较大内核数，单个脱机检查点线程会落后。  
  
     在 [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)]中，有多个并发线程负责保存内存优化表的更改。  
  
-   **多线程恢复**  
  
     在以前版本的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]中，日志应用属于恢复操作的一部分，是单个线程。 在 [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)]中，日志应用是多线程。  
  
-   **合并操作**  
  
     合并操作现在是多线程。  
  
-   **动态管理视图**  
  
     [sys.dm_db_xtp_checkpoint_stats (Transact-SQL)](../../relational-databases/system-dynamic-management-views/sys-dm-db-xtp-checkpoint-stats-transact-sql.md) 和 [sys.dm_db_xtp_checkpoint_files (Transact-SQL)](../../relational-databases/system-dynamic-management-views/sys-dm-db-xtp-checkpoint-files-transact-sql.md) 发生了显著变化。  
  
 手动合并已禁用，因为多线程合并需要与负荷保持一致。  
  
 内存中 OLTP 引擎将基于文件流继续使用内存优化文件组，但该文件组中的单个文件脱离文件流。 这些文件完全由内存中 OLTP 引擎管理（例如对于创建、删除和垃圾回收）。 不支持 [DBCC SHRINKFILE (Transact-SQL)](../../t-sql/database-console-commands/dbcc-shrinkfile-transact-sql.md)。  
  
  
