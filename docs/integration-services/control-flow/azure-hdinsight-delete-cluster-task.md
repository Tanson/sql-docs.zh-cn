---
title: Azure HDInsight 删除群集任务 | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql13.dts.designer.afpdelcltask.f1
- sql14.dts.designer.afpdelcltask.f1
ms.assetid: e298776e-d18a-4393-a8e6-65ee3d555749
author: janinezhang
ms.author: janinez
manager: craigg
ms.openlocfilehash: a64cf0fecb7313ebd8947a1acd3ef54ccb34636f
ms.sourcegitcommit: 7ccb8f28eafd79a1bddd523f71fe8b61c7634349
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2019
ms.locfileid: "58272358"
---
# <a name="azure-hdinsight-delete-cluster-task"></a>Azure HDInsight 删除群集任务
Azure HDInsight 删除群集任务启用一个 SSIS 包来删除指定的 Azure 订阅和资源组中的一个 Azure HDInsight 群集。
  
Azure HDInsight 删除群集任务是[用于 Azure 的 SQL Server Integration Services (SSIS) 功能包](../../integration-services/azure-feature-pack-for-integration-services-ssis.md)的一个组件。
  
> [!NOTE]
> 删除 HDInsight 群集可能需要 10~20 分钟。  
  
若要添加 **Azure HDInsight 删除群集任务**，可将其拖放到 SSIS 设计器，然后双击或右键单击“编辑”，  以查看以下 **Azure Blob 删除群集任务编辑器** 对话框。  
  
下表提供了此对话框中的字段说明。  
  
|||  
|-|-|  
|**字段**|**Description**|  
|AzureResourceManagerConnection|选择一个现有 Azure 资源管理器连接管理器，或创建一个用于删除 HDInsight 群集的新连接管理器。|
|SubscriptionId|指定 HDInsight 群集所在的订阅的 ID。|
|ResourceGroup|指定 HDInsight 群集所在的 Azure 资源组。|
|ClusterName|指定要删除的群集的名称。|  
|FailIfNotExists|指定如果群集不存在时任务是否会失败。|
