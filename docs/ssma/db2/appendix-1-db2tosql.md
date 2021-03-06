---
title: 附录-1 (DB2ToSQL) |Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: c6a30367-d56f-4fcc-8920-c6a6b0335a67
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: ee92addc2d77c8393c3378762618504344b8d477
ms.sourcegitcommit: 2429fbcdb751211313bd655a4825ffb33354bda3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "52521153"
---
# <a name="appendix---1-db2tosql"></a>附录-1 (DB2ToSQL)
SSMA 控制台命令行选项的快速视图：  
  
|Sl。 否。|开关|必需？|开关参数|允许的值|  
|-----------|----------|-------------|-------------------|--------------------|  
|1|-s/script|用户帐户控制|scriptfile|有效的 XML 文件名称。<br /><br />控制台脚本定义文件。|  
|2|-v/变量|否|variablevaluefile|有效的 XML 文件名称。<br /><br />如果未在脚本文件中使用变量，则必须指定此文件。|  
|3|-c/serverconnection|否|serverconnectionfile|有效的 XML 文件名称。<br /><br />此文件包含服务器连接信息。|  
|4|-x/xmloutput|否|xmloutputfile|此选项指示以 XML 格式的控制台输出。 如果未指定此选项，默认输出的文本格式。<br /><br />如果未指定 xmloutputfile，XML 输出定向到 STDOUT。<br /><br />Xmloutputfile 是文件的以 XML 格式，控制台输出写入到的名称。|  
|5|-l/日志|否|logfile|有效的文件名。|  
|6|-e/projectenvironment|否|projectenvironmentfolder|有效的文件夹名称包含 SSMA 项目环境文件。|  
|7|-p/securepassword|否|-a/添加 {< server_id > [，...n]&#124;所有}-c&#124;serverconnection < 服务器连接文件 > [-v&#124;变量 < 变量值文件 >] [-o/覆盖]<br /><br />或<br /><br />-a/添加 {< server_id > [，...n]&#124;所有}-s&#124;脚本 < 脚本文件 > [-v&#124;变量 < 变量值文件 >] [-o/覆盖]<br /><br />-r/删除 {< server_id > [，...n]&#124;所有}<br /><br />-l/列表<br /><br />-e/导出 {< 服务器 id > [，...n]&#124;所有} < 加密的密码-文件 ><br /><br />-i / 导入 {< 服务器 id > [，...n]&#124;所有} < 加密密码的文件 >|如果指定，此选项不能结合任何其他选项配合使用。<br /><br />服务器 id:为 {string} 的服务器提供唯一 ID<br /><br />服务器连接文件： 服务器定义文件 （serverconnectionfile 或脚本文件）。<br /><br />变量值文件：它是一个变量定义文件，并使用服务器连接文件中。<br /><br />加密密码的文件：它是使用用户指定通行短语加密的服务器的密码文件。|  
|8|-?|否|不适用|不适用|  
  
## <a name="see-also"></a>请参阅  
[执行 SSMA 控制台](https://msdn.microsoft.com/ce63f633-067d-4f04-b8e9-e1abd7ec740b)  
  
