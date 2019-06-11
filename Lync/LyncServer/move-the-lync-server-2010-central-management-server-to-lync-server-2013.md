---
title: Lync Server 2010 Central Management Server を Lync Server 2013 に移動する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abcb361beb82b98cd765b3797b63b22c280fdf70
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848030"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a>Lync Server 2010 Central Management Server を Lync Server 2013 に移動する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-11-25_

Lync server 2010 から Lync Server 2013 に移行した後、従来の Lync Server 2010 サーバーを削除する前に、lync Server 2010 Central Management Server を Lync Server 2013 フロントエンドサーバーまたはプールに移動する必要があります。

サーバーの全体管理サーバーは、1つのマスター/マルチレプリカシステムです。このシステムでは、データベースの読み取り/書き込みのコピーが、中央管理サーバーを含むフロントエンドサーバーによって保持されています。 トポロジ内の各コンピューターには、サーバーを含むフロントエンドサーバーを含む、セットアップ時にコンピューターにインストールされた、SQL Server データベースの中央管理ストアデータの読み取り専用コピーがあります (既定では、RTCLOCAL という名前が付いています)。デプロイメント. ローカルデータベースは、すべてのコンピューターでサービスとして実行される Lync Server Replica Replicator エージェントを介して、レプリカの更新を受信します。 サーバーの全体管理サーバー上の実際のデータベースの名前とローカルレプリカは XDS で、これらは xds と xds のファイルで構成されます。 Master データベースの場所は、Active Directory ドメインサービスのサービスコントロールポイント (SCP) によって参照されます。 一元管理サーバーを使用して Lync Server を管理および構成するすべてのツール SCP を使用して、中央管理ストアを検索します。

サーバーの全体管理サーバーが正常に移動されたら、元のフロントエンドサーバーから中央管理サーバーのデータベースを削除する必要があります。 サーバーの全体管理サーバーデータベースの削除については、「[フロントエンドプールの SQL Server データベースを削除](remove-the-sql-server-database-for-a-front-end-pool.md)する」を参照してください。

Lync server 管理シェルで Windows PowerShell コマンドレット**CsManagementServer**を使用して、lync SERVER 2010 sql server データベースから lync SERVER 2013 sql server データベースにデータベースを移動し、次にその lync をポイントして lync を指すようにします。サーバー2013サーバーの全体管理サーバーの場所。

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a>サーバーの中央管理サーバーを移動する前に、Lync Server 2013 フロントエンドサーバーを準備する

Lync Server 2010 Central Management Server を移動する前に、このセクションの手順を使用して、Lync Server 2013 フロントエンドサーバーを準備します。

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Enterprise Edition フロントエンドプールを準備するには

1.  セントラル管理サーバーを再配置する Lync Server 2013 Enterprise Edition のフロントエンドプールで、 **RTCUniversalServerAdmins**グループのメンバーとして Lync Server 管理シェルがインストールされているコンピューターにログオンします。 また、中央管理ストアをインストールするデータベースの SQL Server データベース sysadmin ユーザー権限と権限が必要です。

2.  Lync Server 管理シェルを開きます。

3.  Lync Server 2013 SQL Server データベースに新しい中央管理ストアを作成するには、Lync Server 管理シェルで次のように入力します。
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  **Lync Server フロントエンド**サービスの状態が**開始**されていることを確認します。

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a>Standard Edition フロントエンドサーバーを準備するには

1.  セントラル管理サーバーを再配置する Lync Server 2013 Standard Edition フロントエンドサーバーで、 **RTCUniversalServerAdmins**グループのメンバーとして Lync Server 管理シェルがインストールされているコンピューターにログオンします。

2.  Lync Server 展開ウィザードを開きます。

3.  Lync Server 展開ウィザードで、[**最初の Standard Edition サーバーの準備**] をクリックします。

