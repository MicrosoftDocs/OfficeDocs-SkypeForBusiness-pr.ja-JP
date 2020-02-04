---
title: 'Lync Server 2013: トポロジの変更'
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
ms.openlocfilehash: c4453a9b5b8a5fcd60eaad1e437fd4800caddfba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a><span data-ttu-id="2d90e-102">Lync Server 2013 のトポロジの変更</span><span class="sxs-lookup"><span data-stu-id="2d90e-102">Topology changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d90e-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="2d90e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="2d90e-104">このセクションで説明するように、トポロジの要件と Lync Server 2013 に関する考慮事項は、以前のリリースとは異なります。</span><span class="sxs-lookup"><span data-stu-id="2d90e-104">Topology requirements and considerations for Lync Server 2013 are different from those for earlier releases, as described in this section.</span></span>

<div>

## <a name="new-front-end-pools-architecture"></a><span data-ttu-id="2d90e-105">新しいフロントエンドプールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="2d90e-105">New Front End Pools Architecture</span></span>

<span data-ttu-id="2d90e-106">Lync Server 2013 では、Enterprise Edition のフロントエンドプールのアーキテクチャが分散システムアーキテクチャに変更されています。</span><span class="sxs-lookup"><span data-stu-id="2d90e-106">In Lync Server 2013, the architecture of Enterprise Edition Front End pools has changed to a distributed systems architecture.</span></span>

<span data-ttu-id="2d90e-107">この新しいアーキテクチャでは、バックエンドデータベースはプール内のリアルタイムデータストアではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="2d90e-107">With this new architecture, the Back End database is no longer the real-time data store in a pool.</span></span> <span data-ttu-id="2d90e-108">特定のユーザーに関する情報は、プール内の3つのフロントエンドサーバー上に保持されます。</span><span class="sxs-lookup"><span data-stu-id="2d90e-108">Information about a particular user is kept on three Front End Servers in the pool.</span></span> <span data-ttu-id="2d90e-109">各ユーザーに対して、1つのフロントエンドサーバーがそのユーザーの情報のマスターとして機能し、他の2つのフロントエンドサーバーが複製として機能します。</span><span class="sxs-lookup"><span data-stu-id="2d90e-109">For each user, one Front End Server acts as the master for that user’s information, and two other Front End Servers serve as replicas.</span></span> <span data-ttu-id="2d90e-110">フロントエンドサーバーがダウンした場合、レプリカとして提供されている別のフロントエンドサーバーが自動的にマスターに昇格されます。</span><span class="sxs-lookup"><span data-stu-id="2d90e-110">If a Front End Server goes down, another Front End Server which served as a replica is automatically promoted to master.</span></span>

<span data-ttu-id="2d90e-111">これはバックグラウンドで行われるため、管理者はどのフロントエンドサーバーがどのユーザー用のマスターであるかを知る必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2d90e-111">This happens behind the scenes, and administrators do not need to know which Front End Servers are the masters for which users.</span></span> <span data-ttu-id="2d90e-112">このデータ記憶域の配布によって、プール内のパフォーマンスとスケーラビリティが向上し、1つのバックエンドサーバーの1つの障害ポイントが排除されます。</span><span class="sxs-lookup"><span data-stu-id="2d90e-112">This distribution of data storage improves performance and scalability within the pool, and eliminates the single point of failure of a single Back End Server.</span></span>

<span data-ttu-id="2d90e-113">バックエンドサーバーは、ユーザーおよび会議データのバックアップストレージとして機能します。また、応答グループデータベースなど、他のデータベースのプライマリストレージでもあります。</span><span class="sxs-lookup"><span data-stu-id="2d90e-113">The Back End Server serves as backup storage for user and conference data, and is also the primary storage for other databases such as the Response Group database.</span></span>

