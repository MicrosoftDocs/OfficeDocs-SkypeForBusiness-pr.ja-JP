---
title: Skype for Business Server 2015 でバックエンド サーバーの高可用性を実現するための SQL ミラーリングの展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: SQL ミラーリングを展開できるようにするには、サーバーで最小限の SQL Server 2008 R2 を実行する必要があります。 このバージョンは、すべての関連サーバー (プライマリ、ミラー、およびミラーリング監視の各サーバー) で実行する必要があります。 詳細については、「SQL Server 2008 Service Pack 1 の累積更新プログラムパッケージ9」を参照してください。
ms.openlocfilehash: 49ccc2057641b23dffa309726bc5cdf0d74f6b08
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2019
ms.locfileid: "35222117"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a>Skype for Business server 2015 でバックエンドサーバーの高可用性を実現するための SQL ミラーリングを展開する


SQL ミラーリングを展開できるようにするには、サーバーで最小限の SQL Server 2008 R2 を実行する必要があります。 このバージョンは、すべての関連サーバー (プライマリ、ミラー、およびミラーリング監視の各サーバー) で実行する必要があります。 詳細については、「 [SQL Server 2008 Service Pack 1 の累積更新プログラムパッケージ 9](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921)」を参照してください。

一般に、2 つのバックエンド サーバー間での SQL ミラーリングを設定するには、以下の要件を満たしている必要があります。

- プライマリサーバーの SQL Server のバージョンでは、SQL のミラーリングがサポートされている必要があります。

- プライマリ、ミラー、およびミラーリング監視 (展開されている場合) の各 SQL Server が同一バージョンである。

- プライマリおよびミラーの各 SQL Server が同一エディションである (ミラーリング監視のエディションは異なっていても構いません)。

