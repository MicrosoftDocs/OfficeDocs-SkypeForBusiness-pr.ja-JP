---
title: ミラー化された Enterprise Edition バックエンドサーバーを復元する-ミラー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 113d69d7aa39673686ff870c36a64bd1a8fe90f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a>Lync Server 2013-mirror でのミラー化された Enterprise Edition バックエンドサーバーの復元

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-19_

ミラーリングされた構成で Enterprise Edition バックエンドサーバーを使用していて、ミラーのみが失敗した場合は、このセクションの手順に従ってください。 プライマリデータベースとミラーの両方が失敗した場合は、「 [Lync Server 2013 で Enterprise Edition バックエンドサーバーを復元する](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)」を参照してください。 プライマリのみが失敗した場合は、「 [Lync Server 2013-プライマリでのミラーリングされた Enterprise Edition バックエンドサーバーの復元](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)」を参照してください。 中央管理ストアをホストしているデータベースに障害が発生した場合は、「 [Lync server 2013 で中央管理ストアをホストしているサーバーの復元](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)」を参照してください。 バックエンドサーバーではない Enterprise Edition のメンバーサーバーに障害が発生した場合は、「 [Lync server 2013 で Enterprise edition のメンバーサーバーを復元](lync-server-2013-restoring-an-enterprise-edition-member-server.md)する」を参照してください。

復元を開始する前に、システムのイメージコピーを取得することをお勧めします。 復元中に問題が発生した場合に備えて、この画像をロールバックポイントとして使うことができます。 オペレーティングシステムと SQL Server をインストールした後に画像のコピーを取得し、証明書を復元または reenroll することができます。

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a>Enterprise Edition バックエンドサーバーミラーデータベースを復元するには

1.  RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、フロントエンドサーバーにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  ミラーリングをアンインストールします。 最初に、次のコマンドレットを入力します。
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    次に例を示します。
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    このサーバー上のすべてのデータベースの種類に対して、この操作を実行します。

4.  障害のあるコンピューターと同じ完全修飾ドメイン名 (FQDN) (DB1.contoso.com) を持つクリーンまたは新しいサーバーを作成し、オペレーティングシステムをインストールして、証明書を復元または reenroll します。 このサーバは、新しいミラーとして機能します。

5.  RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、新しいサーバーにログオンします。

6.  SQL Server 2012 または SQL Server 2008 R2 をインストールして、インスタンス名がエラーの前と同じになるようにします。

7.  RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、フロントエンドサーバーにログオンします。

8.  トポロジビルダーを使用して、ミラーデータベースをインストールします。 次の手順を実行します。
    
      - トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。
    
      - [Lync Server 2013] ノードを右クリックし、[**トポロジ**] をクリックして、[**データベースのインストール**] をクリックします。
    
      - データベースの**インストール**ウィザードを実行します。 [**データベースの作成**] ページで、再作成するデータベースを選びます。
    
      - ウィザードの指示に従って、**ミラーデータベースの作成**のプロンプトが表示されるまで待ちます。 インストールするデータベースを選んで、このプロセスを完了します。
        
        <div>
        

        > [!TIP]
        > Topology Builder を実行する代わりに、 <STRONG>CsMirrorDatabase</STRONG>コマンドレットを使用して、ミラーリングを構成することができます。 詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

