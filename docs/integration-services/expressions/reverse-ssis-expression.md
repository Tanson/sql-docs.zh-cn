---
title: REVERSE（SSIS 表达式）| Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- REVERSE function
- reverse character expressions
ms.assetid: bcebcc55-7247-4896-8f53-4d582d58cfb4
author: janinezhang
ms.author: janinez
manager: craigg
ms.openlocfilehash: 85d35a4f1fbf0f55960e1550e9bd030631ca2c04
ms.sourcegitcommit: 7ccb8f28eafd79a1bddd523f71fe8b61c7634349
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2019
ms.locfileid: "58277297"
---
# <a name="reverse-ssis-expression"></a>REVERSE（SSIS 表达式）
  按相反顺序返回字符表达式。  
  
## <a name="syntax"></a>语法  
  
```  
  
REVERSE(character_expression)  
```  
  
## <a name="arguments"></a>参数  
 *character_expression*  
 是要反转的字符表达式。  
  
## <a name="result-types"></a>结果类型  
 DT_WSTR  
  
## <a name="remarks"></a>Remarks  
 character_expression 参数必须具有 DT_WSTR 数据类型。  
  
 如果 character_expression 为 Null，则 REVERSE 将返回 Null 结果。  
  
## <a name="expression-examples"></a>表达式示例  
 此示例使用一个字符串文字。 返回结果为“ekiB niatnuoM”。  
  
```  
REVERSE("Mountain Bike")  
```  
  
 此示例使用一个变量。 如果 **Name** 包含 Touring Bike，则返回的结果为“ekiB gniruoT”。  
  
```  
REVERSE(@Name)  
```  
  
## <a name="see-also"></a>另请参阅  
 [函数（SSIS 表达式）](../../integration-services/expressions/functions-ssis-expression.md)  
  
  
