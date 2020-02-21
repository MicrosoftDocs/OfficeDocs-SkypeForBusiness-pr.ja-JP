---
title: バックエンドサーバーの高可用性を実現するための SQL ミラーリングの展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying SQL mirroring for Back End Server high availability
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204992(v=OCS.15)
ms:contentKeyID: 48184451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 577d6bb312ae2b31f96fed5f3e5b02e84844adf6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a>Lync Server 2013 でバックエンドサーバーの高可用性を実現するための SQL ミラーリングの展開

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-01-08_

SQL ミラーリングを展開できるようにするには、サーバーで最小限の SQL Server 2008 R2 を実行する必要があります。 このバージョンは、すべての関連サーバー (プライマリ、ミラー、およびミラーリング監視の各サーバー) で実行する必要があります。 詳細について[https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921)は、「」を参照してください。

一般に、2 つのバックエンド サーバー間での SQL ミラーリングを設定するには、以下の要件を満たしている必要があります。

  - プライマリ サーバーの SQL Server のバージョンが SQL ミラーリングをサポートしている。

  - プライマリ、ミラー、およびミラーリング監視 (展開されている場合) の各 SQL Server が同一バージョンである。

  - プライマリおよびミラーの各 SQL Server が同一エディションである (ミラーリング監視のエディションは異なっていても構いません)。

