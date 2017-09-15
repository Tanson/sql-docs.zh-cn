---
title: "快照代理（新建发布向导）| Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.rep.newpubwizard.configuresnapshotagent.f1
ms.assetid: 0257d4ee-1f7b-49fd-b4ef-65bfc1ef6951
caps.latest.revision: 29
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 7682f989a77d79eb011088fe927c199b6c2b36fe
ms.contentlocale: zh-cn
ms.lasthandoff: 06/22/2017

---
# <a name="snapshot-agent-new-publication-wizard"></a>快照代理（新建发布向导）
  快照代理可以创建包含发布架构和数据（用于初始化新订阅）的文件。 默认情况下，在新建发布向导中创建发布之后，快照代理将立即运行。 此后，该代理将按照您指定的计划运行。 代理每次运行时是否创建新的快照文件取决于复制类型和所选择的选项。 有关详细信息，请参阅[创建并应用快照](../../relational-databases/replication/create-and-apply-the-snapshot.md)。  
  
 对于使用参数化筛选器的合并发布，在完成发布快照后，您必须为数据的每个分区创建一个快照。 有关详细信息，请参阅 [Snapshots for Merge Publications with Parameterized Filters](../../relational-databases/replication/snapshots-for-merge-publications-with-parameterized-filters.md)。  
  
## <a name="options"></a>选项  
 **“立即创建快照”** （合并复制）或 **“立即创建快照并使快照保持可用状态，以初始化订阅”** （事务复制）  
 选中此复选框，可以在新建发布向导完成后立即创建快照。 如果计划在生成快照之前更改 **“发布属性”** 对话框中的快照属性，或者要在没有快照的情况下初始化订阅服务器，请清除此复选框。 有关详细信息，请参阅 [Initialize a Transactional Subscription Without a Snapshot](../../relational-databases/replication/initialize-a-transactional-subscription-without-a-snapshot.md)中手动初始化订阅。  
  
> [!NOTE]  
>  该向导可能会提示您连接到分发服务器，以启动分发代理或合并代理的相应作业。  
  
 **计划在以下时间运行快照代理**  
 接受运行快照代理的默认计划，或单击 **“更改”** 指定一个计划。  
  
## <a name="see-also"></a>另请参阅  
 [Create a Publication](../../relational-databases/replication/publish/create-a-publication.md)   
 [创建并应用初始快照](../../relational-databases/replication/create-and-apply-the-initial-snapshot.md)   
 [查看和修改发布属性](../../relational-databases/replication/publish/view-and-modify-publication-properties.md)   
 [使用快照初始化订阅](../../relational-databases/replication/initialize-a-subscription-with-a-snapshot.md)   
 [发布数据和数据库对象](../../relational-databases/replication/publish/publish-data-and-database-objects.md)   
 [Replication Agents Overview](../../relational-databases/replication/agents/replication-agents-overview.md)  
  
  