4.  [**コマンドの実行**] ページでは、SQL Server Express が中央管理サーバーとしてインストールされています。 必要なファイアウォールルールが作成されます。 データベースと必須ソフトウェアのインストールが完了したら、[**完了**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 最初のインストールでは、コマンド出力の概要画面に表示される更新プログラムがないと、時間がかかる場合があります。 これは、SQL Server Express がインストールされているためです。 データベースのインストールを監視する必要がある場合は、タスクマネージャーを使用してセットアップを監視します。

    
    </div>

5.  Lync Server 2013 Standard Edition フロントエンドサーバーで新しい中央管理ストアを作成するには、Lync Server 管理シェルで次のように入力します。
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  **Lync Server フロントエンド**サービスの状態が**開始**されていることを確認します。

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a>Lync Server 2010 Central Management Server を Lync Server 2013 に移動するには

1.  サーバーの全体管理サーバーとなる Lync Server 2013 サーバーで、 **RTCUniversalServerAdmins**グループのメンバーとして Lync Server 管理シェルがインストールされているコンピューターにログオンします。 SQL Server データベース管理者のユーザー権限と権限も必要です。

2.  Lync Server 管理シェルを開きます。

3.  Lync Server 管理シェルで、次のように入力します。
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > 問題<CODE>Enable-CsTopology</CODE>が解決しない場合は、続行する前にコマンドの完了を妨げる問題を解決してください。 <STRONG>Enable-CsTopology</STRONG>方法で問題が発生した場合は、移行が失敗し、中央管理ストアがない状態でトポロジが残る場合があります。

    
    </div>

4.  Lync Server 2013 フロントエンドサーバーまたはフロントエンドプールの Lync Server 管理シェルで、次のように入力します。
    
        Move-CsManagementServer

5.  Lync Server 管理シェルには、サーバー、ファイルストア、データベースストア、現在の状態と提案された状態のサービス接続ポイントが表示されます。 情報を慎重に読み、目的のソースと行先であることを確認します。 続行する場合は「 **Y** 」、移動を停止する場合は**N**を入力します。

6.  **CsManagementServer**コマンドによって生成された警告またはエラーを確認し、解決します。

7.  Lync Server 2013 サーバーで、Lync Server 展開ウィザードを開きます。

8.  Lync Server の展開ウィザードで、[ **Lync Server System のインストールまたは更新**] をクリックし、[**手順 2: lync サーバーコンポーネントをセットアップまたは削除します**] をクリックし、[**次へ**] をクリックして概要を確認し、[**完了**] をクリックします。

9.  Lync Server 2010 サーバーで、Lync Server 展開ウィザードを開きます。

10. Lync Server の展開ウィザードで、[ **Lync Server System のインストールまたは更新**] をクリックし、[**手順 2: lync サーバーコンポーネントをセットアップまたは削除します**] をクリックし、[**次へ**] をクリックして概要を確認し、[**完了**] をクリックします。

11. Lync Server 2013 サーバーを再起動します。 これが必要なのは、サーバーの全体管理サーバーデータベースにアクセスするためのグループメンバーシップが変更されたためです。

12. 新しい中央管理ストアでのレプリケーションが行われていることを確認するには、Lync Server 管理シェルで次のように入力します。
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > レプリケーションは、現在のすべてのレプリカの更新に時間がかかる場合があります。

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a>移行後に Lync Server 2010 全体管理ストアのファイルを削除するには

1.  Lync Server 2010 サーバーで、Lync Server 管理シェルが**RTCUniversalServerAdmins**グループのメンバーとしてインストールされているコンピューターにログオンします。 SQL Server データベース管理者のユーザー権限と権限も必要です。

2.  Lync Server 管理シェルを開く
    
    <div>
    

    > [!WARNING]  
    > 複製が完了し、安定しているまで、以前のデータベースファイルの削除は行わないでください。 複製処理を完了する前にファイルを削除すると、レプリケーションプロセスが中断され、新しく移動した中央管理サーバーは不明な状態のままになります。 <STRONG>CsManagementStoreReplicationStatus</STRONG>コマンドレットを使用して、レプリケーションの状態を確認します。

    
    </div>

3.  Lync Server 2010 Central Management サーバーから全体管理ストアデータベースファイルを削除するには、次のように入力します。
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    次に例を示します。
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    SQL Server \<\>の FQDN は、Enterprise Edition の展開の Lync Server 2010 バックエンドサーバー、または STANDARD Edition サーバーの fqdn のいずれかです。

</div>

</div>

<span> </span>

</div>

</div>

</div>