ミラーリング監視の役割でサポートされる SQL のバージョンに関する SQL のベストプラクティスについては、MSDN ライブラリの「データベースミラーリング[https://go.microsoft.com/fwlink/p/?LinkId=247345](https://go.microsoft.com/fwlink/p/?linkid=247345)監視」を参照してください。

SQL ミラーリングを展開するには、トポロジビルダーを使用します。 トポロジビルダーでデータベースをミラー化するオプションを選択すると、トポロジビルダーは、トポロジを公開するときに、ミラーリング (必要な場合は、監視の設定を含む) を設定します。 ミラーリング監視は、ミラーの設定または削除と同時に設定または削除します。 ミラーリング監視のみ展開または削除する独立したコマンドはありません。

サーバー ミラーリングを構成するには、最初に SQL データベース アクセス許可を正しく設定する必要があります。 詳細については、「」の「データベースミラーリングまたは AlwaysOn 可用性グループのログインアカウントをセットアップ[https://go.microsoft.com/fwlink/p/?LinkId=268454](https://go.microsoft.com/fwlink/p/?linkid=268454)する (SQL Server)」を参照してください。

SQL ミラーリングでは、データベース復旧モードは常に [**完全**] に設定されます。これは、トランザクション ログ サイズを綿密に監視し、トランザクション ログを定期的にバックアップしてバックエンド サーバー上のディスク容量の不足を回避する必要があることを意味します。トランザクション ログのバックアップ頻度は、ログの増加率によって決まります。ログの増加率は、フロントエンド プールのユーザー アクティビティによるデータベース トランザクションによって決まります。Lync 展開ワークロードに対して予想されるトランザクション ログの増加を判断し、それに応じて計画することをお勧めします。次の記事では、SQL バックアップおよびログ管理に関する追加情報を提供しています。

  - データベース回復モデル: "復旧モデル (SQL Server)"[https://go.microsoft.com/fwlink/p/?LinkId=268446](https://go.microsoft.com/fwlink/p/?linkid=268446)

  - バックアップの概要: 「バックアップの概要 (SQL Server)」[https://go.microsoft.com/fwlink/p/?LinkId=268449](https://go.microsoft.com/fwlink/p/?linkid=268449)

  - バックアップトランザクションログ: "トランザクションログのバックアップ (SQL Server)"[https://go.microsoft.com/fwlink/p/?LinkId=268452](https://go.microsoft.com/fwlink/p/?linkid=268452)

SQL ミラーリングでは、ミラーリングのトポロジの構成を、プールの作成時、またはプールが既に作成された後のどちらでも行うことができます。



> [!IMPORTANT]
> トポロジビルダーまたはコマンドレットを使用した SQL ミラーリングの設定および削除は、プライマリ、ミラー、およびミラーリング監視 (必要な場合) がすべて同じドメインに属している場合にのみサポートされます。 異なるドメインのサーバーに SQL ミラーリングを設定する場合は、SQL Server のドキュメントを参照してください。





> [!IMPORTANT]
> バックエンド データベース ミラーリング関係を変更するたびに、プール内のすべてのフロントエンド サーバーを再起動する必要があります。<BR>ミラーリングの変更 (ミラーの場所の変更など) については、トポロジビルダーを使用して、次の3つの手順を実行する必要があります。 
> <OL>
> <LI>
> <P>古いミラー サーバーからミラーリングを削除します。</P>
> <LI>
> <P>新しいミラー サーバーにミラーリングを追加します。</P>
> <LI>
> <P>トポロジを公開します。</P></LI></OL>




> [!NOTE]
> ミラーファイルに書き込むためのファイル共有を作成する必要があります。また、SQL Server と SQL エージェントが実行しているサービスには、読み取り/書き込みアクセス権が必要です。 SQL Server サービスがネットワークサービスのコンテキストで実行されている場合は、 &lt;ドメイン&gt;&#92;&lt;Sqlservername&gt;$ のプリンシパルとミラーの両方の sql サーバーを共有のアクセス許可に追加できます。 $ は、これがコンピューターアカウントであることを識別するために重要です。


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>トポロジビルダーでプールを作成しているときに SQL ミラーリングを構成するには

1.  [**SQL ストアの定義**] ページで、[**SQL ストア**] ボックスの横にある [**新規作成**] をクリックします。

2.  [**新しい SQL ストアの定義**] ページで、プライマリ ストアを指定し、[**この SQL インスタンスはミラーリングの関係にある**] を選択して、SQL ミラーリングのポート番号 (既定値は 5022) を指定したうえで [**OK**] をクリックします。

3.  [**SQL ストアの定義**] ページに戻ったら、[**SQL ストアのミラーリングを有効にする**] を選択します。

4.  [**新しい SQL ストアの定義**] ページで、ミラーとして使用する SQL ストアを指定し、[**この SQL インスタンスはミラーリングの関係にある**] を選択して、ポート番号 (既定値は 5022) を指定したうえで [**OK**] をクリックします。

5.  このミラーのミラーリング監視が必要な場合は、以下の操作を実行します。
    
    1.  [**SQL ミラーリング監視を使用して自動フェールオーバーを有効にする**] を選択します。
    
    2.  [**SQL ストアの定義**] ページで、[**SQL ミラーリング監視を使用して自動フェールオーバーを有効にする**] を選択し、ミラーリング監視として使用する SQL ストアを指定します。
    
    3.  ポート番号 (既定値は 7022) を指定し、[**OK**] をクリックします。

6.  フロントエンドプールの定義とトポロジ内の他のすべての役割を終えたら、トポロジビルダーを使用してトポロジを公開します。 トポロジの公開時に、中央管理ストアをホストするフロントエンドプールの SQL ミラーリングが有効になっている場合は、プライマリとミラーの両方の SQL ストアデータベースを作成するオプションが表示されます。
    
    [**設定**] をクリックし、ミラーリング バックアップのファイル共有として使用するパスを入力します。
    
    [**OK**]、[**次へ**] の順にクリックして、データベースを作成し、トポロジを公開します。ミラーリングとミラーリング監視 (指定した場合) が展開されます。

トポロジビルダーを使用して、既存のプールのプロパティを編集し、SQL ミラーリングを有効にすることができます。

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>トポロジビルダーで既存のフロントエンドプールに SQL ミラーリングを追加するには

1.  トポロジビルダーで、プールを右クリックし、[**プロパティの編集**] をクリックします。

2.  [**SQL ストアのミラーリングを有効にする**] を選択し、[**ミラーリング SQL ストア**] の横にある [**新規作成**] をクリックします。

3.  ミラーとして使用する SQL ストアを指定します。

4.  [**この SQL インスタンスはミラーリングの関係にある**] を選択し、SQL ミラーリングのポート番号 (既定のポートは 5022 番) を指定して、[**OK**] をクリックします。

5.  ミラーリング監視を構成する場合は、[**SQL ミラーリング監視を使用して自動フェールオーバーを有効にする**] を選択し、[**新規作成**] をクリックします。

6.  ミラーリング監視として使用する SQL ストアを指定します。

7.  [**この SQL インスタンスはミラーリングの関係にある**] を選択し、SQL ミラーリングのポート番号 (既定のポートは 7022 番) を指定して、[**OK**] をクリックします。

8.  [**OK**] をクリックします。

9.  トポロジを公開します。この操作を行うと、データベースをインストールするように求められます。
    
    トポロジの公開プロセス時に、ファイル共有パスの定義を求められます。 ミラーリングに参加する SQL サーバーは、ミラーを確立するために、このファイル共有への読み取り/書き込みアクセス権を持っている必要があります。

その場合、次の手順に進む前にデータベースをインストールする必要があります。

SQL ミラーリングの設定時には次の点に留意する必要があります。

  - 既に存在するミラーリング エンドポイントは、そこに定義されたポートを使用して再利用され、トポロジ内で指定したポートは無視されます。

  - 同じサーバー上の他のアプリケーションに既に割り当てられたポート (他の SQL インスタンス用のポートを含みます) は、ここでインストールする SQL インスタンスでは使用しないでください。これは、複数の SQL インスタンスを同じサーバー上にインストールしている場合、それらのインスタンスは同じポートをミラーリングに使用してはならないことを意味します。詳細については、以下の記事を参照してください。
    
      - MSDN ライブラリの「サーバーネットワークアドレス (データベースミラーリング) を指定する」[https://go.microsoft.com/fwlink/p/?LinkId=247346](https://go.microsoft.com/fwlink/p/?linkid=247346)
    
      - "データベースミラーリングエンドポイント (SQL Server)"[https://go.microsoft.com/fwlink/p/?LinkId=247347](https://go.microsoft.com/fwlink/p/?linkid=247347)

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a>Lync Server 管理シェルコマンドレットを使用して SQL ミラーリングをセットアップする

ミラーリングをセットアップする最も簡単な方法は、トポロジビルダーを使用することですが、コマンドレットを使用することもできます。

1.  Lync Server 管理シェルウィンドウを開き、次のコマンドレットを実行します。
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    例:
    
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
    
      - プライマリ SQL Server e04-ocs\_\\で Windows ファイアウォールが有効になっている場合は、ポート5022がファイアウォール経由でアクセス可能です。
    
      - ミラー SQL Server K16-ocs\_\\で Windows ファイアウォールが有効になっている場合は、ファイアウォール経由でポート5022にアクセスできます。
    
      - ミラーリング監視 SQL Server AB14-lct\_\\で Windows ファイアウォールが有効になっている場合は、ファイアウォール経由でポート7022にアクセスできます。
    
      - すべてのプライマリおよびミラー sql サーバーで sql server を実行しているアカウントには、ファイル共有\\ \\E04\\cs に対する読み取り/書き込みアクセス許可が付与されます。
    
      - これらすべてのサーバーで、Windows Management Instrumentation (WMI) プロバイダーが実行されている。コマンドレットでは、このプロバイダーを使用して、すべてのプライマリ サーバー、ミラー サーバー、およびミラーリング監視サーバーで実行されている SQL Server サービスのアカウント情報が検索されます。
    
      - このコマンドレットを実行しているアカウントに、すべてのミラー サーバーのデータおよびログ ファイル用のフォルダーを作成するためのアクセス許可がある。
    
      - SQL インスタンスの実行に使用するユーザー アカウントに、ファイル共有に対する読み取り/書き込みアクセス許可がある。ファイル共有が別のサーバーにあり、SQL インスタンスがローカル システム アカウントを実行している場合は、SQL インスタンスをホストするサーバーへのファイル共有アクセス許可を付与する必要があります。

3.  「A」と入力し、Enter キーを押します。
    
    ミラーリングの構成が行われます。

**Install-csmirrordatabase**は、ミラーをインストールし、プライマリ SQL ストアに存在するすべてのデータベースのミラーリングを構成します。 特定のデータベースに対してのみミラーリングを構成する場合は、-DatabaseType オプションを使用できます。また、少数を除くすべてのデータベースのミラーリングを構成する場合は、-ExcludeDatabaseList オプションを使用できます。また、データベースの一覧はコンマで区切られています。除外する名前。

たとえば、次のオプションを **Install-CsMirrorDatabase** に追加した場合は、rtcab と rtcxds を除くすべてのデータベースがミラーリングされます。

`-ExcludeDatabaseList rtcab,rtcxds`

たとえば、次のオプションを **Install-CsMirrorDatabase** に追加した場合は、rtcab、rtcshared、および rtcxds データベースのみミラーリングされます。

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a>SQL ミラーリングの削除または変更

トポロジ ビルダーのプールの SQL ミラーリングを削除するには、最初にコマンドレットを使用して、SQL Server のミラーを削除する必要があります。次に、トポロジ ビルダーを使用して、トポロジからミラーを削除できます。SQL Server でミラーを削除するには、次のコマンドレットを使用します。

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

たとえば、ミラーリングを削除し、User データベースのデータベースを削除するには、次のように入力します。

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

この`-DropExistingDatabasesOnMirror`オプションを指定すると、影響を受けるデータベースがミラーから削除されます。

次に、トポロジからミラーを削除するには、次の操作を行います。

1.  トポロジ ビルダーで、プールを右クリックし、[**プロパティの編集**] をクリックします。

2.  [**SQL ストアのミラーリングを有効にする**] チェック ボックスをオフにし、[**OK**] をクリックします。

3.  トポロジを公開します。

</div>

<div>

## <a name="removing-a-mirroring-witness"></a>ミラーリング監視の削除

バックエンドサーバーのミラーリング構成からミラーリング監視を削除する必要がある場合は、この手順を使用します。

1.  トポロジ ビルダーで、プールを右クリックし、[**プロパティの編集**] をクリックします。

2.  [**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] をオフにし、[**OK**] をクリックします。

3.  トポロジを公開します。
    
    トポロジを公開すると、トポロジビルダーに、次のようなメッセージが表示されます。
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    ただし、その手順を実行するのではなく、 `Uninstall-CsMirrorDatabase`ミラーリング構成全体をアンインストールするのではなく、と入力してください。

4.  SQL Server 構成からミラーリング監視のみを削除するには、「データベースミラーリングセッション (SQL Server) からのミラーリング監視を削除する」の[https://go.microsoft.com/fwlink/p/?LinkId=268456](https://go.microsoft.com/fwlink/p/?linkid=268456)手順に従ってください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

