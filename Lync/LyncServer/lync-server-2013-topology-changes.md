---
title: Lync Server 2013 トポロジの変更
description: Lync Server 2013 トポロジの変更。
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
ms.openlocfilehash: 562766eae939e4510a0d3af20e40b4731c361040
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549103"
---
# <a name="topology-changes-in-lync-server-2013"></a><span data-ttu-id="b812a-103">Lync Server 2013 のトポロジの変更</span><span class="sxs-lookup"><span data-stu-id="b812a-103">Topology changes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b812a-104">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="b812a-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="b812a-105">Lync Server 2013 のトポロジの要件および考慮事項は、このセクションで説明するように、以前のリリースとは異なります。</span><span class="sxs-lookup"><span data-stu-id="b812a-105">Topology requirements and considerations for Lync Server 2013 are different from those for earlier releases, as described in this section.</span></span>

<div>

## <a name="new-front-end-pools-architecture"></a><span data-ttu-id="b812a-106">新しいフロントエンド プール アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="b812a-106">New Front End Pools Architecture</span></span>

<span data-ttu-id="b812a-107">Lync Server 2013 では、Enterprise Edition フロントエンドプールのアーキテクチャが分散システムアーキテクチャに変更されました。</span><span class="sxs-lookup"><span data-stu-id="b812a-107">In Lync Server 2013, the architecture of Enterprise Edition Front End pools has changed to a distributed systems architecture.</span></span>

<span data-ttu-id="b812a-p101">この新しいアーキテクチャでは、バック エンド データベースはプールのリアルタイム データ ストアではなくなりました。特定のユーザーに関する情報は、プールの 3 つのフロントエンド サーバーで保持されます。各ユーザーに対して、1 つのフロントエンド サーバーがそのユーザーの情報のマスターとして機能し、他の 2 つのフロントエンド サーバーがレプリカとして機能します。フロントエンド サーバーがダウンすると、レプリカとして機能していた別のフロントエンド サーバーが自動的にマスターに昇格します。</span><span class="sxs-lookup"><span data-stu-id="b812a-p101">With this new architecture, the Back End database is no longer the real-time data store in a pool. Information about a particular user is kept on three Front End Servers in the pool. For each user, one Front End Server acts as the master for that user’s information, and two other Front End Servers serve as replicas. If a Front End Server goes down, another Front End Server which served as a replica is automatically promoted to master.</span></span>

<span data-ttu-id="b812a-112">この操作は内部で行われるため、どのフロントエンド サーバーがどのユーザーのマスターになっているかを管理者が知る必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b812a-112">This happens behind the scenes, and administrators do not need to know which Front End Servers are the masters for which users.</span></span> <span data-ttu-id="b812a-113">このデータ記憶域の配布により、プール内のパフォーマンスとスケーラビリティが向上し、単一のバックエンドサーバーの単一障害点が排除されます。</span><span class="sxs-lookup"><span data-stu-id="b812a-113">This distribution of data storage improves performance and scalability within the pool, and eliminates the single point of failure of a single Back End Server.</span></span>

<span data-ttu-id="b812a-114">バック エンド サーバーは、ユーザー データと会議データのバックアップ ストレージとして機能します。バック エンド サーバーは、応答グループ データベースなどの他のデータベースのプライマリ ストレージでもあります。</span><span class="sxs-lookup"><span data-stu-id="b812a-114">The Back End Server serves as backup storage for user and conference data, and is also the primary storage for other databases such as the Response Group database.</span></span>