監視ロールでサポートされる SQL バージョンについては、SQL のベストプラクティスについては、「[データベースミラーリングの監視](https://go.microsoft.com/fwlink/p/?LinkId=247345)」をご覧ください。

SQL ミラーリングを展開するには、トポロジビルダーを使います。 トポロジビルダーでデータベースをミラーリングするオプションを選ぶと、トポロジビルダーは、トポロジを公開するときに、(必要に応じて、監視の設定を含む) ミラーリングを設定します。 ミラーリング監視は、ミラーの設定または削除と同時に設定または削除することに注意してください。 ミラーリング監視のみ展開または削除する独立したコマンドはありません。

サーバー ミラーリングを構成するには、最初に SQL データベース アクセス許可を正しく設定する必要があります。 詳細について[は、「データベースミラーリングまたは AlwaysOn 可用性グループ (SQL Server) のログインアカウントを設定する](https://go.microsoft.com/fwlink/p/?LinkId=268454)」を参照してください。

SQL ミラーリングでは、データベース復旧モードは常に [**完全**] に設定されます。これは、トランザクション ログ サイズを綿密に監視し、トランザクション ログを定期的にバックアップしてバックエンド サーバー上のディスク容量の不足を回避する必要があることを意味します。トランザクション ログのバックアップ頻度は、ログの増加率によって決まります。ログの増加率は、フロントエンド プールのユーザー アクティビティによるデータベース トランザクションによって決まります。展開ワークロードに対して予想されるトランザクション ログの増加を判断し、それに応じて計画することをお勧めします。次の記事では、SQL バックアップおよびログ管理に関する追加情報を提供しています。

- [データベースの回復モデル](https://go.microsoft.com/fwlink/p/?LinkId=268446)

- [バックアップの概要](https://go.microsoft.com/fwlink/p/?LinkId=268449)

- [バックアップトランザクションログ](https://go.microsoft.com/fwlink/p/?LinkId=268452)

SQL ミラーリングでは、ミラーリングのトポロジの構成を、プールの作成時、またはプールが既に作成された後のどちらでも行うことができます。

> [!IMPORTANT]
> SQL ミラーリングのセットアップと削除を行うためのトポロジビルダーまたはコマンドレットの使用は、プライマリ、ミラー、および監視 (必要な場合) サーバーがすべて同じドメインに属している場合にのみサポートされます。 異なるドメインのサーバーに SQL ミラーリングを設定する場合は、SQL Server のドキュメントを参照してください。

> [!IMPORTANT]
> バックエンド データベース ミラーリング関係を変更するたびに、プール内のすべてのフロントエンド サーバーを再起動する必要があります。 ミラーリングの変更 (ミラーの場所の変更など) の > は、次の3つの手順を実行するためにトポロジビルダーを使用する必要があります。

1. 古いミラー サーバーからミラーリングを削除します。

2. 新しいミラー サーバーにミラーリングを追加します。

3. トポロジを公開します。

> [!NOTE]
> 書き込み先のミラーファイルに対してファイル共有を作成し、SQL Server と SQL エージェントが実行されているサービスが読み取り/書き込みアクセスを必要とするようにする必要があります。 SQL Server サービスが Network service のコンテキストで実行されている場合は、 \<プリンシパル\> \\とミラーの\>SQL server の両方のドメイン<sqlservername $ を共有アクセス許可に追加できます。 $ は、これがコンピュータアカウントであることを特定するために重要です。

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>トポロジビルダーでプールを作成するときに SQL ミラーリングを構成するには

1. [**SQL ストアの定義**] ページで、[**SQL ストア**] ボックスの隣にある [**新規作成**] をクリックします。

2. [**新しい SQL ストアの定義**] ページで、プライマリ ストアを指定し、[**この SQL インスタンスはミラーリングの関係にある **] を選択して、SQL ミラーリングのポート番号 (既定値は 5022) を指定したうえで [**OK**] をクリックします。

3. [**SQL ストアの定義**] ページに戻ったら、[**SQL ストアのミラーリングを有効にする**] を選択します。

4. [**新しい SQL ストアの定義**] ページで、ミラーとして使用する SQL ストアを指定し、[**この SQL インスタンスはミラーリングの関係にある**] を選択して、ポート番号 (既定値は 5022) を指定したうえで [**OK**] をクリックします。

5. このミラーのミラーリング監視が必要な場合は、以下の操作を実行します。

    a. [**SQL ミラーリング監視を使用して自動フェールオーバーを有効にする**] を選択します。

    b. [**SQL ストアの定義**] ページで、[**SQL ミラーリング監視を使用して自動フェールオーバーを有効にする**] を選択し、ミラーリング監視として使用する SQL ストアを指定します。

    c. ポート番号 (既定値は 7022) を指定し、[**OK**] をクリックします。

6. フロントエンドプールとトポロジ内の他のすべての役割の定義が完了したら、トポロジビルダーを使用してトポロジを公開します。 トポロジが公開されている場合、中央管理ストアをホストするフロントエンドプールに SQL ミラーリングが有効になっていると、プライマリとミラーの両方の SQL ストアデータベースを作成するオプションが表示されます。

    [**設定**] をクリックし、ミラーリング バックアップのファイル共有として使用するパスを入力します。

    [**OK**]、[**次へ**] の順にクリックして、データベースを作成し、トポロジを公開します。ミラーリングとミラーリング監視 (指定した場合) が展開されます。

トポロジビルダーを使用して、既存のプールのプロパティを編集し、SQL のミラーリングを有効にすることができます。

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>トポロジビルダーで既存のフロントエンドプールに SQL ミラーリングを追加するには

1. トポロジビルダーで、プールを右クリックし、[**プロパティの編集**] をクリックします。

2. [**SQL ストアのミラーリングを有効にする**] を選択し、[**ミラーリング SQL ストア**] の横にある [**新規作成**] をクリックします。

3. ミラーとして使用する SQL ストアを指定します。

4. [**この SQL インスタンスはミラーリングの関係にある**] を選択し、SQL ミラーリングのポート番号 (既定のポートは 5022 番) を指定して、[**OK**] をクリックします。

5. ミラーリング監視を構成する場合は、[**SQL ミラーリング監視を使用して自動フェールオーバーを有効にする**] を選択し、[**新規作成**] をクリックします。

6. ミラーリング監視として使用する SQL ストアを指定します。

7. [**この SQL インスタンスはミラーリングの関係にある**] を選択し、SQL ミラーリングのポート番号 (既定のポートは 7022 番) を指定して、[**OK**] をクリックします。

8. [**OK**] をクリックします。

9. トポロジを公開します。この操作を行うと、データベースをインストールするように求められます。

    トポロジ公開プロセスでは、ファイル共有パスの入力を求められます。ミラーリングを確立するには、ミラーリングに参加するすべての SQL Server に、このファイル共有への読み取り/書き込みのアクセス権が必要です。

その場合、次の手順に進む前にデータベースをインストールする必要があります。

SQL ミラーリングの設定時には次の点に留意する必要があります。

- 既に存在するミラーリング エンドポイントは、そこに定義されたポートを使用して再利用され、トポロジ内で指定したポートは無視されます。

- 同じサーバー上の他のアプリケーションに既に割り当てられたポート (他の SQL インスタンス用のポートを含みます) は、ここでインストールする SQL インスタンスでは使用しないでください。これは、複数の SQL インスタンスを同じサーバー上にインストールしている場合、それらのインスタンスは同じポートをミラーリングに使用してはならないことを意味します。詳細については、以下の記事を参照してください。

  - [サーバーのネットワークアドレスを指定する (データベースのミラーリング)](https://go.microsoft.com/fwlink/p/?LinkId=247346)

  - [データベースミラーリングエンドポイント (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=247347)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a>Skype for Business Server 2015 Management Shell コマンドレットを使用して SQL ミラーリングを設定する

ミラーリングを設定する最も簡単な方法は、トポロジビルダーを使用することですが、コマンドレットを使って行うこともできます。

1. Skype for Business Server 2015 管理シェルウィンドウを開いて、次のコマンドレットを実行します。

   ```
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    例:

   ```
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose
   ```

    以下のように表示されます。

   <pre>
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
   </pre>

2. 次のことを確認します。

    - プライマリ SQL Server e04-ocs.los_a.lsipt.local\rtc で Windows ファイアウォールが有効になっている場合は、ポート 5022 がファイアウォール経由でアクセスできる。

    - ミラー SQL Server K16-ocs.los_a.lsipt.local\rtc で Windows ファイアウォールが有効になっている場合は、ポート 5022 がファイアウォール経由でアクセスできる。

    - ミラーリング監視 SQL Server AB14-lct.los_a.lsipt.local\rtc で Windows ファイアウォールが有効になっている場合は、ポート 7022 がファイアウォール経由でアクセスできる。

   - すべてのプライマリおよびミラー SQL server で SQL Server を実行しているアカウントは、ファイル共有\\E04-OCS\csdatabackup の読み取り/書き込みアクセス許可を持っている

   - これらすべてのサーバーで、Windows Management Instrumentation (WMI) プロバイダーが実行されている。コマンドレットでは、このプロバイダーを使用して、すべてのプライマリ サーバー、ミラー サーバー、およびミラーリング監視サーバーで実行されている SQL Server サービスのアカウント情報が検索されます。

   - このコマンドレットを実行しているアカウントに、すべてのミラー サーバーのデータおよびログ ファイル用のフォルダーを作成するためのアクセス許可がある。

   - SQL インスタンスの実行に使用するユーザー アカウントに、ファイル共有に対する読み取り/書き込みアクセス許可が必要であることに注意してください。ファイル共有が別のサーバーにあり、SQL インスタンスがローカル システム アカウントを実行している場合は、SQL インスタンスをホストするサーバーへのファイル共有アクセス許可を付与する必要があります。

3. 「A」と入力し、Enter キーを押します。

    ミラーリングの構成が行われます。

    **CsMirrorDatabase をインストール**すると、ミラーがインストールされ、プライマリ SQL ストアに存在するすべてのデータベースのミラーリングが構成されます。 特定のデータベースに対してのみミラーリングを構成する場合は、-DatabaseType オプションを使用できます。また、少数を除くすべてのデータベースのミラーリングを構成する場合は、-ExcludeDatabaseList オプションと、少数のデータベースのコンマ区切りリストを使用することができます。除外する名前。

    たとえば、次のオプションを **Install-CsMirrorDatabase** に追加した場合は、rtcab と rtcxds を除くすべてのデータベースがミラーリングされます。

    `-ExcludeDatabaseList rtcab,rtcxds`

   たとえば、次のオプションを **Install-CsMirrorDatabase** に追加した場合は、rtcab、rtcshared、および rtcxds データベースのみがミラーリングされます。

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a>SQL ミラーリングの削除または変更

トポロジ ビルダーのプールの SQL ミラーリングを削除するには、最初にコマンドレットを使用して、SQL Server のミラーを削除する必要があります。次に、トポロジ ビルダーを使用して、トポロジからミラーを削除できます。SQL Server でミラーを削除するには、次のコマンドレットを使用します。

```
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

たとえば、ミラーリングを削除し、User データベースのデータベースを削除するには、次のように入力します。

```
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

この`-DropExistingDatabasesOnMirror`オプションを選択すると、影響を受けるデータベースがミラーから削除されます。

その後、トポロジからミラーを削除するために次の操作を行います。

1. トポロジ ビルダーで、プールを右クリックし、[**プロパティの編集**] をクリックします。

2. [**SQL ストアのミラーリングを有効にする**] チェック ボックスをオフにし、[**OK**] をクリックします。

3. トポロジを公開します。

## <a name="removing-a-mirroring-witness"></a>ミラーリング監視の削除

バックエンドサーバーのミラーリング構成から監視を削除する必要がある場合は、この手順を使用します。

1. トポロジ ビルダーで、プールを右クリックし、[**プロパティの編集**] をクリックします。

2. [**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] をオフにし、[**OK**] をクリックします。

3. トポロジを公開します。

    トポロジを公開すると、次のようなメッセージが表示されます。

   ```
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    ただし、この手順に従ってはいけません。 `Uninstall-CsMirrorDatabase`また、ミラーリング構成全体をアンインストールするのと同じように入力しないでください。

4. SQL Server の構成から監視のみを削除するには、「[データベースミラーリングセッション (SQL Server) から監視を削除](https://go.microsoft.com/fwlink/p/?LinkId=268456)する」の手順に従います。


