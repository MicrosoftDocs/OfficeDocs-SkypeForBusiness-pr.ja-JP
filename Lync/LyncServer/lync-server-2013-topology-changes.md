---
title: 'Lync Server 2013: トポロジの変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f0ea02d1643a686e16d3d1984e756a48311b421
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a>Lync Server 2013 のトポロジの変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-02_

このセクションで説明するように、トポロジの要件と Lync Server 2013 に関する考慮事項は、以前のリリースとは異なります。

<div>

## <a name="new-front-end-pools-architecture"></a>新しいフロントエンドプールのアーキテクチャ

Lync Server 2013 では、Enterprise Edition のフロントエンドプールのアーキテクチャが分散システムアーキテクチャに変更されています。

この新しいアーキテクチャでは、バックエンドデータベースはプール内のリアルタイムデータストアではなくなりました。 特定のユーザーに関する情報は、プール内の3つのフロントエンドサーバー上に保持されます。 各ユーザーに対して、1つのフロントエンドサーバーがそのユーザーの情報のマスターとして機能し、他の2つのフロントエンドサーバーが複製として機能します。 フロントエンドサーバーがダウンした場合、レプリカとして提供されている別のフロントエンドサーバーが自動的にマスターに昇格されます。

これはバックグラウンドで行われるため、管理者はどのフロントエンドサーバーがどのユーザー用のマスターであるかを知る必要はありません。 このデータ記憶域の配布によって、プール内のパフォーマンスとスケーラビリティが向上し、1つのバックエンドサーバーの1つの障害ポイントが排除されます。

バックエンドサーバーは、ユーザーおよび会議データのバックアップストレージとして機能します。また、応答グループデータベースなど、他のデータベースのプライマリストレージでもあります。

これらの改善により、プールの計画や管理方法が変更されることもあります。 すべての Enterprise Edition のフロントエンドプールには、少なくとも3台のフロントエンドサーバーが含まれていることをお勧めします。これには、フロントエンドプールアーキテクチャが設計されているすべてのレプリカの数を指定します。 また、フロントエンドプールにサーバーを追加するとき、サーバーからサーバーを削除するとき、またはサーバーをアップグレードするときに、特定の手順に従う必要があります。 詳細については、「 [Lync Server 2013 のフロントエンドサーバー、インスタントメッセージング、およびプレゼンスのトポロジとコンポーネント」を](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)参照してください。

<div>

## <a name="server-role-topology-changes"></a>サーバーの役割のトポロジの変更

別のサーバー上で以前に実行した一部のサーバーの役割は、フロントエンドサーバーの役割に統合され、ハードウェアのコストを節約できるようになりました。

  - Lync Server 2013 では、A/V 会議サーバーは、常にフロントエンドサーバーと連携しています。

  - 監視とアーカイブの両方のフロントエンドが、常にフロントエンドサーバーと併置されるようになりました。 監視とアーカイブを行うには、フロントエンドプールのバックエンドデータベースと同じサーバーに併置できる別個のバックエンドデータベースが必要です。または、個別のバックエンドサーバーでホストすることもできます。

  - 常設チャットサーバーがサーバーの役割になりました。 Microsoft Lync Server 2010 では、グループチャットサーバーは Microsoft Lync Server 2010 用のサードパーティの信頼済みアプリケーションです。 Lync Server 2013 では、次の3つの新しいサーバーの役割を使用して、常設チャットサーバー機能が実装されています。
    
      - **PersistentChatService:** フロントエンドロールとして実装されたメインの常設チャットサーバーサービス
    
      - **PersistentChatStore:** バックエンドサーバーの役割
    
      - **PersistentChatComplianceStore:** 常設チャットのコンプライアンスのためのバックエンドサーバーの役割

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

