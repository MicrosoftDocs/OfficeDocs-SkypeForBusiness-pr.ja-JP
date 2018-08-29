---
title: Skype for Business Server 2015 でバックエンド サーバーの高可用性を実現するための SQL ミラーリングの展開
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: SQL ミラーリングを展開できるようにするには、サーバーで最小限の SQL Server 2008 R2 を実行する必要があります。 このバージョンは、すべての関連サーバー (プライマリ、ミラー、およびミラーリング監視の各サーバー) で実行する必要があります。 詳細については、更新プログラム パッケージ 9 を SQL Server 2008 Service Pack 1 の累積を参照してください。
ms.openlocfilehash: 37444cb9825c473657722a0b4e61745385730d7e
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23254607"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype のバック エンド サーバーの高可用性の SQL のミラーリングを導入します。


SQL ミラーリングを展開できるようにするには、サーバーで最小限の SQL Server 2008 R2 を実行する必要があります。 このバージョンは、すべての関連サーバー (プライマリ、ミラー、およびミラーリング監視の各サーバー) で実行する必要があります。 詳細については、[更新プログラム パッケージ 9 SQL Server 2008 Service Pack 1 の累積](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921)を参照してください。

一般に、2 つのバックエンド サーバー間での SQL ミラーリングを設定するには、以下の要件を満たしている必要があります。

- SQL Server のプライマリ サーバーのバージョンでは、SQL のミラーリングをサポートする必要があります。

- プライマリ、ミラー、およびミラーリング監視 (展開されている場合) の各 SQL Server が同一バージョンである。

- プライマリおよびミラーの各 SQL Server が同一エディションである (ミラーリング監視のエディションは異なっていても構いません)。

