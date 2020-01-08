---
title: 'Lync Server 2013: Lync Server 管理シェルを使用したデータベースのインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: deac68fb5f20066632bc48a9e9b6244a9bd34fe9
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a>Lync Server 2013 での Lync Server 管理シェルを使用したデータベースのインストール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-06-16_

サーバー管理者と SQL Server 管理者との間で役割と責任を分離すると、実装で遅延が発生する可能性があります。 Lync Server 2013 は、役割ベースのアクセス制御 (RBAC) を使用して、このような問題を軽減します。 場合によっては、SQL Server 管理者が、RBAC の外部の SQL Server ベースのサーバーにデータベースのインストールを管理する必要があります。 Lync Server 2013 管理シェルは、SQL Server 管理者が Windows PowerShell コマンドレットを実行して、適切なデータとログファイルを使ってデータベースを構成するための手段を提供します。 詳細については、「 [Lync server 2013 の SQL Server の展開権限](lync-server-2013-deployment-permissions-for-sql-server.md)」を参照してください。

<div class=" ">


> [!IMPORTANT]  
> 次の手順では、少なくとも Lync Server 2013 OCSCore .msi、SQL Server Native Client (sqlncli) Microsoft SQL server 2012 の管理オブジェクト、Microsoft sql Server 2012 および Microsoft SQL Server 2012 ADOMD.NET の CLR 型がインストールされていることを前提としています。 OCSCore .msi は、インストールメディアの \Setup\AMD64\Setup ディレクトリにあります。 残りのコンポーネントは、「¥の場合」に記載されています。 さらに、Lync Server 2013 の Active Directory の準備が正常に完了しました。



</div>

**CsDatabase をインストール**すると、データベースのインストールに使用する Windows PowerShell コマンドレットが表示されます。 **CsDatabase**コマンドレットには、多数のパラメーターがあります。一部のパラメーターはここで説明しています。 使用可能なパラメーターの詳細については、「Lync Server 2013 管理シェルのドキュメント」を参照してください。

<div class=" ">


> [!WARNING]  
> パフォーマンスが低下したり、タイムアウトの問題が発生したりする場合は、SQL Server ベースのサーバーを参照するときに常に完全修飾ドメイン名 (Fqdn) を使用します。 ホスト名のみの参照を使用しないでください。 たとえば、sqlbe01.contoso.net を使用しますが、SQLBE01 の使用は避けてください。



</div>

データベースをインストールするには、 **CsDatabase をインストール**するために、準備された SQL server ベースのサーバーにデータベースを配置するために、3つの主な方法を使用します。

  - DatabasePaths または UseDefaultSqlPath なしで **、CsDatabase を**実行します。 このコマンドレットは、組み込みのアルゴリズムを使って、ログファイルとデータファイルの最適な配置を決定します。 このアルゴリズムは、スタンドアロンの SQL Server 実装でのみ動作します。

  - DatabasePaths パラメーターを使用して**CsDatabase Install**を実行します。 DatabasePaths パラメーターが定義されている場合、ログとデータファイルの場所を最適化する組み込みアルゴリズムは使用されません。 このパラメーターを使うと、ログとデータファイルが配置される場所を定義できます。

  - UseDefaultSqlPaths で**CsDatabase Install**を実行します。 このオプションでは、組み込みのアルゴリズムを使ってログとデータファイルの場所を最適化しません。 ログとデータファイルは、SQL Server 管理者が設定した既定値に従って展開されます。 通常、これらのパスは、SQL Server のログファイルとデータファイルの自動管理を目的として設定され、Lync Server 2013 のセットアップには関連付けられません。

  - DatabasePathMap パラメーターを使って、各データベースとそのログファイルの場所を明示的に指定することもできます。

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a>Windows PowerShell コマンドレットを使用して SQL Server の中央管理ストアを構成するには

1.  任意のコンピューターで、SQL Server ベースのサーバー上でデータベースを作成するための管理者資格情報を使ってログオンします。 詳細については、「 [Lync server 2013 の SQL Server の展開権限](lync-server-2013-deployment-permissions-for-sql-server.md)」を参照してください。

2.  Lync Server 2013 管理シェルを開きます。 Windows PowerShell の実行ポリシーを調整していない場合は、Windows PowerShell スクリプトの実行を許可するようにポリシーを調整する必要があります。 詳細については、の「実行ポリシーを[http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093)調査する」を参照してください。

