---
title: ミラー化された Enterprise Edition バックエンドサーバーを復元する-ミラー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 658b271bc71a78c564c42fc96126ce276071709c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a>Lync Server 2013 のミラー化された Enterprise Edition バックエンドサーバーを復元する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-19_

ミラー化された構成に Enterprise Edition バックエンドサーバーがあり、ミラーのみが失敗した場合は、このセクションの手順を実行します。 プライマリデータベースとミラーの両方で障害が発生した場合は、「 [Lync Server 2013 で Enterprise Edition バックエンドサーバーを復元する](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)」を参照してください。 プライマリのみが失敗する場合は、「 [Lync Server 2013-プライマリのミラー化された Enterprise Edition バックエンドサーバーの復元](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)」を参照してください。 中央管理ストアをホストしているデータベースに障害が発生した場合は、「 [Lync server 2013 の中央管理ストアをホスト](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)しているサーバーを復元する」を参照してください。 バックエンドサーバーに含まれていない Enterprise Edition メンバーサーバーの障害が発生した場合は、「 [Lync server 2013 で Enterprise edition のメンバーサーバーを復元](lync-server-2013-restoring-an-enterprise-edition-member-server.md)する」を参照してください。

復元を開始する前に、システムのイメージコピーを取得することをお勧めします。 復元中に問題が発生した場合に備えて、このイメージをロールバックポイントとして使用できます。 オペレーティングシステムと SQL Server をインストールした後、画像コピーを取得し、証明書を復元または reenroll することができます。

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a>Enterprise Edition バックエンドサーバーミラーデータベースを復元するには

1.  RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、フロントエンドサーバーにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  ミラーリングをアンインストールします。 最初に、次のコマンドレットを入力します。
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    次に例を示します。
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    このサーバー上のすべてのデータベースの種類に対してこれを実行します。

4.  障害が発生したコンピューターと同じ完全修飾ドメイン名 (FQDN) (DB1.contoso.com) を持つクリーンサーバーまたは新しいサーバーを作成し、オペレーティングシステムをインストールしてから、証明書を復元または reenroll します。 このサーバーは、新しいミラーとして機能します。

5.  RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、新しいサーバーにログオンします。

6.  SQL Server 2012 または SQL Server 2008 R2 をインストールして、インスタンス名を失敗前と同じ状態に保ちます。

7.  RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、フロントエンドサーバーにログオンします。

8.  トポロジビルダーを使用して、ミラーデータベースをインストールします。 次の手順を実行します。
    
      - トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。
    
      - [Lync Server 2013] ノードを右クリックし、[**トポロジ**] をクリックして、[**データベースのインストール**] をクリックします。
    
      - [**データベースのインストール**] ウィザードに従います。 [**データベースの作成**] ページで、再作成するデータベースを選択します。
    
      - [**ミラーデータベースの作成**] プロンプトが表示されるまで、ウィザードの指示に従います。 インストールするデータベースを選択し、このプロセスを完了します。
        
        <div>
        

        > [!TIP]
        > トポロジビルダーを実行する代わりに、 <STRONG>install-csmirrordatabase</STRONG>コマンドレットを使用してミラーリングを構成できます。 詳細については、Lync Server 管理シェルのドキュメントを参照してください。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

