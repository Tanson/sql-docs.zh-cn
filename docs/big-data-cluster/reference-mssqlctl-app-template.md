---
title: mssqlctl 应用模板参考
titleSuffix: SQL Server big data clusters
description: Mssqlctl 应用模板命令的参考文章。
author: rothja
ms.author: jroth
manager: craigg
ms.date: 02/28/2019
ms.topic: reference
ms.prod: sql
ms.technology: big-data-cluster
ms.openlocfilehash: c67ed74750ac36d1a5c79503417414a9dd8ab6b5
ms.sourcegitcommit: 2de5446fbc57787f18a907dd5deb02a7831ec07d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58860098"
---
# <a name="mssqlctl-app-template"></a>mssqlctl 应用模板

[!INCLUDE[tsql-appliesto-ssver15-xxxx-xxxx-xxx](../includes/tsql-appliesto-ssver15-xxxx-xxxx-xxx.md)]

以下文章提供了参考**应用模板**中的命令**mssqlctl**工具。 有关其他详细信息**mssqlctl**命令，请参阅[mssqlctl 引用](reference-mssqlctl.md)。

## <a id="commands"></a> 命令

|||
|---|---|
| [“选择设备” 列表](#list) | 提取支持的模板。 |
| [pull](#pull) | 下载支持的模板。 |

## <a id="list"></a> mssqlctl 应用模板列表

提取支持的模板。

```
mssqlctl app template list
   --url
```

### <a name="parameters"></a>Parameters

| Parameters | Description |
|---|---|
| **--url -u** | 指定不同的模板存储库位置。 默认值： https://github.com/Microsoft/sql-server-samples.git。 |

### <a name="examples"></a>示例

提取默认模板存储库位置下的所有模板。

```
mssqlctl app template list
```

提取不同的存储库位置下的所有模板。

```
mssqlctl app template list --url https://github.com/diffrent/templates.git
```

## <a id="pull"></a> mssqlctl 应用模板请求

下载支持的模板。

```
mssqlctl app template pull
   --destination
   --name
   --url
```

### <a name="parameters"></a>Parameters

| Parameters | Description |
|---|---|
| **--destination -d** | 应用程序框架模板放在何处。  默认值:。 / 模板。 |
| **--name -n** | 模板名称。 有关关闭受支持的模板名称的完整列表运行`mssqlctl app template list`。 |
| **--url -u** | 指定不同的模板存储库位置。 默认值：
https://github.com/Microsoft/sql-server-samples.git 的用户。 |

### <a name="examples"></a>示例

下载默认模板存储库位置下的所有模板。

```
mssqlctl app template pull
```

下载其他存储库位置下的所有模板。

```
mssqlctl app template list --url https://github.com/diffrent/templates.git
```

下载单个模板，按名称。

```
mssqlctl app template pull --name ssis
```

## <a name="next-steps"></a>后续步骤

有关其他详细信息**mssqlctl**命令，请参阅[mssqlctl 引用](reference-mssqlctl.md)。 有关如何安装详细信息**mssqlctl**工具，请参阅[安装 mssqlctl 来管理 SQL Server 2019 大数据群集](deploy-install-mssqlctl.md)。