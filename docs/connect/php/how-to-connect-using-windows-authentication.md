---
title: "如何： 使用 Windows 身份验证进行连接 |Microsoft 文档"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connecting to the server, Windows Authentication
ms.assetid: f403a4e0-b0a8-4939-9dc1-e1209626367e
caps.latest.revision: 35
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 669ea9f70127c383f1390930a842cfee70366dd9
ms.contentlocale: zh-cn
ms.lasthandoff: 09/09/2017

---
# <a name="how-to-connect-using-windows-authentication"></a>如何：使用 Windows 身份验证进行连接
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

默认情况下， [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] 使用 Windows 身份验证连接 SQL Server。 请务必注意，在大多数情况下，这通常意味着使用 Web 服务器的进程标识或线程标识（如果 Web 服务器正在使用模拟）来连接服务器，而不是最终用户的标识。  
  
使用 Windows 身份验证连接 SQL Server 时，必须要考虑以下几点：  
  
-   运行 Web 服务器的进程（或线程）所依据的凭据必须映射到有效的 SQL Server 登录才能建立连接。  
  
-   如果 SQL Server 和 Web 服务器位于不同的计算机上，则必须配置 SQL Server 才能启用远程连接。  
  
> [!NOTE]  
> 建立连接时可以设置连接属性，如 *Database* 和 *ConnectionPooling* 。 有关受支持的连接属性的完整列表，请参阅 [Connection Options](../../connect/php/connection-options.md)。  
  
只要可能存在以下原因，都应使用 Windows 身份验证来连接 SQL Server：  
  
-   没有任何凭据在身份验证期间通过网络传递；用户名和密码未嵌入在数据库连接字符串中。 这意味着恶意用户或攻击者无法通过监视网络或查看配置文件内部的连接字符串来获取凭据。  
  
-   用户要进行集中式帐户管理；强制执行多次无效登录请求后的安全策略，如密码有效期、最短密码长度和帐户锁定。  
  
如果 Windows 身份验证不可行，请参阅 [How to: Connect Using SQL Server Authentication](../../connect/php/how-to-connect-using-sql-server-authentication.md)。  
  
## <a name="example"></a>示例  
通过使用 [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)]的 SQLSRV 驱动程序，以下示例将使用 Windows 身份验证连接到 SQL Server 的本地实例。 建立连接后，服务器将查询正在访问数据库的用户登录名。  
  
该示例假定本地计算机上已安装了 SQL Server 和 [AdventureWorks](http://go.microsoft.com/fwlink/?LinkID=67739) 数据库。 当从浏览器运行该示例时，所有输出都将写入该浏览器。  
  
```  
<?php  
/* Specify the server and connection string attributes. */  
$serverName = "(local)";  
$connectionInfo = array( "Database"=>"AdventureWorks");  
  
/* Connect using Windows Authentication. */  
$conn = sqlsrv_connect( $serverName, $connectionInfo);  
if( $conn === false )  
{  
     echo "Unable to connect.</br>";  
     die( print_r( sqlsrv_errors(), true));  
}  
  
/* Query SQL Server for the login of the user accessing the  
database. */  
$tsql = "SELECT CONVERT(varchar(32), SUSER_SNAME())";  
$stmt = sqlsrv_query( $conn, $tsql);  
if( $stmt === false )  
{  
     echo "Error in executing query.</br>";  
     die( print_r( sqlsrv_errors(), true));  
}  
  
/* Retrieve and display the results of the query. */  
$row = sqlsrv_fetch_array($stmt);  
echo "User login: ".$row[0]."</br>";  
  
/* Free statement and connection resources. */  
sqlsrv_free_stmt( $stmt);  
sqlsrv_close( $conn);  
?>  
```  
  
## <a name="example"></a>示例  
下面的示例使用 PDO_SQLSRV 驱动程序来完成与上一示例相同的任务。  
  
```  
<?php  
try {  
   $conn = new PDO( "sqlsrv:Server=(local);Database=AdventureWorks", NULL, NULL);   
   $conn->setAttribute( PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION );  
}  
  
catch( PDOException $e ) {  
   die( "Error connecting to SQL Server" );   
}  
  
echo "Connected to SQL Server\n";  
  
$query = 'select * from Person.ContactType';   
$stmt = $conn->query( $query );   
while ( $row = $stmt->fetch( PDO::FETCH_ASSOC ) ){   
   print_r( $row );   
}  
?>  
```  
  
## <a name="see-also"></a>另请参阅  
[How to: Connect Using SQL Server Authentication](../../connect/php/how-to-connect-using-sql-server-authentication.md)  
[PHP SQL 驱动程序编程指南](../../connect/php/programming-guide-for-php-sql-driver.md)
[关于文档中的代码示例](../../connect/php/about-code-examples-in-the-documentation.md)  
[如何创建 SQL Server 登录名](http://go.microsoft.com/fwlink/?LinkId=106325)  
[如何创建数据库用户](http://go.microsoft.com/fwlink/?LinkId=106327)  
[管理用户、角色和登录名](http://go.microsoft.com/fwlink/?LinkId=106329)  
[用户架构分离](http://go.microsoft.com/fwlink/?LinkId=106330)  
[Grant 对象权限 (TRANSACT-SQL)](http://go.microsoft.com/fwlink/?LinkId=106332)  
  
