---
title: 'Lync Server 2013: Lync Server 管理シェルを使用したデータベースのインストール'
TOCTitle: Lync Server 管理シェルを使用したデータベースのインストール
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48273554
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Lync Server 管理シェルを使用したデータベースのインストール

 

_**トピックの最終更新日:** 2016-12-08_

サーバーの管理者と SQL Server 管理者の間で役割と責任を分割すると、実装で遅延が生じる可能性があります。Lync Server 2013 は、役割ベースのアクセス制御 (RBAC) を使用してこれらの問題を軽減します。場合によっては、SQL Server 管理者は、RBAC の外部で SQL Server ベース サーバーでのデータベースのインストールを管理する必要があります。Lync Server 2013 管理シェルでは、SQL Server 管理者は、正しいデータおよびログ ファイルを使用してデータベースを構成する Windows PowerShell コマンドレットを実行できます。詳細については、「[Lync Server 2013 の SQL Server の展開のアクセス許可](lync-server-2013-deployment-permissions-for-sql-server.md)」を参照してください。


> [!IMPORTANT]
> 次の手順では、最低でも Lync Server 2013 OCSCore.msi、SQL Server Native Client (sqlncli.msi)、Microsoft SQL Server 2012 Management Objects、CLR Types for Microsoft SQL Server 2012、および Microsoft SQL Server 2012 ADOMD.NET がインストールされていることを想定しています。OCSCore.msi は、インストール メディアの \Setup\AMD64\Setup ディレクトリにあります。その他のコンポーネントは、\Setup\amd64 にあります。また、 Lync Server 2013 を使用するための Active Directory の準備も正常に行われていると想定しています。



**Install-CsDatabase** は、データベースのインストールに使用する Windows PowerShell コマンドレットです。**Install-CsDatabase** コマンドレットには数多くのパラメーターがありますが、ここではその一部についてのみ説明します。使用可能なパラメーターの詳細については、Lync Server 2013 管理シェルのドキュメントを参照してください。


> [!WARNING]
> パフォーマンスの問題と考えられるタイムアウトの問題を防止するため、SQL Server ベースのサーバーを参照するときには、必ず完全修飾ドメイン名 (FQDN) を使用してください。ホスト名のみの参照は使用しないでください。たとえば、sqlbe01.contoso.net を使用し、SQLBE01 の使用は避けます。



データベースをインストールする場合、 **Install-CsDatabase** は、次の 3 つの主要な方法を使用して、準備のできた SQL Server ベースのサーバーにデータベースを配置します。

  - DatabasePaths または UseDefaultSqlPath なしで **Install-CsDatabase** を実行します。このコマンドレットは、組み込みアルゴリズムを使用して、ログおよびデータ ファイルの最善の配置方法を決定します。このアルゴリズムは、スタンドアロンの SQL Server 実装でのみ機能します。

  - DatabasePaths パラメーターを指定して **Install-CsDatabase** を実行します。DtabasePaths パラメーターが定義されている場合、ログおよびデータ ファイルの場所を最適化する組み込みアルゴリズムは使用されません。このパラメーターを使用すると、ログおよびデータ ファイルを展開する場所を定義できます。

  - UseDefaultSqlPaths を指定して **Install-CsDatabase** を実行します。このオプションでは、組み込みアルゴリズムを使用してログおよびデータ ファイルの場所を最適化しません。ログおよびデータ ファイルは、SQL Server 管理者が設定する既定値に従って展開されます。これらのパスは、一般に SQL Server でログおよびデータ ファイルを自動管理する目的で事前に設定され、 Lync Server 2013 のセットアップと関連付けられません。

  - DatabasePathMap パラメーターは、各データベースとそのログ ファイルの場所の明示的な指定にも使用できます。

## Windows PowerShell コマンドレットを使用して SQL Server 中央管理ストアを構成するには

1.  任意のコンピューターで、SQL Server ベースのサーバーでデータベースを作成するための管理資格情報を使用してログオンします。詳細については、「[Lync Server 2013 の SQL Server の展開のアクセス許可](lync-server-2013-deployment-permissions-for-sql-server.md)」を参照してください。

