---
title: Lync Server 2010 中央管理サーバーから Lync Server 2013 への移動
TOCTitle: Lync Server 2010 中央管理サーバーから Lync Server 2013 への移動
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49886900
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2010 中央管理サーバーから Lync Server 2013 への移動

 

_**トピックの最終更新日:** 2013-11-25_

Lync Server 2010 から Lync Server 2013 に移行した後、従来の Lync Server 2010 サーバーを削除する前に、Lync Server 2010中央管理サーバーを Lync Server 2013フロント エンド サーバーまたはプールに移動する必要があります。

中央管理サーバーは、単一のマスターと複数のレプリカから構成されたシステムであり、データベースの読み取り/書き込みコピーは 中央管理サーバーを含む フロント エンド サーバーによって保持されます。 中央管理サーバーを含む フロント エンド サーバーなど、トポロジ内のすべてのコンピューターには、セットアップおよび展開時にコンピューターにインストールされた SQL Server データベース (既定の名前は RTCLOCAL) に 中央管理ストア データの読み取り専用コピーが保持されます。ローカル データベースは、すべてのコンピューター上でサービスとして実行されている Lync Server レプリカ レプリケーター エージェント経由でレプリカの更新を受信します。 中央管理サーバー上の実際のデータベースおよびローカル レプリカの名前は XDS であり、xds.mdf ファイルと xds.ldf ファイルで構成されています。マスター データベースの場所は、Active Directory ドメイン サービス のサービス コントロール ポイント (SCP) によって参照されます。 中央管理サーバーを使用して Lync Server を管理および構成するすべてのツールは、SCP を使用して 中央管理ストアの場所を特定します。

中央管理サーバーが正常に移動された後、元の フロント エンド サーバーから 中央管理サーバー データベースを削除する必要があります。 中央管理サーバー データベースの削除の詳細については、「[フロントエンド プールの SQL Server データベースの削除](remove-the-sql-server-database-for-a-front-end-pool.md)」を参照してください。

Lync Server 管理シェルで Windows PowerShell コマンドレット **Move-CsManagementServer** を使用して、データベースを Lync Server 2010 SQL Server データベースから Lync Server 2013 SQL Server データベースに移動し、Lync Server 2013中央管理サーバーの場所を指すように SCP を更新します。

## 中央管理サーバーを移動する前に Lync Server 2013フロント エンド サーバーを準備する

この手順を使用して、Lync Server 2010中央管理サーバーを移動する前に Lync Server 2013フロント エンド サーバーを準備します。

## Enterprise Edition の フロント エンド プールを準備するには

1.  中央管理サーバーを移動する先の Lync Server 2013 Enterprise Edition フロント エンド プールで、コンピューターにログオンします。 Lync Server 管理シェルが **RTCUniversalServerAdmins** グループのメンバーとしてインストールされている必要があります。また、中央管理ストアをインストールするデータベースに対して、SQL Server データベースの sysadmin のユーザー権限およびアクセス許可が必要です。

2.  Lync Server 管理シェルを開きます。

3.  新しい 中央管理ストアを Lync Server 2013 の SQL Server データベースに作成するには、Lync Server 管理シェルで次のコマンドを入力します。
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  \[ **Lync Server フロントエンド** \] サービスのステータスが \[ **開始**\] であることを確認します。

## Standard Edition の フロント エンド サーバーを準備するには

1.  中央管理サーバーを移動する先の Lync Server 2013 Standard Edition フロント エンド サーバーで、コンピューターにログオンします。 Lync Server 管理シェルが **RTCUniversalServerAdmins** グループのメンバーとしてインストールされている必要があります。

2.  Lync Server 展開ウィザードを開きます。

3.  Lync Server 展開ウィザードで、\[ **最初の Standard Edition サーバーの準備**\] をクリックします。

4.  \[ **コマンドの実行**\] ページで、SQL Server Express が 中央管理サーバーとしてインストールされます。必要なファイアウォール規則が作成されます。データベースと必要なソフトウェアのインストールが完了したら、\[ **完了**\] をクリックします。
    
    > [!NOTE]
    > 最初のインストールには少し時間がかかります。この際、コマンド出力の概要画面が更新されることはありません。これは、SQL Server Express がインストールされるためです。データベースのインストールの進行状況を監視する必要がある場合は、タスク マネージャーを使用してセットアップを監視してください。


