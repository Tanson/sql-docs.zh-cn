---
title: "PolyBase 查询 | Microsoft Docs"
ms.custom:
- SQL2016_New_Updated
ms.date: 03/09/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine-polybase
ms.tgt_pltfrm: 
ms.topic: article
keywords:
- PolyBase
helpviewer_keywords:
- PolyBase, import and export
- Hadoop, import with PolyBase
- Hadoop, export with PolyBase
- Azure blob storage, import with PolyBase
- Azure blob storage, export with PolyBase
ms.assetid: 2c5aa2bd-af7d-4f57-9a28-9673c2a4c07e
caps.latest.revision: 18
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: d6cc1b4523bdb0b48cfc22b34b205e15613fb290
ms.contentlocale: zh-cn
ms.lasthandoff: 06/22/2017

---
# <a name="polybase-queries"></a>PolyBase Queries
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  以下是使用 SQL Server 2016 [PolyBase 指南](../../relational-databases/polybase/polybase-guide.md) 功能的示例查询。 在使用这些示例之前，你还必须了解安装 PolyBase 所需的 T-SQL 语句（请参阅 [PolyBase T-SQL 对象](../../relational-databases/polybase/polybase-t-sql-objects.md)。）  
  
## <a name="queries"></a>查询  
 对外部表运行 Transact-SQL 语句或使用 BI 工具来查询外部表。  
  
## <a name="select-from-external-table"></a>外部表中的 SELECT  
 从已定义的外部表中返回数据的简单查询。  
  
```tsql  
SELECT TOP 10 * FROM [dbo].[SensorData];   
```  
  
 包含一个谓词的简单查询。  
  
```  
SELECT * FROM [dbo].[SensorData]   
WHERE Speed > 65;   
```  
  
## <a name="join-external-tables-with-local-tables"></a>带有本地表的 JOIN 外部表  
  
```  
SELECT InsuranceCustomers.FirstName,   
                           InsuranceCustomers.LastName,   
                           SensorData.Speed  
FROM InsuranceCustomers INNER JOIN SensorData    
ON InsuranceCustomers.CustomerKey = SensorData.CustomerKey   
WHERE SensorData.Speed > 65   
ORDER BY SensorData.Speed DESC  
  
```  
  
## <a name="pushdown-computation-to-hadoop"></a>将计算下推到 Hadoop  
 下推变体如下所示。  
  
### <a name="pushdown-for-selecting-a-subset-of-rows"></a>用于选择行子集的下推  
 使用谓词下推来提高从外部表中选择行子集的查询的性能。  
  
 此处 SQL Server 2016 启动 map-reduce 作业，以检索与 Hadoop 上的谓词 customer.account_balance < 200000 相匹配的行。 由于查询可以无需扫描表中的所有行就能成功完成，只有满足谓词条件的行才会复制到 SQL Server。 与帐户余额 >= 200000 的客户数相比，余额 < 200000 的客户数是很小的，这样可以节省大量时间，并且需要的临时存储空间更少。  
  复制 imageCopy 代码   
SELECT * FROM customer WHERE customer.account_balance < 200000.  
  
```  
SELECT * FROM SensorData WHERE Speed > 65;  
```  
  
### <a name="pushdown-for-selecting-a-subset-of-columns"></a>用于选择列子集的下推  
 使用谓词下推来提高从外部表中选择列子集的查询的性能。  
  
 在此查询中，SQL Server 启动 map-reduce 作业，以预处理 Hadoop 分隔文本文件，因此只有 customer.name 和 customer.zip_code 这两列的数据将复制到 SQL Server PDW。  
  
```  
SELECT customer.name, customer.zip_code FROM customer WHERE customer.account_balance < 200000  
  
```  
  
### <a name="pushdown-for-basic-expressions-and-operators"></a>基本表达式和运算符的下推  
 SQL Server 允许以下谓词下推的基本表达式和运算符。  
  
-   数字、日期和时间值的二进制比较运算符（\<、>、=、!=、<>、>=、<=）。  
  
-   算术运算符（+、-、*、/、%）。  
  
-   逻辑运算符（AND、OR）。  
  
-   一元运算符（NOT、IS NULL、IS NOT NULL）。  
  
 运算符 BETWEEN、NOT、IN 和 LIKE 可能能够下推。 这取决于查询优化器如何将它们重写为一系列使用基本关系运算符的语句。  
  
 此查询有多个可以下推到 Hadoop 的谓词。 SQL Server 可以将 map-reduce 作业推送到 Hadoop 以执行谓词 customer.account_balance <= 200000。 表达式 “BETWEEN 92656 and 92677” 由可以推送到 Hadoop 的二进制和逻辑运算符组成。 customer.account_balance customer.zipcode 的逻辑 AND 是最终的表达式。  
  
 把它们放在一起，map-reduce 作业可以执行所有的 WHERE 子句。 只有符合 SELECT 条件的数据才会复制回 SQL Server PDW。  
  
