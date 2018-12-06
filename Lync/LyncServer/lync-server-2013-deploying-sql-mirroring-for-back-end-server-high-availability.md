---
title: 'Lync Server 2013: バックエンド サーバーの高可用性を実現するための SQL ミラーリングの展開'
TOCTitle: バックエンド サーバーの高可用性を実現するための SQL ミラーリングの展開
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204992(v=OCS.15)
ms:contentKeyID: 48272488
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのバックエンド サーバーの高可用性を実現するための SQL ミラーリングの展開

 

_**トピックの最終更新日:** 2016-12-08_

SQL ミラーリングを展開できるようにするには、サーバーで最小限の SQL Server 2008 R2 を実行する必要があります。このバージョンは、すべての関連サーバー (プライマリ、ミラー、およびミラーリング監視の各サーバー) で実行する必要があります。詳細については、[http://go.microsoft.com/fwlink/?linkid=3052\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=3052%26clcid=0x411) を参照してください。

一般に、2 つのバックエンド サーバー間での SQL ミラーリングを設定するには、以下の要件を満たしている必要があります。

  - プライマリ サーバーの SQL Server のバージョンが SQL ミラーリングをサポートしている。

  - プライマリ、ミラー、およびミラーリング監視 (展開されている場合) の各 SQL Server が同一バージョンである。

  - プライマリおよびミラーの各 SQL Server が同一エディションである (ミラーリング監視のエディションは異なっていても構いません)。

ミラーリング監視の役割でサポートされる SQL のバージョンに関する SQL のベスト プラクティスについては、MSDN ライブラリの「データベース ミラーリング監視サーバー」 ( [http://go.microsoft.com/fwlink/?linkid=247345\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=247345%26clcid=0x411)) を参照してください。

トポロジ ビルダーを使用して、SQL ミラーリングを展開します。 トポロジ ビルダーのオプションを選択してデータベースをミラーリングし、トポロジを公開するときにトポロジ ビルダーでミラーリングを設定します (必要に応じてミラーリング監視の設定を含む)。ミラーリング監視は、ミラーの設定または削除と同時に設定または削除します。ミラーリング監視のみ展開または削除する独立したコマンドはありません。

サーバー ミラーリングを構成するには、最初に SQL データベース アクセス許可を正しく設定する必要があります。詳細については、「データベース ミラーリングまたは AlwaysOn 可用性グループのログイン アカウントの設定 (SQL Server)」( [http://go.microsoft.com/fwlink/?linkid=268454\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268454%26clcid=0x411)) を参照してください。

SQL ミラーリングでは、データベース復旧モードは常に \[**完全**\] に設定されます。これは、トランザクション ログ サイズを綿密に監視し、トランザクション ログを定期的にバックアップしてバックエンド サーバー上のディスク容量の不足を回避する必要があることを意味します。トランザクション ログのバックアップ頻度は、ログの増加率によって決まります。ログの増加率は、フロントエンド プールのユーザー アクティビティによるデータベース トランザクションによって決まります。Lync 展開ワークロードに対して予想されるトランザクション ログの増加を判断し、それに応じて計画することをお勧めします。次の記事では、SQL バックアップおよびログ管理に関する追加情報を提供しています。

  - データベース復旧モデル: 「復旧モデル (SQL Server)」( [http://go.microsoft.com/fwlink/?linkid=268446\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268446%26clcid=0x411))

  - バックアップの概要: 「バックアップの概要 (SQL Server)」( [http://go.microsoft.com/fwlink/?linkid=268449\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268449%26clcid=0x411))

  - トランザクション ログのバックアップ: 「トランザクション ログのバックアップ (SQL Server)」( [http://go.microsoft.com/fwlink/?linkid=268452\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268452%26clcid=0x411))

SQL ミラーリングでは、ミラーリングのトポロジの構成を、プールの作成時、またはプールが既に作成された後のどちらでも行うことができます。


> [!IMPORTANT]
> トポロジ ビルダーまたはコマンドレットを使用した SQL ミラーリングの設定および削除は、プライマリ サーバー、ミラー サーバー、およびミラーリング監視サーバー (必要な場合) がすべて同じドメインに属する場合にのみサポートされます。異なるドメインのサーバーに SQL ミラーリングを設定する場合は、SQL Server のドキュメントを参照してください。




> [!IMPORTANT]
> バックエンド データベース ミラーリング関係を変更するたびに、プール内のすべてのフロントエンド サーバーを再起動する必要があります。<BR>ミラーリングを変更する場合 (ミラーの場所の変更など) は、 トポロジ ビルダーを使用して次の 3 つの手順を実行する必要があります。 
> <OL>
> <LI>
> <P>古いミラー サーバーからミラーリングを削除します。</P>
> <LI>
> <P>新しいミラー サーバーにミラーリングを追加します。</P>
> <LI>
> <P>トポロジを公開します。</P></LI></OL>



> [!NOTE]
> ミラー ファイルを書き込むためのファイル共有を作成する必要があります。また SQL Server と SQL エージェントを実行するサービスには、読み取り/書き込みアクセスが必要です。SQL Server サービスがネットワーク サービスによって動作する場合、プリンシパルの SQL Server とミラー SQL Server の両方の &lt;Domain&gt;\\&lt;SQLSERVERNAME&gt;$ をこの共有のアクセス許可に追加します。「$」はこれがコンピューター アカウントであることを示すために重要です。


## トポロジ ビルダーでのプールの作成時に SQL ミラーリングを構成するには

1.  \[**SQL ストアの定義**\] ページで、\[**SQL ストア**\] ボックスの横にある \[**新規作成**\] をクリックします。

2.  \[**新しい SQL ストアの定義**\] ページで、プライマリ ストアを指定し、\[**この SQL インスタンスはミラーリングの関係にある**\] を選択して、SQL ミラーリングのポート番号 (既定値は 5022) を指定したうえで \[**OK**\] をクリックします。

3.  \[**SQL ストアの定義**\] ページに戻ったら、\[**SQL ストアのミラーリングを有効にする**\] を選択します。

4.  \[**新しい SQL ストアの定義**\] ページで、ミラーとして使用する SQL ストアを指定し、\[**この SQL インスタンスはミラーリングの関係にある**\] を選択して、ポート番号 (既定値は 5022) を指定したうえで \[**OK**\] をクリックします。

5.  このミラーのミラーリング監視が必要な場合は、以下の操作を実行します。
    
    1.  \[**SQL ミラーリング監視を使用して自動フェールオーバーを有効にする**\] を選択します。
    
    2.  \[**SQL ストアの定義**\] ページで、\[**SQL ミラーリング監視を使用して自動フェールオーバーを有効にする**\] を選択し、ミラーリング監視として使用する SQL ストアを指定します。
    
    3.  ポート番号 (既定値は 7022) を指定し、\[**OK**\] をクリックします。

6.  トポロジ内でフロントエンド プールとその他すべての役割の定義を完了した後、 トポロジ ビルダーを使用してトポロジを公開します。 中央管理ストアをホストしているフロントエンド プールで SQL ミラーリングが有効になっている場合、トポロジを公開すると、プライマリとミラーの両方の SQL ストア データベースを作成するオプションが表示されます。
    
    \[**設定**\] をクリックし、ミラーリング バックアップのファイル共有として使用するパスを入力します。
    
    \[**OK**\]、\[**次へ**\] の順にクリックして、データベースを作成し、トポロジを公開します。ミラーリングとミラーリング監視 (指定した場合) が展開されます。

トポロジ ビルダーを使用すると、既存のプールのプロパティを編集して SQL ミラーリングを有効にできます。

## トポロジ ビルダーで既存のフロントエンド プールに SQL ミラーリングを追加するには

1.  トポロジ ビルダーで、プールを右クリックし、\[**プロパティの編集**\] をクリックします。

2.  \[**SQL ストアのミラーリングを有効にする**\] を選択し、\[**ミラーリング SQL ストア**\] の横にある \[**新規作成**\] をクリックします。

3.  ミラーとして使用する SQL ストアを指定します。

4.  \[**この SQL インスタンスはミラーリングの関係にある**\] を選択し、SQL ミラーリングのポート番号 (既定のポートは 5022 番) を指定して、\[**OK**\] をクリックします。

5.  ミラーリング監視を構成する場合は、\[**SQL ミラーリング監視を使用して自動フェールオーバーを有効にする**\] を選択し、\[**新規作成**\] をクリックします。

6.  ミラーリング監視として使用する SQL ストアを指定します。

7.  \[**この SQL インスタンスはミラーリングの関係にある**\] を選択し、SQL ミラーリングのポート番号 (既定のポートは 7022 番) を指定して、\[**OK**\] をクリックします。

8.  \[**OK**\] をクリックします。

9.  トポロジを公開します。この操作を行うと、データベースをインストールするように求められます。
    
    トポロジ公開プロセスでは、ファイル共有パスの入力を求められます。ミラーリングを確立するには、ミラーリングに参加するすべての SQL Server に、このファイル共有への読み取り/書き込みのアクセス権が必要です。

その場合、次の手順に進む前にデータベースをインストールする必要があります。

SQL ミラーリングの設定時には次の点に留意する必要があります。

  - 既に存在するミラーリング エンドポイントは、そこに定義されたポートを使用して再利用され、トポロジ内で指定したポートは無視されます。

  - 同じサーバー上の他のアプリケーションに既に割り当てられたポート (他の SQL インスタンス用のポートを含みます) は、ここでインストールする SQL インスタンスでは使用しないでください。これは、複数の SQL インスタンスを同じサーバー上にインストールしている場合、それらのインスタンスは同じポートをミラーリングに使用してはならないことを意味します。詳細については、以下の記事を参照してください。
    
      - MSDN ライブラリの「サーバー ネットワーク アドレスの指定 (データベース ミラーリング)」( [http://go.microsoft.com/fwlink/?linkid=247346\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=247346%26clcid=0x411))
    
      - 「データベース ミラーリング エンドポイント (SQL Server)」 ( [http://go.microsoft.com/fwlink/?linkid=247347\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=247347%26clcid=0x411))

## Lync Server 管理シェル コマンドレットを使用した SQL ミラーリングの設定

ミラーリングを最も簡単に設定する方法は トポロジ ビルダーを使用することですが、コマンドレットを使用して設定することもできます。

1.  Lync Server 管理シェル ウィンドウを開き、次のコマンドレットを実行します。
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    次に例を示します。
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    以下のように表示されます。
    
        Database Name:rtcxds 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcxds.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcxds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcshared 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcshared.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcshared.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcab 
                Data File:D:\CsData\ABSStore\rtc\DbPath\rtcab.mdf 
                 Log File:D:\CsData\ABSStore\rtc\LogPath\rtcab.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsconfig 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsconfig.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsconfig.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:cpsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\cpsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\cpsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:xds 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\xds.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\xds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:lis 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\lis.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\lis.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$
        [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): 

2.  次のことを確認します。
    
      - プライマリ SQL Server e04-ocs.los\_a.lsipt.local\\rtc で Windows ファイアウォールが有効になっている場合は、ポート 5022 がファイアウォール経由でアクセスできる。
    
      - ミラー SQL Server K16-ocs.los\_a.lsipt.local\\rtc で Windows ファイアウォールが有効になっている場合は、ポート 5022 がファイアウォール経由でアクセスできる。
    
      - ミラーリング監視 SQL Server AB14-lct.los\_a.lsipt.local\\rtc で Windows ファイアウォールが有効になっている場合は、ポート 7022 がファイアウォール経由でアクセスできる。
    
      - すべてのプライマリおよびミラー SQL Server 上の SQL Server を実行しているアカウントに、ファイル共有 \\\\E04-OCS\\csdatabackup への読み取り/書き込みアクセス許可がある。
    
      - これらすべてのサーバーで、Windows Management Instrumentation (WMI) プロバイダーが実行されている。コマンドレットでは、このプロバイダーを使用して、すべてのプライマリ サーバー、ミラー サーバー、およびミラーリング監視サーバーで実行されている SQL Server サービスのアカウント情報が検索されます。
    
      - このコマンドレットを実行しているアカウントに、すべてのミラー サーバーのデータおよびログ ファイル用のフォルダーを作成するためのアクセス許可がある。
    
      - SQL インスタンスの実行に使用するユーザー アカウントに、ファイル共有に対する読み取り/書き込みアクセス許可がある。ファイル共有が別のサーバーにあり、SQL インスタンスがローカル システム アカウントを実行している場合は、SQL インスタンスをホストするサーバーへのファイル共有アクセス許可を付与する必要があります。

3.  「A」と入力し、Enter キーを押します。
    
    ミラーリングの構成が行われます。

**Install-CsMirrorDatabase** により、ミラーがインストールされ、プライマリ SQL ストア上に存在するすべてのデータベースでミラーリングが構成されます。特定のデータベースに対してのみミラーリングを構成する場合は、-DatabaseType オプションを使用できます。また、少数のものを除くすべてのデータベースでミラーリングを構成する場合は、-ExcludeDatabaseList オプションと共に、除外するデータベース名のカンマ区切りリストを使用します。

たとえば、次のオプションを **Install-CsMirrorDatabase** に追加した場合は、rtcab と rtcxds を除くすべてのデータベースがミラーリングされます。

`-ExcludeDatabaseList rtcab,rtcxds`

たとえば、次のオプションを **Install-CsMirrorDatabase** に追加した場合は、rtcab、rtcshared、および rtcxds データベースのみミラーリングされます。

`-DatabaseType User`

## SQL ミラーリングの削除または変更

トポロジ ビルダーのプールの SQL ミラーリングを削除するには、最初にコマンドレットを使用して、SQL Server のミラーを削除する必要があります。次に、トポロジ ビルダーを使用して、トポロジからミラーを削除できます。SQL Server でミラーを削除するには、次のコマンドレットを使用します。

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

たとえば、ミラーリングを削除し、User データベースのデータベースを削除するには、次のように入力します。

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

`-DropExistingDatabasesOnMirror` オプションにより、影響を受けるデータベースがミラーから削除されます。

その後、トポロジからミラーを削除するために次の操作を行います。

1.  トポロジ ビルダーで、プールを右クリックし、\[**プロパティの編集**\] をクリックします。

2.  \[**SQL ストアのミラーリングを有効にする**\] チェック ボックスをオフにし、\[**OK**\] をクリックします。

3.  トポロジを公開します。

## ミラーリング監視の削除

バック エンド サーバー ミラーリング構成からミラーリング監視を削除する必要がある場合は、次の手順を使用します。

1.  トポロジ ビルダーで、プールを右クリックし、\[**プロパティの編集**\] をクリックします。

2.  \[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**\] をオフにし、\[**OK**\] をクリックします。

3.  トポロジを公開します。
    
    トポロジを公開した後で、 トポロジ ビルダーに次のようなメッセージが表示されます。
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    ただし、この手順には従わないでください。また、ミラーリング構成全体がアンインストールされるため `Uninstall-CsMirrorDatabase` と入力しないでください。

4.  SQL Server 構成からミラーリング監視のみ削除するには、「データベース ミラーリング セッションからのミラーリング監視の削除 (SQL Server)」( [http://go.microsoft.com/fwlink/?linkid=268456\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268456%26clcid=0x411)) の手順に従います。

