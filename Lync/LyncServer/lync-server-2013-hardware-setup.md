---
title: 'Lync Server 2013: ハードウェアのセットアップ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e2d05db28ffa61ea25dbb237c388c37a87ac5a0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-setup-for-lync-server-2013"></a>Lync Server 2013 のハードウェアのセットアップ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

トポロジを実装するために必要なハードウェアおよびその他のコンポーネントをセットアップするには、トポロジビルダーでトポロジを公開する前に、次の操作を行う必要があります。

  - 必要なすべてのコンピューター (すべての必須コンピューター (Lync Server 2013 を実行しているサーバー、データベースサーバー、インターネットインフォメーションサービス (IIS) を実行しているサーバー) を含むトポロジ設計で、各コンポーネントのハードウェアをインストールし、必要に応じてプロキシサーバーを逆にします)、ネットワークアダプター、ハードウェアロードバランサー、ストレージデバイス (ファイルサーバーなど)。 ネットワークアダプターの数と速度に関する推奨事項に従っていることを確認します。 ハードウェアロードバランサーを使用する場合は、Lync Server 2013 で使用するために、ベンダーから適切な情報が設定されていることを確認してください。 ファイルサーバーまたは他のサーバーを使用して、Lync Server に必要なファイル共有を保存する場合は、サーバーが使用可能であり、ファイル共有を構成する準備ができていることを確認します。 展開に必要なコンポーネントを指定するトポロジの定義方法について詳しくは、「 [Lync Server 2013 でトポロジを定義して構成](lync-server-2013-defining-and-configuring-the-topology.md)する」をご覧ください。 サーバーのハードウェア要件の詳細については、サポートされているドキュメントで「 [Lync Server 2013 に](lync-server-2013-supported-hardware.md)対応したハードウェア」を参照してください。

  - ネットワークインフラストラクチャが要件を満たしていることを確認します。 詳細については、計画ドキュメントの「 [Lync Server 2013 のネットワークインフラストラクチャ要件](lync-server-2013-network-infrastructure-requirements.md)」を参照してください。

  - Active Directory ドメインサービスをセットアップします。 Ad ds のセットアップには、ad ds の準備と、AD DS に展開するすべてのコンポーネントの定義が含まれます。 AD DS の準備について詳しくは、展開ドキュメントの「 [Lync Server 2013 用 Active Directory ドメインサービスの準備](lync-server-2013-preparing-active-directory-domain-services.md)」をご覧ください。

  - ファイル共有の作成に必要なアクセス許可を設定します。 Lync Server 2013 によるファイル共有を使用するためのアクセス許可は、トポロジの公開時にトポロジビルダーによって自動的に構成されます。 ただし、トポロジビルダーで必要なアクセス許可を構成するには、トポロジを公開するために使用されるユーザーアカウントで、ファイル共有に対してフルコントロール (読み取り/書き込み/変更) が必要です。 トポロジビルダーの公開プロセス中にファイル共有を適切に管理できるようにするには、ユーザーがメンバーになっているユーザーまたはドメイングループを、ファイル共有があるコンピューターのローカル管理者グループのメンバーにする必要があります。 マルチドメインシナリオでは、ドメインのユーザーまたはグループが、ファイル共有が配置されているドメイン B のコンピューターのローカル管理者グループのメンバーである必要があります。
    
    分散ファイルシステム (DFS) でファイル共有を使用して更新する方法の詳細については、「 [Lync Server 2013 用にファイルストレージを構成](lync-server-2013-configure-dfs-file-storage.md)する」を参照してください。
    
    <div>
    

    > [!WARNING]  
    > Lync Server 2013 用のファイル共有 (Enterprise Edition) は、フロントエンドサーバー上に配置することはできません。

    
    </div>

  - Web サービス用のハードウェアロードバランサーをインストールしてセットアップします。 ドメインネームシステム (DNS) 負荷分散が展開されている場合でも、これらのプールにはハードウェアロードバランサーを使用する必要があります。ただし、HTTP/HTTPS トラフィックに対してのみ必要です。 ハードウェアロードバランサーは、ポート443および80経由のクライアントからの HTTPS トラフィックに使用されます。 ただし、これらのプールについては、ハードウェアロードバランサーが必要ですが、これらの設定と管理は主に HTTP/HTTPS トラフィック用であり、ハードウェアロードバランサーの管理者は使い慣れています。

このトピックで説明したすべての準備作業を完了した後で、トポロジを公開する前に、次のことも行う必要があります。

  - [Lync Server 2013 のオペレーティング システムと必要なソフトウェアのサーバーへのインストール](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [Lync Server 2013 での IIS の構成](lync-server-2013-configure-iis.md)

  - [Lync Server 2013 用 SQL Server の構成](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Lync Server 2013 でのフロント エンド プールまたは Standard Edition サーバー用の DNS レコードの構成](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

