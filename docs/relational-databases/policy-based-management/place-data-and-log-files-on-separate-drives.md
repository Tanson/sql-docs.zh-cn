---
title: "将数据和日志文件放到不同的驱动器上 | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 6cbedc27-4d77-44ad-bed2-c23b628475a7
caps.latest.revision: 9
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: d1105f11c98ac0b0c509f4c1d43a92ddd1a7a10c
ms.contentlocale: zh-cn
ms.lasthandoff: 06/22/2017

---
# <a name="place-data-and-log-files-on-separate-drives"></a>将数据和日志文件放到不同的驱动器上
  此规则检查是否将数据和日志文件放到了不同的逻辑驱动器上。 将数据和日志文件放到同一个设备上会导致该设备的争用，导致性能降低。 将文件放到不同的驱动器上允许数据和日志文件的 I/O 活动同时发生。  
  
## <a name="recommendations"></a>建议  
 创建新的数据库时，为数据和日志指定不同的驱动器。 若要在创建数据库后移动文件，则必须使数据库脱机。 使用下列方法之一移动文件：  
  
> [!NOTE]  
>  此策略无法通过装入点检测分开的物理设备。  
  
-   使用具有 WITH MOVE 选项的 RESTORE DATABASE 语句从备份还原数据库。  
  
-   通过为数据和日志设备指定不同的位置来分离然后附加数据库。  
  
-   指定新位置，方法是运行具有 MODIFY FILE 选项的 ALTER DATABASE 语句，然后重新启动 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]实例。  
  
## <a name="for-more-information"></a>有关详细信息  
 [移动数据库文件](../../relational-databases/databases/move-database-files.md)  
  
 [移动用户数据库](../../relational-databases/databases/move-user-databases.md)  
  
 [数据库分离和附加 (SQL Server)](../../relational-databases/databases/database-detach-and-attach-sql-server.md)  
  
## <a name="see-also"></a>另请参阅  
 [使用基于策略的管理来监视和强制执行最佳实践](../../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  