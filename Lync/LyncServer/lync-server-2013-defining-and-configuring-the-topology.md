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
ms.openlocfilehash: 8430ec5cc8b362aa78f97afc24ab0e588c7bc650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a>Lync Server 2013 でのトポロジの定義と構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-14_

トポロジを定義して構成するには、トポロジビルダーを使用します。 トポロジビルダーでは、ローカルの管理者グループまたは (Domain Admins など) の権限を持つドメイングループのメンバーである必要はありません。 トポロジは標準ユーザーとして定義できます。 最初の使用時と後続の編集セッションでトポロジビルダーを起動すると、トポロジビルダーで現在の構成ドキュメントを読み込む場所を確認するメッセージが表示されます。 以下の選択肢があります。

  - 既存の展開環境からトポロジをダウンロードする

  - ローカルファイルからトポロジを開く

  - 新しいトポロジ

トポロジを既に定義していて、全体管理ストアを確立している場合は、既存の展開からトポロジをダウンロードすることを選択する必要があります。 トポロジビルダーはデータベースを読み取り、現在の定義を取得します。 既存のサーバーの全体管理ストアがある場合は、常にこのオプションを選択する必要があります。

一元管理ストアを確立していない場合に、以前に保存した構成を編集するには、ローカルファイルからトポロジを開くように選択する必要があります。 開こうとしているファイルは、以前のセッションで保存された構成ファイルです。 このオプションを使用して、以前に保存したトポロジを編集できます。

<div>


> [!WARNING]  
> 公開されているトポロジを既に持っている場合は、ローカル構成ファイルを読み込まないでください。 既存の展開からトポロジをダウンロードすることを選択する必要があります。



</div>

新しいトポロジビルダー構成を作成する場合は、新しいトポロジを作成します。 以前のデザインセッションで作成したのと同じファイルとして保存するように選択しない限り、以前に保存したデザインは上書きされません。

これらの各オプションでは、トポロジビルダー構成ファイルを保存する場所を指定するように求められます。 ファイルの場所は、ローカルの場所、確立されたファイル共有上の共有の場所、リムーバブルメディアのいずれかになります。

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 のトポロジ ビルダーでのトポロジの定義と構成](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [Lync Server 2013 でフロントエンド プールまたは Standard Edition サーバーを定義および構成する](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [Lync Server 2013 での障害復旧用のペアのフロント エンド プールの展開](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [Lync Server 2013 でのバックエンド サーバーの高可用性を実現するための SQL ミラーリングの展開](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [Lync Server 2013 での簡単な URL の編集または構成](lync-server-2013-edit-or-configure-simple-urls.md)

  - [Lync Server 2013 での中央管理サーバーの選択](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

