---
title: "脚本 |Microsoft 文档"
ms.custom: 
ms.date: 08/06/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: smo
ms.reviewer: 
ms.suite: sql
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- dependencies [SMO]
- scripts [SMO]
ms.assetid: 13a35511-3987-426b-a3b7-3b2e83900dc7
caps.latest.revision: "43"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: e3e98e7685b68b81a5dd586cdb92529456b3c935
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="scripting"></a>脚本编写
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]在 SMO 中编写脚本由控制<xref:Microsoft.SqlServer.Management.Smo.Scripter>对象及其子对象，或**脚本**能在单个对象的方法。 <xref:Microsoft.SqlServer.Management.Smo.Scripter>对象控制外针对的实例上的对象的依赖关系映射[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]。  
  
 使用 <xref:Microsoft.SqlServer.Management.Smo.Scripter> 对象及其子对象进行的高级脚本撰写是一个由三个阶段组成的过程：  
  
1.  发现  
  
2.  生成列表  
  
3.  脚本生成  
  
 发现阶段使用 <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker> 对象。 如果给定对象的 URN 列表，则 <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.DiscoverDependencies%2A> 对象的 <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker> 方法将为该 URN 列表中的对象返回 <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> 对象。 布尔值*fParents*参数用于选择父项或指定的对象的子级是要发现。 在此阶段可以修改依赖关系树。  
  
 在生成列表阶段，会传入该树并返回生成的列表。 此对象列表是按脚本撰写顺序排列的，可以对其进行操作。  
  
 生成列表阶段使用 <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.WalkDependencies%2A> 方法返回 <xref:Microsoft.SqlServer.Management.Smo.DependencyTree>。 在此阶段可以修改 <xref:Microsoft.SqlServer.Management.Smo.DependencyTree>。  
  
 第三阶段也是最后一个阶段，在此阶段中，使用指定的列表和脚本撰写选项生成脚本。 结果以 <xref:System.Collections.Specialized.StringCollection> 系统对象的形式返回。 在此阶段中，接下来会从 <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> 对象和属性（如 <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.NumberOfSiblings%2A> 和 <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.FirstChild%2A>）的项集合中提取依赖对象的名称。  
  
## <a name="example"></a>示例  
 若要使用所提供的任何代码示例，您必须选择创建应用程序所需的编程环境、编程模板和编程语言。 有关详细信息，请参阅[创建 Visual C &#35;Visual Studio.NET 中的 SMO 项目](../../../relational-databases/server-management-objects-smo/how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md)。  
  
 此代码示例需要**导入**System.Collections.Specialized 命名空间的语句。 请将此语句与其他 Imports 语句一同插入在应用程序中的任何声明代码前。  
  
```  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Common  
Imports System.Collections.Specialized  
```  
  
## <a name="scripting-out-the-dependencies-for-a-database-in-visual-basic"></a>在 Visual Basic 中撰写数据库依赖项的脚本  
 此代码示例说明如何发现依赖项并循环访问列表以显示结果。  
  
```  
' compile with:   
' /r:Microsoft.SqlServer.Smo.dll   
' /r:Microsoft.SqlServer.ConnectionInfo.dll   
' /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Sdk.Sfc  
  
Public Class A  
   Public Shared Sub Main()  
      ' database name  
      Dim dbName As [String] = "AdventureWorksLT2012"   ' database name  
  
      ' Connect to the local, default instance of SQL Server.   
      Dim srv As New Server()  
  
      ' Reference the database.    
      Dim db As Database = srv.Databases(dbName)  
  
      ' Define a Scripter object and set the required scripting options.   
      Dim scrp As New Scripter(srv)  
      scrp.Options.ScriptDrops = False  
      scrp.Options.WithDependencies = True  
      scrp.Options.Indexes = True   ' To include indexes  
      scrp.Options.DriAllConstraints = True   ' to include referential constraints in the script  
  
      ' Iterate through the tables in database and script each one. Display the script.  
      For Each tb As Table In db.Tables  
         ' check if the table is not a system table  
         If tb.IsSystemObject = False Then  
            Console.WriteLine("-- Scripting for table " + tb.Name)  
  
            ' Generating script for table tb  
            Dim sc As System.Collections.Specialized.StringCollection = scrp.Script(New Urn() {tb.Urn})  
            For Each st As String In sc  
               Console.WriteLine(st)  
            Next  
            Console.WriteLine("--")  
         End If  
      Next  
   End Sub  
End Class  
```  
  
## <a name="scripting-out-the-dependencies-for-a-database-in-visual-c"></a>在 Visual C# 中撰写数据库依赖项的脚本  
 此代码示例说明如何发现依赖项并循环访问列表以显示结果。  
  
```  
// compile with:   
// /r:Microsoft.SqlServer.Smo.dll   
// /r:Microsoft.SqlServer.ConnectionInfo.dll   
// /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
using System;  
using Microsoft.SqlServer.Management.Smo;  
using Microsoft.SqlServer.Management.Sdk.Sfc;  
  
public class A {  
   public static void Main() {   
      String dbName = "AdventureWorksLT2012"; // database name  
  
      // Connect to the local, default instance of SQL Server.   
      Server srv = new Server();  
  
      // Reference the database.    
      Database db = srv.Databases[dbName];  
  
      // Define a Scripter object and set the required scripting options.   
      Scripter scrp = new Scripter(srv);  
      scrp.Options.ScriptDrops = false;  
      scrp.Options.WithDependencies = true;  
      scrp.Options.Indexes = true;   // To include indexes  
      scrp.Options.DriAllConstraints = true;   // to include referential constraints in the script  
  
      // Iterate through the tables in database and script each one. Display the script.     
      foreach (Table tb in db.Tables) {   
         // check if the table is not a system table  
         if (tb.IsSystemObject == false) {  
            Console.WriteLine("-- Scripting for table " + tb.Name);  
  
            // Generating script for table tb  
            System.Collections.Specialized.StringCollection sc = scrp.Script(new Urn[]{tb.Urn});  
            foreach (string st in sc) {  
               Console.WriteLine(st);  
            }  
            Console.WriteLine("--");  
         }  
      }   
   }  
}  
```  
  
## <a name="scripting-out-the-dependencies-for-a-database-in-powershell"></a>在 PowerShell 中撰写数据库依赖项的脚本  
 此代码示例说明如何发现依赖项并循环访问列表以显示结果。  
  
```  
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\default  
  
# Create a Scripter object and set the required scripting options.  
$scrp = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Scripter -ArgumentList (Get-Item .)  
$scrp.Options.ScriptDrops = $false  
$scrp.Options.WithDependencies = $true  
$scrp.Options.IncludeIfNotExists = $true  
  
# Set the path context to the tables in AdventureWorks2012.  
  
CD Databases\AdventureWorks2012\Tables  
  
foreach ($Item in Get-ChildItem)  
 {    
 $scrp.Script($Item)  
 }  
```  
  
  