5.  Lync Server 2013 Standard Edition フロント エンド サーバーで新しい 中央管理ストアを作成するには、Lync Server 管理シェルで次のコマンドを入力します。
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  \[ **Lync Server フロントエンド** \] サービスのステータスが \[ **開始**\] であることを確認します。

## Lync Server 2010中央管理サーバーを Lync Server 2013 に移動するには

1.  中央管理サーバーとなる Lync Server 2013 サーバーで、コンピューターにログオンします。 Lync Server 管理シェルが **RTCUniversalServerAdmins** グループのメンバーとしてインストールされている必要があります。また、SQL Server データベースの管理者のユーザー権限およびアクセス許可が必要です。

2.  Lync Server 管理シェルを開きます。

3.  Lync Server 管理シェルで次のように入力します。
    
        Enable-CsTopology
    

    > [!WARNING]
    > <CODE>Enable-CsTopology</CODE> が成功しない場合は、コマンドの実行を妨げている問題を解決してから続行してください。<STRONG>Enable-CsTopology</STRONG> が成功しない場合、移動は失敗し、トポロジが、中央管理ストアが存在しない状態のままになる可能性があります。



4.  Lync Server 2013フロント エンド サーバーまたは フロント エンド プールの Lync Server 管理シェルで、次のコマンドを入力します。
    
        Move-CsManagementServer

5.  Lync Server 管理シェルに、現在の状態と提案された状態の、サーバー、ファイル ストア、データベース ストア、およびサービス接続ポイントが表示されます。この情報を注意深く読み、移動元と移動先が意図したものであることを確認します。続行するには「**Y**」を入力し、移動を中止するには「**N**」を入力します。

6.  **Move-CsManagementServer** コマンドで表示される警告またはエラーを確認して解決します。

7.  Lync Server 2013 サーバーで、Lync Server 展開ウィザードを開きます。

8.  Lync Server 展開ウィザードで、\[ **Lync Server システムのインストールまたは更新** \]、\[ **ステップ 2: Lync Server コンポーネントのセットアップまたは削除** \]、\[ **次へ** \] の順にクリックし、概要を確認し、\[ **完了** \] をクリックします。

9.  Lync Server 2010 サーバーで、Lync Server 展開ウィザードを開きます。

10. Lync Server 展開ウィザードで、\[ **Lync Server システムのインストールまたは更新** \]、\[ **ステップ 2: Lync Server コンポーネントのセットアップまたは削除** \]、\[ **次へ** \] の順にクリックし、概要を確認し、\[ **完了** \] をクリックします。

11. Lync Server 2013 サーバーを再起動します。この操作が必要なのは、中央管理サーバー データベースにアクセスするためのグループ メンバーシップが変更されたためです。

12. 新しい 中央管理ストアでレプリケーションが行われていることを確認するには、Lync Server 管理シェルで次のように入力します。
    
        Get-CsManagementStoreReplicationStatus
    
    > [!NOTE]
    > レプリケーションが現在のすべてのレプリカを更新するには、少し時間がかかる場合があります。


## 移動後に Lync Server 2010中央管理ストア ファイルを削除するには

1.  Lync Server 2010 サーバーで、コンピューターにログオンします。 Lync Server 管理シェルが **RTCUniversalServerAdmins** グループのメンバーとしてインストールされている必要があります。また、SQL Server データベースの管理者のユーザー権限およびアクセス許可が必要です。

2.  Lync Server 管理シェルを開きます。
    

    > [!WARNING]
    > レプリケーションが完了して安定するまで、以前のデータベース ファイルを削除しないでください。レプリケーションが完了する前にファイルを削除すると、レプリケーション プロセスが中断し、新しく移動した 中央管理サーバーが不明状態のままになります。レプリケーションの状態を確認するには、<STRONG>Get-CsManagementStoreReplicationStatus</STRONG> コマンドレットを使用します。



3.  Lync Server 2010中央管理サーバーから 中央管理ストア データベース ファイルを削除するには、次のコマンドを入力します。
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    次に例を示します。
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    *\<FQDN of SQL Server\>* は、Enterprise Edition 展開内の Lync Server 2010 バックエンド サーバーまたは Standard Edition サーバーの FQDN です。

