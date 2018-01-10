---
title: "sp_foreignkeys (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sp_foreignkeys_TSQL
- sp_foreignkeys
dev_langs: TSQL
helpviewer_keywords: sp_foreignkeys
ms.assetid: 935fe385-19ff-41a4-8d0b-30618966991d
caps.latest.revision: "39"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 248113fe68932f385203b067d77afad506fabbdf
ms.sourcegitcommit: 9fbe5403e902eb996bab0b1285cdade281c1cb16
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2017
---
# <a name="spforeignkeys-transact-sql"></a>sp_foreignkeys (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  返回引用链接服务器中的表的主键的外键。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
sp_foreignkeys [ @table_server = ] 'table_server'   
     [ , [ @pktab_name = ] 'pktab_name' ]   
     [ , [ @pktab_schema = ] 'pktab_schema' ]   
     [ , [ @pktab_catalog = ] 'pktab_catalog' ]   
     [ , [ @fktab_name = ] 'fktab_name' ]   
     [ , [ @fktab_schema = ] 'fktab_schema' ]   
     [ , [ @fktab_catalog = ] 'fktab_catalog' ]  
```  
  
## <a name="arguments"></a>参数  
 [  **@table_server =** ] *table_server*  
 要为其返回表信息的链接服务器的名称。 *table_server*是**sysname**，无默认值。  
  
 [  **@pktab_name =** ] *pktab_name*  
 包含主键的表的名称。 *pktab_name*是**sysname**，默认值为 NULL。  
  
 [  **@pktab_schema =** ] *pktab_schema*  
 包含主键的架构的名称。 *pktab_schema*是**sysname**，默认值为 NULL。 在 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 中，该名称包含所有者名称。  
  
 [  **@pktab_catalog =** ] *pktab_catalog*  
 包含主键的目录的名称。 *pktab_catalog*是**sysname**，默认值为 NULL。 在 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 中，该名称包含数据库名称。  
  
 [  **@fktab_name =** ] *fktab_name*  
 是具有外键的名称。 *fktab_name*是**sysname**，默认值为 NULL。  
  
 [  **@fktab_schema =** ] *fktab_schema*  
 包含外键的架构的名称。 *fktab_schema*是**sysname**，默认值为 NULL。  
  
 [  **@fktab_catalog =** ] *fktab_catalog*  
 包含外键的目录的名称。 *fktab_catalog*是**sysname**，默认值为 NULL。  
  
## <a name="return-code-values"></a>返回代码值  
 无  
  
## <a name="result-sets"></a>结果集  
 各种 DBMS 产品支持三部分命名表 (*目录***。***架构***。***表*)，这表示在结果集中。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**PKTABLE_CAT**|**sysname**|主键所在表的目录。|  
|**PKTABLE_SCHEM**|**sysname**|主键所在表的架构。|  
|**PKTABLE_NAME**|**sysname**|（带有主键） 的表的名称。 此字段始终返回值。|  
|**PKCOLUMN_NAME**|**sysname**|主键列或列，每个列名称的**TABLE_NAME**返回。 此字段始终返回值。|  
|**FKTABLE_CAT**|**sysname**|外键所在表的目录。|  
|**FKTABLE_SCHEM**|**sysname**|外键所在表的架构。|  
|**FKTABLE_NAME**|**sysname**|（带有外键） 表的名称。 此字段始终返回值。|  
|**FKCOLUMN_NAME**|**sysname**|返回的外键列，TABLE_NAME 的每一列的名称。 此字段始终返回值。|  
|**KEY_SEQ**|**int**|多列主键中列的序列号。 此字段始终返回值。|  
|**UPDATE_RULE**|**int**|当 SQL 操作是更新操作时应用于外键的操作。 对于这些列，[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 将返回 0、1 或 2：<br /><br /> 0=对外键的 CASCADE 更改。<br /><br /> 1=NO ACTION 更改（如果有外键）。<br /><br /> 2=SET_NULL；将外键设置为 NULL。|  
|**DELETE_RULE**|**int**|当 SQL 操作是删除操作时应用于外键的操作。 对于这些列，[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 将返回 0、1 或 2：<br /><br /> 0=对外键的 CASCADE 更改。<br /><br /> 1=NO ACTION 更改（如果有外键）。<br /><br /> 2=SET_NULL；将外键设置为 NULL。|  
|**FK_NAME**|**sysname**|外键标识符。 如果不适用于数据源，则为 NULL。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 将返回 FOREIGN KEY 约束名称。|  
|**PK_NAME**|**sysname**|主键标识符。 如果不适用于数据源，则为 NULL。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 将返回 PRIMARY KEY 约束名称。|  
|**延迟**|**int**|指示是否可延迟约束检查。|  
  
 在结果集中，FK_NAME 和 PK_NAME 列总是返回 NULL。  
  
## <a name="remarks"></a>注释  
 **sp_foreignkeys**查询 FOREIGN_KEYS 行集**IDBSchemaRowset**对应的 OLE DB 访问接口的接口*table_server*。 *Table_name*， *table_schema*， *table_catalog*，和*列*参数传递给此接口可限制的行返回。  
  
## <a name="permissions"></a>Permissions  
 需要对架构的 SELECT 权限。  
  
## <a name="examples"></a>示例  
 下面的示例返回有关链接服务器 `Department` 上 [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] 数据库中的 `Seattle1` 表中的外键的信息。  
  
```  
EXEC sp_foreignkeys @table_server = N'Seattle1',   
   @pktab_name = N'Department',   
   @pktab_catalog = N'AdventureWorks2012';  
```  
  
## <a name="see-also"></a>另请参阅  
 [sp_catalogs &#40;Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-catalogs-transact-sql.md)   
 [sp_column_privileges &#40;Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-column-privileges-transact-sql.md)   
 [sp_indexes &#40;Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-indexes-transact-sql.md)   
 [sp_linkedservers (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-linkedservers-transact-sql.md)   
 [sp_primarykeys &#40;Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-primarykeys-transact-sql.md)   
 [sp_tables_ex &#40;Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-tables-ex-transact-sql.md)   
 [sp_table_privileges &#40;Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-table-privileges-transact-sql.md)   
 [系统存储过程 (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  