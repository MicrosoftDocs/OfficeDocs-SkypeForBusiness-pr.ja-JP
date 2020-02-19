---
title: 'Lync Server 2013: ハードウェアセットアップ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d55ac04a06984889a3038aceee7fd0f311efcfb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138018"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardware-setup-for-lync-server-2013"></a>Lync Server 2013 のハードウェアのセットアップ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

トポロジを実装するために必要なインフラストラクチャで必要なハードウェアとその他のコンポーネントを設定するには、トポロジビルダーでトポロジを公開する前に、次のことを行う必要があります。

  - 必要なすべてのコンピューター (Lync Server 2013、データベースサーバー、インターネットインフォメーションサービス (IIS) を実行しているサーバーを実行しているサーバー) を含む、トポロジビルダーを使用して作成および保存した各コンポーネントのハードウェアをインストールし、必要に応じて、リバースプロキシサーバー、ネットワークアダプター、ハードウェアロードバランサー、およびストレージデバイス (ファイルサーバーなど)。 ネットワーク アダプターについて推奨される数および速度に従っていることを確認してください。 ハードウェアロードバランサーを使用する場合は、それらを構成して Lync Server 2013 で使用できるようにするための適切な情報がベンダーから得られていることを確認してください。 ファイルサーバーまたはその他のサーバーを使用して Lync Server で必要なファイル共有を格納する場合は、サーバーが利用可能であり、ファイル共有の構成の準備が整っていることを確認してください。 展開に必要なコンポーネントを指定するトポロジを定義する方法の詳細については、「 [Lync Server 2013 でのトポロジの定義と構成](lync-server-2013-defining-and-configuring-the-topology.md)」を参照してください。 サーバーのハードウェア要件の詳細については、「サポート」のドキュメントの「supported [hardware For Lync Server 2013](lync-server-2013-supported-hardware.md) 」を参照してください。

  - ネットワークインフラストラクチャが要件を満たしていることを確認してください。 詳細については、「計画」のドキュメントの「 [Lync Server 2013 のネットワークインフラストラクチャ要件](lync-server-2013-network-infrastructure-requirements.md)」を参照してください。

  - Active Directory ドメインサービスをセットアップします。 AD DS の設定には、AD DS の準備、AD DS に展開するすべてのコンポーネントの定義などが含まれます。 AD DS の準備の詳細については、「展開」のドキュメントの「 [Active Directory ドメインサービスの Lync Server 2013 の準備](lync-server-2013-preparing-active-directory-domain-services.md)」を参照してください。

  - ファイル共有の作成に必要なアクセス許可を設定します。 Lync Server 2013 でファイル共有を使用するためのアクセス許可は、トポロジを公開するときに、トポロジビルダーによって自動的に構成されます。 ただし、トポロジビルダーで必要なアクセス許可を構成するためには、トポロジの公開に使用されるユーザーアカウントに、ファイル共有のフルコントロール (読み取り/書き込み/変更) が必要です。 トポロジビルダーの公開プロセス中にファイル共有を適切に管理できるようにするには、ユーザーまたはユーザーがメンバーになっているドメイングループを、ファイル共有が配置されているコンピューターのローカルの Administrators グループのメンバーにする必要があります。 マルチドメイン シナリオでは、ドメイン A のユーザーまたはグループを、ファイル共有が配置されるドメイン B のマシン上でローカルの Administrators グループのメンバーにしてください。
    
    分散ファイルシステム (DFS) でのファイル共有の使用を更新する方法の詳細については、「 [Configure file storage For Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md)」を参照してください。
    
    <div>
    

    > [!WARNING]  
    > Lync Server 2013 Enterprise Edition のファイル共有は、フロントエンドサーバーに配置できません。

    
    </div>

  - Web サービス用のロードバランサー機器をインストールしてセットアップします。 ドメイン ネーム システム (DNS) の負荷分散が展開されている場合には、その後もこれらのプールでハードウェア ロード バランサーを使用する必要がありますが、HTTP/HTTPS トラフィックの場合だけです。 ハードウェア ロード バランサーは、クライアントからのポート 443 および 80 経由での HTTPS トラフィックで使用されます。 これらのプール用のハードウェア ロード バランサーは引き続き必要ですが、そのセットアップと管理は主に HTTP/HTTPS トラフィックに対するものであり、ハードウェア ロード バランサーの管理者にはなじみのあるものです。

このトピックの説明に従ってすべての準備タスクを完了したた場合でも、トポロジの公開前に、次のタスクを完了させておく必要があります。

  - [Lync Server 2013 のサーバーにオペレーティングシステムと必要なソフトウェアをインストールする](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [Lync Server 2013 の IIS を構成する](lync-server-2013-configure-iis.md)

  - [Lync Server 2013 用 SQL Server の構成](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [フロントエンドプールまたは Standard Edition サーバーの Lync Server 2013 で DNS レコードを構成する](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

