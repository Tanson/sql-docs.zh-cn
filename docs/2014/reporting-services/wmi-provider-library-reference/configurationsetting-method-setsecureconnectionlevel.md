---
title: SetSecureConnectionLevel 方法 (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- reporting-services-native
ms.topic: conceptual
api_name:
- SetSecureConnectionLevel (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetSecureConnectionLevel method
ms.assetid: 0fac7d5e-2670-4657-9439-331e7d93babb
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: b22e8d9e67e0c897aaab859dde097707d3272ec3
ms.sourcegitcommit: dfb1e6deaa4919a0f4e654af57252cfb09613dd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "56029059"
---
# <a name="setsecureconnectionlevel-method-wmi-msreportserverconfigurationsetting"></a>SetSecureConnectionLevel 方法 (WMI MSReportServer_ConfigurationSetting)
  设置报表服务器的安全连接级别。  
  
## <a name="syntax"></a>语法  
  
```vb  
Public Sub SetSecureConnectionLevel(Level as Integer, _  
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetSecureConnectionLevel(Int32 Level,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a>Parameters  
 *级别*  
 表示安全连接级别的整数值。  
  
 *HRESULT*  
 [out] 指示调用是成功还是失败的值。  
  
## <a name="return-value"></a>返回值  
 返回 *HRESULT* ，指示方法调用是成功还是失败。 值 0 指示方法调用已成功。 非零值指示已发生错误。  
  
## <a name="remarks"></a>备注  
 调用时，报表服务器 SecureConnectionLevel 属性设置为指定的值。 值为 0 表示关闭了 SSL。 值大于或等于 1 标识打开了 SSL。  
  
-   当设置值时，更改报表服务器配置文件中的 SecureConnectionLevel 元素，并`URLRoot`配置文件中的元素设置为使用"https://"，如果指定*级别*大于或如果等于 1 或使用"http://"指定*级别*为 0。  
  
 在 [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]中，SecureConnectionLevel 成为一个开关，默认值为 0。 对于任何通过 SetSecureConnectionLevel 方法 API 传递的大于或等于 1 的值，SSL 将被视为打开，并且在 rsreportserver.config 文件中相应地设置配置属性 SecureConnectionLevel。 将仍允许值为 2 和 3，以便向后兼容。  
  
## <a name="requirements"></a>要求  
 **命名空间:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [MSReportServer_ConfigurationSetting 成员](msreportserver-configurationsetting-members.md)  
  
  
