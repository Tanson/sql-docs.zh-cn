---
title: put_OLEDBCommand 方法 |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- put_OLEDBCommand method [ADO]
ms.assetid: ca6a5804-bf5c-4afc-99db-22904bc0b33d
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 3dc19da014bc0909e44180ff4176adf1902694b0
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2018
ms.locfileid: "47828732"
---
# <a name="putoledbcommand-method"></a>put_OLEDBCommand 方法
此方法会执行任何操作并始终返回 S_OK。  
  
## <a name="syntax"></a>语法  
  
```  
  
HRESULT put_OLEDBCommand(  
      IUnknown *pOLEDBCommand  
);  
```  
  
#### <a name="parameters"></a>Parameters  
 *pOLEDBCommand*  
 [in]指向 OLE DB 命令对象的指针。  
  
## <a name="applies-to"></a>适用范围  
 [IADOCommandConstruction](https://msdn.microsoft.com/library/windows/desktop/aa965677.aspx)
