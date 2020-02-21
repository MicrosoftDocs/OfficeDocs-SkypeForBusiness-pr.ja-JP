---
title: 移行フェーズ
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d8101e5dee47699421ed83effed3c578c96bfda
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a><span data-ttu-id="3d150-102">移行フェーズ</span><span class="sxs-lookup"><span data-stu-id="3d150-102">Migration phases</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d150-103">_**トピックの最終更新日:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="3d150-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="3d150-104">Lync Server 2013 では、Lync Server 2013 コンポーネントを含むネットワーク上のサイトを定義します。</span><span class="sxs-lookup"><span data-stu-id="3d150-104">In Lync Server 2013, you define sites on your network that contain Lync Server 2013 components.</span></span> <span data-ttu-id="3d150-105">サイトとは、1 つのローカル エリア ネットワーク (LAN) または高速の光ファイバー ネットワークで接続された 2 つのネットワークのように、高速で遅延の少ないネットワークによる良好な接続が保たれているコンピューターの集合です。</span><span class="sxs-lookup"><span data-stu-id="3d150-105">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span>

<span data-ttu-id="3d150-106">*フロントエンドプール*は、同一のユーザーグループに対してサービスを提供するために、同一に構成されたフロントエンドサーバーのセットです。</span><span class="sxs-lookup"><span data-stu-id="3d150-106">A *Front End pool* is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="3d150-107">プールはユーザーにスケーラビリティとフェールオーバー機能をもたらします。</span><span class="sxs-lookup"><span data-stu-id="3d150-107">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="3d150-108">プール内の各サーバーでは、同一のサーバーの役割を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d150-108">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="3d150-109">小規模な組織向けに設計された Standard Edition サーバーも、プールを定義し、単一のサーバー上で実行します。</span><span class="sxs-lookup"><span data-stu-id="3d150-109">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="3d150-110">これにより、Lync Server 2013 の機能を低コストで利用できるようになりますが、実際の高可用性ソリューションは提供されません。</span><span class="sxs-lookup"><span data-stu-id="3d150-110">This enables you to have Lync Server 2013 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="3d150-111">次のフェーズでは、Lync Server 2010 から Lync Server 2013 へのプールの移行プロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3d150-111">The following phases describe the process of a pool migration from Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="3d150-112">複数のプールで構成される複数のサイトの場合は、それぞれのプールに対して以下のフェーズの手順を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d150-112">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>

1.  [<span data-ttu-id="3d150-113">フェーズ 1: Lync Server 2010 からの移行を計画する</span><span class="sxs-lookup"><span data-stu-id="3d150-113">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [<span data-ttu-id="3d150-114">フェーズ 2: 移行の準備をする</span><span class="sxs-lookup"><span data-stu-id="3d150-114">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

3.  [<span data-ttu-id="3d150-115">フェーズ 3: Lync Server 2013 パイロットプールを展開する</span><span class="sxs-lookup"><span data-stu-id="3d150-115">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [<span data-ttu-id="3d150-116">フェーズ 4: テストユーザーをパイロットプールに移動する</span><span class="sxs-lookup"><span data-stu-id="3d150-116">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [<span data-ttu-id="3d150-117">フェーズ 5: Lync Server 2013 エッジサーバーをパイロットプールに追加する</span><span class="sxs-lookup"><span data-stu-id="3d150-117">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [<span data-ttu-id="3d150-118">フェーズ 6: パイロット展開から運用への移行</span><span class="sxs-lookup"><span data-stu-id="3d150-118">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

7.  [<span data-ttu-id="3d150-119">フェーズ 7: 移行後のタスクを完了する</span><span class="sxs-lookup"><span data-stu-id="3d150-119">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

8.  [<span data-ttu-id="3d150-120">フェーズ 8: 従来のプールを使用停止にする</span><span class="sxs-lookup"><span data-stu-id="3d150-120">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

