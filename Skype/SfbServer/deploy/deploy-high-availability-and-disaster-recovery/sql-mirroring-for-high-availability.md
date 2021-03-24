---
title: Skype SQL 2015 でバック エンド サーバーの高可用性をミラーリングする方法を展開する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: SQL ミラーリングを展開できるようにするには、サーバーで最小限の SQL Server 2008 R2 を実行する必要があります。 このバージョンは、すべての関連サーバー (プライマリ、ミラー、およびミラーリング監視の各サーバー) で実行する必要があります。 詳細については、「累積的な更新プログラム パッケージ 9 for SQL Server 2008 Service Pack 1」を参照してください。
ms.openlocfilehash: 38c3e749b39cd510623232e9f29ace03a1c19f6c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100723"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a>Skype SQL 2015 でバック エンド サーバーの高可用性をミラーリングする方法を展開する


SQL ミラーリングを展開できるようにするには、サーバーで最小限の SQL Server 2008 R2 を実行する必要があります。 このバージョンは、すべての関連サーバー (プライマリ、ミラー、およびミラーリング監視の各サーバー) で実行する必要があります。 詳細については、「 [累積的な更新プログラム パッケージ 9 for SQL Server 2008 Service Pack 1」を参照してください](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921)。

一般に、2 つのバックエンド サーバー間での SQL ミラーリングを設定するには、以下の要件を満たしている必要があります。

- プライマリ サーバーのバージョンのサーバーは、SQL ServerミラーリングをSQL必要があります。

- プライマリ、ミラー、およびミラーリング監視 (展開されている場合) の各 SQL Server が同一バージョンである。

- プライマリおよびミラーの各 SQL Server が同一エディションである (ミラーリング監視のエディションは異なっていても構いません)。

ミラーリングSQLの役割でサポートされているSQLのベスト プラクティスについては、「データベース ミラーリング監視」 [を参照してください](/sql/database-engine/database-mirroring/database-mirroring-witness)。

トポロジ ビルダーを使用して、ミラーリングSQL展開します。 トポロジ ビルダーでデータベースをミラーリングするオプションを選択し、トポロジ ビルダーはトポロジの公開時にミラーリングをセットアップします (必要な場合はミラーリング監視の設定を含む)。 ミラーリング監視は、ミラーの設定または削除と同時に設定または削除します。 ミラーリング監視のみ展開または削除する独立したコマンドはありません。

サーバー ミラーリングを構成するには、最初に SQL データベース アクセス許可を正しく設定する必要があります。 詳細については、「データベース ミラーリング [用のログイン アカウントのセットアップ」または「AlwaysOn 可用性グループ (SQL Server)」を参照してください](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability)。

SQL ミラーリングを使用すると、データベース回復モードは常に Fullに設定されます。つまり、トランザクション ログ のサイズを密接に監視し、バック エンド サーバーのディスク領域を使い切らさなくには、定期的にトランザクション ログをバックアップする必要があります。 トランザクション ログ バックアップの頻度は、ログの増加率によって異なります。これは、フロントエンド プールでのユーザー アクティビティによって発生するデータベース トランザクションによって異なります。 計画を適切に実行するために、展開ワークロードで予想されるトランザクション ログの増加量を決定することをお勧めします。 次の記事では、バックアップとログ管理のSQL情報を提供します。

- [データベース復旧モデル](/sql/relational-databases/backup-restore/recovery-models-sql-server)

- [バックアップの概要](/sql/relational-databases/backup-restore/backup-overview-sql-server)

- [バックアップ トランザクション ログ](/sql/relational-databases/backup-restore/back-up-a-transaction-log-sql-server)

SQL ミラーリングでは、ミラーリングのトポロジの構成を、プールの作成時、またはプールが既に作成された後のどちらでも行うことができます。

> [!IMPORTANT]
> トポロジ ビルダーまたはコマンドレットを使用して SQL ミラーリングをセットアップおよび削除すると、プライマリ サーバー、ミラー サーバー、監視サーバー (必要な場合) サーバーすべてが同じドメインに属している場合にのみサポートされます。 異なるドメインのサーバーに SQL ミラーリングを設定する場合は、SQL Server のドキュメントを参照してください。

> [!IMPORTANT]
> バックエンド データベース ミラーリング関係を変更するたびに、プール内のすべてのフロントエンド サーバーを再起動する必要があります。 > ミラーリングの変更 (ミラーの場所の変更など) については、トポロジ ビルダーを使用して、次の 3 つの手順を実行する必要があります。

1. 古いミラー サーバーからミラーリングを削除します。

2. 新しいミラー サーバーにミラーリングを追加します。

