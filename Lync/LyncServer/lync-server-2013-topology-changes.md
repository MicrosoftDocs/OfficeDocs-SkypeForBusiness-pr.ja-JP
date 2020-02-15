---
title: Lync Server 2013 トポロジの変更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a993057d3aae52b1c080d05fe9bba4eaff1ebeab
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a>Lync Server 2013 のトポロジの変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-02_

Lync Server 2013 のトポロジの要件および考慮事項は、このセクションで説明するように、以前のリリースとは異なります。

<div>

## <a name="new-front-end-pools-architecture"></a>新しいフロントエンド プール アーキテクチャ

Lync Server 2013 では、Enterprise Edition フロントエンドプールのアーキテクチャが分散システムアーキテクチャに変更されました。

この新しいアーキテクチャでは、バック エンド データベースはプールのリアルタイム データ ストアではなくなりました。特定のユーザーに関する情報は、プールの 3 つのフロントエンド サーバーで保持されます。各ユーザーに対して、1 つのフロントエンド サーバーがそのユーザーの情報のマスターとして機能し、他の 2 つのフロントエンド サーバーがレプリカとして機能します。フロントエンド サーバーがダウンすると、レプリカとして機能していた別のフロントエンド サーバーが自動的にマスターに昇格します。

この操作は内部で行われるため、どのフロントエンド サーバーがどのユーザーのマスターになっているかを管理者が知る必要はありません。 このデータ記憶域の配布により、プール内のパフォーマンスとスケーラビリティが向上し、単一のバックエンドサーバーの単一障害点が排除されます。

バック エンド サーバーは、ユーザー データと会議データのバックアップ ストレージとして機能します。バック エンド サーバーは、応答グループ データベースなどの他のデータベースのプライマリ ストレージでもあります。

これらの機能強化により、プールの計画と管理の方法が変更されることも意味します。 すべての Enterprise Edition フロントエンドプールには、フロントエンドプールのアーキテクチャが設計されているレプリカの全数を提供するために、少なくとも3台のフロントエンドサーバーを含めることをお勧めします。 また、フロントエンドプールにサーバーを追加したり、サーバーを削除したり、サーバーをアップグレードしたりするときは、特定の手順に従う必要があります。 詳細については、「 [Lync Server 2013 でのフロントエンドサーバー、インスタントメッセージング、およびプレゼンスのトポロジとコンポーネント](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)」を参照してください。

<div>

## <a name="server-role-topology-changes"></a>サーバーの役割のトポロジの変更

これまで個別のサーバーで実行されていたいくつかのサーバーの役割がフロントエンド サーバーの役割に統合され、ハードウェアのコストを節約できます。

  - Lync Server 2013 では、音声ビデオ会議サーバーは常にフロントエンドサーバーと併置されています。

  - 監視とアーカイブのフロントエンドは、常にフロントエンド サーバーと併置されるようになりました。監視とアーカイブは、それぞれ個別のバック エンド データベースが引き続き必要ですが、これはフロントエンド プールのバック エンド データベースと同じサーバーに併置するか、個別のバック エンド サーバーでホストできます。

  - 常設チャットサーバーは、サーバーの役割になっています。 Microsoft Lync Server 2010 のグループチャットサーバーは、Microsoft Lync Server 2010 用のサードパーティの信頼されたアプリケーションです。 Lync Server 2013 では、次の3つの新しいサーバーの役割を使用して常設チャットサーバーの機能が実装されます。
    
      - **PersistentChatService:** フロントエンドの役割として実装されているメインの常設チャットサーバーサービス
    
      - **PersistentChatStore:** バックエンドサーバーの役割
    
      - **PersistentChatComplianceStore:** 常設チャットコンプライアンスのバックエンドサーバーの役割

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

