---
title: Skype for Business Server 2019 への移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: このセクションのトピックでは、Skype for Business Server 2019 への移行プロセスについて説明します。
ms.openlocfilehash: bd1513e5ca2a33449f982394e4abc15b9616393b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298149"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="c4e9c-103">Skype for Business Server 2019 への移行</span><span class="sxs-lookup"><span data-stu-id="c4e9c-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="c4e9c-104">このセクションのトピックでは、Skype for Business Server 2019 への移行プロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c4e9c-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="c4e9c-105">この記事では、Lync Server 2013 または Skype for business Server 2015 から Skype for Business Server 2019 への移行について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4e9c-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4e9c-106">このコンテンツ全体を通して、*従来*の Lync server 2013 または Skype For business server 2015 を使って、Skype For business server 2019 に移行していることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c4e9c-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c4e9c-107">このガイドでは、移行の各フェーズを実行するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4e9c-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="c4e9c-108">これは、すべてのレガシ展開トポロジまたは可能な移行シナリオには対応していません。</span><span class="sxs-lookup"><span data-stu-id="c4e9c-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="c4e9c-109">このため、説明されている手順をすべて実行する必要がない場合や、展開によっては追加の手順を実行する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="c4e9c-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="c4e9c-110">このガイドでは、確認手順の例についても説明します。</span><span class="sxs-lookup"><span data-stu-id="c4e9c-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="c4e9c-111">この確認手順は、移行の進行に合わせて各フェーズが正常に完了するために必要な情報を確認するために用意されています。</span><span class="sxs-lookup"><span data-stu-id="c4e9c-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="c4e9c-112">この確認手順は、特定の移行プロセスに合わせて調整してください。</span><span class="sxs-lookup"><span data-stu-id="c4e9c-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="c4e9c-113">このガイドには、既存の展開のアップグレードに固有の情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="c4e9c-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="c4e9c-114">既存のトポロジを変更する方法については説明しません。</span><span class="sxs-lookup"><span data-stu-id="c4e9c-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="c4e9c-115">このガイドでは、新機能の実装については説明しません。</span><span class="sxs-lookup"><span data-stu-id="c4e9c-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="c4e9c-116">詳細な手順については、このガイドの「記事または記事」で説明します。</span><span class="sxs-lookup"><span data-stu-id="c4e9c-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="c4e9c-117">この記事では、次の一覧で指定された用語について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4e9c-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="c4e9c-118">**移行:** Lync Server 2013 または Skype for business Server 2015 から運用展開を Skype for Business Server 2019 に移行します。</span><span class="sxs-lookup"><span data-stu-id="c4e9c-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="c4e9c-119">**共存:** 一部の機能が Skype for Business Server 2019 に移行されていて、その他の機能が以前のバージョンでも残っている場合、移行中に存在する一時的な環境。</span><span class="sxs-lookup"><span data-stu-id="c4e9c-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="c4e9c-120">**相互運用性:** 共存期間中に展開が正常に動作する能力。</span><span class="sxs-lookup"><span data-stu-id="c4e9c-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="c4e9c-121">**従来:** 移行元のシステムは、Lync Server 2013 または Skype for Business Server 2015 のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="c4e9c-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="c4e9c-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c4e9c-122">In this section</span></span>

- [<span data-ttu-id="c4e9c-123">移行を始める前に</span><span class="sxs-lookup"><span data-stu-id="c4e9c-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="c4e9c-124">フェーズ 1: 移行の計画</span><span class="sxs-lookup"><span data-stu-id="c4e9c-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="c4e9c-125">フェーズ 2: 移行の準備</span><span class="sxs-lookup"><span data-stu-id="c4e9c-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="c4e9c-126">フェーズ 3: パイロット プールの展開</span><span class="sxs-lookup"><span data-stu-id="c4e9c-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- [<span data-ttu-id="c4e9c-127">フェーズ 4: テストユーザーをパイロットプールに移動する</span><span class="sxs-lookup"><span data-stu-id="c4e9c-127">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [<span data-ttu-id="c4e9c-128">フェーズ 5: パイロット プールへのエッジ サーバーの追加</span><span class="sxs-lookup"><span data-stu-id="c4e9c-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="c4e9c-129">フェーズ 6: パイロット展開から運用展開への移行</span><span class="sxs-lookup"><span data-stu-id="c4e9c-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="c4e9c-130">フェーズ 7: 移行後のタスクの実行</span><span class="sxs-lookup"><span data-stu-id="c4e9c-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="c4e9c-131">フェーズ 8: レガシ プールの使用停止</span><span class="sxs-lookup"><span data-stu-id="c4e9c-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

