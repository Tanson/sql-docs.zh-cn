---
title: 下载 SQL Server Management Studio (SSMS) | Microsoft Docs
ms.custom: ''
ms.date: 03/29/2019
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: sstein
ms.technology: ssms
ms.topic: conceptual
keywords:
- 安装 SSMS，下载 SSMS，最新的 SSMS
- SQL Server Management Studio
- ssms.exe
- sql man studio
- sql management studio
- SQL Management Studio 安装
- 下载 SQL Management Studio
- MS SQL Management Studio
- 安装 SQL Management Studio
- ssms download
- sql server ssms
- ssms express
ms.assetid: adafeeef-4255-4924-8042-02f503d599ca
author: dnethi
ms.author: dinethi
manager: craigg
ms.openlocfilehash: 9bc678f69df60ec07e1cca6eddbb337aab8ed8ff
ms.sourcegitcommit: 3cfedfeba377560d460ca3e42af1e18824988c07
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2019
ms.locfileid: "59042024"
---
# <a name="download-sql-server-management-studio-ssms"></a>下载 SQL Server Management Studio (SSMS)
[!INCLUDE[appliesto-ss-asdb-asdw-xxx-md](../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

SQL Server Management Studio (SSMS) 是一种集成环境，用于管理从 SQL Server 到 Azure SQL 数据库的任何 SQL 基础结构。 SSMS 提供用于配置、监视和管理 SQL Server 和数据库实例的工具。 使用 SSMS 部署、监视和升级应用程序使用的数据层组件，以及生成查询和脚本。

使用 SSMS 在本地计算机或云端查询、设计和管理数据库及数据仓库，无论它们位于何处。

SSMS 是免费的！

[SSMS 18.0 候选发布 1 (RC1) 现已推出](#ssms-180-rc1)，它是为 [!INCLUDE[sql-server-2019](../includes/sssqlv15-md.md)] 提供支持的最新一代 SQL Server Management Studio。

## <a name="ssms-1791-is-the-current-general-availability-ga-version-of-ssms"></a>SSMS 17.9 1 是当前 SSMS 的正式发布 (GA) 版本

[![d下载](../ssdt/media/download.png) 下载 SQL Server Management Studio 17.9.1](https://go.microsoft.com/fwlink/?linkid=2043154)

[![d下载](../ssdt/media/download.png) 下载 SQL Server Management Studio 17.9.1 升级包（将 17.x 升级到 17.9.1）](https://go.microsoft.com/fwlink/?linkid=2043430)

**版本信息**

- 版本号：17.9.1<br>
- 生成号：14.0.17289.0<br>
- 发布日期：2018 年 11 月 21 日

### <a name="available-languages-ssms-1791"></a>可用语言 (SSMS 17.9.1)

> [!NOTE]
> 如果安装在以下平台中，非英语本地化版本的 SSMS 17.x 需要 [KB 2862966 安全更新程序包](https://support.microsoft.com/kb/2862966)：Windows 8、Windows 7、Windows Server 2012 和 Windows Server 2008 R2。

[中文（中国）](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x804) | [中文（繁体）](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x404) | [英语（美国）](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x409) | [法语](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x40c) | [德语](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x407) | [意大利语](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x410) | [日语](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x411) | [朝鲜语](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x412) | [葡萄牙语（巴西）](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x416) | [俄语](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x419) | [西班牙语](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x40a)

有关 SSMS 17.9.1 的其他详细信息，请参阅 [SSMS 17.9.1 更改日志](release-notes-ssms.md#1791-latest-ga-release)。

## <a name="ssms-installation-tips-and-issues-ssms-1791"></a>SSMS 安装提示和问题 (SSMS 17.9.1)

### <a name="minimize-installation-reboots"></a>尽量减少安装重启的次数

* 执行以下操作以降低 SSMS 安装程序在安装结束时需要重新启动的可能性：
  * 请确保运行的是最新版 Visual C++ 2013 Redistributable Package。 需要版本 12.0.40649.5（或更高版本）。 仅需要版本 x64。
  * 验证计算机上的 .NET Framework 版本是否为 4.6.1（或更高版本）。
  * 关闭计算机上打开的所有 Visual Studio 实例。
  * 请确保计算机上已安装所有最新 OS 更新。
  * 所提及的操作通常只需执行一次。 有几种情况需要在额外升级到 SSMS 的同一主版本期间重新启动。 对于次要升级，计算机上已安装 SSMS 的所有先决条件。

## <a name="ssms-180-rc1"></a>SSMS 18.0 (RC1)

**SSMS 18.0 候选发布 1 (RC1) 现已推出，它是为 [!INCLUDE[sql-server-2019](../includes/sssqlv15-md.md)] 提供支持的最新一代 SQL Server Management Studio！**

**[![dow下载](../ssdt/media/download.png) 下载 SQL Server Management Studio 18.0 (RC1)](https://go.microsoft.com/fwlink/?linkid=2085742)**

RC1 是 SSMS 18.0 的最新公共预览版。 如果安装了以前的 SSMS 18.0 预览版，请在安装 SSMS 18.0 RC1 之前将其卸载。

**版本信息**

- 版本号：18.0 (RC1)<br>
- 生成号：15.0.18098.0<br>
- 发布日期：2019 年 3 月 28 日

如果你有意见或建议，或想报告问题，最好是通过 [UserVoice](https://aka.ms/sqlfeedback) 与 SSMS 团队取得联系。

SSMS 18.x 安装不会升级或替换 SSMS 17.x 或更早版本。 SSMS 18.x 与以前的版本并行安装，因此，这两个版本均可供使用。

如果计算机包含 SSMS 的并行安装，请验证你是否针对特定需求启动相应的版本。 最新版本标记为 Microsoft SQL Server Management Studio 18：
 
## <a name="available-languages-ssms-180-rc1"></a>可用语言 (SSMS 18.0 RC1)

此版本的 SSMS 可以安装在以下语言中：

SQL Server Management Studio 18.0 (RC1)：<br>
[中文（中国）](https://go.microsoft.com/fwlink/?linkid=2085742&clcid=0x804) | [中文（繁体）](https://go.microsoft.com/fwlink/?linkid=2085742&clcid=0x404) | [英语（美国）](https://go.microsoft.com/fwlink/?linkid=2085742&clcid=0x409) | [法语](https://go.microsoft.com/fwlink/?linkid=2085742&clcid=0x40c) | [德语](https://go.microsoft.com/fwlink/?linkid=2085742&clcid=0x407) | [意大利语](https://go.microsoft.com/fwlink/?linkid=2085742&clcid=0x410) | [日语](https://go.microsoft.com/fwlink/?linkid=2085742&clcid=0x411) | [朝鲜语](https://go.microsoft.com/fwlink/?linkid=2085742&clcid=0x412) | [葡萄牙语（巴西）](https://go.microsoft.com/fwlink/?linkid=2085742&clcid=0x416) | [俄语](https://go.microsoft.com/fwlink/?linkid=2085742&clcid=0x419) | [西班牙语](https://go.microsoft.com/fwlink/?linkid=2085742&clcid=0x40a)

SQL Server Management Studio 18.0 升级包（升级到 18.0）：<br>
此时没有可用的升级选项。 如果安装了以前的 SSMS 18.0 预览版，请在安装 SSMS 18.0 RC1 之前将其卸载。

> [!NOTE]
> SQL Server PowerShell 模块可通过 PowerShell 库单独安装。 有关详细信息，请参阅[下载 SQL Server PowerShell 模块](download-sql-server-ps-module.md)。

## <a name="new-in-this-release-ssms-180-rc1"></a>此版本 (SSMS 18.0 RC1) 中的新增功能

SSMS 18.0 (RC1) 是最新版本的 SQL Server Management Studio。 SSMS 的 18.x 一代提供对 SQL Server 2008 到 SQL Server 2019 预览版几乎所有功能领域的支持。

有关此版本中新增功能的详细信息，请参阅 [SSMS 发行说明](release-notes-ssms.md)。

## <a name="supported-sql-offerings-ssms-180-rc1"></a>受支持的 SQL 产品/服务 (SSMS 18.0 RC1)

* 此版本的 SSMS 适用于所有[受支持 SQL Server 2008 - [!INCLUDE[sql-server-2019](../includes/sssqlv15-md.md)]](https://support.microsoft.com/lifecycle?C2=1044)，并且在最大程度上支持与 Azure SQL 数据库和 Azure SQL 数据仓库中的最新云功能配合使用。
* 此外，SSMS 18.x 可与 SSMS 17.x、SSMS 16.x 或 SQL Server 2014 SSMS 及早期版本并行安装。
* SQL Server Integration Services (SSIS) - SSMS 版本 17.x 或更高版本不支持连接到旧版 SQL Server Integration Services 服务。 要连接到早期版本的 Integration Services，请使用与 SQL Server 版本一致的 SSMS 版本。 例如，使用 SSMS 16.x 连接到旧版 SQL Server 2016 Integration Services 服务。 可以在同一台计算机上并行安装 SSMS 17.x 和 SSMS 16.x。 由于 SQL Server 2012 的发布，建议使用 SSIS 目录数据库 (SSISDB) 来存储、管理、运行和监视 Integration Services 包。 有关详细信息，请参阅 [SSIS 目录](../integration-services/catalog/ssis-catalog.md)。

## <a name="supported-operating-systems-ssms-180-rc1"></a>受支持的操作系统 (SSMS 18.0 RC1)

与最新可用的服务包一起使用时，此版本的 SSMS 支持以下 64 位平台：

- Windows 10（64 位）<sup>*</sup>
- Windows Server 2016 <sup>*</sup>
- Windows Server 2012 R2（64 位）
- Windows Server 2012（64 位）
- Windows Server 2008 R2（64 位）

<sup>*</sup> 需要版本 1607 (10.0.14939) 或更高版本

> [!NOTE]
> SSMS 仅在 Windows 上运行。 如果需要在 Windows 以外的平台上运行的工具，请查看 Azure Data Studio。 Azure Data Studio 是一个全新的跨平台工具，可在 macOS、Linux 以及 Windows 上运行。 有关详细信息，请参阅 [Azure Data Studio](../azure-data-studio/what-is.md)。
  
## <a name="release-notes-ssms-180-rc1"></a>发行说明 (SSMS 18.0 RC1)

N/A

## <a name="previous-releases"></a>以前的版本

[以前的 SQL Server Management Studio 版本](../ssms/release-notes-ssms.md#previous-ssms-releases)

## <a name="feedback"></a>反馈

![needhelp_person_icon](../ssms/media/needhelp_person_icon.png) [SQL 客户端工具论坛](https://social.msdn.microsoft.com/Forums/home?forum=sqltools)

[!INCLUDE[get-help-options](../includes/paragraph-content/get-help-options.md)]

## <a name="see-also"></a>另请参阅

- [教程：SQL Server Management Studio](tutorials/tutorial-sql-server-management-studio.md)
- [SQL Server Management Studio 文档](sql-server-management-studio-ssms.md)
- [其他更新和 Service Pack](https://technet.microsoft.com/sqlserver/ff803383.aspx)
- [下载 SQL Server Data Tools (SSDT)](../ssdt/download-sql-server-data-tools-ssdt.md)

[!INCLUDE[contribute-to-content](../includes/paragraph-content/contribute-to-content.md)]

如果你有意见或建议，或想报告问题，最好是通过 [UserVoice](https://aka.ms/sqlfeedback) 与 SSMS 团队取得联系。