```  
SELECT * FROM customer WHERE customer.account_balance <= 200000 AND customer.zipcode BETWEEN 92656 AND 92677  
  
```  
  
### <a name="force-pushdown"></a>强制下推  
  
```  
SELECT * FROM [dbo].[SensorData]   
WHERE Speed > 65  
OPTION (FORCE EXTERNALPUSHDOWN);   
```  
  
### <a name="disable-pushdown"></a>禁用下推  
  
```  
SELECT * FROM [dbo].[SensorData]   
WHERE Speed > 65  
OPTION (DISABLE EXTERNALPUSHDOWN);  
```  
  
## <a name="import-data"></a>导入数据  
 从 Hadoop 或 Azure 存储空间将数据导入到 SQL Server 进行永久存储。 使用 SELECT INTO 导入外部表所引用的数据以在 SQL Server 中进行永久存储。 动态创建关系表，然后在第二步中创建基于该表的列存储索引。  
  
```sql  
-- PolyBase Scenario 2: Import external data into SQL Server.  
-- Import data for fast drivers into SQL Server to do more in-depth analysis and  
-- leverage Columnstore technology.  
  
SELECT DISTINCT   
        Insured_Customers.FirstName, Insured_Customers.LastName,   
        Insured_Customers.YearlyIncome, Insured_Customers.MaritalStatus  
INTO Fast_Customers from Insured_Customers INNER JOIN   
(  
        SELECT * FROM CarSensor_Data where Speed > 35   
) AS SensorD  
ON Insured_Customers.CustomerKey = SensorD.CustomerKey  
ORDER BY YearlyIncome  
  
CREATE CLUSTERED COLUMNSTORE INDEX CCI_FastCustomers ON Fast_Customers;  
```  
  
## <a name="export-data"></a>导出数据  
将数据从 SQL Server 导出到 Hadoop 或 Azure 存储空间。 首先，通过将“允许 polybase 导出”的sp_configure 值设置为 1，启用导出功能。 然后，创建一个指向目标目录的外部表。 然后，使用 INSERT INTO 将数据从本地 SQL Server 表导出到外部数据源。 INSERT INTO 语句将创建目标目录（如果不存在），而 SELECT 语句的结果将以指定的文件格式导出到指定位置。 外部文件被命名为 *QueryID_date_time_ID.format*，其中 *ID* 是增量标识符， *format* 是导出的数据格式。 例如，QID776_20160130_182739_0.orc。  
  
```sql  
-- PolyBase Scenario 3: Export data from SQL Server to Hadoop.  
-- Create an external table.   
CREATE EXTERNAL TABLE [dbo].[FastCustomers2009] (  
        [FirstName] char(25) NOT NULL,   
        [LastName] char(25) NOT NULL,   
        [YearlyIncome] float NULL,   
        [MaritalStatus] char(1) NOT NULL  
)  
WITH (  
        LOCATION='/old_data/2009/customerdata',  
        DATA_SOURCE = HadoopHDP2,  
        FILE_FORMAT = TextFileFormat,  
        REJECT_TYPE = VALUE,  
        REJECT_VALUE = 0  
);  
  
-- Export data: Move old data to Hadoop while keeping it query-able via an external table.  
INSERT INTO dbo.FastCustomer2009  
SELECT T.* FROM Insured_Customers T1 JOIN CarSensor_Data T2  
ON (T1.CustomerKey = T2.CustomerKey)  
WHERE T2.YearMeasured = 2009 and T2.Speed > 40;  
```  
  
## <a name="new-catalog-views"></a>新目录视图  
 下面的新目录视图显示外部资源。  
  
```sql  
SELECT * FROM sys.external_data_sources;   
SELECT * FROM sys.external_file_formats;  
SELECT * FROM sys.external_tables;  
```  
  
 使用 `is_external`  
  
```sql  
SELECT name, type, is_external FROM sys.tables WHERE name='myTableName'   
```  
  
## <a name="next-steps"></a>后续步骤  
 若要了解有关故障排除的详细信息，请参阅 [PolyBase 故障排除](../../relational-databases/polybase/polybase-troubleshooting.md)。  
  
  
