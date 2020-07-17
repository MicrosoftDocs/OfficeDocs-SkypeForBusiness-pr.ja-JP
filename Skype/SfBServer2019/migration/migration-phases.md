---
title: 移行フェーズ
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for business Server 2019 では、Skype for Business Server 2019 コンポーネントを含むネットワーク上のサイトを定義します。 サイトとは、1 つのローカル エリア ネットワーク (LAN) または高速の光ファイバー ネットワークで接続された 2 つのネットワークのように、高速で遅延の少ないネットワークによる良好な接続が保たれているコンピューターの集合です。
ms.openlocfilehash: d05fc0c4eb7d12a6d96b638fe7f59acc830fbcd1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752629"
---
# <a name="migration-phases"></a><span data-ttu-id="8cdd4-104">移行フェーズ</span><span class="sxs-lookup"><span data-stu-id="8cdd4-104">Migration phases</span></span>

<span data-ttu-id="8cdd4-105">Skype for business Server 2019 では、Skype for Business Server 2019 コンポーネントを含むネットワーク上のサイトを定義します。</span><span class="sxs-lookup"><span data-stu-id="8cdd4-105">In Skype for Business Server 2019, you define sites on your network that contain Skype for Business Server 2019 components.</span></span> <span data-ttu-id="8cdd4-106">サイトとは、1 つのローカル エリア ネットワーク (LAN) または高速の光ファイバー ネットワークで接続された 2 つのネットワークのように、高速で遅延の少ないネットワークによる良好な接続が保たれているコンピューターの集合です。</span><span class="sxs-lookup"><span data-stu-id="8cdd4-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> 
  
<span data-ttu-id="8cdd4-107">フロントエンドプールは、同一のユーザーグループに対してサービスを提供するために、同一に構成されたフロントエンドサーバーのセットです。</span><span class="sxs-lookup"><span data-stu-id="8cdd4-107">A Front End pool is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="8cdd4-108">プールはユーザーにスケーラビリティとフェールオーバー機能をもたらします。</span><span class="sxs-lookup"><span data-stu-id="8cdd4-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="8cdd4-109">プール内の各サーバーでは、同一のサーバーの役割を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cdd4-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="8cdd4-110">小規模な組織向けに設計された Standard Edition サーバーも、プールを定義し、単一のサーバー上で実行します。</span><span class="sxs-lookup"><span data-stu-id="8cdd4-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="8cdd4-111">これにより、Skype for Business Server 2019 の機能を低コストで利用できるようになりますが、実際の高可用性ソリューションは提供されません。</span><span class="sxs-lookup"><span data-stu-id="8cdd4-111">This enables you to have Skype for Business Server 2019 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span> 
  
<span data-ttu-id="8cdd4-112">次のフェーズでは、Skype for Business Server 2019 へのプールの移行プロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8cdd4-112">The following phases describe the process of a pool migration to Skype for Business Server 2019.</span></span> <span data-ttu-id="8cdd4-113">複数のプールで構成される複数のサイトの場合は、それぞれのプールに対して以下のフェーズの手順を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cdd4-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>
  
1. [<span data-ttu-id="8cdd4-114">フェーズ 1: 移行の計画</span><span class="sxs-lookup"><span data-stu-id="8cdd4-114">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
2. [<span data-ttu-id="8cdd4-115">フェーズ 2: 移行の準備</span><span class="sxs-lookup"><span data-stu-id="8cdd4-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
3. [<span data-ttu-id="8cdd4-116">フェーズ 3: Skype for Business Server 2019 パイロットプールを展開する</span><span class="sxs-lookup"><span data-stu-id="8cdd4-116">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
4. [<span data-ttu-id="8cdd4-117">フェーズ 4: テストユーザーをパイロットプールに移動する</span><span class="sxs-lookup"><span data-stu-id="8cdd4-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [<span data-ttu-id="8cdd4-118">フェーズ 5: Skype for Business Server 2019 エッジサーバーをパイロットプールに追加する</span><span class="sxs-lookup"><span data-stu-id="8cdd4-118">Phase 5: Add Skype for Business Server 2019 Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [<span data-ttu-id="8cdd4-119">フェーズ 6: パイロット展開から運用展開への移行</span><span class="sxs-lookup"><span data-stu-id="8cdd4-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [<span data-ttu-id="8cdd4-120">フェーズ 7: 移行後のタスクの実行</span><span class="sxs-lookup"><span data-stu-id="8cdd4-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
8. [<span data-ttu-id="8cdd4-121">フェーズ 8: レガシ プールの使用停止</span><span class="sxs-lookup"><span data-stu-id="8cdd4-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

