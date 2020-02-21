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
ms.openlocfilehash: ac7cf9fe1bdabcba4b0b5fc1134f1835407041a5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a><span data-ttu-id="43c7b-102">Lync Server 2013 のトポロジの変更</span><span class="sxs-lookup"><span data-stu-id="43c7b-102">Topology changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43c7b-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="43c7b-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="43c7b-104">Lync Server 2013 のトポロジの要件および考慮事項は、このセクションで説明するように、以前のリリースとは異なります。</span><span class="sxs-lookup"><span data-stu-id="43c7b-104">Topology requirements and considerations for Lync Server 2013 are different from those for earlier releases, as described in this section.</span></span>

<div>

## <a name="new-front-end-pools-architecture"></a><span data-ttu-id="43c7b-105">新しいフロントエンド プール アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="43c7b-105">New Front End Pools Architecture</span></span>

<span data-ttu-id="43c7b-106">Lync Server 2013 では、Enterprise Edition フロントエンドプールのアーキテクチャが分散システムアーキテクチャに変更されました。</span><span class="sxs-lookup"><span data-stu-id="43c7b-106">In Lync Server 2013, the architecture of Enterprise Edition Front End pools has changed to a distributed systems architecture.</span></span>

<span data-ttu-id="43c7b-p101">この新しいアーキテクチャでは、バック エンド データベースはプールのリアルタイム データ ストアではなくなりました。特定のユーザーに関する情報は、プールの 3 つのフロントエンド サーバーで保持されます。各ユーザーに対して、1 つのフロントエンド サーバーがそのユーザーの情報のマスターとして機能し、他の 2 つのフロントエンド サーバーがレプリカとして機能します。フロントエンド サーバーがダウンすると、レプリカとして機能していた別のフロントエンド サーバーが自動的にマスターに昇格します。</span><span class="sxs-lookup"><span data-stu-id="43c7b-p101">With this new architecture, the Back End database is no longer the real-time data store in a pool. Information about a particular user is kept on three Front End Servers in the pool. For each user, one Front End Server acts as the master for that user’s information, and two other Front End Servers serve as replicas. If a Front End Server goes down, another Front End Server which served as a replica is automatically promoted to master.</span></span>

<span data-ttu-id="43c7b-111">この操作は内部で行われるため、どのフロントエンド サーバーがどのユーザーのマスターになっているかを管理者が知る必要はありません。</span><span class="sxs-lookup"><span data-stu-id="43c7b-111">This happens behind the scenes, and administrators do not need to know which Front End Servers are the masters for which users.</span></span> <span data-ttu-id="43c7b-112">このデータ記憶域の配布により、プール内のパフォーマンスとスケーラビリティが向上し、単一のバックエンドサーバーの単一障害点が排除されます。</span><span class="sxs-lookup"><span data-stu-id="43c7b-112">This distribution of data storage improves performance and scalability within the pool, and eliminates the single point of failure of a single Back End Server.</span></span>

<span data-ttu-id="43c7b-113">バック エンド サーバーは、ユーザー データと会議データのバックアップ ストレージとして機能します。バック エンド サーバーは、応答グループ データベースなどの他のデータベースのプライマリ ストレージでもあります。</span><span class="sxs-lookup"><span data-stu-id="43c7b-113">The Back End Server serves as backup storage for user and conference data, and is also the primary storage for other databases such as the Response Group database.</span></span>

