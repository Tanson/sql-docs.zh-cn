---
title: "NEWSEQUENTIALID (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 08/08/2015
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- NEWSEQUENTIALID
- NEWSEQUENTIALID_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- NEWSEQUENTIALID function
- GUIDs [SQL Server]
ms.assetid: e06d2cab-f1ff-42f1-8550-6aaec57be36f
caps.latest.revision: 33
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 2a453b99d7ab0512e57275b5ad1805f5a66522ba
ms.contentlocale: zh-cn
ms.lasthandoff: 09/01/2017

---
# <a name="newsequentialid-transact-sql"></a>NEWSEQUENTIALID (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  在启动 Windows 后在指定计算机上创建大于先前通过该函数生成的任何 GUID 的 GUID。 在重新启动 Windows 后，GUID 可以再次从一个较低的范围开始，但仍是全局唯一的。 在 GUID 列用作行标识符时，使用 NEWSEQUENTIALID 可能比使用 NEWID 函数的速度更快。 其原因在于，NEWID 函数导致随机行为并且使用更少的缓存数据页。 使用 NEWSEQUENTIALID 还有助于完全填充数据和索引页。  
  
> [!IMPORTANT]  
>  如果涉及保密问题，则不要使用该函数。 因为有可能猜到下一个生成的 GUID 的值，从而访问与该 GUID 关联的数据。  
  
 NEWSEQUENTIALID 是通过 Windows 的包装器[UuidCreateSequential](http://go.microsoft.com/fwlink/?LinkId=164027)函数。  
  
> [!WARNING]  
>  UuidCreateSequential 函数具有硬件依赖关系。 上[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]，在数据库 （例如包含的数据库） 移到其他计算机时，可以开发群集的连续值。 在使用 Alwayson 时并且在[!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)]，如果数据库故障转移到另一台计算机，可以开发群集的连续值。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
NEWSEQUENTIALID ( )  
```  
  
## <a name="return-type"></a>返回类型  
 **uniqueidentifier**  
  
## <a name="remarks"></a>注释  
 Newsequentialid （） 仅用于类型的表列的默认约束**uniqueidentifier**。 例如：  
  
```  
CREATE TABLE myTable (ColumnA uniqueidentifier DEFAULT NEWSEQUENTIALID());   
```  
  
 当 NEWSEQUENTIALID() 用于 DEFAULT 表达式时，不能与其他标量运算符结合使用。 例如，您不能执行以下操作：  
  
```  
CREATE TABLE myTable (ColumnA uniqueidentifier DEFAULT dbo.myfunction(NEWSEQUENTIALID()));  
```  
  
 在上一个示例中，`myfunction()` 是一个由标量用户定义的标题函数，它接受并返回 `uniqueidentifier` 值。  
  
 不能在查询中引用 NEWSEQUENTIALID  
  
 可以使用 NEWSEQUENTIALID 生成 GUID 以减少叶级别索引上的页拆分和随机 IO。  
  
 使用 NEWSEQUENTIALID 生成的每个 GUID 在该计算机上都是唯一的。 仅当源计算机具有网卡时，使用 NEWSEQUENTIALID 生成的 GUID 在多台计算机上才是唯一的。  
  
## <a name="see-also"></a>另请参阅  
 [NEWID &#40;Transact SQL &#41;](../../t-sql/functions/newid-transact-sql.md)   
 [比较运算符 &#40;Transact SQL &#41;](../../t-sql/language-elements/comparison-operators-transact-sql.md)  
  
  