3.  [**インストール-CsDatabase**コマンドレットを使用して、中央管理ストアをインストールします。
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
        -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > Report パラメーターは省略可能ですが、インストールプロセスを文書化する場合に便利です。

    
    </div>

4.  **CsDatabase-DatabasePaths**では、最大6つの path パラメーターを使うことができます。それぞれ、SQL Server データとログファイルの配置で定義されたドライブのパスを定義します。 Lync Server 2013 のデータベース構成の論理的なルールにより、ドライブは2、4、または6のバケットに分けて解析されます。 SQL Server の構成とバケット数に応じて、2つのパス、4つのパス、または6つのパスを指定します。
    
    3つのドライブがある場合は、ログが優先され、データファイルは後で配布されます。 6台のドライブで構成された SQL Server ベースのサーバーの例:
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  データベースのインストールが完了したら、Lync Server 2013 管理シェルを閉じるか、またはトポロジビルダーで定義されている Lync Server 2013 構成データベースのインストールに進みます。

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a>Windows PowerShell コマンドレットを使用して、SQL Server トポロジで構成されたデータベースを構成するには

1.  Lync server 2013 用にトポロジビルダーで構成されたデータベースをインストールするには、Lync Server 2013 管理者がトポロジを公開する必要があります。 詳細については、展開ドキュメントの「 [Lync Server 2013 でトポロジを発行](lync-server-2013-publish-the-topology.md)する」を参照してください。

2.  任意のコンピューターで、SQL Server ベースのサーバー上でデータベースを作成するための管理者資格情報を使ってログオンします。 「 [Lync server 2013 の SQL Server の展開権限](lync-server-2013-deployment-permissions-for-sql-server.md)」のトピックを参照してください。
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > SQL Server ベースのデータベースを構成できるようにするには、ここで説明する手順を実行するために使用した SQL Server 管理者アカウントも、SQL Server を実行しているサーバー上の管理者グループ (または同等の機能) のメンバーであることを確認して、一元管理を保持する必要があります。サーバーの役割。 これは、SQL Server のデータベースのインストールまたは構成が必要な追加の Lync Server 2013 プールを確認する場合に特に重要です。 たとえば、2つ目のプール (pool02) を展開しているが、サーバーの全体管理サーバーの役割が pool01 によって保持されている場合です。 Sql Server sysadmin グループ (または同等の機能) には、SQL Server ベースの両方のデータベースに対するアクセス許可が必要です。

    
    </div>

3.  まだ開いていない場合は、Lync Server 2013 管理シェルを開きます。

4.  **CsDatabase**コマンドレットを使用して、トポロジビルダーで構成されたデータベースをインストールします。
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
         -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > Report パラメーターは省略可能ですが、インストールプロセスを文書化する場合に便利です。

    
    </div>

5.  データベースのインストールが完了したら、Lync Server 2013 Management Shell を閉じます。

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a>Windows PowerShell コマンドレットを使用して、DatabasePathMap パラメーターを使って SQL Server トポロジを構成するには

1.  Lync server 2013 のデータベースをインストールするには、Lync Server の管理者が、パスを作成し、事前定義された一連のルールに従ってデータベースファイルとログファイルを展開する必要があります。

2.  任意のコンピューターで、SQL Server ベースのサーバー上でデータベースを作成するための管理者資格情報を使ってログオンします。 「 [Lync server 2013 の SQL Server の展開権限](lync-server-2013-deployment-permissions-for-sql-server.md)」のトピックを参照してください。
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > SQL Server ベースのデータベースを構成できるようにするには、ここで説明する手順を実行するために使用した SQL Server 管理者アカウントも、SQL Server を実行しているサーバー上の管理者グループ (または同等の機能) のメンバーであることを確認して、一元管理を保持する必要があります。サーバーの役割。 これは、SQL Server データベースのインストールまたは構成が必要な追加の Lync Server プールを確認する場合に特に重要です。 たとえば、2つ目のプール (pool02) を展開しているが、サーバーの全体管理サーバーの役割が pool01 によって保持されている場合です。 Sql Server sysadmin グループ (または同等の機能) には、SQL Server ベースの両方のデータベースに対するアクセス許可が必要です。

    
    </div>

3.  まだ開いていない場合は、Lync Server 管理シェルを開きます。

4.  DatabasePathMap パラメーターと PowerShell ハッシュテーブルを使って、 **CsDatabase**コマンドレットを使用して、トポロジビルダーで構成されたデータベースをインストールします。

5.  このコード例では、データベースに対して定義されているパスは、– DatabasePathMap パラメーターと定義されたハッシュテーブル (すべてのデータベース (.mdf) ファイルの場合\\は "c: csdata"、すべてのログ (.ldf) ファイルに\\ついては "c: csdata" を使用します) を使って特定できます。 必要に応じて、CsDatabase からフォルダーを作成します):
    ```powershell
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="C:\CsData";"BackendStore:BlobStore:LogPath"="C:\CsLogFiles"
    "BackendStore:RtcSharedDatabase:DbPath"="C:\CsData";"BackendStore:RtcSharedDatabase:LogPath"="C:\CsLogFiles"
    "ABSStore:AbsDatabase:DbPath"="C:\CsData";"ABSStore:AbsDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsConfigDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsConfigDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsDynDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:CpsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:CpsDynDatabase:LogPath"="C:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="C:\CsData";"ArchivingStore:ArchivingDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:MonitoringDatabase:DbPath"="C:\CsData";"MonitoringStore:MonitoringDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="C:\CsData";"MonitoringStore:QoEMetricsDatabase:LogPath"="C:\CsLogFiles"
    }
    Install-CsDatabase -ConfigureDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
6.  データベースとログファイルには、ターゲットデータベースサーバー上の場所と共に明示的に名前が付けられているため、サービスの種類ごとに実際のデータベースとログの場所の特定の場所を定義できます。 次の例では、特定のサービスの種類ごとにデータベースを別々のディスクに配置し、関連するログファイルを別のディスクに配置します。 次に例を示します。
    
      - すべての RTC データベースの "D\\: rtcdatabase"
    
      - "E:\\rtclogs" のすべての RTC ログファイル
    
      - すべてのアプリケーションストアデータベースを "F\\: cpsdatabases" に保存する
    
      - すべてのアプリケーションストアログを "G\\: cpslogs" に記録する
    
      - すべての応答グループストアデータベースの "H\\: RGSDatabases"
    
      - すべての応答グループは、"I:\\RGSLogs" に記録します。
    
      - すべてのアドレス帳ストアデータベースを "J\\: ABSDatabases" にする
    
      - すべてのアドレス帳ストアのログファイルを "\\K: ABSLogs" に保存します。
    
      - "L:\\ArchivingDatabases" のすべてのアーカイブストアデータベース
    
      - すべてのアーカイブストアログは "M\\: ArchivingLogs" になります。
    
      - すべての監視ストアデータベースを "N\\: monitoringdatabases" に保存する
    
      - すべての監視ストアのログファイルを "\\O: monitoringlogfiles monitoringlogfiles" に保存する
    
    <!-- end list -->
    
    ```powershell    
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="D:\RTCDatabase";"BackendStore:BlobStore:LogPath"="E:\RTCLogs"
    "BackendStore:RtcSharedDatabase:DbPath"="D:\RTCDatabase";"BackendStore:RtcSharedDatabase:LogPath"="E:\RTCLogs"
    "ABSStore:AbsDatabase:DbPath"="J:\ABSDatabases";"ABSStore:AbsDatabase:LogPath"="K:\ABSLogs"
    "ApplicationStore:RgsConfigDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsConfigDatabase:LogPath"="G:\CPSLogs"
    "ApplicationStore:RgsDynDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsDynDatabase:LogPath"="I:\RGSLogs"
    "ApplicationStore:CpsDynDatabase:DbPath"="F:\CPSDatabases";"ApplicationStore:CpsDynDatabase:LogPath"="G:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="M:\ArchivingLogs";"ArchivingStore:ArchivingDatabase:LogPath"="N:\MonitoringDatabases"
    "MonitoringStore:MonitoringDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:MonitoringDatabase:LogPath"="O:\MonitoringLogfiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:QoEMetricsDatabase:LogPath"="O:\MonitoringLogfiles"
    }
    
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
    
    – DatabasePathMap パラメーターを使用すると、SQL Server のパフォーマンスと配置の要件に最適なソリューションを提供する論理ドライブ文字のマッピングの組み合わせを定義できます。

**DatabasePathMap**メソッドを使用してデータベースデータファイルとログファイルを構成する場合は、トポロジビルダーを使用するときに、通常のプロセスに若干の変更を加える必要があります。 通常は、トポロジの選択肢を定義し、トポロジを公開して、選択したデータベースを展開します。

**DatabasePathMap**を使ったことがある場合は、既にトポロジビルダープロセスの3番目の部分を完了しています。 トポロジビルダーの実行前に完全に構成されたデータベースサーバーがある場合は、すべてのサーバーの役割とオプションを定義したままで、データベースを作成するオプションの選択を解除します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

