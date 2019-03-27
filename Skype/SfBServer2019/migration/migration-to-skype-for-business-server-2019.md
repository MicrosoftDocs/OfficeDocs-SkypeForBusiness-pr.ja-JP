---
title: ビジネス サーバー 2019 の Skype への移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: このセクションのトピックでは、ビジネス サーバー 2019 の Skype に移行するプロセスを説明します。
ms.openlocfilehash: 32babd6fedd5defc756f73bbf001716c7c0b8a72
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881598"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="ff5d6-103">ビジネス サーバー 2019 の Skype への移行</span><span class="sxs-lookup"><span data-stu-id="ff5d6-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="ff5d6-104">このセクションのトピックでは、ビジネス サーバー 2019 の Skype に移行するプロセスを説明します。</span><span class="sxs-lookup"><span data-stu-id="ff5d6-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="ff5d6-105">取り上げて移行の Lync Server 2013 または Skype の Skype をビジネスのサーバー 2015 ビジネス サーバー 2019 のです。</span><span class="sxs-lookup"><span data-stu-id="ff5d6-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ff5d6-106">コンテンツ全体にわたって使用して、用語*レガシ*または参照する従来の Lync Server 2013 Skype ビジネス サーバー 2019 の Skype に移行するビジネス サーバー 2015 の。</span><span class="sxs-lookup"><span data-stu-id="ff5d6-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ff5d6-107">このガイドでは、移行の各フェーズを実行するのには一般的に必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="ff5d6-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="ff5d6-108">すべての可能な従来の配置トポロジ、またはすべての可能な移行シナリオは対処できません。</span><span class="sxs-lookup"><span data-stu-id="ff5d6-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="ff5d6-109">したがって、記載されている、すべての手順を実行する必要はありませんまたは、配置によって、追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff5d6-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="ff5d6-110">このガイドでは、検証手順の例も示します。</span><span class="sxs-lookup"><span data-stu-id="ff5d6-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="ff5d6-111">検証手順は、検索する各フェーズが完了すると、移行の進行状況として正常にことを確認する必要がありますを理解するために提供されます。</span><span class="sxs-lookup"><span data-stu-id="ff5d6-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="ff5d6-112">検証手順に従って、特定の移行プロセスを調整します。</span><span class="sxs-lookup"><span data-stu-id="ff5d6-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="ff5d6-113">このガイドでは、アップグレード、既存の配置に固有の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ff5d6-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="ff5d6-114">既存のトポロジを変更する方法については説明しません。</span><span class="sxs-lookup"><span data-stu-id="ff5d6-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="ff5d6-115">このガイドでは、新機能の実装は含まれません。</span><span class="sxs-lookup"><span data-stu-id="ff5d6-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="ff5d6-116">詳細な手順は、文書化された他の場所と、このガイドは記事または記事のセクションに指示します。</span><span class="sxs-lookup"><span data-stu-id="ff5d6-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="ff5d6-117">この資料では、次の一覧で指定されている用語を定義します。</span><span class="sxs-lookup"><span data-stu-id="ff5d6-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="ff5d6-118">**移行:** 移動、運用環境の導入から Lync Server 2013 または Skype ビジネス サーバー 2015 の Skype ビジネス サーバー 2019 の。</span><span class="sxs-lookup"><span data-stu-id="ff5d6-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="ff5d6-119">**共存:** ビジネス サーバー 2019 およびその他の機能に、Skype をいくつかの機能が移動された場合は、移行中に存在する一時的な環境は、以前のバージョンに残っています。</span><span class="sxs-lookup"><span data-stu-id="ff5d6-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="ff5d6-120">**相互運用性:** 共存の期間中に正常に機能する、展開の機能です。</span><span class="sxs-lookup"><span data-stu-id="ff5d6-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="ff5d6-121">**レガシー:** システムを移行するから、Lync Server 2013 またはビジネス サーバー 2015 の Skype のいずれかであります。</span><span class="sxs-lookup"><span data-stu-id="ff5d6-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="ff5d6-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ff5d6-122">In this section</span></span>

- [<span data-ttu-id="ff5d6-123">移行を始める前に</span><span class="sxs-lookup"><span data-stu-id="ff5d6-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="ff5d6-124">フェーズ 1: 移行の計画</span><span class="sxs-lookup"><span data-stu-id="ff5d6-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="ff5d6-125">フェーズ 2: 移行の準備</span><span class="sxs-lookup"><span data-stu-id="ff5d6-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="ff5d6-126">フェーズ 3: パイロット プールの展開</span><span class="sxs-lookup"><span data-stu-id="ff5d6-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- [<span data-ttu-id="ff5d6-127">フェーズ 4: パイロット プールにテスト ユーザーの移動</span><span class="sxs-lookup"><span data-stu-id="ff5d6-127">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [<span data-ttu-id="ff5d6-128">フェーズ 5: パイロット プールへのエッジ サーバーの追加</span><span class="sxs-lookup"><span data-stu-id="ff5d6-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="ff5d6-129">フェーズ 6: パイロット展開から運用展開への移行</span><span class="sxs-lookup"><span data-stu-id="ff5d6-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="ff5d6-130">フェーズ 7: 移行後のタスクの実行</span><span class="sxs-lookup"><span data-stu-id="ff5d6-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="ff5d6-131">フェーズ 8: レガシ プールの使用停止</span><span class="sxs-lookup"><span data-stu-id="ff5d6-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