3. トポロジを公開します。

> [!NOTE]
> ミラー ファイルを書き込むにはファイル共有を作成する必要があります。また、SQL Server および SQL エージェントが実行しているサービスには、読み取り/書き込みアクセスが必要です。 SQL Server サービスがネットワーク サービスのコンテキストで実行されている場合は、プリンシパル サーバーとミラー SQL サーバーの両方の \<Domain\> \\<SQLSERVERNAME $ を共有アクセス許可 \> に追加できます。 $$、これがコンピューター アカウントである場合に重要です。

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>トポロジ ビルダー SQL作成中にミラーリングを構成するには

1. [**SQL ストアの定義**] ページで、[**SQL ストア**] ボックスの横にある [**新規作成**] をクリックします。

2. [**新しい SQL ストアの定義**] ページで、プライマリ ストアを指定し、[**この SQL インスタンスはミラーリングの関係にある**] を選択して、SQL ミラーリングのポート番号 (既定値は 5022) を指定したうえで [**OK**] をクリックします。

3. [**SQL ストアの定義**] ページに戻ったら、[**SQL ストアのミラーリングを有効にする**] を選択します。

4. [**新しい SQL ストアの定義**] ページで、ミラーとして使用する SQL ストアを指定し、[**この SQL インスタンスはミラーリングの関係にある**] を選択して、ポート番号 (既定値は 5022) を指定したうえで [**OK**] をクリックします。

5. このミラーのミラーリング監視が必要な場合は、以下の操作を実行します。

    a. [**SQL ミラーリング監視を使用して自動フェールオーバーを有効にする**] を選択します。

    b. [**SQL ストアの定義**] ページで、[**SQL ミラーリング監視を使用して自動フェールオーバーを有効にする**] を選択し、ミラーリング監視として使用する SQL ストアを指定します。

    c. ポート番号 (既定値は 7022) を指定し、[**OK**] をクリックします。

6. フロントエンド プールとトポロジ内の他のすべての役割の定義が完了したら、トポロジ ビルダーを使用してトポロジを公開します。 トポロジが公開されている場合、サーバーの全体管理ストアをホストするフロントエンド プールで SQL ミラーリングが有効になっている場合は、プライマリ ストア データベースとミラー サーバー ストア データベースの両方を作成SQLオプションが表示されます。

    [**設定**] をクリックし、ミラーリング バックアップのファイル共有として使用するパスを入力します。

    [**OK**]、[**次へ**] の順にクリックして、データベースを作成し、トポロジを公開します。ミラーリングとミラーリング監視 (指定した場合) が展開されます。

トポロジ ビルダーを使用して、既存のプールのプロパティを編集して、ミラーリングを有効SQLできます。

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>トポロジ ビルダー SQL既存のフロントエンド プールにミラーリングを追加するには

1. トポロジ ビルダーで、プールを右クリックし、[プロパティの編集] **をクリックします**。

2. [**SQL ストアのミラーリングを有効にする**] を選択し、[**ミラーリング SQL ストア**] の横にある [**新規作成**] をクリックします。

3. ミラーとして使用する SQL ストアを指定します。

4. [**この SQL インスタンスはミラーリングの関係にある**] を選択し、SQL ミラーリングのポート番号 (既定のポートは 5022 番) を指定して、[**OK**] をクリックします。

5. ミラーリング監視を構成する場合は、[**SQL ミラーリング監視を使用して自動フェールオーバーを有効にする**] を選択し、[**新規作成**] をクリックします。

6. ミラーリング監視として使用する SQL ストアを指定します。

7. [**この SQL インスタンスはミラーリングの関係にある**] を選択し、SQL ミラーリングのポート番号 (既定のポートは 7022 番) を指定して、[**OK**] をクリックします。

8. [**OK**] をクリックします。

9. トポロジを公開します。この操作を行うと、データベースをインストールするように求められます。

    トポロジの公開プロセス中に、ファイル共有パスの定義を求めるメッセージが表示されます。 ミラー SQLに参加するサーバーには、ミラーを確立するために、このファイル共有への読み取り/書き込みアクセス権が必要です。

その場合、次の手順に進む前にデータベースをインストールする必要があります。

SQL ミラーリングの設定時には次の点に留意する必要があります。

- 既に存在するミラーリング エンドポイントは、そこに定義されたポートを使用して再利用され、トポロジ内で指定したポートは無視されます。

