---
title: Lync Server 2010 Central Management サーバーを Lync Server 2013 に移動する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29bdf9a5956dfec0dd35703aaf7a7606da63595b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034467"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a>Lync Server 2010 Central Management サーバーを Lync Server 2013 に移動する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-11-25_

Lync server 2010 から Lync Server 2013 に移行した後、lync server 2010 Central Management サーバーを Lync Server の2013フロントエンドサーバーまたはプールに移動してから、従来の Lync 2010 Server のサーバーを使用しているサーバーを削除する必要があります。

中央管理サーバーは、中央管理サーバーを含むフロントエンドサーバーによって、データベースの読み取り/書き込みコピーが保持されている単一のマスター/マルチレプリカシステムです。 トポロジ内の各コンピューター (中央管理サーバーを含むフロントエンドサーバーを含む) には、セットアップ時にコンピューターにインストールされている SQL Server データベース内の中央管理ストアのデータの読み取り専用コピーがあります (既定では RTCLOCAL という名前が付いています)。展開. ローカルデータベースは、すべてのコンピューターでサービスとして実行される Lync Server Replica Replicator エージェントを経由して、レプリカの更新を受信します。 中央管理サーバーとローカルレプリカの実際のデータベースの名前は XDS で、このファイルは xds ファイルと xds ファイルで構成されています。 Master データベースの場所は、Active Directory ドメインサービスのサービスコントロールポイント (SCP) によって参照されます。 中央管理サーバーを使用して Lync Server を管理および構成するすべてのツール SCP を使用して、中央管理ストアを特定します。

中央管理サーバーを正常に移動したら、元のフロントエンドサーバーから中央管理サーバーデータベースを削除する必要があります。 中央管理サーバーデータベースの削除の詳細については、「[フロントエンドプールの SQL Server データベースを削除](remove-the-sql-server-database-for-a-front-end-pool.md)する」を参照してください。

Lync server 管理シェルで**move-csmanagementserver**コマンドレットを使用して、lync SERVER 2010 sql server データベースから lync SERVER 2013 sql server データベースにデータベースを移動した後、lync Server 2013 中央管理サーバーの場所を指すように SCP を更新します。

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a>中央管理サーバーを移動する前に Lync Server 2013 フロントエンドサーバーを準備する

Lync Server 2010 Central Management サーバーを移動する前に、このセクションの手順を使用して、Lync Server 2013 フロントエンドサーバーを準備します。

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Enterprise Edition フロントエンドプールを準備するには

1.  中央管理サーバーを再配置する Lync Server 2013 Enterprise Edition フロントエンドプールで、 **RTCUniversalServerAdmins**グループのメンバーとして Lync Server 管理シェルがインストールされているコンピューターにログオンします。 また、中央管理ストアをインストールするデータベースに対して、SQL Server データベース sysadmin のユーザー権限とアクセス許可も持っている必要があります。

2.  Lync Server 管理シェルを開きます。

3.  Lync server 2013 の SQL Server データベースに新しい中央管理ストアを作成するには、Lync Server 管理シェルで、次のように入力します。
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  [**Lync Server フロントエンド**] サービスのステータスが [**開始**] であることを確認します。

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a>Standard Edition フロントエンドサーバーを準備するには

1.  中央管理サーバーを再配置する Lync Server 2013 Standard Edition フロントエンドサーバーで、 **RTCUniversalServerAdmins**グループのメンバーとして Lync Server 管理シェルがインストールされているコンピューターにログオンします。

2.  [Lync Server 展開ウィザード] を開きます。

3.  Lync Server 展開ウィザードで、[**最初の Standard Edition サーバーの準備**] をクリックします。

