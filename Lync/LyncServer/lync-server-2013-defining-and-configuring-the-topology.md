---
title: 'Lync Server 2013: トポロジの定義と構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86f98c5961385bd2f99c0698af1b5f422abe4c60
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504544"
---
# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a>Lync Server 2013 でのトポロジの定義と構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-14_

トポロジビルダーを使用して、トポロジを定義および構成します。 トポロジビルダーでは、ローカルの Administrators グループまたは権限のあるドメイングループ (Domain Admins など) のメンバーである必要はありません。 標準ユーザーでもトポロジを定義できます。 初めてトポロジ ビルダーを起動して、その後、編集セッションを行う場合、トポロジ ビルダーに現在の構成ドキュメントを読み込ませる場所を指定するようメッセージが表示されます。 選択肢には以下があります。

  - 既存の展開環境からトポロジをダウンロードする

  - ローカル ファイルからトポロジを開く

  - 新しいトポロジ

トポロジを既に定義していて、中央管理ストアを設定している場合は、既存の展開からトポロジをダウンロードすることを選択する必要があります。 トポロジ ビルダーは、データベースを読み取り、現在の定義を取得します。 既存の中央管理ストアがある場合は、常にこのオプションを選択する必要があります。

中央管理ストアが確立されておらず、以前に保存された構成を編集する場合は、ローカルファイルからトポロジを開くことを選択する必要があります。 開くファイルは、以前のセッションで保存した構成ファイルになります。 このオプションを使用して、以前保存されたトポロジを編集することができます。

<div>


> [!WARNING]  
> トポロジを既に公開している場合は、ローカル構成ファイルを読み込まないでください。 既存の展開環境からトポロジをダウンロードする必要があります。



</div>

新しいトポロジビルダー構成を作成する場合は、新しいトポロジを作成することを選択します。 以前の設計セッションで作成したものと同じファイルとして保存しなければ、以前保存した設計は上書きされません。

これらの各オプションでは、トポロジビルダー構成ファイルを保存する場所を指定するように求められます。 ファイルの場所は、ローカルの場所、確立されたファイル共有の共有の場所、またはリムーバブル メディアにすることができます。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 のトポロジビルダーでのトポロジの定義と構成](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [Lync Server 2013 でのフロントエンドプールまたは Standard Edition サーバーの定義と構成](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [Lync Server 2013 での障害復旧用のペアのフロントエンドプールの展開](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [Lync Server 2013 でバックエンドサーバーの高可用性を実現するための SQL ミラーリングの展開](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [Lync Server 2013 での簡易 Url の編集または構成](lync-server-2013-edit-or-configure-simple-urls.md)

  - [Lync Server 2013 で中央管理サーバーを選択します。](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

