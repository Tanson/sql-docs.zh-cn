---
title: "转换类型时不进行转换检查（SQL Server 导入和导出向导） | Microsoft Docs"
ms.custom: ""
ms.date: "01/11/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.dts.impexpwizard.nomappingfile.f1"
ms.assetid: 87d9d3e5-477f-4117-a37f-bff53ea3e14d
caps.latest.revision: 25
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 24
---
# 转换类型时不进行转换检查（SQL Server 导入和导出向导）
  选择现有表和视图进行复制或查看提供的查询之后，[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 导入和导出向导可能会显示“转换类型时不进行转换检查”。 当向导找不到在源和目标之间映射数据类型所需的一个或多个数据类型转换和映射文件时，将显示此页。 此页包含的信息可帮助你了解缺少的内容。
  
 在不知道数据类型转换是否会成功的情况下，单击“下一步”继续操作。 否则，请单击“返回”更改选择，或单击“取消”退出向导。
  
 有关向导如何将数据类型从源列映射到目标列以及向导如何使用数据类型映射文件的信息，请参阅[向导如何在源和目标之间映射数据类型？](Import%20and%20Export%20Data%20with%20the%20SQL%20Server%20Import%20and%20Export%20Wizard.md\#wizardMapping)。  

## <a name="screen-shot-of-the-convert-types-page"></a>“转换类型”页的屏幕截图  
  
下面的屏幕截图显示了向导中的“转换类型时不进行转换检查”页的一个示例。

![转换类型](../../integration-services/import-export-data/media/convert-types.png)

此处的问题在于向导找不到映射所选目标的数据类型的映射文件。

此页上的信息不包括缺少的映射文件的名称。 由于该向导不知道用于指定的数据提供程序的文件是否存在，因此不能提供缺少的文件的名称。

## <a name="whats-next"></a>下一步是什么？  
 在不知道数据类型转换是否会成功的情况下，单击“下一步”，下一页是“保存并运行包”。 在此页上，你可以指定是否要立即运行复制操作。 根据你的配置，或许还可以保存向导创建的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 包，以便对其进行自定义并在以后重新使用。 有关详细信息，请参阅[保存并运行包](../../integration-services/import-export-data/save-and-run-package-sql-server-import-and-export-wizard.md)。  