4.  [**コマンドの実行**] ページで、中央管理サーバーとして SQL Server Express がインストールされます。 必要なファイアウォール規則が作成されます。 データベースと必要なソフトウェアのインストールが完了したら、[**完了**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 最初のインストールには、コマンド出力の概要画面に表示される更新がないと、しばらく時間がかかる場合があります。 これは、SQL Server Express がインストールされているためです。 データベースのインストールを監視する必要がある場合は、タスクマネージャーを使用してセットアップを監視します。

    
    </div>

5.  Lync server 2013 Standard Edition フロントエンドサーバー上に新しい中央管理ストアを作成するには、Lync Server 管理シェルで、次のように入力します。
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  [**Lync Server フロントエンド**] サービスのステータスが [**開始**] であることを確認します。

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a>Lync Server 2010 Central Management サーバーを Lync Server 2013 に移動するには

1.  中央管理サーバーとなる Lync Server 2013 サーバー上で、Lync Server 管理シェルがインストールされているコンピューターに**RTCUniversalServerAdmins**グループのメンバーとしてログオンします。 また、SQL Server データベース管理者のユーザー権限とアクセス許可を持っている必要があります。

2.  Lync Server 管理シェルを開きます。

3.  Lync Server 管理シェルで、次のように入力します。
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > 成功<CODE>Enable-CsTopology</CODE>しない場合は、続行する前に、コマンドの完了を妨げている問題を解決してください。 <STRONG>Enable-CsTopology テクノロジ</STRONG>が成功しなかった場合、移動は失敗し、中央管理ストアがない状態で、トポロジがそのまま残る場合があります。

    
    </div>

4.  Lync server 2013 のフロントエンドサーバーまたはフロントエンドプールの場合は、Lync Server 管理シェルで、次のように入力します。
    
        Move-CsManagementServer

5.  Lync Server 管理シェルには、サーバー、ファイルストア、データベースストア、および現在の状態のサービス接続ポイントと提案済みの状態が表示されます。 この情報を注意深く読み、移動元と移動先が意図したものであることを確認します。 続行するには「**Y**」を入力し、移動を中止するには「**N**」を入力します。

6.  **Move-CsManagementServer** コマンドで表示される警告またはエラーを確認して解決します。

7.  Lync Server 2013 サーバーで、[Lync Server 展開ウィザード] を開きます。

8.  Lync Server 展開ウィザードで、[ **Lync Server システムのインストールまたは更新**] をクリックし、[**ステップ 2: lync Server コンポーネントのセットアップまたは削除**] をクリックし、[**次へ**] をクリックして概要を確認し、[**完了**] をクリックします。

9.  Lync Server 2010 サーバーで、[Lync Server 展開ウィザード] を開きます。

10. Lync Server 展開ウィザードで、[ **Lync Server システムのインストールまたは更新**] をクリックし、[**ステップ 2: lync Server コンポーネントのセットアップまたは削除**] をクリックし、[**次へ**] をクリックして概要を確認し、[**完了**] をクリックします。

11. Lync Server 2013 サーバーを再起動します。 これは、グループメンバーシップの変更によって中央管理サーバーデータベースにアクセスするために必要です。

12. 新しい中央管理ストアとのレプリケーションが行われていることを確認するには、Lync Server 管理シェルで、次のように入力します。
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > レプリケーションが現在のすべてのレプリカを更新するには、少し時間がかかる場合があります。

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a>移行後に Lync Server 2010 Central Management store ファイルを削除するには

1.  Lync server 2010 サーバー上で、Lync Server 管理シェルがインストールされているコンピューターに**RTCUniversalServerAdmins**グループのメンバーとしてログオンします。 また、SQL Server データベース管理者のユーザー権限とアクセス許可を持っている必要があります。

2.  Lync Server 管理シェルを開く
    
    <div>
    

    > [!WARNING]  
    > レプリケーションが完了して安定するまで、以前のデータベース ファイルを削除しないでください。 レプリケーションを完了する前にファイルを削除すると、レプリケーションプロセスが中断され、新しく移動した中央管理サーバーが不明な状態のままになります。 レプリケーションの状態を確認するには、<STRONG>Get-CsManagementStoreReplicationStatus</STRONG> コマンドレットを使用します。

    
    </div>

3.  Lync Server 2010 Central Management サーバーから中央管理ストアデータベースファイルを削除するには、次のように入力します。
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    例:
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    SQL Server \<\>の FQDN は、Enterprise Edition 展開の Lync Server 2010 バックエンドサーバー、または STANDARD Edition サーバーの fqdn のいずれかです。

</div>

</div>

<span> </span>

</div>

</div>

</div>

