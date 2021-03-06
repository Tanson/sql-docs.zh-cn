---
title: WillMove 和 MoveComplete 事件 (ADO) |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Recordset::MoveComplete
- WillMove
- MoveComplete
- Recordset::WillMove
helpviewer_keywords:
- MoveComplete event [ADO]
- WillMove event [ADO]
ms.assetid: 1a3d1042-4f30-4526-a0c7-853c242496db
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 47040adf2ce7be17d0540755f7fa972d7a76266f
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2018
ms.locfileid: "47772547"
---
# <a name="willmove-and-movecomplete-events-ado"></a>WillMove 和 MoveComplete 事件 (ADO)
**WillMove**挂起操作更改中的当前位置之前调用事件[记录集](../../../ado/reference/ado-api/recordset-object-ado.md)。 **MoveComplete**中的当前位置后，将调用事件**记录集**更改。  
  
## <a name="syntax"></a>语法  
  
```  
  
WillMove adReason, adStatus, pRecordset  
MoveComplete adReason, pError, adStatus, pRecordset  
```  
  
#### <a name="parameters"></a>Parameters  
 *adReason*  
 [EventReasonEnum](../../../ado/reference/ado-api/eventreasonenum.md)值，该值指定此事件的原因。 其值可以是**adRsnMoveFirst**， **adRsnMoveLast**， **adRsnMoveNext**， **adRsnMovePrevious**， **adRsnMove**，或**adRsnRequery**。  
  
 *pError*  
 [错误](../../../ado/reference/ado-api/error-object.md)对象。 它描述了如果发生的错误的值*adStatus*是**adStatusErrorsOccurred**; 不会设置该参数。  
  
 *adStatus*  
 [EventStatusEnum](../../../ado/reference/ado-api/eventstatusenum.md)状态值。  
  
 当**WillMove**是调用，此参数设置为**adStatusOK**引发该事件的操作是否成功。 设置为**adStatusCantDeny**如果此事件不能请求取消的挂起的操作。  
  
 当**MoveComplete**是调用，此参数设置为**adStatusOK**引发该事件的操作是否成功，或向**adStatusErrorsOccurred**如果操作失败。  
  
 之前**WillMove**返回时，将此参数设置为**adStatusCancel**若要请求取消的挂起的操作，或将此参数设置为**adStatusUnwantedEvent**若要防止后续的通知。  
  
 之前**MoveComplete**返回时，将此参数设置为**adStatusUnwantedEvent**以防止后续的通知。  
  
 *pRecordset*  
 一个[记录集](../../../ado/reference/ado-api/recordset-object-ado.md)对象。 **记录集**有关发生此事件。  
  
## <a name="remarks"></a>备注  
 一个**WillMove**或**MoveComplete**事件可能是由于以下**记录集**operations:[打开](../../../ado/reference/ado-api/open-method-ado-recordset.md)，[移动](../../../ado/reference/ado-api/move-method-ado.md)， [MoveFirst](../../../ado/reference/ado-api/movefirst-movelast-movenext-and-moveprevious-methods-ado.md)， [MoveLast](../../../ado/reference/ado-api/movefirst-movelast-movenext-and-moveprevious-methods-ado.md)， [MoveNext](../../../ado/reference/ado-api/movefirst-movelast-movenext-and-moveprevious-methods-ado.md)， [MovePrevious](../../../ado/reference/ado-api/movefirst-movelast-movenext-and-moveprevious-methods-ado.md)， [AddNew](../../../ado/reference/ado-api/addnew-method-ado.md)，并[再次查询](../../../ado/reference/ado-api/requery-method.md)。 这些事件可能是因为以下属性：[筛选器](../../../ado/reference/ado-api/filter-property.md)，[索引](../../../ado/reference/ado-api/index-property.md)，[书签](../../../ado/reference/ado-api/bookmark-property-ado.md)， [AbsolutePage](../../../ado/reference/ado-api/absolutepage-property-ado.md)，和[AbsolutePosition](../../../ado/reference/ado-api/absoluteposition-property-ado.md)。 如果子级，也会发生这些事件**记录集**已**记录集**连接的事件和父**记录集**移动。  
  
 必须设置*adStatus*参数**adStatusUnwantedEvent**对每个可能*adReason*值，以便完全停用的任何事件的事件通知，包括*adReason*参数。  
  
## <a name="see-also"></a>请参阅  
 [ADO 事件模型示例 （VC + +）](../../../ado/reference/ado-api/ado-events-model-example-vc.md)   
 [ADO 事件处理程序摘要](../../../ado/guide/data/ado-event-handler-summary.md)   
 [记录集对象 (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)
