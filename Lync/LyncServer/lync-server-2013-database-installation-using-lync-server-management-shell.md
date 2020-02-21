---
title: 'Lync Server 2013: Lync Server 管理シェルを使用したデータベースのインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 443f353a43c2fdfd2f9fc8c7ce1a1b20c11a4a84
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a>Lync Server 2013 での Lync Server 管理シェルを使用したデータベースインストール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-06-16_

サーバーの管理者と SQL Server 管理者の間で役割と責任を分割すると、実装で遅延が生じる可能性があります。 Lync Server 2013 は、役割ベースのアクセス制御 (RBAC) を使用してこれらの問題を軽減します。 場合によっては、SQL Server 管理者は、RBAC の外部で SQL Server ベース サーバーでのデータベースのインストールを管理する必要があります。 Lync Server 2013 管理シェルは、SQL Server 管理者が、適切なデータおよびログファイルを使用してデータベースを構成するために設計された Windows PowerShell コマンドレットを実行できるようにします。 詳細については、「 [Lync server 2013 の SQL Server の展開権限](lync-server-2013-deployment-permissions-for-sql-server.md)」を参照してください。

<div class=" ">


> [!IMPORTANT]  
> 次の手順では、少なくとも Lync Server 2013 OCSCore .msi、SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 管理オブジェクト、Microsoft SQL Server 2012 および Microsoft SQL Server 2012 ADOMD.NET の CLR 型がインストールされていることを前提としています。 OCSCore.msi は、インストール メディアの \Setup\AMD64\Setup ディレクトリにあります。 残りのコンポーネントは、\ が含まれています。 さらに、Lync Server 2013 の Active Directory の準備が正常に完了しました。



</div>

**Install-CsDatabase**は、データベースのインストールに使用する Windows PowerShell コマンドレットです。 **Install-CsDatabase** コマンドレットには数多くのパラメーターがありますが、ここではその一部についてのみ説明します。 使用可能なパラメーターの詳細については、「Lync Server 2013 Management Shell」のドキュメントを参照してください。

<div class=" ">


> [!WARNING]  
> パフォーマンスの問題と考えられるタイムアウトの問題を防止するため、SQL Server ベースのサーバーを参照するときには、必ず完全修飾ドメイン名 (FQDN) を使用してください。 ホスト名のみの参照は使用しないでください。 たとえば、sqlbe01.contoso.net を使用しますが、SQLBE01 は使用しないでください。



</div>

データベースをインストールするには、を**インストール**するには、データベースを準備した SQL server ベースのサーバーに配置するための3つの主な方法を使用します。

  - DatabasePaths または UseDefaultSqlPath なしで **Install-CsDatabase** を実行します。 このコマンドレットは、組み込みアルゴリズムを使用して、ログおよびデータ ファイルの最善の配置方法を決定します。 このアルゴリズムは、スタンドアロンの SQL Server 実装に対してのみ機能します。

  - DatabasePaths パラメーターを指定して **Install-CsDatabase** を実行します。 DtabasePaths パラメーターが定義されている場合、ログおよびデータ ファイルの場所を最適化する組み込みアルゴリズムは使用されません。 このパラメーターを使用すると、ログおよびデータ ファイルを展開する場所を定義できます。

  - UseDefaultSqlPaths を指定して **Install-CsDatabase** を実行します。 このオプションでは、組み込みアルゴリズムを使用してログおよびデータ ファイルの場所を最適化しません。 ログおよびデータ ファイルは、SQL Server 管理者が設定する既定値に従って展開されます。 これらのパスは、通常、SQL Server 上のログおよびデータファイルを事前に自動管理する目的で設定されており、Lync Server 2013 のセットアップには関連付けられていません。

  - DatabasePathMap パラメーターを使用して、各データベースおよびそれぞれのログファイルの場所を明示的に指定することもできます。

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a>Windows PowerShell コマンドレットを使用して SQL Server 中央管理ストアを構成するには

1.  任意のコンピューターで、SQL Server ベースのサーバーでデータベースを作成するための管理資格情報を使用してログオンします。 詳細については、「 [Lync server 2013 の SQL Server の展開権限](lync-server-2013-deployment-permissions-for-sql-server.md)」を参照してください。

2.  Lync Server 2013 管理シェルを開きます。 Windows PowerShell の実行ポリシーを調整していない場合は、Windows PowerShell スクリプトの実行を許可するようにポリシーを調整する必要があります。 詳細については、「」の「実行[https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093)ポリシーを調べる」を参照してください。

3.  中央管理ストアをインストールするには、**インストール-CsDatabase**コマンドレットを使用します。
    
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
    > Report パラメーターはオプションですが、インストール プロセスを文書化する場合に役立ちます。

    
    </div>

4.  **Install-CsDatabase – DatabasePaths**は最大6つのパスパラメーターを使用できます。各パラメーターには、SQL Server データとログファイルの配置で定義されたドライブのパスを定義します。 Lync Server 2013 のデータベース構成の論理ルールによって、ドライブは2、4、または6のバケットで解析されます。 SQL Server の構成とバケット数に応じて、2つのパス、4つのパス、または6つのパスを指定します。
    
    ドライブが 3 つの場合は、ログに優先順位が付けられ、データ ファイルはその優先順位に従って配布されます。 6つのドライブを使用して構成された SQL Server ベースのサーバーの例を次に示します。
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  データベースのインストールが完了したら、Lync Server 2013 管理シェルを閉じるか、またはトポロジビルダーで定義された Lync Server 2013 構成済みデータベースのインストールに進むことができます。

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a>Windows PowerShell コマンドレットを使用して SQL Server トポロジ構成のデータベースを構成するには

