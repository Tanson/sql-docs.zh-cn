---
title: 选项 （文本编辑器-Transact-SQL-选项卡页） |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.SQL.Tabs
dev_langs:
- TSQL
ms.assetid: a4499784-67f7-46ef-9f7c-2d0fdd117a52
caps.latest.revision: 10
author: craigg-msft
ms.author: craigg
manager: craigg
ms.openlocfilehash: 9c97c95ec2dff4d96f37eb274ee6ec98af117f89
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37152638"
---
# <a name="options-text-editor---transact-sql---tabs-page"></a>选项 （文本编辑器-Transact-SQL-选项卡页）
  使用此对话框可以更改用于对 [!INCLUDE[ssDE](../includes/ssde-md.md)] 脚本进行编程的[!INCLUDE[tsql](../includes/tsql-md.md)]查询编辑器的跳格行为。 若要显示这些设置，请在“工具”菜单上单击“选项”，依次展开“文本编辑器”文件夹和“Transact-SQL”子文件夹，然后单击“制表符”。  
  
## <a name="setting-options-in-multiple-locations"></a>在多个位置设置选项  
 [!INCLUDE[ssDE](../includes/ssde-md.md)] 查询编辑器的选项也可在“所有语言选项卡”对话框中设置。 如果使用 **“所有语言”** 对话框来设置其他 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] 编辑器（例如 DMX 或 MDX 编辑器）的其他选项，则必须使用此对话框重置 [!INCLUDE[ssDE](../includes/ssde-md.md)] 查询编辑器选项。  
  
## <a name="indenting"></a>缩进  
 **无**  
 选择此选项后，则按 Enter 键时所创建的新行不会缩进。 光标置于新行的第一列。  
  
 **块**  
 如果选择此选项，则按 Enter 时创建的新行的自动缩进距离与上一行的缩进距离相同。  
  
 **智能**  
 此选项不可用。  
  
## <a name="tabs"></a>制表符  
 **制表符大小**  
 设置制表位之间的距离（以空格为单位）。 默认为四个空格。  
  
 **缩进大小**  
 设置自动缩进的大小（以空格为单位）。 默认为四个空格。 可能会插入制表符、空格字符，或同时插入这二者，以填充为指定大小。  
  
 **插入空格**  
 选择此选项后，缩进操作仅插入空格字符，而不会插入制表符。 例如，如果 **“缩进大小”** 设置为 5，则每次按 Tab 键或单击 **主窗口工具栏上的** “增加缩进” [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] 按钮时会插入五个空格。  
  
 **保留制表符**  
 选择此选项后，缩进操作会插入尽可能多的制表符。 每个制表符都会填充 **“制表符大小”** 中指定的空格数。 如果 **“缩进大小”** 不是 **“制表符大小”** 的偶数倍，则会添加空格字符补齐。  
  
  