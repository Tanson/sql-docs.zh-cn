---
title: "sqlcmd 实用工具 |Microsoft 文档"
ms.custom: 
ms.date: 07/27/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- statements [SQL Server], command prompt
- QUIT command
- Transact-SQL statements, command prompt
- EXIT command
- sqlcmd commands
- ED command
- sqlcmd utility
- command prompt utilities [SQL Server], sqlcmd
- '!! command'
- stored procedures [SQL Server], command prompt
- system stored procedures [SQL Server], command prompt
- sqlcmd utility, about sqlcmd utility
- scripts [SQL Server], command prompt
- RESET command
- GO command
ms.assetid: e1728707-5215-4c04-8320-e36f161b834a
caps.latest.revision: 155
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 2be7d74bde1731e9b4312ec80eb8a9a75b0c4d70
ms.contentlocale: zh-cn
ms.lasthandoff: 08/02/2017

---
# <a name="sqlcmd-utility"></a>sqlcmd Utility
[!INCLUDE[tsql-appliesto-ss2008-asdb-asdw-pdw-_md](../includes/tsql-appliesto-ss2008-asdb-asdw-pdw-md.md)]

 > SQL Server 2014 和更低，请参阅[sqlcmd 实用工具](https://msdn.microsoft.com/en-US/library/ms162773(SQL.120).aspx)。


  **Sqlcmd**实用工具，可以在输入 TRANSACT-SQL 语句、 系统过程和脚本文件在命令提示符下，**查询编辑器**在 SQLCMD 模式下，Windows 脚本文件或 SQL Server 代理作业的操作系统 (Cmd.exe) 作业步骤。 此实用工具使用 ODBC 执行 TRANSACT-SQL 批处理。 
  
> [!NOTE]
> Sqlcmd 实用工具的最新版本可作为 Web 版本从 [下载中心](http://go.microsoft.com/fwlink/?LinkID=825643)获取。 你需要版本 13.1 或更高版本以支持始终加密 (`-g`) 和 Azure Active Directory 身份验证 (`-G`)。 （你的计算机上可能已安装多个版本的 sqlcmd.exe。 请确保使用正确的版本。 若要确定版本，请执行 `sqlcmd -?`。）

  若要在 SSMS 中运行 sqlcmd 语句，请从顶部导航栏上的“查询菜单”下拉列表中选择“SQLCMD 模式”。  
  
> [!IMPORTANT] 
> [!INCLUDE[ssManStudioFull_md](../includes/ssmanstudiofull-md.md)](SSMS) 使用 Microsoft[!INCLUDE[dnprdnshort_md](../includes/dnprdnshort-md.md)]用于执行的常规和中的 SQLCMD 模式下的 SqlClient**查询编辑器**。 从命令行运行 **sqlcmd** 时， **sqlcmd** 使用 ODBC 驱动程序。 由于可以应用不同的默认选项，因此在 [!INCLUDE[ssManStudioFull_md](../includes/ssmanstudiofull-md.md)] SQLCMD 模式下以及在 **sqlcmd** 实用工具中执行相同的查询时，可能会看到不同的行为。  
>   
  
 当前， **sqlcmd** 在命令行选项和值之间不需要空格。 但是，在将来的版本中，在命令行选项和值之间可能需要空格。  
 
 其他主题：
- [启动 sqlcmd 实用工具](../relational-databases/scripting/sqlcmd-start-the-utility.md)   
-  [使用 sqlcmd 实用工具](../relational-databases/scripting/sqlcmd-use-the-utility.md)   
  
## <a name="syntax"></a>语法  
  
```  
sqlcmd   
   -a packet_size  
   -A (dedicated administrator connection)  
   -b (terminate batch job if there is an error)  
   -c batch_terminator  
   -C (trust the server certificate)  
   -d db_name  
   -e (echo input)  
   -E (use trusted connection)  
   -f codepage | i:codepage[,o:codepage] | o:codepage[,i:codepage] 
   -g (enable column encryption) 
   -G (use Azure Active Directory for authentication)
   -h rows_per_header  
   -H workstation_name  
   -i input_file  
   -I (enable quoted identifiers)  
   -j (Print raw error messages)
   -k[1 | 2] (remove or replace control characters)  
   -K application_intent  
   -l login_timeout  
   -L[c] (list servers, optional clean output)  
   -m error_level  
   -M multisubnet_failover  
   -N (encrypt connection)  
   -o output_file  
   -p[1] (print statistics, optional colon format)  
   -P password  
   -q "cmdline query"  
   -Q "cmdline query" (and exit)  
   -r[0 | 1] (msgs to stderr)  
   -R (use client regional settings)  
   -s col_separator  
   -S [protocol:]server[instance_name][,port]  
   -t query_timeout  
   -u (unicode output file)  
   -U login_id  
   -v var = "value"  
   -V error_severity_level  
   -w column_width  
   -W (remove trailing spaces)  
   -x (disable variable substitution)  
   -X[1] (disable commands, startup script, environment variables, optional exit)  
   -y variable_length_type_display_width  
   -Y fixed_length_type_display_width  
   -z new_password   
   -Z new_password (and exit)  
   -? (usage)  
```  
  
## <a name="command-line-options"></a>命令行选项  
 **登录相关选项**  
  **-A**  
 到与专用的管理员连接 (DAC) 的 SQL Server 中的日志。 此类型连接用于排除服务器故障。 这只适用于支持 DAC 的服务器。 如果 DAC 不可用， **sqlcmd** 会生成错误消息，然后退出。 有关 DAC 的详细信息，请参阅[用于数据库管理员的诊断连接](../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md)。 -A 选项不支持使用-G 选项。 时连接到 SQL 数据库使用-A，你必须是 SQL server 管理员联系。 DAC 不可用的 Azure Active Directory 管理员。
  
 **-C**  
 该开关供客户端用于将其配置为隐式表示信任服务器证书且无需验证。 此选项等同于 ADO.NET 选项 `TRUSTSERVERCERTIFICATE = true`。  
  
 **-d** *db_name*  
 启动 **sqlcmd** 时发出一个 `USE` *db_name* 语句。 此选项设置 **sqlcmd** 脚本变量 SQLCMDDBNAME。 它指定初始数据库。 默认为您的登录名的默认数据库属性。 如果数据库不存在，则生成错误消息且 **sqlcmd** 退出。  
  
 **-l** *login_timeout*  
 指定在你尝试连接到服务器时 **sqlcmd** 登录 ODBC 驱动程序的超时时间（以秒为单位）。 此选项设置 **sqlcmd** 脚本变量 SQLCMDLOGINTIMEOUT。 登录到 **sqlcmd** 的默认超时时间为 8 秒。 当使用 **-G** 选项连接到 SQL 数据库或 SQL 数据仓库并使用 Azure Active Directory 进行身份验证时，建议超时值至少为 30 秒。 登录超时必须是介于 0 和 65534 之间的数字。 如果提供的值不是数值或不在此范围内， **sqlcmd** 将生成错误消息。 该值为 0 时，则允许无限制等待。
  
 **-E**  
 使用可信的连接而不是使用用户名和密码登录到 SQL Server。 默认情况下，如果未指定 **-E** ， **sqlcmd** 将使用信任连接选项。  
  
 **-E** 选项会忽略可能的用户名和密码环境变量设置，例如 SQLCMDPASSWORD。 如果将 **-E** 选项与 **-U** 选项或 **-P** 选项一起使用，将生成错误消息。  

**-g**  
将列加密设置设为 `Enabled`。 有关详细信息，请参阅 [Always Encrypted](../relational-databases/security/encryption/always-encrypted-database-engine.md)。 仅支持存储在 Windows 证书存储中的主密钥。 -g 开关至少需要 **sqlcmd** 版本 [13.1](http://go.microsoft.com/fwlink/?LinkID=825643)。 若要确定你的版本，请执行 `sqlcmd -?`。

 **-G**  
 当连接到 SQL 数据库或 SQL 数据仓库时，客户端将使用此开关指定该用户使用 Azure Active Directory 身份验证来进行身份验证。 此选项设置 **sqlcmd** 脚本变量 SQLCMDUSEAAD = true。 -G 开关至少需要 **sqlcmd** 版本 [13.1](http://go.microsoft.com/fwlink/?LinkID=825643)。 若要确定你的版本，请执行 `sqlcmd -?`。 有关详细信息，请参阅 [使用 Azure Active Directory 身份验证连接到 SQL 数据库或 SQL 数据仓库](https://azure.microsoft.com/documentation/articles/sql-database-aad-authentication/)。 -A 选项不支持使用-G 选项。

> [!IMPORTANT]
> **-G** 选项仅适用于 Azure SQL 数据库 和 Azure 数据仓库。 

- **Azure Active Directory 用户名和密码：** 

    当你想要使用 Azure Active Directory 用户名和密码时，可以提供 **-G** 选项，也可以通过提供 **-U** 选项和 **-P** 选项来使用用户名和密码。
    ``` 
    Sqlcmd -S testsrv.database.windows.net -d Target_DB_or_DW -U bob@contoso.com -P MyAADPassword -G 
    ``` 
    这将在后端生成以下连接字符串： 

    ```
     SERVER = Target_DB_or_DW.testsrv.database.windows.net;UID= bob@contoso.com;PWD=MyAADPassword;AUTHENTICATION = ActiveDirectoryPassword 
    ```

- **Azure Active Directory 集成** 
 
   要进行 Azure Active Directory 集成身份验证，可提供 **-G** 选项而无需用户名或密码： 

    ```
    Sqlcmd -S Target_DB_or_DW.testsrv.database.windows.net  -G
    ```  

    这将在后端生成以下连接字符串： 

    ```
    SERVER = Target_DB_or_DW.testsrv.database.windows.net Authentication = ActiveDirectoryIntegrated; Trusted_Connection=NO
    ``` 

    > [!NOTE] 
    > -E 选项 (Trusted_Connection) 不能与 -G 选项一起使用。

    
 **-H** *workstation_name*  
 工作站的名称。 此选项设置 **sqlcmd** 脚本变量 SQLCMDWORKSTATION。 工作站名称列出在 **sys.sysprocesses** 目录视图的 **hostname** 列中，并且可使用存储过程 **sp_who**返回。 如果不指定此选项，则默认为当前计算机名称。 此名称可用来标识不同的 **sqlcmd** 会话。  


**-j** 将原始错误消息输出到银幕上。
  
 **-K** *application_intent*  
 连接到服务器时声明应用程序工作负荷类型。 目前唯一支持的值是 **ReadOnly**。 如果未指定 **-K** ，sqlcmd 实用工具将不支持连接到 AlwaysOn 可用性组中的次要副本。 有关详细信息，请参阅 [活动次要副本：可读次要副本（AlwaysOn 可用性组）](https://msdn.microsoft.com/library/ff878253.aspx)  
  
 **-M** *multisubnet_failover*  
 始终指定**-M**连接到 SQL Server 可用性组或 SQL Server 故障转移群集实例的可用性组侦听器时。 **-M** 将为（当前）活动服务器提供更快的检测和连接。 如果不指定 **–M**，则 **-M** 处于关闭状态。 有关 [!INCLUDE[ssHADR](../includes/sshadr-md.md)] 的详细信息，请参阅[可用性组侦听器、客户端连接和应用程序故障转移 (SQL Server)](https://msdn.microsoft.com/library/hh213417.aspx)、[创建和配置可用性组 (SQL Server)](../database-engine/availability-groups/windows/creation-and-configuration-of-availability-groups-sql-server.md)、[故障转移群集和 AlwaysOn 可用性组 (SQL Server)](https://msdn.microsoft.comlibrary/ff929171.aspx，和 [活动次要副本：可读次要副本（AlwaysOn 可用性组）](https://msdn.microsoft.com/library/ff878253.aspx。  
  
 **-N**  
 此开关供客户端用于请求加密连接。  
  
 **-P** *password*  
 用户指定的密码。 密码是区分大小写的。 如果使用了 -U 选项而未使用 **-P** 选项，并且未设置 **SQLCMDPASSWORD** 环境变量，则 sqlcmd 会提示用户输入密码。 若要指定空密码（不推荐），请使用 **-P ""**。 请记住始终：
 
#### <a name="use-a-strong-passwordhttpsmsdnmicrosoftcomlibraryms161962sql130aspx"></a>[**使用强密码！！**](https://msdn.microsoft.com/library/ms161962(SQL.130).aspx)
  
  
 通过向控制台输出密码提示，可以显示密码提示，如下所示： `Password:`  
  
 隐藏用户输入。 也就是说，将不会显示任何输入的内容，光标保留原位不动。  
  
 使用 SQLCMDPASSWORD 环境变量可以为当前会话设置默认密码。 因此，不必将密码硬编码到批处理文件中。  
  
 以下示例首先在命令提示符处设置 SQLCMDPASSWORD 变量，然后访问 **sqlcmd** 实用工具。 在命令提示符下，键入：  
  
 `SET SQLCMDPASSWORD= p@a$$w0rd`  
 在以下命令提示符处键入：  
  
 `sqlcmd`  
  
 如果用户名和密码组合不正确，将生成错误消息。  
  
**注意！**  为实现向后兼容性而保留了 OSQLPASSWORD 环境变量。 SQLCMDPASSWORD 环境变量优先于 OSQLPASSWORD 环境变量；也就是说 **sqlcmd** 和 **osql** 可以彼此相邻使用而不会相互干扰，并且旧式脚本可以继续使用。  
  
 如果将 **-P** 选项与 **-E** 选项一起使用，将生成错误消息。  
  
 如果 **-P** 选项后有多个参数，将生成错误消息并退出程序。  
  
 **-S** [*protocol*:]*server*[**\\***instance_name*][**,***port*]  
 指定要连接到 SQL Server 的实例。 它设置 **sqlcmd** 脚本变量 SQLCMDSERVER。  
  
 指定*server_name*连接到 SQL Server 在该服务器计算机上的默认实例。 指定*server_name* [  **\\**  *instance_name* ] 若要连接到该服务器计算机上的 SQL Server 的命名实例。 如果指定服务器的计算机，则**sqlcmd**连接到本地计算机上 SQL Server 的默认实例。 从网络上的远程计算机执行 **sqlcmd** 时，此选项是必需的。  
  
 *protocol* 可以是 **tcp** (TCP/IP)、 **lpc** （共享内存）或 **np** （命名管道）。  
  
 如果不指定*server_name* [  **\\**  *instance_name* ] 当启动**sqlcmd**，SQL Server 检查并使用 SQLCMDSERVER 环境变量。  
  
> [!NOTE]  
>  为实现向后兼容性而保留了 OSQLSERVER 环境变量。 SQLCMDSERVER 环境变量优先于 OSQLSERVER 环境变量；也就是说 **sqlcmd** 和 **osql** 可以彼此相邻使用而不会相互干扰，并且旧式脚本可以继续使用。  
  
 **-U** *login_id*  
 登录名或包含的数据库用户名。 对于包含的数据库用户，必须提供数据库名称选项 (-d)。  
  
> [!NOTE]  
>  OSQLUSER 环境变量可用于实现向后兼容性。 SQLCMDUSER 环境变量优先于 OSQLUSER 环境变量。 也就是说， **sqlcmd** 和 **osql** 可以彼此相邻使用而不会相互干扰。 此外，现有的 **osql** 脚本可以继续使用。  
  
 如果既没有**-U**选项也不**-P**指定选项，则**sqlcmd**尝试通过使用 Microsoft Windows 身份验证模式连接。 身份验证基于运行 **sqlcmd**的用户的 Windows 帐户。  
  
 如果 **-U** 选项与 **-E** 选项（将在本主题的后面进行说明）一起使用，则会生成错误消息。 如果 **–U** 选项后有多个参数，将生成错误消息并退出程序。  
  
 **-z** *new_password*  
 更改密码：  
  
 `sqlcmd -U someuser -P s0mep@ssword -z a_new_p@a$$w0rd`  
  
 **-Z** *new_password*  
 更改密码并退出：  
  
 `sqlcmd -U someuser -P s0mep@ssword -Z a_new_p@a$$w0rd`  
  
 **输入/输出选项**  
  **-f** *codepage* | **i:***codepage*[**,o:***codepage*] | **o:***codepage*[**,i:***codepage*]  
 指定输入和输出代码页。 代码页页码是指定已安装的 Windows 代码页的数值。  
  
 代码页转换规则：  
  
-   如果未指定代码页， **sqlcmd** 会将当前代码页同时用于输入文件和输出文件，除非输入文件为 Unicode 文件，在此情况下无需进行转换。  
  
-   **sqlcmd** 自动识别 Big-endian Unicode 和 Little-endian Unicode 输入文件。 如果已指定 **-u** 选项，输出将始终为 Little-endian Unicode。  
  
-   如果未指定输出文件，输出代码页将为控制台代码页。 这将使输出正确显示在控制台上。  
  
-   假定多个输入文件具有相同的代码页。 可以将 Unicode 和非 Unicode 输入文件混合在一起。  
  
 在命令提示符处输入 **chcp** 以验证 Cmd.exe 的代码页。  
  
 **-i** *input_file*[**、***input_file2*...]  
 标识包含一批 SQL 语句或存储过程的文件。 可以指定要按顺序读取和处理的多个文件。 文件名之间不要使用任何空格。 **sqlcmd** 将首先检查所有指定的文件是否都存在。 如果有一个或多个文件不存在， **sqlcmd** 将退出。 -i 和 -Q/-q 选项是互斥的。  
  
 路径示例：  

```  
-i C:\<filename>  
-i \\<Server>\<Share$>\<filename>  
-i "C:\Some Folder\<file name>"  
```
  
 包含空格的文件路径必须用引号引起来。  
  
 此选项可以使用多次：**-i***input_file* **-I***I input_file.*  
  
 **-o** *output_file*  
 标识从 **sqlcmd**接收输出的文件。  
  
 如果指定了 **-u** ，则 *output_file* 以 Unicode 格式存储。 如果文件名无效，将生成一个错误消息，并且 **sqlcmd** 将退出。 **sqlcmd** 不支持向同一文件并发写入多个 **sqlcmd** 进程。 文件输出将损坏或不正确。 有关文件格式的详细信息，请参阅 **-f** 开关。 如果此文件不存在，将创建此文件。 前一个 **sqlcmd** 会话中的同名文件将被覆盖。 此处指定的文件不是 **stdout** 文件。 如果指定了 **stdout** 文件，将不使用此文件。  
  
 路径示例：  

```  
-o C:< filename>  
-o \\<Server>\<Share$>\<filename>  
-o "C:\Some Folder\<file name>"  
 ``` 
 包含空格的文件路径必须用引号引起来。  
  
 **-r**[**0** | **1**]  
 将错误消息输出重定向到屏幕 (**stderr**)。 如果未指定参数或指定参数为 **0**，则仅重定向严重级别为 11 或更高的错误消息。 如果指定参数为 **1**，则将重定向所有消息输出（包括 PRINT）。 如果使用 -o，将不起任何作用。 默认情况下，消息将发送到 **stdout**。  
  
 **-R**  
 导致**sqlcmd**本地化数字、 货币、 日期和时间列从 SQL Server 检索基于客户端的区域设置。 默认情况下，将使用服务器的区域设置显示这些列。  
  
 **-u**  
 指定无论 *input_file* 为何种格式，都以 Unicode 格式存储 *output_file*。  
  
 **查询执行选项**  
  **-e**  
 将输入脚本写入标准输出设备 (**stdout**)。  
  
 **-I**  
 将 SET QUOTED_IDENTIFIER 连接选项设置为 ON。 默认情况下，此选项设置为 OFF。 有关详细信息，请参阅 [SET QUOTED_IDENTIFIER (Transact-SQL)](~/t-sql/statements/set-quoted-identifier-transact-sql.md)。  
  
 **-q"** *cmdline query* **"**  
 启动 **sqlcmd** 时执行查询，但是在查询结束运行时不退出 **sqlcmd** 。 可以执行多个以分号分隔的查询。 将查询用引号引起来，如下例所示。  
  
 在命令提示符下，键入：  
  
 `sqlcmd -d AdventureWorks2012 -q "SELECT FirstName, LastName FROM Person.Person WHERE LastName LIKE 'Whi%';"`  
  
 `sqlcmd -d AdventureWorks2012 -q "SELECT TOP 5 FirstName FROM Person.Person;SELECT TOP 5 LastName FROM Person.Person;"`  
  
> [!IMPORTANT]  
>  请不要在查询中使用 GO 终止符。  
  
 如果在指定此选项的同时还指定了 **-b** ， **sqlcmd** 在遇到错误时将退出。 **-b** 将在本主题后面部分进行介绍。  
  
 **-Q"** *cmdline query* **"**  
 在 **sqlcmd** 启动时执行查询，随后立即退出 **sqlcmd**。 可以执行多个以分号分隔的查询。  
  
 将查询用引号引起来，如下例所示。  
  
 在命令提示符下，键入：  
  
 `sqlcmd -d AdventureWorks2012 -Q "SELECT FirstName, LastName FROM Person.Person WHERE LastName LIKE 'Whi%';"`  
  
 `sqlcmd -d AdventureWorks2012 -Q "SELECT TOP 5 FirstName FROM Person.Person;SELECT TOP 5 LastName FROM Person.Person;"`  
  
> [!IMPORTANT]  
>  请不要在查询中使用 GO 终止符。  
  
 如果在指定此选项的同时还指定了 **-b** ， **sqlcmd** 在遇到错误时将退出。 **-b** 将在本主题后面部分进行介绍。  
  
 **-t** *query_timeout*  
 指定命令（或 SQL 语句）超时的时间。 此选项设置 **sqlcmd** 脚本变量 SQLCMDSTATTIMEOUT。 如果未指定 *time_out* 值，则命令将不会超时。 *query**time_out* 必须是介于 1 和 65534 之间的数字。 如果提供的值不是数值或不在此范围内， **sqlcmd** 将生成错误消息。  
  
> [!NOTE]  
>  实际的超时值可能会与指定的 time_out  值相差几秒。  
  
 **-vvar =**  *value*[ **var =** *value*...]  
 创建可在 **sqlcmd**脚本中使用的 **sqlcmd** 脚本变量。 如果该值包含空格，则将其用引号引起来。 可以指定多个 ***var***=**"***values***"** 值。 如果指定的任何值中有错误， **sqlcmd** 会生成错误消息，然后退出。  
  
 `sqlcmd -v MyVar1=something MyVar2="some thing"`  
  
 `sqlcmd -v MyVar1=something -v MyVar2="some thing"`  
  
 **-x**  
 导致 **sqlcmd** 忽略脚本变量。 当脚本中包含多个 INSERT 语句，并且这些语句可能包含格式与常规变量（例如 $(*variable_name*)）相同的字符串时，这一选项很有用。  
  
 **格式设置选项**  
  **-h** *headers*  
 指定要在列标题之间输出的行数。 默认为每一组查询结果输出一次标题。 此选项设置 **sqlcmd** 脚本变量 SQLCMDHEADERS。 使用 **-1** 指定不可输出标题。 任何无效的值都将导致 **sqlcmd** 生成错误消息并随后退出。  
  
 **-k** [**1** | **2**]  
 删除输出中的所有控制字符，例如制表符和换行符。 这会在返回数据时保留列格式。 如果指定了 1，则控制字符被一个空格替代。 如果指定了 2，则连续的控制字符被一个空格替代。 **-k** 与 **-k1**相同。  
  
 **-s** *col_separator*  
 指定列分隔符字符。 默认为空格。 此选项设置 **sqlcmd** 脚本变量 SQLCMDCOLSEP。 若要使用对操作系统有特殊含义的字符，如“与”符号 (&) 或分号 (;)，请将该字符用双引号 (") 引起来。 列分隔符可以是任意 8 位字符。  
  
 **-w** *column_width*  
 指定用于输出的屏幕宽度。 此选项设置 **sqlcmd** 脚本变量 SQLCMDCOLWIDTH。 该列宽必须是介于 8 和 65536 之间的数字。 如果指定的列宽不在此范围内，则 **sqlcmd** 将生成错误消息。 默认宽度为 80 个字符。 在输出行超出指定的列宽时，将转到下一行。  
  
 **-W**  
 此选项删除列的尾随空格。 在准备要导出到另一应用程序的数据时，请将此选项和 **-s** 选项一起使用。 不能与 **-y** 或 **-Y** 选项一起使用。  
  
 **-y** *variable_length_type_display_width*  
 设置 **sqlcmd** 脚本变量 `SQLCMDMAXVARTYPEWIDTH`。 默认值为 256。 它限制为下列大型可变长度数据类型返回的字符的数目：  
  
-   **varchar(max)**  
  
-   **nvarchar(max)**  
  
-   **varbinary(max)**  
  
-   **xml**  
  
-   **UDT（用户定义数据类型）**  
  
-   **text**  
  
-   **ntext**  
  
-   **image**  
  
> [!NOTE]  
>  根据实现，UDT 可以使用固定的长度。 如果此固定长度 UDT 的长度比 *display_width*短，则返回的 UDT 值将不受影响。 但是，如果此长度比 *display_width*长，则输出会被截断。  
   
  
> [!IMPORTANT]  
>  使用 **-y 0** 选项时要特别注意，因为根据返回的数据量大小，此选项可能导致服务器和网络上出现严重性能问题。  
  
 **-Y** *fixed_length_type_display_width*  
 设置 **sqlcmd** 脚本变量 `SQLCMDMAXFIXEDTYPEWIDTH`。 默认值为 0（无限制）。 它限制为以下数据类型返回的字符数：  
  
-   **char(** *n* **)**, where 1<=n<=8000  
  
-   **nchar(n** *n* **)**, where 1<=n<=4000  
  
-   **varchar(n** *n* **)**, where 1<=n<=8000  
  
-   **nvarchar(n** *n* **)**, where 1<=n<=4000  
  
-   **varbinary(n** *n* **)**, where 1<=n\<=4000  
  
-   **变量**  
  
 **错误报告选项**  
  **-b**  
 指定发生错误时， **sqlcmd** 退出并返回一个 DOS ERRORLEVEL 值。 返回给 DOS ERRORLEVE 变量的值是**1**时 SQL Server 错误消息具有严重级别大于 10; 否则，返回的值是**0**。 如果除 **-b** 选项外还设置了 **-V**选项，则当严重级别低于使用 **-V** 设置的值时， **sqlcmd**将不报告错误。 命令提示符批处理文件可以测试 ERRORLEVEL 的值并相应处理错误。 **sqlcmd** 不对严重级别 10 报告错误（信息性消息）。  
  
 如果 **sqlcmd** 脚本包含错误的注释、语法错误或缺少脚本变量，则返回的 ERRORLEVEL 为 1。  
  
 **-m** *error_level*  
 控制发送到 **stdout**的错误消息类型。 将发送严重级别大于或等于此级别的消息。 如果此值设置为 **-1**，将发送所有消息（包括信息性消息）。 **-m** 和 **-1**之间不允许有空格。 例如， **-m-1** 有效，而 **-m-1** 无效。  
  
 此选项还设置 **sqlcmd** 脚本变量 SQLCMDERRORLEVEL。 此变量的默认值为 0。  
  
 **-b** *error_severity_level*  
 控制用于设置 ERRORLEVEL 变量的严重级别。 严重级别大于或等于此值的错误消息将设置 ERRORLEVEL。 小于 0 的值将报告为 0。 可以使用批处理文件和 CMD 文件来测试 ERRORLEVEL 变量的值。  
  
 **其他选项**  
  **-a** *packet_size*  
 需要不同大小的数据包。 此选项设置 **sqlcmd** 脚本变量 SQLCMDPACKETSIZE。 *packet_size* 必须是介于 512 和 32767 之间的值。 默认值为 4096。 如果脚本的两个 GO 命令之间包含大量 SQL 语句，则使用较大的数据包可以提高脚本执行的性能。 您可以请求更大的包大小。 但是，如果请求遭拒绝， **sqlcmd** 将对包大小使用服务器默认值。  
  
 **-c** *batch_terminator*  
 指定批处理终止符。 默认情况下，命令会终止然后发送到 SQL Server 通过键入 go"在行本身。 重置批处理终止符时，请不使用 TRANSACT-SQL 保留关键字或对操作系统有特殊含义的字符即使它们的前面有反斜杠。  
  
 **-L**[**c**]  
 列出本地配置的服务器计算机和在网络上播发的服务器计算机的名称。 此参数不能与其他参数结合使用。 可以列出的服务器的最大数目是 3000。 如果服务器列表由于缓冲区大小而被截断，则会显示错误消息。  
  
> [!NOTE]  
>  鉴于网络广播的特点， **sqlcmd** 不可能及时接收来自所有服务器的响应。 因此，每次调用该选项所返回的服务器列表都可能不同。  
  
 如果指定可选参数 **c** ，则输出不会显示 Servers: 标题行，并且列出的每个服务器行都没有前导空格。 这被称为清除输出。 清除输出可以提高脚本语言的处理性能。  
  
 **-p**[**1**]  
 输出每个结果集的性能统计信息。 以下示例是性能统计信息的格式：  
  
 `Network packet size (bytes): n`  
  
 `x xact[s]:`  
  
 `Clock Time (ms.): total       t1  avg       t2 (t3 xacts per sec.)`  
  
 其中：  
  
 `x`= 由 SQL Server 处理的事务数。  
  
 `t1` = 所有事务的总时间。  
  
 `t2` = 单个事务的平均时间。  
  
 `t3` = 每秒平均事务数。  
  
 所有时间均以毫秒表示。  
  
 如果指定了可选参数 **1** ，则统计信息的输出格式为以冒号分隔的格式，此格式可以由脚本轻松导入到电子表格中或进行处理。  
  
 如果可选参数是除 **1**之外的任何值，则将生成错误并且 **sqlcmd** 将退出。  
  
 **-X**[**1**]  
 从批处理文件执行 **sqlcmd** 时，将禁用可能危及系统安全的命令。 禁用的命令仍然可以被识别； **sqlcmd** 发出警告消息并继续。 如果指定了可选参数 **1** ，则 **sqlcmd** 将生成错误消息，然后退出。 使用 **-X** 选项时，将禁用以下命令：  
  
-   **ED**  
  
-   **!!** *command*  
  
 如果指定 **-X** 选项，则会阻止将环境变量传递给 **sqlcmd**。 同时该选项还会阻止执行通过使用 SQLCMDINI 脚本变量指定的启动脚本。 有关 **sqlcmd** 脚本变量的详细信息，请参阅 [将 sqlcmd 与脚本变量结合使用](~/relational-databases/scripting/sqlcmd-use-with-scripting-variables.md)。  
  
 **-?**  
 显示 **sqlcmd** 的版本和 **sqlcmd** 选项的语法摘要。  
  
## <a name="remarks"></a>注释  
 不必按语法部分所示的顺序使用选项。  
  
 在返回多个结果时， **sqlcmd** 在批处理中的每个结果集之间输出一个空行。 此外，如果没有应用于已执行的语句，则不会出现 `<x> rows affected` 消息。  
  
 若要交互使用 **sqlcmd** ，请在命令提示符处带本主题前面介绍的一个或多个选项键入 **sqlcmd** 。 有关详细信息，请参阅 [使用 sqlcmd 实用工具](~/relational-databases/scripting/sqlcmd-use-the-utility.md)  
  
> [!NOTE]  
>  选项 **-L**、 **-Q**、 **-Z** 或 **-i** 会导致 **sqlcmd** 在执行后退出。  
  
 命令环境 (Cmd.exe) 中的 **sqlcmd** 命令行的总长度（包括所有参数和扩展变量）取决于 Cmd.exe 所在的操作系统。  
  
## <a name="variable-precedence-low-to-high"></a>变量优先级（从低到高）  
  
1.  系统级环境变量。  
  
2.  用户级环境变量  
  
3.  运行**sqlcmd** 之前在命令提示符处设置的命令 shell ( **SET**X=Y)。  
  
4.  **sqlcmd-v** X=Y  
  
5.  **:Setvar** X Y  
  
> [!NOTE]  
>  若要查看环境变量，请在“控制面板” 中打开“系统” ，然后单击“高级”  选项卡。  
  
## <a name="sqlcmd-scripting-variables"></a>sqlcmd 脚本变量  
  
|变量|相关开关|R/W|默认|  
|--------------|--------------------|----------|-------------|  
|SQLCMDUSER|-U|R|""|  
|SQLCMDPASSWORD|-P|--|""|  
|SQLCMDSERVER|-S|R|"DefaultLocalInstance"|  
|SQLCMDWORKSTATION|-H|R|"ComputerName"|  
|SQLCMDDBNAME|-d|R|""|  
|SQLCMDLOGINTIMEOUT|-l|R/W|"8"（秒）|  
|SQLCMDSTATTIMEOUT|-t|R/W|"0" = 无限期等待|  
|SQLCMDHEADERS|-H|R/W|"0"|  
|SQLCMDCOLSEP|-S|R/W|“ ”|  
|SQLCMDCOLWIDTH|-w|R/W|"0"|  
|SQLCMDPACKETSIZE|-A|R|"4096"|  
|SQLCMDERRORLEVEL|-M|R/W|0|  
|SQLCMDMAXVARTYPEWIDTH|-y|R/W|"256"|  
|SQLCMDMAXFIXEDTYPEWIDTH|-y|R/W|"0" = 无限制|  
|SQLCMDEDITOR||R/W|"edit.com"|  
|SQLCMDINI||R|""|
|SQLCMDUSEAAD  | -G | R/W | "" |  
  
 使用 **:Connect** 时设置 SQLCMDUSER、SQLCMDPASSWORD 和 SQLCMDSERVER。  
  
 R 表示在程序初始化过程中只能设置一次值。  
  
 R/W 表示可以使用 **setvar** 命令修改值，并且后续命令将受新值的影响。  
  
## <a name="sqlcmd-commands"></a>sqlcmd 命令  
 除了中的 TRANSACT-SQL 语句**sqlcmd**，也有以下命令：  
  
|||  
|-|-|  
|**GO** [*count*]|**:List**|  
|[**:**] **RESET**|**:Error**|  
|[**:**] **ED**|**:Out**|  
|[**:**] **!!**|**:Perftrace**|  
|[**:**] **QUIT**|**:Connect**|  
|[**:**] **EXIT**|**:On Error**|  
|**:r**|**:Help**|  
|**:ServerList**|**:XML** [**ON** &#124; **OFF**]|  
|**:Setvar**|**:Listvar**|  
  
 使用 **sqlcmd** 命令时，请注意以下事项：  
  
-   除 GO 以外，所有 **sqlcmd** 命令必须以冒号 (:) 为前缀。  
  
    > [!IMPORTANT]  
    >  为了保持现有 **osql** 脚本的向后兼容性，有些命令会被视为不带冒号。 这由 [**:**] 指示。  
  
-   **sqlcmd** 命令只有出现在一行的开头时，才能够被识别。  
  
-   所有 **sqlcmd** 命令都不区分大小写。  
  
-   每个命令都必须位于单独的行中。 命令不能跟 TRANSACT-SQL 语句或另一个命令。  
  
-   命令将被立即执行。 它们不会放在执行缓冲区，如 TRANSACT-SQL 语句。  
  
 **编辑命令**  
  [**:**] **ED**  
 启动文本编辑器。 此编辑器可以用于编辑当前的 TRANSACT-SQL 批处理中，或最后一个执行批处理。 若要编辑上次执行的批处理，必须在上一批处理执行完之后立即键入 **ED** 命令。  
  
 文本编辑器由 SQLCMDEDITOR 环境变量定义。 默认编辑器为“Edit”。 若要更改编辑器，请设置 SQLCMDEDITOR 环境变量。 例如，若要在命令提示符下设置为 Microsoft 记事本的编辑器中，键入：  
  
 `SET SQLCMDEDITOR=notepad`  
  
 [**:**] **RESET**  
 清除语句缓存。  
  
 **:List**  
 输出语句缓存的内容。  
  
 **变量**  
  **:Setvar** \<**var**> [ **"***value***"** ]  
 定义 **sqlcmd** 脚本变量。 脚本变量具有如下格式： `$(VARNAME)`。  
  
 变量名称不区分大小写。  
  
 可以通过下列方式设置脚本变量：  
  
-   隐式使用命令行选项。 例如， **-l** 选项可设置 SQLCMDLOGINTIMEOUT **sqlcmd** 变量。  
  
-   显式使用 **:Setvar** 命令。  
  
-   在运行 **sqlcmd**之前定义一个环境变量。  
  
> [!NOTE]  
>  **-X** 选项可阻止将环境变量传递给 **sqlcmd**。  
  
 如果使用 **:Setvar** 定义的变量和某个环境变量同名，则使用 **:Setvar** 定义的变量优先。  
  
 变量名中不能包含空格字符。  
  
 变量名不能与变量表达式（如 $(var)）具有相同的形式。  
  
 如果脚本变量的字符串值中含有空格，请用引号将该值引起来。 如果未指定脚本变量的值，则将删除该脚本变量。  
  
 **:Listvar**  
 显示当前设置的脚本变量列表。  
  
> [!NOTE]  
>  只显示由 **sqlcmd**设置的脚本变量和使用 **:Setvar** 命令设置的脚本变量。  
  
 **输出命令**  
  **:Error**   
 ***\<***  *filename*  ***>|* STDERR|STDOUT**  
 将所有错误输出重定向到 *file name*指定的文件、 **stderr** 或 **stdout**。 **Error** 命令可以在一个脚本中多次出现。 默认情况下，错误输出将发送到 **stderr**。  
  
 *file name*  
 创建并打开一个要接收输出的文件。 若该文件已经存在，则将其截断为零字节。 若该文件不可用（由于权限或其他原因），将不会切换输出，也不会将输出发送到上次指定的目标或默认目标。  
  
 **STDERR**  
 将错误输出切换到 **stderr** 流。 如果已经重定向，流的重定向目标将会收到错误输出。  
  
 **STDOUT**  
 将错误输出切换到 **stdout** 流。 如果已经重定向，流的重定向目标将会收到错误输出。  
  
 **:Out \<** *filename* **>**| **STDERR**| **STDOUT**  
 创建所有查询结果并将它们重定向到 *file name*指定的文件、 **stderr** 或 **stdout**。 默认情况下，输出将发送到 **stdout**。 若该文件已经存在，则将其截断为零字节。 **Out** 命令可以在一个脚本中多次出现。  
  
 **:Perftrace \<** *filename* **>**| **STDERR**| **STDOUT**  
 创建所有性能跟踪信息并将它们重定向到 *file name*指定的文件、 **stderr** 或 **stdout**。 默认情况下，性能跟踪输出将发送到 **stdout**。 若该文件已经存在，则将其截断为零字节。 **Perftrace** 命令可以在一个脚本中多次出现。  
  
 **执行控制命令**  
  **:On Error**[ **exit** | **ignore**]  
 设置在脚本或批处理执行过程中发生错误时要执行的操作。  
  
 使用 **exit** 选项时， **sqlcmd** 退出，并显示相应的错误值。  
  
 使用 **ignore** 选项时， **sqlcmd** 会忽略错误，并继续执行批处理或脚本。 默认情况下，会输出错误消息。  
  
 [**:**] **QUIT**  
 导致 **sqlcmd** 退出。  
  
 [**:**] **EXIT**[ **(***statement***)** ]  
 允许将 SELECT 语句的结果用作 **sqlcmd**的返回值。 如果为数值，最后一个结果行的第一列将转换为 4 字节的整数（长整型）。 MS-DOS 将低字节传递给父进程或操作系统错误级别。 Windows 200x 传递整个 4 字节整数。 语法为：  
  
 `:EXIT(query)`  
  
 例如：  
  
 `:EXIT(SELECT @@ROWCOUNT)`  
  
 您还可以在批处理文件中包含 **EXIT** 参数。 例如，在命令提示符处键入：  
  
 `sqlcmd -Q "EXIT(SELECT COUNT(*) FROM '%1')"`  
  
 使用 **sqlcmd** 实用工具将圆括号 **()** 中的所有内容发送给服务器。 如果系统存储过程选择了一个集合并返回一个值，则仅返回选择的内容。 如果圆括号中没有任何内容，则 EXIT**()** 语句会执行批处理中此语句前的所有内容，然后退出，且不返回任何值。  
  
 当指定了不正确的查询时， **sqlcmd** 将退出，且不返回任何值。  
  
 下面是 EXIT 格式的列表：  
  
-   :EXIT  
  
 不执行批处理就立即退出，无返回值。  
  
-   :EXIT( )  
  
 执行批处理后退出，不返回值。  
  
-   :EXIT(query)  
  
 执行包括查询的批处理，返回查询的结果后退出。  
  
 如果在 **sqlcmd** 脚本中使用 RAISERROR，并且出现状态 127，则 **sqlcmd** 将退出，并将消息 ID 返回给客户端。 例如：  
  
 `RAISERROR(50001, 10, 127)`  
  
 该错误会导致 **sqlcmd** 脚本终止并将消息 ID 50001 返回给客户端。  
  
 返回值为-1 到-99 保留了 SQL Server;**sqlcmd**定义以下的其他返回值：  
  
|返回值|Description|  
|-------------------|-----------------|  
|-100|选择返回值前遇到错误。|  
|-101|选择返回值时找不到行。|  
|-102|选择返回值时发生转换错误。|  
  
 **GO** [*count*]  
 转到发出信号，这两个批的末尾，并执行任何缓存 TRANSACT-SQL 语句。作为单独的批处理文件; 多次执行批处理不能在单个批处理中多次声明变量。
  
 **其他命令**  
  **:r \<** *filename***>**  
 分析其他 TRANSACT-SQL 语句和**sqlcmd**从指定的文件的命令 **\<**  *filename***>**到语句缓存。  
  
 如果该文件包含不跟的 TRANSACT-SQL 语句**转**，必须输入**转**后面的行上**: r**。  
  
> [!NOTE]  
>  系统会相对于 **sqlcmd** 在其中运行的启动目录读取 **\<** *filename* **>**。  
  
 当遇到批处理终止符之后，将读取并执行该文件。 可以发出多个 **:r** 命令。 该文件可以包含任何 **sqlcmd** 命令， 包括批处理终止符 **GO**。  
  
> [!NOTE]  
>  每遇到一个 **:r** 命令，交互模式下显示的行计数都会加一。 **:r** 命令会出现在 list 命令的输出中。  
  
 **:Serverlist**  
 列出在本地配置的服务器和在网络上广播的服务器的名称。  
  
 **:Connect**  *server_name*[**\\***instance_name*] [-l *timeout*] [-U *user_name* [-P *password*]]  
 连接到 SQL Server 的实例。 同时关闭当前的连接。  
  
 超时选项：  
  
|||  
|-|-|  
|0|永远等待|  
|n>0|等待 n 秒钟|  
  
 SQLCMDSERVER 脚本变量将反映当前的活动连接。  
  
 如果未指定 *timeout* ，则其默认值将为 SQLCMDLOGINTIMEOUT 变量的值。  
  
 仅当指定了 *user_name* （作为选项或环境变量）时，才会提示用户输入密码。 如果已设置 SQLCMDUSER 或 SQLCMDPASSWORD 环境变量，则不会出现此提示。 如果既未提供选项，又未提供环境变量，则使用 Windows 身份验证模式登录。 例如，若要连接到的实例， `instance1`，SQL server `myserver`，通过使用集成的安全性，你将使用以下：  
  
 `:connect myserver\instance1`  
  
 若要使用脚本变量连接到 `myserver` 的默认实例，您会使用以下内容：  
  
 `:setvar myusername test`  
  
 `:setvar myservername myserver`  
  
 `:connect $(myservername) $(myusername)`  
  
 [**:**] **!!**< *command*>  
 执行操作系统命令。 若要执行操作系统命令，请用两个感叹号 (**!!**) 开始一行，后面输入操作系统命令。 例如：  
  
 `:!! Dir`  
  
> [!NOTE]  
>  该命令在运行 **sqlcmd** 的计算机上执行。  
  
 **:XML** [**ON** | **OFF**]  
 有关详细信息，请参阅本主题中的 [XML 输出格式](#OutputXML) 和 [JSON 输出格式](#OutputJSON)  
  
 **:Help**  
 列出 **sqlcmd** 命令以及每个命令的简短说明。  
  
### <a name="sqlcmd-file-names"></a>sqlcmd 文件名  
 可以使用**sqlcmd** 选项或 **sqlcmd** 命令指定 **sqlcmd** 输入文件。 可以使用 **-o** 选项或 **:Error**、 **:Out** 和 **:Perftrace** 命令指定输出文件。 以下是使用这些文件的一些原则：  
  
-   **:Error**、 **:Out** 和 **:Perftrace** 应使用不同的 **\<***filename***>**。 如果使用了相同的 **\<***filename***>** ，这些命令的输入可能会混杂在一起。  
  
-   如果从本地计算机的 **sqlcmd** 调用远程服务器上的输入文件，并且该文件包含驱动器文件路径（如 :out c:\OutputFile.txt）， 将在本地计算机而不是远程服务器上创建输出文件。  
  
-   有效文件路径包括： `C:\<filename>`、 `\\<Server>\<Share$>\<filename>` 和 `"C:\Some Folder\<file name>"`。 如果路径中包含空格，请使用引号。  
  
-   每个新的 **sqlcmd** 会话都将覆盖现有的同名文件。  
  
### <a name="informational-messages"></a>信息性消息  
 **sqlcmd** 将输出由服务器发送的所有信息性消息。 在以下示例中，执行 TRANSACT-SQL 语句后，一条信息性消息都将打印。  
  
 在命令提示符下键入以下内容：  
  
 `sqlcmd`  
  
 `At the sqlcmd prompt type:`  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 按下 Enter 时，会输出以下信息性消息：“已将数据库上下文改为 'AdventureWorks2012'。”  
  
### <a name="output-format-from-transact-sql-queries"></a>Transact-SQL 查询的输出格式  
 **sqlcmd** 首先输出列标题，其中包含在选择列表中指定的列名。 列名使用 SQLCMDCOLSEP 字符分隔。 默认情况下，将使用空格。 如果列名短于列宽，则使用空格填充输出，直到下一列。  
  
 此行将跟随一行分隔行，分隔行是一系列的破折号字符。 以下输出显示了一个示例。  
  
 启动 **sqlcmd**。 在 **sqlcmd** 命令提示符下键入以下命令：  
  
 `USE AdventureWorks2012;`  
  
 `SELECT TOP (2) BusinessEntityID, FirstName, LastName`  
  
 `FROM Person.Person;`  
  
 `GO`  
  
 按下 Enter 时，会返回以下结果集。  
  
 `BusinessEntityID FirstName    LastName`  
  
 `---------------- ------------ ----------`  
  
 `285              Syed         Abbas`  
  
 `293              Catherine    Abel`  
  
 `(2 row(s) affected)`  
  
 虽然 `BusinessEntityID` 列只有 4 个字符宽，但已将其扩展以适应更长的列名。 默认情况下，输出会在 80 个字符处终止。 可通过使用 **-w** 选项或设置 SQLCMDCOLWIDTH 脚本变量来进行更改。  
  
###  <a name="OutputXML"></a> XML 输出格式  
 从 FOR XML 子句得到的 XML 输出是在连续流中的未格式化的输出。  
  
 若要得到 XML 输出，请使用以下命令： `:XML ON`。  
  
> [!NOTE]  
>  **sqlcmd** 将采用常见的格式返回错误消息。 请注意，XML 文本流中的错误消息还将采用 XML 格式输出。 如果使用 `:XML ON`，则 **sqlcmd** 不显示信息性消息。  
  
 若要关闭 XML 模式，请使用以下命令： `:XML OFF`。  
  
 发出 XML OFF 命令之前不应显示 GO 命令，因为 XML OFF 命令会将 **sqlcmd** 切换回面向行的输出。  
  
 XML（流形式）数据和行集数据不能混合。 如果未执行输出 XML 流的 TRANSACT-SQL 语句之前发出 XML ON 命令，则输出将为乱码。 如果已发出 XML ON 命令，则无法执行输出常规行集的 TRANSACT-SQL 语句。  
  
> [!NOTE]  
>  **:XML** 命令不支持 SET STATISTICS XML 语句。  
  
###  <a name="OutputJSON"></a> JSON 输出格式  
 若要得到 JSON 输出，请使用以下命令： `:XML ON`。 否则，输出包括的列名和 JSON 文本。 此输出不是有效的 JSON。  
  
 若要关闭 XML 模式，请使用以下命令： `:XML OFF`。  
  
 有关详细信息，请参阅本主题中的 [XML 输出格式](#OutputXML) 。  

### <a name="using-azure-active-directory-authentication"></a>使用 Azure Active Directory 身份验证  
使用 Azure Active Directory 身份验证的示例：
```
sqlcmd -S Target_DB_or_DW.testsrv.database.windows.net  -G  -l 30
sqlcmd -S Target_DB_or_DW.testsrv.database.windows.net -U bob@contoso.com -P MyAADPassword -G -l 30
```
  
## <a name="sqlcmd-best-practices"></a>sqlcmd 最佳方法  
 使用以下方法来帮助实现最高的安全性和效率。  
  
-   使用集成安全性。  
  
-   在自动化环境中使用 **-X** 。  
  
-   使用适当的 NTFS 文件系统权限保护输入文件和输出文件。  
  
-   若要提高性能，请在一个 **sqlcmd** 会话中执行尽可能多的操作，而不是在一系列会话中来执行这些操作。  
  
-   将批处理或查询执行的超时值设置为大于您所预期的值。  
  
## <a name="see-also"></a>另请参阅  
 [启动 sqlcmd 实用工具](~/relational-databases/scripting/sqlcmd-start-the-utility.md)   
 [使用 sqlcmd 运行 Transact-SQL 脚本文件](~/relational-databases/scripting/sqlcmd-run-transact-sql-script-files.md)   
 [使用 sqlcmd 实用工具](~/relational-databases/scripting/sqlcmd-use-the-utility.md)   
 [将 sqlcmd 与脚本变量结合使用](~/relational-databases/scripting/sqlcmd-use-with-scripting-variables.md)   
 [使用 sqlcmd 连接到数据库引擎](~/relational-databases/scripting/sqlcmd-connect-to-the-database-engine.md)   
 [使用查询编辑器编辑 SQLCMD 脚本](~/relational-databases/scripting/edit-sqlcmd-scripts-with-query-editor.md)   
 [管理作业步骤](~/ssms/agent/manage-job-steps.md)   
 [创建 CmdExec 作业步骤](~/ssms/agent/create-a-cmdexec-job-step.md)  
  
  









