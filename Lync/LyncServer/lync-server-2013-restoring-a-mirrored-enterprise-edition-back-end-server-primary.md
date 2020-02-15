---
title: ミラー化された Enterprise Edition バックエンドサーバーの復元-プライマリ
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
ms.openlocfilehash: b895a5071a3844e755fe453f92959f98ec0fbff5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a>Lync Server 2013 のミラー化された Enterprise Edition バックエンドサーバーの復元-プライマリ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-17_

ミラー化された構成に Enterprise Edition バックエンドサーバーがあり、プライマリデータベースのみに障害が発生した場合は、このセクションの手順を実行します。 プライマリデータベースとミラーの両方で障害が発生した場合は、「 [Lync Server 2013 で Enterprise Edition バックエンドサーバーを復元する](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)」を参照してください。 ミラーのみに障害が発生した場合は、「 [Lync Server 2013-mirror でのミラー化された Enterprise Edition バックエンドサーバーの復元](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)」を参照してください。 中央管理ストアをホストしているデータベースに障害が発生した場合は、「 [Lync server 2013 の中央管理ストアをホスト](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)しているサーバーを復元する」を参照してください。 バックエンドサーバーに含まれていない Enterprise Edition メンバーサーバーの障害が発生した場合は、「 [Lync server 2013 で Enterprise edition のメンバーサーバーを復元](lync-server-2013-restoring-an-enterprise-edition-member-server.md)する」を参照してください。

復元を開始する前に、システムのイメージコピーを取得することをお勧めします。 復元中に問題が発生した場合に備えて、このイメージをロールバックポイントとして使用できます。 オペレーティングシステムと SQL Server をインストールした後、画像コピーを取得し、証明書を復元または reenroll することができます。

このトピックでは、プライマリデータベースの例は BE1.contoso.com の完全修飾ドメイン名 (FQDN) を持ち、ミラーデータベースの FQDN は BE2.contoso.com です。

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a>Enterprise Edition バックエンドサーバーのプライマリデータベースを復元するには

1.  RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、フロントエンドサーバーにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  構成済みのすべてのデータベースを強制的にミラーにフェールオーバーします。 このサーバーに構成したデータベースの種類ごとに、次のコマンドレットを入力します。
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    例:
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > ミラーリング監視を伴う同期されたミラーリングを使用するようにバックエンド データベースを構成している場合、フェールオーバーは自動で行われます。

    
    </div>

4.  フェールオーバーの完了後、次の手順を実行します。
    
      - トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。
    
      - バックエンドサーバーでミラーリングを無効にする: **Enterprise Edition フロントエンドプール**の下にあるプールを右クリックし、[**プロパティの編集**] を選択します。 [**全般**] タブの [**関連付け**] で、[ **SQL Server ストアミラーリングの有効化**] チェックボックスをオフにします。 必要に応じて、アーカイブと監視に対して行います。 次に、[ **OK**] をクリックします。
    
      - [Lync Server 2013] ノードを右クリックし、[**トポロジ**] をクリックして、[**発行**] をクリックします。
    
      - 引き続き機能するバックエンド (BE2.contoso.com) を選択して、新しい SQL ストアにします。 これを行うには、 **Enterprise Edition フロントエンドプール**の下にあるプールを右クリックし、[**プロパティの編集**] を選択します。 [**全般**] タブの [**関連付け**] で、正常に機能しているバックエンドの FQDN を**SQL Server ストア**のフィールドに入力します (この例では、BE2.contoso.com)。
    
      - [Lync Server 2013] ノードを右クリックし、[**トポロジ**] をクリックして、[**発行**] をクリックします。
    
      - 各サーバーが新しいトポロジを読み取ることができるように、サービスを再起動します。 Lync Server 管理シェルから、このプールに属する各フロントエンドサーバーで次のコマンドレットを実行します。
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  ミラーリングをアンインストールします。 Lync Server 管理シェルから、次のコマンドレットを実行します。
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    例:
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    このサーバー上のすべてのデータベースの種類に対してこれを実行します。

6.  障害が発生したコンピューターと同じ FQDN (この例では DB1.contoso.com) を持つクリーンサーバーまたは新しいサーバーを作成し、オペレーティングシステムをインストールしてから、証明書を復元または reenroll します。 このサーバーは、新しいミラーとして機能します。

7.  RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、新しいサーバーにログオンします。

8.  SQL Server 2012 または SQL Server 2008 R2 をインストールして、インスタンス名を失敗前と同じ状態に保ちます。

9.  RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、フロントエンドサーバーにログオンします。

10. トポロジビルダーを使用して、ミラー DB をインストールします。 次の手順を実行します。
    
      - トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。
    
      - バックエンドサーバーでミラーリングを有効にします。 これを行うには、 **Enterprise Edition フロントエンドプール**の下にあるプールを右クリックし、[**プロパティの編集**] を選択します。 [**全般**] タブの [**関連付け**] で、[ **SQL Server ストアミラーリングの有効化**] チェックボックスをオンにします。 また、必要に応じてアーカイブと監視にも行います。
        
        次に、[ **SQL Server ストアのミラーリング**] フィールドに新しいサーバーの FQDN (n この例では BE1.contoso.com) を入力します。 次に、[ **OK**] をクリックします。
    
      - [Lync Server 2013] ノードを右クリックし、[**トポロジ**] をクリックして、[**データベースのインストール**] をクリックします。
    
      - [**データベースのインストール**] ウィザードに従います。 [**データベースの作成**] ページで、再作成するデータベースを選択します。
    
      - プロンプトが表示されるまで、ウィザードの指示に従って、**ミラーデータベースを作成**します。 インストールするデータベースを選択し、このプロセスを完了します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