<span data-ttu-id="43c7b-114">これらの機能強化により、プールの計画と管理の方法が変更されることも意味します。</span><span class="sxs-lookup"><span data-stu-id="43c7b-114">These improvements also mean there are changes in how you plan and maintain your pools.</span></span> <span data-ttu-id="43c7b-115">すべての Enterprise Edition フロントエンドプールには、フロントエンドプールのアーキテクチャが設計されているレプリカの全数を提供するために、少なくとも3台のフロントエンドサーバーを含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="43c7b-115">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers, to provide the full number of replicas that the Front End pool architecture is designed for.</span></span> <span data-ttu-id="43c7b-116">また、フロントエンドプールにサーバーを追加したり、サーバーを削除したり、サーバーをアップグレードしたりするときは、特定の手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="43c7b-116">Additionally, you must follow certain procedures when adding servers to a Front End pool, removing servers from it, or upgrading servers.</span></span> <span data-ttu-id="43c7b-117">詳細については、「 [Lync Server 2013 でのフロントエンドサーバー、インスタントメッセージング、およびプレゼンスのトポロジとコンポーネント](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43c7b-117">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<div>

## <a name="server-role-topology-changes"></a><span data-ttu-id="43c7b-118">サーバーの役割のトポロジの変更</span><span class="sxs-lookup"><span data-stu-id="43c7b-118">Server Role Topology Changes</span></span>

<span data-ttu-id="43c7b-119">これまで個別のサーバーで実行されていたいくつかのサーバーの役割がフロントエンド サーバーの役割に統合され、ハードウェアのコストを節約できます。</span><span class="sxs-lookup"><span data-stu-id="43c7b-119">Some server roles that previously ran on separate servers are now consolidated into the Front End Server role, enabling you to save on hardware costs</span></span>

  - <span data-ttu-id="43c7b-120">Lync Server 2013 では、音声ビデオ会議サーバーは常にフロントエンドサーバーと併置されています。</span><span class="sxs-lookup"><span data-stu-id="43c7b-120">In Lync Server 2013, A/V Conferencing Server is always collocated with Front End Server.</span></span>

  - <span data-ttu-id="43c7b-p104">監視とアーカイブのフロントエンドは、常にフロントエンド サーバーと併置されるようになりました。監視とアーカイブは、それぞれ個別のバック エンド データベースが引き続き必要ですが、これはフロントエンド プールのバック エンド データベースと同じサーバーに併置するか、個別のバック エンド サーバーでホストできます。</span><span class="sxs-lookup"><span data-stu-id="43c7b-p104">The front ends for both Monitoring and Archiving are now always collocated with Front End Server. Monitoring and Archiving each still require a separate Back-End Database, which can be collocated on the same server as the Front End Pool’s back-end database, or can be hosted on separate Back-End Servers.</span></span>

  - <span data-ttu-id="43c7b-123">常設チャットサーバーは、サーバーの役割になっています。</span><span class="sxs-lookup"><span data-stu-id="43c7b-123">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="43c7b-124">Microsoft Lync Server 2010 のグループチャットサーバーは、Microsoft Lync Server 2010 用のサードパーティの信頼されたアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="43c7b-124">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="43c7b-125">Lync Server 2013 では、次の3つの新しいサーバーの役割を使用して常設チャットサーバーの機能が実装されます。</span><span class="sxs-lookup"><span data-stu-id="43c7b-125">In Lync Server 2013, Persistent Chat Server functionality is implemented using three new server roles:</span></span>
    
      - <span data-ttu-id="43c7b-126">**PersistentChatService:** フロントエンドの役割として実装されているメインの常設チャットサーバーサービス</span><span class="sxs-lookup"><span data-stu-id="43c7b-126">**PersistentChatService:** Main Persistent Chat Server services implemented as a front end role</span></span>
    
      - <span data-ttu-id="43c7b-127">**PersistentChatStore:** バックエンドサーバーの役割</span><span class="sxs-lookup"><span data-stu-id="43c7b-127">**PersistentChatStore:** Back End Server role</span></span>
    
      - <span data-ttu-id="43c7b-128">**PersistentChatComplianceStore:** 常設チャットコンプライアンスのバックエンドサーバーの役割</span><span class="sxs-lookup"><span data-stu-id="43c7b-128">**PersistentChatComplianceStore:** Back End Server role for Persistent Chat Compliance</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