ミラーリング監視ロールのどのような SQL のバージョンはサポートされているという点で SQL のベスト プラクティスは、[データベース ミラーリングの監視](https://go.microsoft.com/fwlink/p/?LinkId=247345)を参照してください。

SQL のミラーリングを展開するのにには、トポロジ ビルダーを使用します。 データベースをミラー化するのにはトポロジ ビルダーのオプションを選択して、トポロジ ビルダーの設定をミラーリングなど、ミラーリング監視サーバーを設定する場合は、トポロジを公開するとします。 ミラーリング監視は、ミラーの設定または削除と同時に設定または削除することに注意してください。 ミラーリング監視のみ展開または削除する独立したコマンドはありません。

サーバー ミラーリングを構成するには、最初に SQL データベース アクセス許可を正しく設定する必要があります。 詳細については、[データベース ミラーリングまたは AlwaysOn 可用性グループ (SQL Server) には、[ログイン アカウントの設定](https://go.microsoft.com/fwlink/p/?LinkId=268454)を参照してください。

SQL ミラーリングでは、データベース復旧モードは常に [**完全**] に設定されます。これは、トランザクション ログ サイズを綿密に監視し、トランザクション ログを定期的にバックアップしてバックエンド サーバー上のディスク容量の不足を回避する必要があることを意味します。トランザクション ログのバックアップ頻度は、ログの増加率によって決まります。ログの増加率は、フロントエンド プールのユーザー アクティビティによるデータベース トランザクションによって決まります。展開ワークロードに対して予想されるトランザクション ログの増加を判断し、それに応じて計画することをお勧めします。次の記事では、SQL バックアップおよびログ管理に関する追加情報を提供しています。

- [データベースのリカバリ モデル](https://go.microsoft.com/fwlink/p/?LinkId=268446)

- [バックアップの概要](https://go.microsoft.com/fwlink/p/?LinkId=268449)

- [トランザクション ログのバックアップ](https://go.microsoft.com/fwlink/p/?LinkId=268452)

SQL ミラーリングでは、ミラーリングのトポロジの構成を、プールの作成時、またはプールが既に作成された後のどちらでも行うことができます。

> [!IMPORTANT]
> 設定し、SQL を削除するのにはトポロジ ビルダーまたはコマンドレットを使用してミラーリングがサポートされているプライマリ、ミラー、および (必要な場合)、ミラーリング監視サーバーが同じドメインに属している場合にのみです。 異なるドメインのサーバーに SQL ミラーリングを設定する場合は、SQL Server のドキュメントを参照してください。

> [!IMPORTANT]
> バックエンド データベース ミラーリング関係を変更するたびに、プール内のすべてのフロントエンド サーバーを再起動する必要があります。 > 変更するなど、ミラーの場所)、の変更がミラー化にこれら 3 つの手順を実行するのにはトポロジ ビルダーを使用する必要があります。

1. 古いミラー サーバーからミラーリングを削除します。

2. 新しいミラー サーバーにミラーリングを追加します。

3. トポロジを公開します。

> [!NOTE]
> ファイル共有への書き込みをミラー ファイルを作成してで、SQL Server と SQL エージェントが実行されているサービスには、読み取り/書き込みアクセスが必要があります。 追加するかどうかは、ネットワーク サービスのコンテキストで SQL Server サービスが実行されて、\<ドメイン\>\\< SQLSERVERNAME\>共有のアクセス許可にプリンシパルとミラーの SQL サーバーの両方の $。 $ では、これは、コンピューター アカウントを識別する必要があります。

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>トポロジ ビルダーでのプールの作成時に SQL のミラーリングを構成するのには

1. [**SQL ストアの定義**] ページで、[**SQL ストア**] ボックスの隣にある [**新規作成**] をクリックします。

2. [**新しい SQL ストアの定義**] ページで、プライマリ ストアを指定し、[**この SQL インスタンスはミラーリングの関係にある **] を選択して、SQL ミラーリングのポート番号 (既定値は 5022) を指定したうえで [**OK**] をクリックします。

3. [**SQL ストアの定義**] ページに戻ったら、[**SQL ストアのミラーリングを有効にする**] を選択します。

4. [**新しい SQL ストアの定義**] ページで、ミラーとして使用する SQL ストアを指定し、[**この SQL インスタンスはミラーリングの関係にある**] を選択して、ポート番号 (既定値は 5022) を指定したうえで [**OK**] をクリックします。

5. このミラーのミラーリング監視が必要な場合は、以下の操作を実行します。

    a. [**SQL ミラーリング監視を使用して自動フェールオーバーを有効にする**] を選択します。

    b. [**SQL ストアの定義**] ページで、[**SQL ミラーリング監視を使用して自動フェールオーバーを有効にする**] を選択し、ミラーリング監視として使用する SQL ストアを指定します。

    c. ポート番号 (既定値は 7022) を指定し、[**OK**] をクリックします。

6. 終了したら、トポロジを公開するのにはトポロジ ビルダーを使用する、トポロジで、フロント エンド プールとその他のすべてのロールを定義します。 トポロジを公開すると、中央管理ストアをホストするフロント エンド プールは、SQL ミラーリングが有効になっている場合は、両方のプライマリを作成し、SQL ストアのデータベースをミラーリングするためのオプションが表示されます。

    [**設定**] をクリックし、ミラーリング バックアップのファイル共有として使用するパスを入力します。

    [**OK**]、[**次へ**] の順にクリックして、データベースを作成し、トポロジを公開します。ミラーリングとミラーリング監視 (指定した場合) が展開されます。

SQL のミラーリングを有効にするのに既存のプールのプロパティを編集するのには、トポロジ ビルダーを使用できます。

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>SQL のミラーリングには、トポロジ ビルダーで既存のフロント エンド プールを追加するのには

1. トポロジ ビルダーでは、プールを右クリックし、**プロパティの編集**] をクリックします。

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

  - [(データベース ミラーリング)、サーバーのネットワーク アドレスを指定します。](https://go.microsoft.com/fwlink/p/?LinkId=247346)

  - [データベース ミラーリング エンドポイント (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=247347)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a>ビジネス サーバー 2015 管理シェル コマンドレット セットの Skype を使用して SQL ミラーのセットアップ

ミラーリングを設定する最も簡単な方法は、トポロジ ビルダーを使用してですが、コマンドレットを使用しても行うことができます。

1. Skype ビジネス サーバー 2015 の管理シェル ウィンドウを開くし、次のコマンドレットを実行します。

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

   - アカウントは、プライマリのすべての SQL サーバーと SQL サーバーのミラーを実行しているファイル共有への読み取り/書き込み権限のある\\E04 OCS\csdatabackup

   - これらすべてのサーバーで、Windows Management Instrumentation (WMI) プロバイダーが実行されている。コマンドレットでは、このプロバイダーを使用して、すべてのプライマリ サーバー、ミラー サーバー、およびミラーリング監視サーバーで実行されている SQL Server サービスのアカウント情報が検索されます。

   - このコマンドレットを実行しているアカウントに、すべてのミラー サーバーのデータおよびログ ファイル用のフォルダーを作成するためのアクセス許可がある。

   - SQL インスタンスの実行に使用するユーザー アカウントに、ファイル共有に対する読み取り/書き込みアクセス許可が必要であることに注意してください。ファイル共有が別のサーバーにあり、SQL インスタンスがローカル システム アカウントを実行している場合は、SQL インスタンスをホストするサーバーへのファイル共有アクセス許可を付与する必要があります。

3. 「A」と入力し、Enter キーを押します。

    ミラーリングの構成が行われます。

    **インストール CsMirrorDatabase**では、ミラーをインストールし、プライマリ SQL ストア上に存在するすべてのデータベースのミラーリングを構成します。 のみ特定のデータベースのミラーリングを構成する場合は、することができますオプションを使用して、- されていません、またはデータベースのコンマ区切りのリストと、- ExcludeDatabaseList オプションを使用するにはいくつかを除くすべてのデータベース ミラーリングを構成する場合は、除外する名前です。

    などの**インストール CsMirrorDatabase**に次のオプションを追加する場合は、rtcab と rtcxds を除くすべてのデータベースがミラーされます。

    `-ExcludeDatabaseList rtcab,rtcxds`

   たとえば、**インストール CsMirrorDatabase**に次のオプションを追加する場合のみ、rtcab、rtcshared、rtcxds データベースがミラーされます。

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

`-DropExistingDatabasesOnMirror`オプションは、ミラーから削除するのには影響を受けるデータベースを指定します。

その後、トポロジからミラーを削除するために次の操作を行います。

1. トポロジ ビルダーで、プールを右クリックし、[**プロパティの編集**] をクリックします。

2. [**SQL ストアのミラーリングを有効にする**] チェック ボックスをオフにし、[**OK**] をクリックします。

3. トポロジを公開します。

## <a name="removing-a-mirroring-witness"></a>ミラーリング監視の削除

バック エンド サーバーの構成をミラー化から、ミラーリング監視サーバーを削除する必要がある場合は、この手順を使用します。

1. トポロジ ビルダーで、プールを右クリックし、[**プロパティの編集**] をクリックします。

2. [**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] をオフにし、[**OK**] をクリックします。

3. トポロジを公開します。

    トポロジ ビルダーでトポロジを公開した後、次を含むメッセージが表示されます

   ```
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    ただし、その手順に従っていないと、入力しないで`Uninstall-CsMirrorDatabase`全体のミラーリング構成をアンインストールするように。

4. SQL Server の構成から、ミラーリング監視サーバーだけを削除するには、[データベース ミラーリング セッション (SQL Server) からミラーリング監視サーバー](https://go.microsoft.com/fwlink/p/?LinkId=268456)の削除] 設定を指示します。


