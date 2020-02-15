---
title: 'Lync Server 2013: インフラストラクチャとシステムの準備'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the infrastructure and systems
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48183458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34de50135ff04c7db1b3eda2b65bdebb4ef10273
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a>Lync Server 2013 のインフラストラクチャとシステムの準備

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

Lync Server 2013 の展開では、トポロジビルダーを使用してトポロジ設計を定義して公開する必要があります。 トポロジに必要なコンポーネントを特定するには、トポロジビルダーを使用してトポロジ設計を作成し、保存します。 トポロジ ビルダーでトポロジを公開する前に、次の操作を実行します。

  - 必要なすべてのコンピューター (Lync Server 2013、データベースサーバー、インターネットインフォメーションサービスを実行しているサーバーを実行しているサーバー) を含む、トポロジビルダーを使用して作成および保存した各コンポーネントのハードウェアを取得してインストールします (IIS)、リバースプロキシサーバー、必要に応じて、ネットワークアダプター、ハードウェアロードバランサー、およびストレージデバイス (ファイルサーバーなど)。 展開に必要なコンポーネントを指定するトポロジを定義する方法の詳細については、「 [Lync Server 2013 でのトポロジの定義と構成](lync-server-2013-defining-and-configuring-the-topology.md)」を参照してください。 サーバーのハードウェア要件の詳細については、「サポート」のドキュメントの「supported [hardware For Lync Server 2013](lync-server-2013-supported-hardware.md) 」を参照してください。

  - ネットワークインフラストラクチャが要件を満たしていることを確認してください。 詳細については、「計画」のドキュメントの「 [Lync Server 2013 のネットワークインフラストラクチャ要件](lync-server-2013-network-infrastructure-requirements.md)」を参照してください。

  - Active Directory ドメインサービスをセットアップします。 トポロジを公開し、有効化するには、内部サーバーが AD DS のコンピューター アカウントで表される必要があります。 そのようにするには、コンピューターを AD DS に参加させます。 AD DS の準備の詳細については、「 [Lync Server 2013 用の Active Directory ドメインサービスの準備](lync-server-2013-preparing-active-directory-domain-services.md)」を参照してください。

  - ファイル共有を作成します。 Standard Edition サーバーは必要なファイルのファイル共有をホストできますが、Enterprise 展開ではフロントエンド サーバーでファイル共有をホストできません。 トポロジ ビルダーが正常に完了するには、フォルダーと共有に対するアクセス制御リスト (ACL) の展開と設定に必要なアクセス許可とグループ メンバーシップを正しく設定する必要があります。 トポロジビルダーを実行しているユーザーに、次のアクセス許可とグループメンバーシップがあることを確認する必要があります。
    
      - ローカルの Administrators グループのメンバー
    
      - Domain Users グループのメンバー
    
      - ファイル ストアの共有とフォルダーに対するフル コントロール

  - Enterprise Edition の場合は、SQL Server をインストールし、構成します。SQL Server を正常にセットアップするには、SQL Server ベースのサーバーがオンラインであることと、トポロジを公開する担当者が SQL Server のローカル管理者であり、SQL Server インスタンスの SQL Server sysadmin グループのメンバーであることが必要です。

このトピックで説明する準備タスクをすべて完了した後、トポロジを公開する前に、Windows オペレーティング システムや前提条件となる他のソフトウェアのインストール、IIS のセットアップ、DNS の構成など、他の準備タスクも行う必要があります。 これらのタスクの詳細については、「 [Lync server 2013 を実行するサーバーのシステム要件](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md)」、「 [Configure IIS for lync server 2013](lync-server-2013-configure-iis.md)」、および「 [lync server 2013 のインフラストラクチャとシステムの準備](lync-server-2013-preparing-the-infrastructure-and-systems.md)」を参照してください。 また、クライアントとクライアントの要件についても把握しておく必要があります。 詳細については、「 [Lync Server 2013 でのクライアントとデバイスの展開](lync-server-2013-deploying-clients-and-devices.md)」を参照してください。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 のハードウェアのセットアップ](lync-server-2013-hardware-setup.md)

  - [Lync Server 2013 のソフトウェアのセットアップ](lync-server-2013-software-setup.md)

  - [Lync Server 2013 用の Active Directory ドメイン サービスの準備](lync-server-2013-preparing-active-directory-domain-services.md)

  - [Lync Server 2013 用 SQL Server の構成](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [フロントエンドプールまたは Standard Edition サーバーの Lync Server 2013 で DNS レコードを構成する](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [Lync Server 2013 管理ツールのインストール](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

