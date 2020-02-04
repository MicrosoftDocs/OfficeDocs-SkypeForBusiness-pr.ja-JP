---
title: ミラー化された Enterprise Edition バックエンドサーバーを復元する-プライマリ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07546b59839631cbd558e91e3e617fefd1c6e362
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723467"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a>Lync Server 2013 でのミラー化された Enterprise Edition バックエンドサーバーの復元-プライマリ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-17_

ミラーリングされた構成で Enterprise Edition バックエンドサーバーを使用していて、プライマリデータベースのみが失敗した場合は、このセクションの手順に従ってください。 プライマリデータベースとミラーの両方が失敗した場合は、「 [Lync Server 2013 で Enterprise Edition バックエンドサーバーを復元する](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)」を参照してください。 ミラーのみが失敗した場合は、「 [Lync Server 2013-mirror でのミラーリングされた Enterprise Edition バックエンドサーバーの復元](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)」を参照してください。 中央管理ストアをホストしているデータベースに障害が発生した場合は、「 [Lync server 2013 で中央管理ストアをホストしているサーバーの復元](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)」を参照してください。 バックエンドサーバーではない Enterprise Edition のメンバーサーバーに障害が発生した場合は、「 [Lync server 2013 で Enterprise edition のメンバーサーバーを復元](lync-server-2013-restoring-an-enterprise-edition-member-server.md)する」を参照してください。

復元を開始する前に、システムのイメージコピーを取得することをお勧めします。 復元中に問題が発生した場合に備えて、この画像をロールバックポイントとして使うことができます。 オペレーティングシステムと SQL Server をインストールした後に画像のコピーを取得し、証明書を復元または reenroll することができます。

このトピックでは、例として、プライマリデータベースの完全修飾ドメイン名 (FQDN) が BE1.contoso.com で、ミラーデータベースの FQDN が BE2.contoso.com になっています。

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a>Enterprise Edition バックエンドサーバーのプライマリデータベースを復元するには

1.  RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、フロントエンドサーバーにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  構成済みのすべてのデータベースに対して、ミラーへのフェールオーバーを強制します。 このサーバーで構成したデータベースの種類ごとに、次のコマンドレットを入力します。
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    次に例を示します。
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > バックエンドデータベースが監視との同期ミラーリングを使用するように構成されている場合、フェールオーバーは自動的に設定されます。

    
    </div>

4.  フェールオーバーが完了したら、次の手順を実行します。
    
      - トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。
    
      - バックエンドサーバーでのミラーリングを無効にする: **Enterprise Edition フロントエンドプール**の下のプールを右クリックし、[**プロパティの編集**] を選択します。 [**全般**] タブの [**関連付け**] で [ **SQL Server ストアのミラーリングを有効にする**] チェックボックスをオフにします。 必要に応じて、アーカイブと監視に使用します。 [ **OK]** をクリックします。
    
      - [Lync Server 2013] ノードを右クリックし、[**トポロジ**] をクリックして、[**発行**] をクリックします。
    
      - 新しい SQL ストアとして、まだ機能しているバックエンドバックエンド (BE2.contoso.com) を選択します。 これを行うには、 **Enterprise Edition のフロントエンドプール**の下にあるプールを右クリックし、[**プロパティの編集**] を選択します。 [**全般**] タブの [**関連付け**] で、機能しているバックエンドの FQDN を**SQL Server ストア**フィールドに入力します (この例では、BE2.contoso.com)。
    
      - [Lync Server 2013] ノードを右クリックし、[**トポロジ**] をクリックして、[**発行**] をクリックします。
    
      - 各サーバーが新しいトポロジを読み取ることができるように、サービスを再起動します。 Lync Server 管理シェルで、このプールに属している各フロントエンドサーバーで次のコマンドレットを実行します。
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  ミラーリングをアンインストールします。 Lync Server 管理シェルで、次のコマンドレットを実行します。
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    次に例を示します。
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    このサーバー上のすべてのデータベースの種類に対して、この操作を実行します。

6.  障害のあるコンピューターと同じ FQDN (この例では DB1.contoso.com) を持つクリーンサーバーまたは新規サーバーを作成し、オペレーティングシステムをインストールして、証明書を復元または reenroll します。 このサーバは、新しいミラーとして機能します。

7.  RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、新しいサーバーにログオンします。

8.  SQL Server 2012 または SQL Server 2008 R2 をインストールして、インスタンス名がエラーの前と同じになるようにします。

9.  RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、フロントエンドサーバーにログオンします。

10. Topology Builder を使ってミラー DB をインストールします。 次の手順を実行します。
    
      - トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。
    
      - バックエンドサーバーでミラーリングを有効にします。 そのためには、 **Enterprise Edition のフロントエンドプール**の下にあるプールを右クリックし、[**プロパティの編集**] を選択します。 [**全般**] タブの [**関連付け**] で、[ **SQL Server ストアのミラーリングを有効にする**] チェックボックスをオンにします。 また、必要に応じてアーカイブと監視にも行います。
        
        次に、[ **SQL Server ストアのミラーリング**] フィールドに新しいサーバーの FQDN を入力します (n この例では BE1.contoso.com)。 [ **OK]** をクリックします。
    
      - [Lync Server 2013] ノードを右クリックし、[**トポロジ**] をクリックして、[**データベースのインストール**] をクリックします。
    
      - データベースの**インストール**ウィザードを実行します。 [**データベースの作成**] ページで、再作成するデータベースを選びます。
    
      - ウィザードの指示に従って、[**ミラーデータベースの作成**] メッセージに移動します。 インストールするデータベースを選んで、このプロセスを完了します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

