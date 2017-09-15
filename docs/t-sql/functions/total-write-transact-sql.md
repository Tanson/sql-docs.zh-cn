---
title: "@@TOTAL_WRITE (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '@@TOTAL_WRITE'
- '@@TOTAL_WRITE_TSQL'
dev_langs:
- TSQL
helpviewer_keywords:
- write activity since last started [SQL Server]
- number of disk writes
- '@@TOTAL_WRITE function'
- disks [SQL Server], numbr of disk writes
- total write [SQL Server]
ms.assetid: cd528126-51ee-4aa4-a21f-f32ce5c80fac
caps.latest.revision: 18
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: a8adaff8c7808b93742fed5435ab275285bbe414
ms.contentlocale: zh-cn
ms.lasthandoff: 09/01/2017

---
# <a name="totalwrite-transact-sql"></a>@@TOTAL_WRITE (Transact SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  返回自上次启动 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 以来 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 所执行的磁盘写入数。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
@@TOTAL_WRITE  
```  
  
## <a name="return-types"></a>返回类型  
 **integer**  
  
## <a name="remarks"></a>注释  
 若要显示报表包含若干个[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]统计信息，包括读取和写入活动，运行**sp_monitor**。  
  
## <a name="examples"></a>示例  
 以下示例显示了如何返回到当前日期和时间为止总的磁盘读写操作的次数。  
  
```  
SELECT @@TOTAL_READ AS 'Reads', @@TOTAL_WRITE AS 'Writes', GETDATE() AS 'As of'  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
Reads       Writes      As of                   
----------- ----------- ----------------------  
7760        97263       12/5/2006 10:23:00 PM   
```  
  
## <a name="see-also"></a>另请参阅  
 [sp_monitor &#40;Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-monitor-transact-sql.md)   
 [系统统计函数 &#40;Transact SQL &#41;](../../t-sql/functions/system-statistical-functions-transact-sql.md)   
 [@@TOTAL_READ (Transact-SQL)](../../t-sql/functions/total-read-transact-sql.md)  
  
  