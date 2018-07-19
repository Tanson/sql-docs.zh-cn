---
title: Web 配置参考 (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- web configuration file [Master Data Services]
ms.assetid: b8cc9a35-97ab-4fe0-ab4b-c07f13d9793a
caps.latest.revision: 5
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 9c345312ddadab6c5efd689d36f36f09cc2d0a41
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37250217"
---
# <a name="web-configuration-reference-master-data-services"></a>Web 配置参考 (Master Data Services)
  [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 使用 Web.config 文件来包含使 Internet Information Services (IIS) 能够承载 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] Web 应用程序和 Web 服务的配置设置。 此 Web.config 文件位于 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 安装路径的 WebApplication 文件夹。 有关路径和权限的详细信息，请参阅[文件夹和文件权限 (Master Data Services)](folder-and-file-permissions-master-data-services.md)。  
  
## <a name="webconfig-elements"></a>Web.Config 元素  
 Web.config 文件除了包含标准的 IIS、.NET Framework、ASP.NET 和 Windows Communication Foundation (WCF) 配置元素外，还包含一个自定义 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 元素 “<masterDataServices\<”。 下表描述了 Web.config 文件中包括的元素。  
  
|配置元素|Description|  
|---------------------------|-----------------|  
|`masterDataServices`|自定义元素。 将 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Web 服务连接到 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 数据库。|  
|`connectionStrings`|ASP.NET 元素。 有关详细信息，请参阅 MSDN Library 中的 [connectionStrings 元素（ASP.NET 设置架构）](http://go.microsoft.com/fwlink/?LinkId=178347) 。|  
|`system.web`|ASP.NET 元素。 有关详细信息，请参阅 MSDN Library 中的 [system.web 元素（ASP.NET 设置架构）](http://go.microsoft.com/fwlink/?LinkId=178348) 。|  
|`startup`|.NET Framework 元素。 有关详细信息，请参阅 MSDN Library 中的 [\<startup> 元素](http://go.microsoft.com/fwlink/?LinkId=178349)。|  
|`runtime`|.NET Framework 元素。 有关详细信息，请参阅 MSDN Library 中的 [runtime> 元素\<](http://go.microsoft.com/fwlink/?LinkId=178350)。|  
|`system.codedom`|.NET Framework 元素。 有关详细信息，请参阅 MSDN Library 中的 [\<system.codedom> 元素](http://go.microsoft.com/fwlink/?LinkId=178351)。|  
|`system.web.extensions`|ASP.NET 元素。 有关详细信息，请参阅 MSDN Library 中的 [system.web.extensions 元素（ASP.NET 设置架构）](http://go.microsoft.com/fwlink/?LinkId=178352) 。|  
|`system.webServer`|包含 IIS 元素的节组。 有关详细信息，请参阅 MSDN Library 中的 [system.webServer 节组 \[IIS 7 设置架构\]](http://go.microsoft.com/fwlink/?LinkId=178353)。|  
|`system.serviceModel`|WCF 元素。 有关详细信息，请参阅 MSDN Library 中的 [\<system.serviceModel>](http://go.microsoft.com/fwlink/?LinkId=178354)。|  
|`system.diagnostics`|.NET Framework 元素。 有关详细信息，请参阅 MSDN Library 中的 [\<system.diagnostics> 元素](http://go.microsoft.com/fwlink/?LinkId=178355)。|  
|`appSettings`|ASP.NET 元素。 有关详细信息，请参阅 MSDN Library 中的 [appSettings 元素（常规设置架构）](http://go.microsoft.com/fwlink/?LinkId=178356) 。|  
  
## <a name="masterdataservices-element"></a>masterDataServices 元素  
 <masterDataServices\< 元素是自定义元素，用于将 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Web 服务连接到 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 数据库。  
  
### <a name="syntax"></a>语法  
  
```  
<masterDataServices>  
   <instance virtualPath="path" siteName="name" connectionName="name" serviceName="name" />  
</masterDataServices>  
```  
  
### <a name="elements-and-attributes"></a>元素和属性  
  
|项|Description|  
|----------|-----------------|  
|`instance`|子元素。 包含指定 Web 服务和数据库连接字符串信息的属性。|  
|`virtualPath`|属性。 指定 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] Web 应用程序和服务的虚拟路径。 这对应于`path`的属性**\<应用程序 >** 元素下的**\<站点 >** IIS ApplicationHost.config 文件中的元素。|  
|`siteName`|属性。 指定承载 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] Web 应用程序和服务的站点的名称。 这对应于`name`的属性**\<站点 >** 元素下的**\<站点 >** IIS ApplicationHost.config 文件中。|  
|`connectionName`|属性。 指定要使用的连接的名称。 这对应于`name`的属性**\<添加 >** 元素下的 **\<connectionStrings >** 在 Web.config 中的元素。|  
|`serviceName`|属性。 指定 Web 服务的名称。 这对应于`name`的属性**\<服务 >** 元素下的**\<服务 >** 在 Web.config 中的元素。|  
  
### <a name="example"></a>示例  
 下面的示例演示了 Contoso 站点上一个名为 MDS1 的服务和使用由 MDSDB 指定的连接字符串的 /MDS 路径。  
  
```  
<masterDataServices>  
   <instance virtualPath="/MDS" siteName="Contoso" connectionName="MDSDB" serviceName="MDS1" />  
</masterDataServices>  
```  
  
  