<span data-ttu-id="2d90e-114">これらの改善により、プールの計画や管理方法が変更されることもあります。</span><span class="sxs-lookup"><span data-stu-id="2d90e-114">These improvements also mean there are changes in how you plan and maintain your pools.</span></span> <span data-ttu-id="2d90e-115">すべての Enterprise Edition のフロントエンドプールには、少なくとも3台のフロントエンドサーバーが含まれていることをお勧めします。これには、フロントエンドプールアーキテクチャが設計されているすべてのレプリカの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d90e-115">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers, to provide the full number of replicas that the Front End pool architecture is designed for.</span></span> <span data-ttu-id="2d90e-116">また、フロントエンドプールにサーバーを追加するとき、サーバーからサーバーを削除するとき、またはサーバーをアップグレードするときに、特定の手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d90e-116">Additionally, you must follow certain procedures when adding servers to a Front End pool, removing servers from it, or upgrading servers.</span></span> <span data-ttu-id="2d90e-117">詳細については、「 [Lync Server 2013 のフロントエンドサーバー、インスタントメッセージング、およびプレゼンスのトポロジとコンポーネント」を](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d90e-117">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<div>

## <a name="server-role-topology-changes"></a><span data-ttu-id="2d90e-118">サーバーの役割のトポロジの変更</span><span class="sxs-lookup"><span data-stu-id="2d90e-118">Server Role Topology Changes</span></span>

<span data-ttu-id="2d90e-119">別のサーバー上で以前に実行した一部のサーバーの役割は、フロントエンドサーバーの役割に統合され、ハードウェアのコストを節約できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2d90e-119">Some server roles that previously ran on separate servers are now consolidated into the Front End Server role, enabling you to save on hardware costs</span></span>

  - <span data-ttu-id="2d90e-120">Lync Server 2013 では、A/V 会議サーバーは、常にフロントエンドサーバーと連携しています。</span><span class="sxs-lookup"><span data-stu-id="2d90e-120">In Lync Server 2013, A/V Conferencing Server is always collocated with Front End Server.</span></span>

  - <span data-ttu-id="2d90e-121">監視とアーカイブの両方のフロントエンドが、常にフロントエンドサーバーと併置されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2d90e-121">The front ends for both Monitoring and Archiving are now always collocated with Front End Server.</span></span> <span data-ttu-id="2d90e-122">監視とアーカイブを行うには、フロントエンドプールのバックエンドデータベースと同じサーバーに併置できる別個のバックエンドデータベースが必要です。または、個別のバックエンドサーバーでホストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2d90e-122">Monitoring and Archiving each still require a separate Back-End Database, which can be collocated on the same server as the Front End Pool’s back-end database, or can be hosted on separate Back-End Servers.</span></span>

  - <span data-ttu-id="2d90e-123">常設チャットサーバーがサーバーの役割になりました。</span><span class="sxs-lookup"><span data-stu-id="2d90e-123">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="2d90e-124">Microsoft Lync Server 2010 では、グループチャットサーバーは Microsoft Lync Server 2010 用のサードパーティの信頼済みアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="2d90e-124">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="2d90e-125">Lync Server 2013 では、次の3つの新しいサーバーの役割を使用して、常設チャットサーバー機能が実装されています。</span><span class="sxs-lookup"><span data-stu-id="2d90e-125">In Lync Server 2013, Persistent Chat Server functionality is implemented using three new server roles:</span></span>
    
      - <span data-ttu-id="2d90e-126">**PersistentChatService:** フロントエンドロールとして実装されたメインの常設チャットサーバーサービス</span><span class="sxs-lookup"><span data-stu-id="2d90e-126">**PersistentChatService:** Main Persistent Chat Server services implemented as a front end role</span></span>
    
      - <span data-ttu-id="2d90e-127">**PersistentChatStore:** バックエンドサーバーの役割</span><span class="sxs-lookup"><span data-stu-id="2d90e-127">**PersistentChatStore:** Back End Server role</span></span>
    
      - <span data-ttu-id="2d90e-128">**PersistentChatComplianceStore:** 常設チャットのコンプライアンスのためのバックエンドサーバーの役割</span><span class="sxs-lookup"><span data-stu-id="2d90e-128">**PersistentChatComplianceStore:** Back End Server role for Persistent Chat Compliance</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

