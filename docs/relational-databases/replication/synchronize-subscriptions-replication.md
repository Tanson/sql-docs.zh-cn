---
title: "同步订阅（复制）| Microsoft Docs"
ms.custom: 
ms.date: 03/07/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- synchronization [SQL Server replication], subscriptions
- subscriptions [SQL Server replication], synchronizing
- replication [SQL Server], synchronization
ms.assetid: cbe13120-8dd9-4309-88dd-07a801c68f5f
caps.latest.revision: 35
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: dbd10248c5a6c358e6e8e6c64b0db355fc4ed66d
ms.contentlocale: zh-cn
ms.lasthandoff: 06/22/2017

---
# <a name="synchronize-subscriptions-replication"></a>同步订阅（复制）
  订阅是由复制代理进行同步的。 分发代理同步针对的是事务发布和快照发布的订阅，而合并代理同步针对的是合并发布的订阅。 可以使用 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]、复制存储过程和复制管理对象 (RMO) 来同步订阅，并控制同步行为。 下面的主题介绍如何同步订阅并指定同步选项。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [创建并应用初始快照](../../relational-databases/replication/create-and-apply-the-initial-snapshot.md)  
  
-   [为包含参数化筛选器的合并发布创建快照](../../relational-databases/replication/create-a-snapshot-for-a-merge-publication-with-parameterized-filters.md)  
  
-   [使用备份来初始化事务发布 &#40;SQL Server Management Studio&#41;](../../relational-databases/replication/enable-initialization-with-backup-for-transactional-publications.md)  
  
-   [从备份初始化事务订阅（复制 Transact-SQL 编程）](../../relational-databases/replication/initialize-a-transactional-subscription-from-a-backup.md)  
  
-   [手动初始化订阅](../../relational-databases/replication/initialize-a-subscription-manually.md)  
  
-   [同步请求订阅](../../relational-databases/replication/synchronize-a-pull-subscription.md)  
  
-   [同步推送订阅](../../relational-databases/replication/synchronize-a-push-subscription.md)  
  
-   [重新初始化订阅](../../relational-databases/replication/reinitialize-a-subscription.md)  
  
-   [在应用快照之前和之后执行脚本 &#40;SQL Server Management Studio&#41;](../../relational-databases/replication/execute-scripts-before-and-after-a-snapshot-is-applied.md)  
  
-   [在同步期间执行脚本（复制 Transact-SQL 编程）](../../relational-databases/replication/execute-scripts-during-synchronization-replication-transact-sql-programming.md)  
  
-   [查看和解决合并发布的数据冲突 &#40;SQL Server Management Studio&#41;](../../relational-databases/replication/view-and-resolve-data-conflicts-for-merge-publications.md)  
  
-   [查看事务发布的数据冲突 &#40;SQL Server Management Studio&#41;](../../relational-databases/replication/view-data-conflicts-for-transactional-publications-sql-server-management-studio.md)  
  
-   [使用 Windows 同步管理器同步订阅（Windows 同步管理器）](../../relational-databases/replication/synchronize-a-subscription-using-windows-synchronization-manager.md)  
  
-   [Implement a Business Logic Handler for a Merge Article](../../relational-databases/replication/implement-a-business-logic-handler-for-a-merge-article.md)  
  
-   [调试业务逻辑处理程序（复制编程）](../../relational-databases/replication/debug-a-business-logic-handler-replication-programming.md)  
  
-   [控制同步期间触发器和约束的行为（复制 Transact-SQL 编程）](../../relational-databases/replication/control-behavior-of-triggers-and-constraints-in-synchronization.md)  
  
-   [为合并项目实现自定义冲突解决程序](../../relational-databases/replication/implement-a-custom-conflict-resolver-for-a-merge-article.md)  
  
## <a name="see-also"></a>另请参阅  
 [同步数据](../../relational-databases/replication/synchronize-data.md)  
  
  