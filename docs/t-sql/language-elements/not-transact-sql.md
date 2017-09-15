---
title: "不 (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- NOT_TSQL
- NOT
dev_langs:
- TSQL
helpviewer_keywords:
- negating Boolean input
- NOT operator [Transact-SQL]
- expressions [SQL Server], negating
- reversing Boolean expression values
ms.assetid: dc07cc35-20f1-46e6-9995-2938390dc19a
caps.latest.revision: 39
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 85cdc60ebe0c6f66624b539e0f20d83f32c19500
ms.contentlocale: zh-cn
ms.lasthandoff: 09/01/2017

---
# <a name="not-transact-sql"></a>NOT (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  对布尔型输入取反。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
-- Syntax for SQL Server, Azure SQL Database, Azure SQL Data Warehouse, Parallel Data Warehouse  
  
[ NOT ] boolean_expression  
```  
  
## <a name="arguments"></a>参数  
 *boolean_expression*  
 是任何有效的布尔值[表达式](../../t-sql/language-elements/expressions-transact-sql.md)。  
  
## <a name="result-types"></a>结果类型  
 **Boolean**  
  
## <a name="result-value"></a>结果值  
 NOT 反转任何布尔表达式的值。  
  
## <a name="remarks"></a>注释  
 使用 NOT 对表达式取反。  
  
 下表显示使用 NOT 运算符比较 TRUE 和 FALSE 值的结果。  
  
||NOT|  
|------|---------|  
|**TRUE**|FALSE|  
|**FALSE**|TRUE|  
|**未知**|UNKNOWN|  
  
## <a name="examples"></a>示例  
 以下示例查找标准价格不超过 400 美元的所有银色自行车。  
  
```  
-- Uses AdventureWorks  
  
SELECT ProductID, Name, Color, StandardCost  
FROM Production.Product  
WHERE ProductNumber LIKE 'BK-%' AND Color = 'Silver' AND NOT StandardCost > 400;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `ProductID   Name                     Color         StandardCost`  
  
 `---------   -------------------      ------      ------------`  
  
 `984         Mountain-500 Silver, 40  Silver        308.2179`  
  
 `985         Mountain-500 Silver, 42  Silver        308.2179`  
  
 `986         Mountain-500 Silver, 44  Silver        308.2179`  
  
 `987         Mountain-500 Silver, 48  Silver        308.2179`  
  
 `988         Mountain-500 Silver, 52  Silver        308.2179`  
  
 `(6 row(s) affected)`  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>示例：[!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)]和[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
 下面的示例限制到的结果`SalesOrderNumber`为开头的值`SO6`和`ProductKeys`大于或等于 400。  
  
```  
-- Uses AdventureWorks  
  
SELECT ProductKey, CustomerKey, OrderDateKey, ShipDateKey  
FROM FactInternetSales  
WHERE SalesOrderNumber LIKE 'SO6%' AND NOT ProductKey < 400;  
```  
  
## <a name="see-also"></a>另请参阅  
 [表达式 &#40;Transact SQL &#41;](../../t-sql/language-elements/expressions-transact-sql.md)   
 [内置函数 (Transact-SQL)](~/t-sql/functions/functions.md)   
 [运算符 &#40;Transact SQL &#41;](../../t-sql/language-elements/operators-transact-sql.md)   
 [SELECT (Transact-SQL)](../../t-sql/queries/select-transact-sql.md)   
 [其中 &#40;Transact SQL &#41;](../../t-sql/queries/where-transact-sql.md)  
  
  