<span data-ttu-id="b812a-115">これらの機能強化により、プールの計画と管理の方法が変更されることも意味します。</span><span class="sxs-lookup"><span data-stu-id="b812a-115">These improvements also mean there are changes in how you plan and maintain your pools.</span></span> <span data-ttu-id="b812a-116">すべての Enterprise Edition フロントエンドプールには、フロントエンドプールのアーキテクチャが設計されているレプリカの全数を提供するために、少なくとも3台のフロントエンドサーバーを含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b812a-116">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers, to provide the full number of replicas that the Front End pool architecture is designed for.</span></span> <span data-ttu-id="b812a-117">また、フロントエンドプールにサーバーを追加したり、サーバーを削除したり、サーバーをアップグレードしたりするときは、特定の手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b812a-117">Additionally, you must follow certain procedures when adding servers to a Front End pool, removing servers from it, or upgrading servers.</span></span> <span data-ttu-id="b812a-118">詳細については、「 [Lync Server 2013 でのフロントエンドサーバー、インスタントメッセージング、およびプレゼンスのトポロジとコンポーネント](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b812a-118">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<div>

## <a name="server-role-topology-changes"></a><span data-ttu-id="b812a-119">サーバーの役割のトポロジの変更</span><span class="sxs-lookup"><span data-stu-id="b812a-119">Server Role Topology Changes</span></span>

<span data-ttu-id="b812a-120">これまで個別のサーバーで実行されていたいくつかのサーバーの役割がフロントエンド サーバーの役割に統合され、ハードウェアのコストを節約できます。</span><span class="sxs-lookup"><span data-stu-id="b812a-120">Some server roles that previously ran on separate servers are now consolidated into the Front End Server role, enabling you to save on hardware costs</span></span>

  - <span data-ttu-id="b812a-121">Lync Server 2013 では、音声ビデオ会議サーバーは常にフロントエンドサーバーと併置されています。</span><span class="sxs-lookup"><span data-stu-id="b812a-121">In Lync Server 2013, A/V Conferencing Server is always collocated with Front End Server.</span></span>

  - <span data-ttu-id="b812a-p104">監視とアーカイブのフロントエンドは、常にフロントエンド サーバーと併置されるようになりました。監視とアーカイブは、それぞれ個別のバック エンド データベースが引き続き必要ですが、これはフロントエンド プールのバック エンド データベースと同じサーバーに併置するか、個別のバック エンド サーバーでホストできます。</span><span class="sxs-lookup"><span data-stu-id="b812a-p104">The front ends for both Monitoring and Archiving are now always collocated with Front End Server. Monitoring and Archiving each still require a separate Back-End Database, which can be collocated on the same server as the Front End Pool’s back-end database, or can be hosted on separate Back-End Servers.</span></span>

  - <span data-ttu-id="b812a-124">常設チャットサーバーは、サーバーの役割になっています。</span><span class="sxs-lookup"><span data-stu-id="b812a-124">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="b812a-125">Microsoft Lync Server 2010 のグループチャットサーバーは、Microsoft Lync Server 2010 用のサードパーティの信頼されたアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="b812a-125">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="b812a-126">Lync Server 2013 では、次の3つの新しいサーバーの役割を使用して常設チャットサーバーの機能が実装されます。</span><span class="sxs-lookup"><span data-stu-id="b812a-126">In Lync Server 2013, Persistent Chat Server functionality is implemented using three new server roles:</span></span>
    
      - <span data-ttu-id="b812a-127">**PersistentChatService:** フロントエンドの役割として実装されているメインの常設チャットサーバーサービス</span><span class="sxs-lookup"><span data-stu-id="b812a-127">**PersistentChatService:** Main Persistent Chat Server services implemented as a front end role</span></span>
    
      - <span data-ttu-id="b812a-128">**PersistentChatStore:** バックエンドサーバーの役割</span><span class="sxs-lookup"><span data-stu-id="b812a-128">**PersistentChatStore:** Back End Server role</span></span>
    
      - <span data-ttu-id="b812a-129">**PersistentChatComplianceStore:** 常設チャットコンプライアンスのバックエンドサーバーの役割</span><span class="sxs-lookup"><span data-stu-id="b812a-129">**PersistentChatComplianceStore:** Back End Server role for Persistent Chat Compliance</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

