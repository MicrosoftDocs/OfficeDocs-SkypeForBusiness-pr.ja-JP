---
title: Lync Server 2010 から Lync Server 2013 への移行
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cab7ac790d08a848cb90a609720c237c4c20062
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a><span data-ttu-id="c48e7-102">Lync Server 2010 から Lync Server 2013 への移行</span><span class="sxs-lookup"><span data-stu-id="c48e7-102">Migration from Lync Server 2010 to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c48e7-103">_**トピックの最終更新日:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="c48e7-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="c48e7-104">このセクションのトピックでは、Lync Server 2010 から Lync Server 2013 に移行するプロセスについて順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="c48e7-104">The topics in this section guide you through the process of migrating from Lync Server 2010 to Lync Server 2013.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c48e7-p101">このドキュメントでは、移行の各フェーズを実現するために一般的に必要となる手順について説明します。この手順は、考え得るすべての従来の展開トポロジやすべての移行シナリオに対応するものではありません。したがって、展開によっては、記載されているすべての手順を実行する必要がない場合や、追加の手順が必要になる場合があります。また、このドキュメントでは検証手順の例も示します。検証手順を見ることによって、移行の作業を進める過程で各フェーズが正常に完了したことを確認するために何を調べる必要があるかを理解できるようになります。各自の移行プロセスに合わせてこれらの検証手順を変更してください。</span><span class="sxs-lookup"><span data-stu-id="c48e7-p101">This document describes the steps generally required to accomplish each phase of migration. It does not address every possible legacy deployment topology or every possible migration scenario. Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment. This document also provides examples of verification steps. These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration. Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="c48e7-p102">このガイドでは、既存の展開をアップグレードする方法についてのみ説明します。既存のトポロジを変更する方法については説明しません。また、このガイドでは新しい機能の実装については説明しません。詳細な手順が他のドキュメントに記載されている場合は、参照先のドキュメントまたはドキュメントのセクションを示します。</span><span class="sxs-lookup"><span data-stu-id="c48e7-p102">This guide provides information specific to upgrading your existing deployment. It does not explain how to change your existing topology. This guide does not cover the implementation of new features. When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="c48e7-115">このドキュメントで使用される用語の定義は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c48e7-115">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="c48e7-116">*転送*</span><span class="sxs-lookup"><span data-stu-id="c48e7-116">*migration*</span></span>  
    <span data-ttu-id="c48e7-117">運用展開を、Lync Server 2010 の以前のバージョンから Lync Server 2013 に移行する。</span><span class="sxs-lookup"><span data-stu-id="c48e7-117">Moving your production deployment from a previous version of Lync Server 2010 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="c48e7-118">*アップグレード*</span><span class="sxs-lookup"><span data-stu-id="c48e7-118">*upgrade*</span></span>  
    <span data-ttu-id="c48e7-119">サーバーまたはクライアント コンピューターに、以前より新しいバージョンのソフトウェアをインストールすること。</span><span class="sxs-lookup"><span data-stu-id="c48e7-119">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="c48e7-120">*共存*</span><span class="sxs-lookup"><span data-stu-id="c48e7-120">*coexistence*</span></span>  
    <span data-ttu-id="c48e7-121">移行中に存在する一時的な環境。一部の機能が Lync Server 2013 に移行され、その他の機能が以前のバージョンの Lync Server 2010 上に残っている場合。</span><span class="sxs-lookup"><span data-stu-id="c48e7-121">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Lync Server 2010.</span></span>

<!-- end list -->

  - <span data-ttu-id="c48e7-122">*作用*</span><span class="sxs-lookup"><span data-stu-id="c48e7-122">*interoperability*</span></span>  
    <span data-ttu-id="c48e7-123">共存の期間中に展開を正常に運用する能力。</span><span class="sxs-lookup"><span data-stu-id="c48e7-123">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c48e7-124">このセクション中</span><span class="sxs-lookup"><span data-stu-id="c48e7-124">In This Section</span></span>

  - [<span data-ttu-id="c48e7-125">移行を開始する前に</span><span class="sxs-lookup"><span data-stu-id="c48e7-125">Before you begin the migration</span></span>](before-you-begin-the-migration.md)

  - [<span data-ttu-id="c48e7-126">フェーズ 1: Lync Server 2010 からの移行を計画する</span><span class="sxs-lookup"><span data-stu-id="c48e7-126">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [<span data-ttu-id="c48e7-127">フェーズ 2: 移行の準備をする</span><span class="sxs-lookup"><span data-stu-id="c48e7-127">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

  - [<span data-ttu-id="c48e7-128">フェーズ 3: Lync Server 2013 パイロットプールを展開する</span><span class="sxs-lookup"><span data-stu-id="c48e7-128">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="c48e7-129">フェーズ 4: テストユーザーをパイロットプールに移動する</span><span class="sxs-lookup"><span data-stu-id="c48e7-129">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="c48e7-130">フェーズ 5: Lync Server 2013 エッジサーバーをパイロットプールに追加する</span><span class="sxs-lookup"><span data-stu-id="c48e7-130">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="c48e7-131">フェーズ 6: パイロット展開から運用への移行</span><span class="sxs-lookup"><span data-stu-id="c48e7-131">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="c48e7-132">フェーズ 7: 移行後のタスクを完了する</span><span class="sxs-lookup"><span data-stu-id="c48e7-132">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

  - [<span data-ttu-id="c48e7-133">フェーズ 8: 従来のプールを使用停止にする</span><span class="sxs-lookup"><span data-stu-id="c48e7-133">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