- 同じサーバー上の他のアプリケーションに既に割り当てられたポート (他の SQL インスタンス用のポートを含みます) は、ここでインストールする SQL インスタンスでは使用しないでください。これは、複数の SQL インスタンスを同じサーバー上にインストールしている場合、それらのインスタンスは同じポートをミラーリングに使用してはならないことを意味します。詳細については、以下の記事を参照してください。

  - [サーバー ネットワーク アドレスの指定 (データベース ミラーリング)](/sql/database-engine/database-mirroring/specify-a-server-network-address-database-mirroring)

  - [データベース ミラーリング エンドポイント (SQL Server)](/sql/database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a>Skype for Business Server 2015 管理シェル コマンドレットを使用したミラーリングSQLする

ミラーリングを設定する最も簡単な方法は、トポロジ ビルダーを使用する方法ですが、コマンドレットを使用することもできます。

1. Skype for Business Server 2015 管理シェル ウィンドウを開き、次のコマンドレットを実行します。

   ```powershell
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    例:

   ```powershell
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

   - すべてのプライマリ サーバー SQLおよびミラー サーバーで SQL サーバーを実行しているアカウントには、ファイル共有 \\ E04-OCS\csdatabackup への読み取り/書き込みアクセス許可があります。

   - これらすべてのサーバーで、Windows Management Instrumentation (WMI) プロバイダーが実行されている。コマンドレットでは、このプロバイダーを使用して、すべてのプライマリ サーバー、ミラー サーバー、およびミラーリング監視サーバーで実行されている SQL Server サービスのアカウント情報が検索されます。

   - このコマンドレットを実行しているアカウントに、すべてのミラー サーバーのデータおよびログ ファイル用のフォルダーを作成するためのアクセス許可がある。

   - SQL インスタンスの実行に使用するユーザー アカウントに、ファイル共有に対する読み取り/書き込みアクセス許可がある。ファイル共有が別のサーバーにあり、SQL インスタンスがローカル システム アカウントを実行している場合は、SQL インスタンスをホストするサーバーへのファイル共有アクセス許可を付与する必要があります。

3. 「A」と入力し、Enter キーを押します。

    ミラーリングの構成が行われます。

    **Install-CsMirrorDatabase** はミラーをインストールし、プライマリ サーバー ストアに存在するすべてのデータベースのミラーリングをSQLします。 特定のデータベースのミラーリングのみを構成する場合は、-DatabaseType オプションを使用するか、または少数を除くすべてのデータベースのミラーリングを構成する場合は、-ExcludeDatabaseList オプションと共に、除外するデータベース名のコンマ区切りリストを使用できます。

    たとえば、次のオプションを **Install-CsMirrorDatabase** に追加した場合は、rtcab と rtcxds を除くすべてのデータベースがミラーリングされます。

    `-ExcludeDatabaseList rtcab,rtcxds`

   たとえば、次のオプションを **Install-CsMirrorDatabase** に追加した場合は、rtcab、rtcshared、および rtcxds データベースのみミラーリングされます。

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a>SQL ミラーリングの削除または変更

トポロジ ビルダーのプールの SQL ミラーリングを削除するには、最初にコマンドレットを使用して、SQL Server のミラーを削除する必要があります。次に、トポロジ ビルダーを使用して、トポロジからミラーを削除できます。SQL Server でミラーを削除するには、次のコマンドレットを使用します。

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

たとえば、ミラーリングを削除し、User データベースのデータベースを削除するには、次のように入力します。

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

この  `-DropExistingDatabasesOnMirror` オプションを使用すると、影響を受けるデータベースがミラーから削除されます。

次に、トポロジからミラーを削除するには、次の操作を行います。

1. トポロジ ビルダーで、プールを右クリックし、[**プロパティの編集**] をクリックします。

2. [**SQL ストアのミラーリングを有効にする**] チェック ボックスをオフにし、[**OK**] をクリックします。

3. トポロジを公開します。

## <a name="removing-a-mirroring-witness"></a>ミラーリング監視の削除

バック エンド サーバーミラーリング構成からミラーリング監視を削除する必要がある場合は、次の手順を実行します。

1. トポロジ ビルダーで、プールを右クリックし、[**プロパティの編集**] をクリックします。

2. [**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] をオフにし、[**OK**] をクリックします。

3. トポロジを公開します。

    トポロジを公開すると、トポロジ ビルダーに次のメッセージが表示されます。

   ```console
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    ただし、この手順に従い、ミラーリング構成全体をアンインストールする場合と同様に  `Uninstall-CsMirrorDatabase` 入力しない。

4. ミラーリング監視を SQL Serverから削除するには、「データベース ミラーリング セッションからミラーリング監視を削除する [(SQL Server) 」の手順に従います](/sql/database-engine/database-mirroring/remove-the-witness-from-a-database-mirroring-session-sql-server)。