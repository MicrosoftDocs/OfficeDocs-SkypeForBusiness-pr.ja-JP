---
title: Skype for Business Server 2019 への移行
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
description: このセクションのトピックでは、Skype for Business Server 2019 に移行するプロセスについて手順を追って説明します。
ms.openlocfilehash: 860fce550de33ed726bbbe723c8c7677ff09fc1c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752619"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="1c822-103">Skype for Business Server 2019 への移行</span><span class="sxs-lookup"><span data-stu-id="1c822-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="1c822-104">このセクションのトピックでは、Skype for Business Server 2019 に移行するプロセスについて手順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="1c822-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="1c822-105">この記事では、Lync Server 2013 または Skype for business server 2015 を Skype for Business Server 2019 に移行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1c822-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c822-106">コンテンツ全体を通して、*従来*の Lync server 2013 または skype For business server 2015 を参照して、skype For business server の2019に移行しているという用語を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c822-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1c822-107">このガイドでは、移行の各フェーズを実行するために一般的に必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="1c822-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="1c822-108">この手順は、考え得るすべての従来の展開トポロジやすべての移行シナリオに対応するものではありません。</span><span class="sxs-lookup"><span data-stu-id="1c822-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="1c822-109">したがって、展開によっては、記載されているすべての手順を実行する必要がない場合や、追加の手順が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1c822-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="1c822-110">このガイドでは、検証手順の例も示します。</span><span class="sxs-lookup"><span data-stu-id="1c822-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="1c822-111">検証手順を見ることによって、移行の作業を進める過程で各フェーズが正常に完了したことを確認するために何を調べる必要があるかを理解できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1c822-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="1c822-112">各自の移行プロセスに合わせてこれらの検証手順を変更してください。</span><span class="sxs-lookup"><span data-stu-id="1c822-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="1c822-113">このガイドでは、既存の展開をアップグレードする方法についてのみ説明します。</span><span class="sxs-lookup"><span data-stu-id="1c822-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="1c822-114">既存のトポロジを変更する方法については説明しません。</span><span class="sxs-lookup"><span data-stu-id="1c822-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="1c822-115">また、このガイドでは新しい機能の実装については説明しません。</span><span class="sxs-lookup"><span data-stu-id="1c822-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="1c822-116">詳細な手順が他の場所で文書化されている場合、このガイドでは記事または記事のセクションについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="1c822-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="1c822-117">この記事では、以下のリストで指定されている用語を定義します。</span><span class="sxs-lookup"><span data-stu-id="1c822-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="1c822-118">**移行:** 運用展開を Lync Server 2013 または Skype for business server 2015 から Skype for Business Server 2019 に移行する。</span><span class="sxs-lookup"><span data-stu-id="1c822-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="1c822-119">**共存:** 一部の機能が Skype for Business Server 2019 に移行されていて、その他の機能が以前のバージョンのまま残っている場合、移行中に存在する一時的な環境。</span><span class="sxs-lookup"><span data-stu-id="1c822-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="1c822-120">**相互運用性:** 共存の期間中に展開を正常に動作させることができます。</span><span class="sxs-lookup"><span data-stu-id="1c822-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="1c822-121">**従来:** 移行元のシステム。 Lync Server 2013 または Skype for Business Server 2015 のどちらかです。</span><span class="sxs-lookup"><span data-stu-id="1c822-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="1c822-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1c822-122">In this section</span></span>

- [<span data-ttu-id="1c822-123">移行を始める前に</span><span class="sxs-lookup"><span data-stu-id="1c822-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="1c822-124">フェーズ 1: 移行の計画</span><span class="sxs-lookup"><span data-stu-id="1c822-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="1c822-125">フェーズ 2: 移行の準備</span><span class="sxs-lookup"><span data-stu-id="1c822-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="1c822-126">フェーズ 3: パイロット プールの展開</span><span class="sxs-lookup"><span data-stu-id="1c822-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- [<span data-ttu-id="1c822-127">フェーズ 4: テストユーザーをパイロットプールに移動する</span><span class="sxs-lookup"><span data-stu-id="1c822-127">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [<span data-ttu-id="1c822-128">フェーズ 5: パイロット プールへのエッジ サーバーの追加</span><span class="sxs-lookup"><span data-stu-id="1c822-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="1c822-129">フェーズ 6: パイロット展開から運用展開への移行</span><span class="sxs-lookup"><span data-stu-id="1c822-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="1c822-130">フェーズ 7: 移行後のタスクの実行</span><span class="sxs-lookup"><span data-stu-id="1c822-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="1c822-131">フェーズ 8: レガシ プールの使用停止</span><span class="sxs-lookup"><span data-stu-id="1c822-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

