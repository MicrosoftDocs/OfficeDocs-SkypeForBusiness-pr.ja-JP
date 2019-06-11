---
title: 移行のフェーズ
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa7226a442d8e41d4ab0e6e3511a35e020decb65
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a><span data-ttu-id="e46cc-102">移行のフェーズ</span><span class="sxs-lookup"><span data-stu-id="e46cc-102">Migration phases</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e46cc-103">_**最終更新日:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="e46cc-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="e46cc-104">Lync server 2013 では、Lync Server 2013 コンポーネントを含むネットワーク上のサイトを定義します。</span><span class="sxs-lookup"><span data-stu-id="e46cc-104">In Lync Server 2013, you define sites on your network that contain Lync Server 2013 components.</span></span> <span data-ttu-id="e46cc-105">サイトは、単一のローカルエリアネットワーク (LAN)、または高速の光ファイバーネットワークによって接続された2つのネットワークなど、高速で待機時間の短いネットワークによって適切に接続されたコンピューターのセットです。</span><span class="sxs-lookup"><span data-stu-id="e46cc-105">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span>

<span data-ttu-id="e46cc-106">*フロントエンドプール*は、共通のユーザーグループに対してサービスを提供するために、同じように構成され、連携して動作するフロントエンドサーバーのセットです。</span><span class="sxs-lookup"><span data-stu-id="e46cc-106">A *Front End pool* is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="e46cc-107">プールにより、ユーザーにスケーラビリティとフェールオーバー機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="e46cc-107">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="e46cc-108">プール内の各サーバーは同じサーバーの役割を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e46cc-108">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="e46cc-109">小規模の組織向けに設計された Standard Edition サーバーでは、プールを定義し、単一のサーバーで実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="e46cc-109">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="e46cc-110">これにより、Lync Server 2013 機能を低コストで利用できるようになりますが、実際の高可用性ソリューションは提供されません。</span><span class="sxs-lookup"><span data-stu-id="e46cc-110">This enables you to have Lync Server 2013 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="e46cc-111">次のフェーズでは、Lync Server 2010 から Lync Server 2013 へのプール移行のプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e46cc-111">The following phases describe the process of a pool migration from Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="e46cc-112">複数のプールを含む複数のサイトの場合、個々のプールはこの段階的なアプローチに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e46cc-112">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>

1.  [<span data-ttu-id="e46cc-113">フェーズ 1: Lync Server 2010 からの移行を計画する</span><span class="sxs-lookup"><span data-stu-id="e46cc-113">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [<span data-ttu-id="e46cc-114">フェーズ 2: 移行の準備</span><span class="sxs-lookup"><span data-stu-id="e46cc-114">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

3.  [<span data-ttu-id="e46cc-115">フェーズ 3: Lync Server 2013 パイロットプールの展開</span><span class="sxs-lookup"><span data-stu-id="e46cc-115">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [<span data-ttu-id="e46cc-116">フェーズ 4: テストユーザーをパイロットプールに移動する</span><span class="sxs-lookup"><span data-stu-id="e46cc-116">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [<span data-ttu-id="e46cc-117">フェーズ 5: Lync Server 2013 エッジサーバーをパイロットプールに追加する</span><span class="sxs-lookup"><span data-stu-id="e46cc-117">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [<span data-ttu-id="e46cc-118">フェーズ 6: パイロット展開から運用展開への移行</span><span class="sxs-lookup"><span data-stu-id="e46cc-118">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

7.  [<span data-ttu-id="e46cc-119">フェーズ 7: 移行後のタスクの実行</span><span class="sxs-lookup"><span data-stu-id="e46cc-119">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

8.  [<span data-ttu-id="e46cc-120">フェーズ 8: レガシ プールの使用停止</span><span class="sxs-lookup"><span data-stu-id="e46cc-120">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