2.  Lync Server 2013 管理シェルを開きます。Windows PowerShellの実行ポリシーを調整していない場合は、Windows PowerShell スクリプトの実行を許可するようにポリシーを調整する必要があります。詳細については、「実行ポリシーの確認」( <http://go.microsoft.com/fwlink/?linkid=203093>) を参照してください。

3.  **Install-CsDatabase** コマンドレットを使用して 中央管理ストアをインストールします。
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
        -Report <path to report file>

       &nbsp;
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
    

    > [!TIP]
    > Report パラメーターはオプションですが、インストール プロセスを文書化する場合に役立ちます。



4.  **Install-CsDatabase –DatabasePaths** では、最大 6 つのパス パラメーターを使用できます。各パラメーターでは、「SQL Server データとログ ファイルの配置」で定義されているように、ドライブのパスを定義します。Lync Server 2013 のデータベース構成の論理ルールにより、ドライブは、2 つ、4 つ、または 6 つのバケットに解析されます。SQL Server の構成とバケットの数に応じて、2 つのパス、4 つのパス、または 6 つのパスを指定できます。
    
    ドライブが 3 つの場合は、ログに優先順位が付けられ、データ ファイルはその優先順位に従って配布されます。6 つのドライブによって構成される SQL Server ベースのサーバーの例を次に示します。
    
        Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"

5.  データベースのインストールが完了したら、 Lync Server 2013 管理シェルを閉じるか、 トポロジ ビルダーで定義された Lync Server 2013 構成のデータベースのインストールに進むことができます。

## Windows PowerShell コマンドレットを使用して SQL Server トポロジ構成のデータベースを構成するには

1.  トポロジ ビルダーによって構成される Lync Server 2013 用のデータベースをインストールするには、Lync Server 2013 管理者は、トポロジを発行する必要があります。詳細については、「展開」のドキュメントの「[Lync Server 2013 でトポロジを公開する](lync-server-2013-publish-the-topology.md)」を参照してください。

2.  任意のコンピューターで、SQL Server ベースのサーバーでデータベースを作成するための管理資格情報を使用してログオンします。「[Lync Server 2013 の SQL Server の展開のアクセス許可](lync-server-2013-deployment-permissions-for-sql-server.md)」を参照してください。
    

    > [!IMPORTANT]
    > SQL Server ベースのデータベースを構成するには、ここで説明する手順の実行に使用する SQL Server 管理者アカウントが、SQL Server を実行しており中央管理サーバーの役割を持つサーバー上の sysadmins グループ (または同等のグループ) のメンバーであることを確認してください。これは特に、SQL Server データベースのインストールまたは構成を必要とする追加の Lync Server 2013 プールの有無を確認する場合に重要です。たとえば、2 つ目のプール (pool02) を展開しているが、中央管理サーバーの役割は pool01 によって保持されている場合があります。SQL Server sysadmin グループ (または同等のグループ) には、両方の SQL Server ベースのデータベースに対するアクセス許可が必要です。



3.  Lync Server 2013 管理シェルを開きます (まだ開いていない場合)。

4.  **Install-CsDatabase** コマンドレットを使用して、 トポロジ ビルダーで構成したデータベースをインストールします。
    
    ```
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
    ```
    
    ```
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
    ```
    

    > [!TIP]
    > Report パラメーターはオプションですが、インストール プロセスを文書化する場合に役立ちます。



5.  データベースのインストールが完了したら、 Lync Server 2013 管理シェルを閉じます。

## Windows PowerShell コマンドレットで DatabasePathMap パラメーターを使用して SQL Server トポロジを構成するには

1.  Lync Server 2013 用のデータベースをインストールするためには、事前定義されたルール セットに従って Lync Server 管理者がパスを作成し、データベース ファイルとログ ファイルを展開する必要があります。

2.  任意のコンピューターで、SQL Server ベースのサーバーでデータベースを作成するための管理資格情報を使用してログオンします。「[Lync Server 2013 の SQL Server の展開のアクセス許可](lync-server-2013-deployment-permissions-for-sql-server.md)」を参照してください。
    

    > [!IMPORTANT]
    > SQL Server ベースのデータベースを構成するには、ここで説明する手順の実行に使用する SQL Server 管理者アカウントが、SQL Server を実行しており 中央管理サーバーの役割を持つサーバー上の sysadmins グループ (または同等のグループ) のメンバーであることを確認してください。これは特に、SQL Serverデータベースのインストールまたは構成を必要とする追加の Lync Server プールの有無を確認する場合に重要です。たとえば、2 つ目のプール (pool02) を展開しているが、中央管理サーバーの役割は pool01 によって保持されている場合があります。SQL Server sysadmin グループ (または同等のグループ) には、両方の SQL Server ベースのデータベースに対するアクセス許可が必要です。



3.  Lync Server 管理シェルを開きます (まだ開いていない場合)。

4.  **Install-CsDatabase** コマンドレットで DatabasePathMap パラメーターと PowerShell ハッシュ テーブルを使用して、 トポロジ ビルダーで構成されたデータベースをインストールします。

5.  この例のコードでは、-DatabasePathsMap パラメーターと定義済みハッシュ テーブルを次のように使用することで、データベース用に定義するパスをきめ細かく決めることができます (例ではすべてのデータベース (.mdf) ファイルに対して 「C:\\CSData」を使用し、すべてのログ (.ldf) ファイルに対して 「C:\\CSLogFiles」 を使用しています。フォルダーは必要に応じて Install-CsDatabase によって作成されます)。
    
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
        Install-CsDatabase -ConfigureDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathsMap $pathmap

6.  データベース ファイルとログ ファイルには、対象のデータベース サーバー上での場所に応じて明示的に名前が付けられるので、サービスの種類ごとのデータベースとログの実際の保存場所について、特定の場所を定義することができます。次の例では、特定のサービスの種類ごとに個別のディスクにデータベースを配置し、関連するログ ファイルは別のディスクに保存しています。たとえば次のようになります。
    
      - すべての RTC データベースを「D:\\RTCDatabase」に
    
      - すべての RTC ログ ファイルを「E:\\RTCLogs」に
    
      - すべてのアプリケーション ストア データベースを「F:\\CPSDatabases」に
    
      - すべてのアプリケーション ストア ログを「G:\\CPSLogs」に
    
      - すべての応答グループ ストア データベースを「H:\\RGSDatabases」に
    
      - すべての応答グループ ストア ログを「I:\\RGSLogs」に
    
      - すべてのアドレス帳ストア データベースを「J:\\ABSDatabases」に
    
      - すべてのアドレス帳ストア ログ ファイルを「K:\\ABSLogs」に
    
      - すべてのアーカイブ ストア データベースを「L:\\ArchivingDatabases」に
    
      - すべてのアーカイブ ストア ログを「M:\\ArchivingLogs」に
    
      - すべての監視ストア データベースを「N:\\MonitoringDatabases」に
    
      - すべての監視ストア データベースを「O:\\MonitoringLogfiles」に
    
    <!-- end list -->
    
    ``` 
    
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
    
    –DatabasePathMap パラメーターを使用して、SQL Server のパフォーマンスと配置に関する要件に最適なソリューションとなる任意の組み合わせで論理ドライブ文字のマッピングを定義できます。

**DatabasePathMap** メソッドを使用してデータベース データ ファイルとログ ファイルを構成する場合は、 トポロジ ビルダー 使用するときの通常のプロセスを若干変更する必要があります。一般には、トポロジの選択肢を定義し、トポロジを公開し、さらにデータベースの選択の展開を選択します。

**DatabasePathMap** を使用したことがある場合は、 トポロジ ビルダーのプロセスの 3 番目の部分は既に完了しています。 トポロジ ビルダーを実行する前にデータベース サーバーの構成が完了している場合、サーバーの役割とオプションをすべて定義する必要はありますが、データベースを作成するオプションは選択解除します。