1.  Lync server 2013 のトポロジビルダー構成データベースをインストールするには、Lync Server 2013 管理者がトポロジを公開する必要があります。 詳細については、「展開」のドキュメントの「 [Publish the topology In Lync Server 2013](lync-server-2013-publish-the-topology.md) 」を参照してください。

2.  任意のコンピューターで、SQL Server ベースのサーバーでデータベースを作成するための管理資格情報を使用してログオンします。 「 [Lync server 2013 の SQL Server の展開権限](lync-server-2013-deployment-permissions-for-sql-server.md)」を参照してください。
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > SQL Server ベースのデータベースを構成できるようにするには、sql server を実行しているサーバーの管理者グループ (または同等のもの) のメンバーであることを確認してください。サーバーの役割。 これは、SQL Server データベースのインストールまたは構成を必要とする追加の Lync Server 2013 プールがあるかどうかを確認する場合に特に重要です。 たとえば、2番目のプール (pool02) を展開している場合に、中央管理サーバーの役割が pool01 によって保持されているとします。 SQL server の sysadmin グループ (または同等のもの) は、両方の SQL Server ベースのデータベースに対する権限を持っている必要があります。

    
    </div>

3.  まだ開いていない場合は、Lync Server 2013 管理シェルを開きます。

4.  トポロジビルダーによって構成されたデータベースをインストールするには、コマンドレットの**インストール**を使用します。
    
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
    > Report パラメーターはオプションですが、インストール プロセスを文書化する場合に役立ちます。

    
    </div>

5.  データベースのインストールが完了したら、Lync Server 2013 管理シェルを閉じます。

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a>Windows PowerShell コマンドレットを使用して SQL Server トポロジを構成するには、DatabasePathMap パラメーターを使用します。

1.  Lync server 2013 のデータベースをインストールするには、Lync Server 管理者がパスを作成し、定義済みのルールセットに従ってデータベースファイルとログファイルを展開する必要があります。

2.  任意のコンピューターで、SQL Server ベースのサーバーでデータベースを作成するための管理資格情報を使用してログオンします。 「 [Lync server 2013 の SQL Server の展開権限](lync-server-2013-deployment-permissions-for-sql-server.md)」を参照してください。
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > SQL Server ベースのデータベースを構成できるようにするには、sql server を実行しているサーバーの管理者グループ (または同等のもの) のメンバーであることを確認してください。サーバーの役割。 これは、SQL Server データベースのインストールまたは構成を必要とする追加の Lync Server プールがあるかどうかを確認する場合に特に重要です。 たとえば、2番目のプール (pool02) を展開している場合に、中央管理サーバーの役割が pool01 によって保持されているとします。 SQL server の sysadmin グループ (または同等のもの) は、両方の SQL Server ベースのデータベースに対する権限を持っている必要があります。

    
    </div>

3.  まだ開いていない場合は、Lync Server 管理シェルを開きます。

4.  トポロジビルダーで構成されたデータベースをインストールするには、DatabasePathMap パラメーターと PowerShell ハッシュテーブルを使用して、**インストール-CsDatabase**コマンドレットを使用します。

5.  このコード例では、-DatabasePathMap パラメーターと定義済みのハッシュテーブルを次のように使用して、データベースに対して定義されているパスを詳細に判断\\できます (例では、すべてのデータベース (.mdf) ファイルに "\\c: csdata"、すべてのログ (.ldf) ファイルの "c: csdata" を使用します) フォルダーは、必要に応じて、-CsDatabase をインストールすることによって作成されます。
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
6.  データベースとログファイルには、移動先のデータベースサーバー上の場所が明示的に指定されているため、サービスの種類ごとに固有のデータベースとログの場所を定義できます。 次の例では、個別のディスク上の特定のサービスタイプごとにデータベースを配置し、関連するログファイルを別のディスクに格納します。 次に例を示します。
    
      - "D:\\rtcdatabase" のすべての RTC データベース
    
      - すべての RTC ログファイルから "E\\: rtclogs" へ
    
      - すべてのアプリケーションストアデータベースを "F\\: cpsdatabases" にする
    
      - すべてのアプリケーションストアのログを "\\G: cpslogs" にする
    
      - すべての応答グループストアデータベースを "H\\: RGSDatabases" にします。
    
      - "I:\\RGSLogs" へのすべての応答グループストアログ
    
      - すべてのアドレス帳ストアデータベースを "J\\: ABSDatabases" にする
    
      - すべてのアドレス帳ストアのログファイルを "\\K: ABSLogs" に
    
      - すべてのアーカイブストアデータベースを "L\\: ArchivingDatabases" にする
    
      - すべてのアーカイブストアログを "M\\: ArchivingLogs" にします。
    
      - すべての監視ストアデータベースを "N\\: monitoringdatabases" にする
    
      - すべての監視ストアのログファイルを "\\O: monitoringlogfiles" にします。
    
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
    
    – DatabasePathMap パラメーターを使用すると、SQL Server のパフォーマンスと配置の要件に最適なソリューションを提供する任意の論理ドライブ文字マッピングの組み合わせを定義できます。

**DatabasePathMap**メソッドを使用してデータベースデータファイルとログファイルを構成する場合は、トポロジビルダーを使用しているときに通常のプロセスに少し変更を加える必要があります。 通常は、トポロジの選択を定義し、トポロジを公開して、データベースの選択を展開します。

**DatabasePathMap**を使用した場合は、トポロジビルダープロセスの3番目の部分が既に完了しています。 トポロジビルダーを実行する前に、完全に構成されたデータベースサーバーがある場合は、すべてのサーバーの役割とオプションを定義しますが、データベースを作成するためのオプションの選択を解除します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

