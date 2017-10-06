---
title: "在 SQL Server 和 Azure SQL 数据库中导入和导出数据 | Microsoft Docs"
ms.custom: 
ms.date: 09/12/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.translationtype: HT
ms.sourcegitcommit: 6e754198cf82a7ba0752fe8f20c3780a8ac551d7
ms.openlocfilehash: 3c41be0642b13b63367c5601b716b506808472e7
ms.contentlocale: zh-cn
ms.lasthandoff: 09/14/2017

---
# <a name="import-and-export-data-from-sql-server-and-azure-sql-database"></a>在 SQL Server 和 Azure SQL 数据库中导入和导出数据
可通过多种方法将数据导入 SQL Server 和 Azure SQL 数据库，以及从 SQL Server 和 Azure SQL 数据库中导出数据。 这些方法包括 Transact-SQL 语句、命令行工具和向导。

也可以各种数据格式导入和导出数据。 这些格式包括平面文件、Excel、主要关系数据库和各种云服务。

## <a name="methods-for-importing-and-exporting-data"></a>导入和导出数据的方法

### <a name="use-transact-sql-statements"></a>使用 Transact-SQL 语句
可以使用 `BULK INSERT` 或 `OPENROWSET(BULK...)` 命令导入数据。 通常在 SQL Server Management Studio (SSMS) 中运行这些命令。 有关详细信息，请参阅[使用 BULK INSERT 或 OPENROWSET(BULK...) 导入批量数据](import-bulk-data-by-using-bulk-insert-or-openrowset-bulk-sql-server.md)。

### <a name="use-bcp-from-the-command-prompt"></a>从命令提示符使用 BCP
可使用 BCP 命令行实用工具导入和导出数据。 有关详细信息，请参阅[使用 BCP 实用工具导入和导出批量数据](import-bulk-data-by-using-bulk-insert-or-openrowset-bulk-sql-server.md)。

### <a name="use-the-sql-server-import-and-export-wizard"></a>使用 SQL Server 导入和导出向导
可使用 SQL Server 导入和导出向导将数据导入各种源和目标，或从其中导出数据。 要使用向导，必须安装 SQL Server Integration Services (SSIS) 或 SQL Server Data Tools (SSDT)。 有关详细信息，请参阅[使用 SQL Server 导入和导出向导导入和导出数据](../../integration-services/import-export-data/import-and-export-data-with-the-sql-server-import-and-export-wizard.md)。

### <a name="design-your-own-import-or-export"></a>设计自己的导入或导出
如果想要设计自定义数据导入，可使用以下功能或服务中的一项：
-   SQL Server Integration Services。 有关详细信息，请参阅 [SQL Server Integration Services](../../integration-services/sql-server-integration-services.md)。
-   Azure 数据工厂。 有关详细信息，请参阅 [Azure 数据工厂简介](https://docs.microsoft.com/azure/data-factory/data-factory-introduction)。

## <a name="data-formats-for-import-and-export"></a>导入和导出的数据格式

### <a name="supported-formats"></a>支持的格式

可使用多种格式导入和导出数据，包括平面文件或多种其他文件格式、关系数据库和云服务。 要详细了解特定工具的这些选项，请参阅以下主题
-   对于 SQL Server 导入和导出向导，请参阅[使用 SQL Server 导入和导出向导连接到数据源](../../integration-services/import-export-data/connect-to-data-sources-with-the-sql-server-import-and-export-wizard.md)。
-   对于 SQL Server Integration Services，请参阅 [Integration Services (SSIS) 连接](../../integration-services/connection-manager/integration-services-ssis-connections.md)。
-   对于 Azure 数据工厂，请参阅 [Azure 数据工厂连接器](https://docs.microsoft.com/en-us/azure/data-factory/data-factory-amazon-redshift-connector)。

### <a name="commonly-used-data-formats"></a>常用的数据格式

某些常用的数据格式具有特殊的注意事项和示例。 要了解有关这些数据格式的详细信息，请参阅以下主题：
-   对于 Excel，请参阅[从 Excel 导入](import-data-from-excel-to-sql.md)。
-   对于 JSON，请参阅[导入 JSON 文档](../json/import-json-documents-into-sql-server.md)。
-   对于 XML，请参阅[导入和导出 XML 文档](examples-of-bulk-import-and-export-of-xml-documents-sql-server.md)。
-   对于 Azure Blob 存储，请参阅[从 Azure Blob 存储导入和导出](examples-of-bulk-access-to-data-in-azure-blob-storage.md)。

## <a name="next-steps"></a>后续步骤
如果不确定从何处开始进行导入或导出任务，请考虑使用 SQL Server 导入和导出向导。 有关快速说明，请参阅[导入和导出向导的简单示例入门](../../integration-services/import-export-data/get-started-with-this-simple-example-of-the-import-and-export-wizard.md)。
