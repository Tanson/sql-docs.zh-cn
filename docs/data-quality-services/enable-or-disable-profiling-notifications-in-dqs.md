---
title: 在 DQS 中启用或禁用事件探查通知 | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: data-quality-services
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
helpviewer_keywords:
- enable notifications
- notifications,enable
- notifications,disable
ms.assetid: e439bb29-60cc-4afd-a79a-f629b8d843c1
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 583ccac2604216c88f14aa9c460437a2aa24c03c
ms.sourcegitcommit: dfb1e6deaa4919a0f4e654af57252cfb09613dd5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "56022148"
---
# <a name="enable-or-disable-profiling-notifications-in-dqs"></a>在 DQS 中启用或禁用事件探查通知

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  本主题介绍如何在 [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) 中启用或禁用事件探查通知。 默认情况下，在 DQS 中启用了事件探查通知。 事件探查通知将指出有关数据源的重要事实以及对数据执行的当前活动的效用。 有关详细信息，请参阅 [Data Profiling and Notifications in DQS](../data-quality-services/data-profiling-and-notifications-in-dqs.md)。  
  
##  <a name="BeforeYouBegin"></a> 开始之前  
  
###  <a name="Security"></a> 安全性  
  
####  <a name="Permissions"></a> Permissions  
 您必须对 DQS_MAIN 数据库具有 dqs_administrator 角色才能启用通知。  
  
##  <a name="Enable"></a> 启用或禁用事件探查通知  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)][运行 Data Quality Client 应用程序](../data-quality-services/run-the-data-quality-client-application.md)。  
  
2.  在 [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] 主屏幕中，单击 **“配置”**。  
  
3.  接下来，单击 **“常规设置”** 选项卡。  
  
4.  取消选中或选中 **“启用通知”** 复选框，以便为 DQS 中的各种活动禁用或启用事件探查通知。  
  
5.  单击 **“关闭”**。  
  
  
