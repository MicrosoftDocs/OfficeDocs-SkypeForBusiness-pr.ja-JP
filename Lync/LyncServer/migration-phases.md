---
title: 移行フェーズ
description: 移行のフェーズ
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72ef47cb9b6c9eba75c395eb9bd94c887ca5a433
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547053"
---
# <a name="migration-phases"></a><span data-ttu-id="778eb-103">移行フェーズ</span><span class="sxs-lookup"><span data-stu-id="778eb-103">Migration phases</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="778eb-104">_**トピックの最終更新日:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="778eb-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="778eb-105">Lync Server 2013 では、Lync Server 2013 コンポーネントを含むネットワーク上のサイトを定義します。</span><span class="sxs-lookup"><span data-stu-id="778eb-105">In Lync Server 2013, you define sites on your network that contain Lync Server 2013 components.</span></span> <span data-ttu-id="778eb-106">サイトとは、1 つのローカル エリア ネットワーク (LAN) または高速の光ファイバー ネットワークで接続された 2 つのネットワークのように、高速で遅延の少ないネットワークによる良好な接続が保たれているコンピューターの集合です。</span><span class="sxs-lookup"><span data-stu-id="778eb-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span>

<span data-ttu-id="778eb-107">*フロントエンドプール*は、同一のユーザーグループに対してサービスを提供するために、同一に構成されたフロントエンドサーバーのセットです。</span><span class="sxs-lookup"><span data-stu-id="778eb-107">A *Front End pool* is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="778eb-108">プールはユーザーにスケーラビリティとフェールオーバー機能をもたらします。</span><span class="sxs-lookup"><span data-stu-id="778eb-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="778eb-109">プール内の各サーバーでは、同一のサーバーの役割を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="778eb-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="778eb-110">小規模な組織向けに設計された Standard Edition サーバーも、プールを定義し、単一のサーバー上で実行します。</span><span class="sxs-lookup"><span data-stu-id="778eb-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="778eb-111">これにより、Lync Server 2013 の機能を低コストで利用できるようになりますが、実際の高可用性ソリューションは提供されません。</span><span class="sxs-lookup"><span data-stu-id="778eb-111">This enables you to have Lync Server 2013 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="778eb-112">次のフェーズでは、Lync Server 2010 から Lync Server 2013 へのプールの移行プロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="778eb-112">The following phases describe the process of a pool migration from Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="778eb-113">複数のプールで構成される複数のサイトの場合は、それぞれのプールに対して以下のフェーズの手順を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="778eb-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>

1.  [<span data-ttu-id="778eb-114">フェーズ 1: Lync Server 2010 からの移行を計画する</span><span class="sxs-lookup"><span data-stu-id="778eb-114">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [<span data-ttu-id="778eb-115">フェーズ 2: 移行の準備</span><span class="sxs-lookup"><span data-stu-id="778eb-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

3.  [<span data-ttu-id="778eb-116">フェーズ 3: Lync Server 2013 パイロットプールを展開する</span><span class="sxs-lookup"><span data-stu-id="778eb-116">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [<span data-ttu-id="778eb-117">フェーズ 4: テストユーザーをパイロットプールに移動する</span><span class="sxs-lookup"><span data-stu-id="778eb-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [<span data-ttu-id="778eb-118">フェーズ 5: Lync Server 2013 エッジサーバーをパイロットプールに追加する</span><span class="sxs-lookup"><span data-stu-id="778eb-118">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [<span data-ttu-id="778eb-119">フェーズ 6: パイロット展開から運用展開への移行</span><span class="sxs-lookup"><span data-stu-id="778eb-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

7.  [<span data-ttu-id="778eb-120">フェーズ 7: 移行後のタスクの実行</span><span class="sxs-lookup"><span data-stu-id="778eb-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

8.  [<span data-ttu-id="778eb-121">フェーズ 8: レガシ プールの使用停止</span><span class="sxs-lookup"><span data-stu-id="778eb-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

