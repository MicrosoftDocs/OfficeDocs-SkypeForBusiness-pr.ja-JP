---
title: 'Lync Server 2013: データと設定の復元'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring data and settings
ms:assetid: b07f5dd7-7bed-4819-8cb5-617f5acd478e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202185(v=OCS.15)
ms:contentKeyID: 51541503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d34d62aa5a27a3f59bae0893c4004ca25c2cb039
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-data-and-settings-in-lync-server-2013"></a>Lync Server 2013 でのデータと設定の復元

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-17_

プールのペアを使用して障害復旧トポロジを実装していて、それらのフロントエンドプールのうちの1つがダウンしていて、ユーザーにサービスを迅速に復元する必要がある場合は、「 [Lync Server 2013 でプールをフェールオーバー](lync-server-2013-failing-over-a-pool.md)する」を参照してください。 それ以外の場合は、以下のトピックの情報を、 [Lync server 2013 のバックアップおよび復元ワークシート](lync-server-2013-backup-and-restoration-worksheets.md)のワークシートと共に使用して、障害または停止の後に lync server を復元します。

<div>


> [!NOTE]  
> ダウンタイムとデータ損失の可能性を軽減するために、このドキュメントで説明する復元手順は、問題を特定して修正する際にトラブルシューティング手順が効果的でない場合にのみ実行してください。 トラブルシューティングの際に、サーバーをシャットダウンして再起動すると、他のサーバーやコンポーネントへの影響を最小限に抑えるようにしてください。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 の復元の準備](lync-server-2013-preparing-to-restore-lync-server.md)

  - [Lync Server 2013 での Standard Edition サーバーの復元](lync-server-2013-restoring-a-standard-edition-server.md)

  - [Lync Server 2013 で中央管理ストアをホストしているサーバーを復元する](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)

  - [Lync Server 2013 で Enterprise Edition バックエンドサーバーを復元する](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)

  - [Lync Server 2013 での Enterprise Edition メンバーサーバーの復元](lync-server-2013-restoring-an-enterprise-edition-member-server.md)

  - [Lync server 2013 での Lync Server プールの復元](lync-server-2013-restoring-a-lync-server-pool.md)

  - [Lync Server 2013 での ABC フロントエンドプールのフェールオーバーの実行](lync-server-2013-performing-an-abc-front-end-pool-failover.md)

  - [Lync Server 2013 でのファイルストアの復元](lync-server-2013-restoring-a-file-store.md)

  - [Lync Server 2013 での監視またはアーカイブデータの復元](lync-server-2013-restoring-monitoring-or-archiving-data.md)

  - [Lync Server 2013 での常設チャットデータの復元](lync-server-2013-restoring-persistent-chat-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

