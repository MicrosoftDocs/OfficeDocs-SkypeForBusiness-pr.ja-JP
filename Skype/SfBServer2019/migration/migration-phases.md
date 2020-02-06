---
title: 移行のフェーズ
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server 2019 では、Skype for business Server 2019 コンポーネントが含まれているネットワーク上のサイトを定義します。 サイトは、単一のローカルエリアネットワーク (LAN)、または高速の光ファイバーネットワークによって接続された2つのネットワークなど、高速で待機時間の短いネットワークによって適切に接続されたコンピューターのセットです。
ms.openlocfilehash: b7d7fbddfe77c1303f0f6bde95827d94d7483f32
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813425"
---
# <a name="migration-phases"></a><span data-ttu-id="6035c-104">移行のフェーズ</span><span class="sxs-lookup"><span data-stu-id="6035c-104">Migration phases</span></span>

<span data-ttu-id="6035c-105">Skype for Business Server 2019 では、Skype for business Server 2019 コンポーネントが含まれているネットワーク上のサイトを定義します。</span><span class="sxs-lookup"><span data-stu-id="6035c-105">In Skype for Business Server 2019, you define sites on your network that contain Skype for Business Server 2019 components.</span></span> <span data-ttu-id="6035c-106">サイトは、単一のローカルエリアネットワーク (LAN)、または高速の光ファイバーネットワークによって接続された2つのネットワークなど、高速で待機時間の短いネットワークによって適切に接続されたコンピューターのセットです。</span><span class="sxs-lookup"><span data-stu-id="6035c-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> 
  
<span data-ttu-id="6035c-107">フロントエンドプールは、共通のユーザーグループに対してサービスを提供するために、同じように構成され、連携して動作するフロントエンドサーバーのセットです。</span><span class="sxs-lookup"><span data-stu-id="6035c-107">A Front End pool is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="6035c-108">プールにより、ユーザーにスケーラビリティとフェールオーバー機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="6035c-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="6035c-109">プール内の各サーバーは同じサーバーの役割を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6035c-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="6035c-110">小規模の組織向けに設計された Standard Edition サーバーでは、プールを定義し、単一のサーバーで実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="6035c-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="6035c-111">これにより、Skype for Business Server の2019機能を低コストで利用できるようになりますが、実際の高可用性ソリューションは提供されません。</span><span class="sxs-lookup"><span data-stu-id="6035c-111">This enables you to have Skype for Business Server 2019 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span> 
  
<span data-ttu-id="6035c-112">以下のフェーズでは、Skype for Business Server 2019 へのプール移行のプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6035c-112">The following phases describe the process of a pool migration to Skype for Business Server 2019.</span></span> <span data-ttu-id="6035c-113">複数のプールを含む複数のサイトの場合、個々のプールはこの段階的なアプローチに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6035c-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>
  
1. [<span data-ttu-id="6035c-114">フェーズ 1: 移行の計画</span><span class="sxs-lookup"><span data-stu-id="6035c-114">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
2. [<span data-ttu-id="6035c-115">フェーズ 2: 移行の準備</span><span class="sxs-lookup"><span data-stu-id="6035c-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
3. [<span data-ttu-id="6035c-116">フェーズ 3: Skype for Business Server 2019 パイロットプールの展開</span><span class="sxs-lookup"><span data-stu-id="6035c-116">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
4. [<span data-ttu-id="6035c-117">フェーズ 4: テストユーザーをパイロットプールに移動する</span><span class="sxs-lookup"><span data-stu-id="6035c-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [<span data-ttu-id="6035c-118">フェーズ 5: Skype for Business Server 2019 エッジサーバーをパイロットプールに追加する</span><span class="sxs-lookup"><span data-stu-id="6035c-118">Phase 5: Add Skype for Business Server 2019 Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [<span data-ttu-id="6035c-119">フェーズ 6: パイロット展開から運用展開への移行</span><span class="sxs-lookup"><span data-stu-id="6035c-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [<span data-ttu-id="6035c-120">フェーズ 7: 移行後のタスクの実行</span><span class="sxs-lookup"><span data-stu-id="6035c-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
8. [<span data-ttu-id="6035c-121">フェーズ 8: レガシ プールの使用停止</span><span class="sxs-lookup"><span data-stu-id="6035c-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

