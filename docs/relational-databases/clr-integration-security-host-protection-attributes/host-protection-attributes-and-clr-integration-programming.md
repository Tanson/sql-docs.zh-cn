---
title: "宿主保护特性和 CLR 集成编程 |Microsoft 文档"
ms.custom: 
ms.date: 03/17/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: clr
ms.reviewer: 
ms.suite: sql
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- host protection attributes [CLR integration]
- HostProtectionAttribute [CLR integration]
- common language runtime [SQL Server], host protection attributes
- disallowed types and members [CLR integration]
- common language runtime [SQL Server], disallowed types and members
- HPAs [CLR integration]
ms.assetid: 268078df-63ca-4c03-a8e7-7108bcea9697
caps.latest.revision: "28"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 68732b099e87a8d890d99e35e17bfff3b1452092
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="host-protection-attributes-and-clr-integration-programming"></a>宿主保护属性和 CLR 集成编程
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]公共语言运行时 (CLR) 提供一种机制来批注托管的应用程序编程接口 (Api) 的某些属性的可能感兴趣的主机的 CLR，如.NET Framework 的一部分[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]开头[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]. 这种宿主保护属性 (HPA) 的示例包括：  
  
-   **SharedState**，指示是否的 API 公开的功能，若要创建或管理共享状态 （例如，静态类字段）。  
  
-   **同步**，指示是否的 API 公开执行线程之间的同步的能力。  
  
-   **ExternalProcessMgmt**，指示是否的 API 公开一种方法来控制主机进程。  
  
 在给定这些属性的基础上，[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 可通过代码访问安全性 (CAS) 指定在宿主环境下不允许的 HPA 的列表。 由三个指定的 CA 要求[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]权限集：**安全**， **EXTERNAL_ACCESS**，或**UNSAFE**。 在服务器上，注册程序集时指定这些三种安全级别之一使用**CREATE ASSEMBLY**语句。 代码中执行**安全**或**EXTERNAL_ACCESS**权限集必须避免某些类型或成员有**System.Security.Permissions.HostProtectionAttribute**应用的属性。 有关详细信息，请参阅[创建程序集](../../relational-databases/clr-integration/assemblies/creating-an-assembly.md)和[CLR 集成编程模型限制](../../relational-databases/clr-integration/database-objects/clr-integration-programming-model-restrictions.md)。  
  
 **HostProtectionAttribute**不是安全权限尽可能多的方法来提高可靠性，在于它标识特定的代码构造，类型或方法，主机可能不允许。 使用**HostProtectionAttribute**强制实施一个编程模型，有助于保护主机的稳定性。  
  
## <a name="host-protection-attributes"></a>宿主保护属性  
 HPA 可标识不适合宿主编程模型的类型或成员，并表示可靠性威胁的以下递增级别：  
  
-   在其他方面为良性。  
  
-   可能会导致反序列化服务器托管的用户代码。  
  
-   可能会导致反序列化服务器进程本身。  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]不允许使用类型或成员有**HostProtectionAttribute** ，它指定**System.Security.Permissions.HostProtectionResource**枚举，其中的值**ExternalProcessMgmt**， **ExternalThreading**， **MayLeakOnAbort**， **SecurityInfrastructure**， **SelfAffectingProcessMgmnt**， **SelfAffectingThreading**， **SharedState**，**同步**，或**UI**. 这会阻止程序集调用启用共享状态、执行同步、可能导致终止时资源泄漏或影响 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 进程的完整性的成员。  
  
### <a name="disallowed-types-and-members"></a>不允许的类型和成员  
 以下主题标识类型和成员其**HostProtectionResource**值不允许[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]。  
  
> [!NOTE]  
>  这些主题中的列表是通过受支持的程序集生成的。  有关详细信息，请参阅[支持.NET Framework 库](../../relational-databases/clr-integration/database-objects/supported-net-framework-libraries.md)。  
  
## <a name="in-this-section"></a>本节内容  
 [Microsoft.VisualBasic.dll 中禁用的类型和成员](../../relational-databases/clr-integration-security-host-protection-attributes/disallowed-types-and-members-in-microsoft-visualbasic-dll.md)  
 列出了 Microsoft.VisualBasic.dll 中其 HPA 值被禁用的类型和成员。  
  
 [mscorlib.dll 中禁用的类型和成员](../../relational-databases/clr-integration-security-host-protection-attributes/disallowed-types-and-members-in-mscorlib-dll.md)  
 列出了 mscorlib.dll 中其 HPA 值被禁用的类型和成员。  
  
 [System.dll 中禁用的类型和成员](../../relational-databases/clr-integration-security-host-protection-attributes/disallowed-types-and-members-in-system-dll.md)  
 列出了 System.dll 中其 HPA 值被禁用的类型和成员。  
  
 [System.Data.dll 中禁用的类型和成员](../../relational-databases/clr-integration-security-host-protection-attributes/disallowed-types-and-members-in-system-data-dll.md)  
 列出了 System.Data.dll 中其 HPA 值被禁用的类型和成员。  
  
 [System.Core.dll 中禁用的类型和成员](../../relational-databases/clr-integration-security-host-protection-attributes/disallowed-types-and-members-in-system-core-dll.md)  
 列出了 System.Core.dll 中其 HPA 值被禁用的类型和成员。  
  
## <a name="see-also"></a>另请参阅  
 [CLR Integration Code Access Security](../../relational-databases/clr-integration/security/clr-integration-code-access-security.md)   
 [CLR 集成编程模型限制](../../relational-databases/clr-integration/database-objects/clr-integration-programming-model-restrictions.md)   
 [创建程序集](../../relational-databases/clr-integration/assemblies/creating-an-assembly.md)  
  
  