---
title: srv_rpcdb（扩展存储过程 API）| Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- srv_rpcdb
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcdb
ms.assetid: d52bfd22-7a7c-4ab0-af65-df96ff359e6f
caps.latest.revision: 30
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: dfbd36d8d208079edbad0ef70df97bf8f93b126d
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37254369"
---
# <a name="srvrpcdb-extended-stored-procedure-api"></a>srv_rpcdb（扩展存储过程 API）
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)]请改用 CLR 集成。  
  
 返回当前远程存储过程的数据库名称部分。  
  
## <a name="syntax"></a>语法  
  
```  
  
DBCHAR * srv_rpcdb (  
SRV_PROC * srvproc,int *len );  
```  
  
## <a name="arguments"></a>参数  
 srvproc  
 指向作为特定客户端连接句柄的 SRV_PROC 结构的指针。 该结构包含扩展存储过程 API 库用于管理应用程序和客户端之间的通信和数据的信息。  
  
 len  
 指向接收数据库名称长度的 `int` 变量的指针。 如果 len 为 NULL，则不返回数据库名称的长度。  
  
## <a name="returns"></a>返回  
 一个 DBCHAR 指针，指向当前远程存储过程的数据库名称部分的以 NULL 值结束的字符串。 如果当前无远程存储过程，则返回 NULL，且 len 参数设置为 -1。  
  
## <a name="remarks"></a>Remarks  
 此函数只返回远程存储过程对象名称的数据库部分。 它不包括所有者、远程存储过程名称和远程存储过程编号的可选说明符。  
  
> [!IMPORTANT]  
>  应全面检查扩展存储过程的源代码，并在生产服务器中安装编译的 DLL 之前，对这些 DLL 进行测试。 有关安全检查和测试的信息，请访问此 [Microsoft 网站](http://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409http://msdn.microsoft.com/security/)。  
  
  