---
title: 移行フェーズ
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ビジネス サーバー 2019 の Skype、Skype にはサーバー 2019 のビジネス コンポーネントが含まれているネットワーク上のサイトを定義します。 サイトは、単一のローカル エリア ネットワーク (LAN) または高速の光ファイバ ・ ネットワークで接続された 2 つのネットワークなど、高速、低レイテンシのネットワークで適切に接続されているコンピューターのセットです。
ms.openlocfilehash: cb6529ac09c10f73a01d3454ef9518d7fe960e1f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027733"
---
# <a name="migration-phases"></a><span data-ttu-id="00a6d-104">移行フェーズ</span><span class="sxs-lookup"><span data-stu-id="00a6d-104">Migration phases</span></span>

<span data-ttu-id="00a6d-105">ビジネス サーバー 2019 の Skype、Skype にはサーバー 2019 のビジネス コンポーネントが含まれているネットワーク上のサイトを定義します。</span><span class="sxs-lookup"><span data-stu-id="00a6d-105">In Skype for Business Server 2019, you define sites on your network that contain Skype for Business Server 2019 components.</span></span> <span data-ttu-id="00a6d-106">サイトは、単一のローカル エリア ネットワーク (LAN) または高速の光ファイバ ・ ネットワークで接続された 2 つのネットワークなど、高速、低レイテンシのネットワークで適切に接続されているコンピューターのセットです。</span><span class="sxs-lookup"><span data-stu-id="00a6d-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> 
  
<span data-ttu-id="00a6d-107">フロント エンド プールは、ユーザーの一般的なグループのサービスを提供すると同じように構成されているフロント エンド サーバーと作業時間を一緒のセットです。</span><span class="sxs-lookup"><span data-stu-id="00a6d-107">A Front End pool is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="00a6d-108">プールは、ユーザーにスケーラビリティとフェールオーバー機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="00a6d-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="00a6d-109">プール内の各サーバーは同じサーバーの役割を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00a6d-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="00a6d-110">Standard Edition サーバー、小規模な組織用に設計されたは、プールを定義し、1 台のサーバー上で実行します。</span><span class="sxs-lookup"><span data-stu-id="00a6d-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="00a6d-111">これを使用すると、Skype をより低いコストでは、ビジネス サーバー 2019 機能のあるが、真の高可用性ソリューションは提供されません。</span><span class="sxs-lookup"><span data-stu-id="00a6d-111">This enables you to have Skype for Business Server 2019 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span> 
  
<span data-ttu-id="00a6d-112">次のフェーズでは、ビジネス サーバー 2019 の Skype にプールの移行プロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="00a6d-112">The following phases describe the process of a pool migration to Skype for Business Server 2019.</span></span> <span data-ttu-id="00a6d-113">複数のプールを含む複数のサイトでは、各プールは、この段階的なアプローチに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="00a6d-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>
  
1. [<span data-ttu-id="00a6d-114">フェーズ 1: 移行を計画します。</span><span class="sxs-lookup"><span data-stu-id="00a6d-114">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
2. [<span data-ttu-id="00a6d-115">フェーズ 2: 移行を準備します。</span><span class="sxs-lookup"><span data-stu-id="00a6d-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
3. [<span data-ttu-id="00a6d-116">フェーズ 3: ビジネス サーバー 2019 パイロット プールに Skype を導入します。</span><span class="sxs-lookup"><span data-stu-id="00a6d-116">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
4. [<span data-ttu-id="00a6d-117">フェーズ 4: パイロット プールにテスト ユーザーの移動</span><span class="sxs-lookup"><span data-stu-id="00a6d-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [<span data-ttu-id="00a6d-118">フェーズ 5: ビジネス 2019 エッジ サーバーのプールをパイロットに Skype を追加します。</span><span class="sxs-lookup"><span data-stu-id="00a6d-118">Phase 5: Add Skype for Business Server 2019 Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [<span data-ttu-id="00a6d-119">フェーズ 6: を運用環境にパイロット展開から移動します。</span><span class="sxs-lookup"><span data-stu-id="00a6d-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [<span data-ttu-id="00a6d-120">フェーズ 7: 移行後のタスクを完了します。</span><span class="sxs-lookup"><span data-stu-id="00a6d-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
8. [<span data-ttu-id="00a6d-121">フェーズ 8: 従来のプールを使用停止します。</span><span class="sxs-lookup"><span data-stu-id="00a6d-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

