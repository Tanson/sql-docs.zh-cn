---
title: 分发服务器设置 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.DistributorSettings.f1
helpviewer_keywords:
- Distributor Settings dialog box
ms.assetid: 8276a521-bdd1-4783-bdb6-7ab43499c0ca
caps.latest.revision: 9
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: bee6eb86ae33552b3ee15edd161aa948651a7d8f
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37305467"
---
# <a name="distributor-settings"></a>分发服务器设置
  使用 **“分发服务器设置”** 对话框，可以更改已添加到复制监视器左窗格中的分发服务器的设置。  
  
## <a name="options"></a>“常规”  
 **复制监视器启动时自动连接**  
 选择此选项可以允许复制监视器连接到分发服务器并检索状态信息。  
  
 **“连接”**  
 单击此选项可以显示 **“连接到服务器”** 对话框。 通过该对话框可以查看和更改复制监视器用来连接分发服务器的连接属性和凭据。  
  
 **自动刷新此分发服务器及其发布的状态**  
 选择此选项可以允许复制监视器自动刷新分发服务器的状态。 如果选择了此选项，复制监视器将基于 **“刷新速率”** 选项中设置的轮询间隔轮询分发服务器，以获取状态信息。 有关在复制监视器中刷新的详细信息，请参阅 [Caching, Refresh, and Replication Monitor Performance](monitor/caching-refresh-and-replication-monitor-performance.md)。  
  
 **“刷新速率”**  
 输入一个值（秒），指定复制监视器对分发服务器的轮询频率（以了解状态信息）。 较低的值会导致更频繁地轮询。 如果您正在监视多个发布服务器，这可能会影响分发服务器的性能。 建议您测试系统，以确定一个适当的值。 如果在复制监视器的任意详细信息窗口中选择 **“自动刷新”** ，则也将使用 **“刷新速率”** 设置。  
  
 **在以下组中显示此分发服务器的所有发布服务器**  
 从该列表中选择某个发布服务器组。 该发布服务器显示在左窗格中此组下面。 通过组可以组织发布服务器，而且对复制的功能没有任何影响。  
  
 **新建组**  
 单击此项可创建新的发布服务器组。 发布服务器组提供了在复制监视器内组织发布服务器的简便方法。 组既不影响数据的复制，也不影响复制拓扑中服务器之间的关系。  
  
## <a name="see-also"></a>请参阅  
 [启动复制监视器](monitor/start-the-replication-monitor.md)   
 [监视复制](monitoring-replication.md)  
  
  