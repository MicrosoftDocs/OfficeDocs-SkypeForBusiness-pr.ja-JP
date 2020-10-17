---
title: Office Communications Server 2007 R2 から Lync Server 2013 への移行
description: Office Communications Server 2007 R2 から Lync Server 2013 への移行。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Office Communications Server 2007 R2 to Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48185802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0afdc754ae691bc674c200addb9fb97c1eb4199
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569593"
---
# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a><span data-ttu-id="e803c-103">Office Communications Server 2007 R2 から Lync Server 2013 への移行</span><span class="sxs-lookup"><span data-stu-id="e803c-103">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e803c-104">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="e803c-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="e803c-105">このセクションのトピックでは、Office Communications Server 2007 R2 から Lync Server 2013 に移行するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e803c-105">The topics in this section guide you through the process of migrating from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e803c-p101">このドキュメントでは、移行の各フェーズを実現するために一般的に必要となる手順について説明します。この手順は、考え得るすべての従来の展開トポロジやすべての移行シナリオに対応するものではありません。したがって、展開によっては、記載されているすべての手順を実行する必要がない場合や、追加の手順が必要になる場合があります。また、このドキュメントでは検証手順の例も示します。検証手順を見ることによって、移行の作業を進める過程で各フェーズが正常に完了したことを確認するために何を調べる必要があるかを理解できるようになります。各自の移行プロセスに合わせてこれらの検証手順を変更してください。</span><span class="sxs-lookup"><span data-stu-id="e803c-p101">This document describes the steps generally required to accomplish each phase of migration. It does not address every possible legacy deployment topology or every possible migration scenario. Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment. This document also provides examples of verification steps. These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration. Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="e803c-p102">このガイドでは、既存の展開をアップグレードする方法についてのみ説明します。既存のトポロジを変更する方法については説明しません。また、このガイドでは新しい機能の実装については説明しません。詳細な手順が他のドキュメントに記載されている場合は、参照先のドキュメントまたはドキュメントのセクションを示します。</span><span class="sxs-lookup"><span data-stu-id="e803c-p102">This guide provides information specific to upgrading your existing deployment. It does not explain how to change your existing topology. This guide does not cover the implementation of new features. When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="e803c-116">このドキュメントで使用される用語の定義は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e803c-116">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="e803c-117">*転送*</span><span class="sxs-lookup"><span data-stu-id="e803c-117">*migration*</span></span>  
    <span data-ttu-id="e803c-118">以前のバージョンの Office Communications Server 2007 R2 から Lync Server 2013 に運用環境の展開を移行する。</span><span class="sxs-lookup"><span data-stu-id="e803c-118">Moving your production deployment from a previous version of Office Communications Server 2007 R2 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="e803c-119">*アップグレード*</span><span class="sxs-lookup"><span data-stu-id="e803c-119">*upgrade*</span></span>  
    <span data-ttu-id="e803c-120">サーバーまたはクライアント コンピューターに、以前より新しいバージョンのソフトウェアをインストールすること。</span><span class="sxs-lookup"><span data-stu-id="e803c-120">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="e803c-121">*共存*</span><span class="sxs-lookup"><span data-stu-id="e803c-121">*coexistence*</span></span>  
    <span data-ttu-id="e803c-122">移行中に存在する一時的な環境は、一部の機能が Lync Server 2013 に移行されていて、その他の機能が以前のバージョンの Office Communications Server 2007 R2 上に残っている場合です。</span><span class="sxs-lookup"><span data-stu-id="e803c-122">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Office Communications Server 2007 R2.</span></span>

<!-- end list -->

  - <span data-ttu-id="e803c-123">*作用*</span><span class="sxs-lookup"><span data-stu-id="e803c-123">*interoperability*</span></span>  
    <span data-ttu-id="e803c-124">共存の期間中に展開を正常に運用する能力。</span><span class="sxs-lookup"><span data-stu-id="e803c-124">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e803c-125">このセクション中</span><span class="sxs-lookup"><span data-stu-id="e803c-125">In This Section</span></span>

  - [<span data-ttu-id="e803c-126">移行を始める前に</span><span class="sxs-lookup"><span data-stu-id="e803c-126">Before you begin the migration</span></span>](before-you-begin-the-migration.md)

  - [<span data-ttu-id="e803c-127">移行のフェーズ</span><span class="sxs-lookup"><span data-stu-id="e803c-127">Migration phases</span></span>](migration-phases.md)

  - [<span data-ttu-id="e803c-128">フェーズ 1: Office Communications Server 2007 R2 からの移行を計画する</span><span class="sxs-lookup"><span data-stu-id="e803c-128">Phase 1: Plan your migration from Office Communications Server 2007 R2</span></span>](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [<span data-ttu-id="e803c-129">フェーズ 2: 移行の準備</span><span class="sxs-lookup"><span data-stu-id="e803c-129">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

  - [<span data-ttu-id="e803c-130">フェーズ 3: Lync Server 2013 パイロットプールを展開する</span><span class="sxs-lookup"><span data-stu-id="e803c-130">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="e803c-131">フェーズ 4: トポロジを結合する</span><span class="sxs-lookup"><span data-stu-id="e803c-131">Phase 4: Merge topologies</span></span>](phase-4-merge-topologies.md)

  - [<span data-ttu-id="e803c-132">フェーズ 5: パイロットプールを構成する</span><span class="sxs-lookup"><span data-stu-id="e803c-132">Phase 5: Configure the pilot pool</span></span>](phase-5-configure-the-pilot-pool.md)

  - [<span data-ttu-id="e803c-133">フェーズ 6: ユーザーをパイロットプールに移動する</span><span class="sxs-lookup"><span data-stu-id="e803c-133">Phase 6: Move users to the pilot pool</span></span>](phase-6-move-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="e803c-134">フェーズ 7: Lync Server 2013 エッジサーバーをパイロットプールに追加する</span><span class="sxs-lookup"><span data-stu-id="e803c-134">Phase 7: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="e803c-135">フェーズ 8: パイロット展開から運用への移行</span><span class="sxs-lookup"><span data-stu-id="e803c-135">Phase 8: Move from pilot deployment into production</span></span>](phase-8-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="e803c-136">フェーズ 9: 移行後のタスクを完了する</span><span class="sxs-lookup"><span data-stu-id="e803c-136">Phase 9: Complete post-migration tasks</span></span>](phase-9-complete-post-migration-tasks.md)

  - [<span data-ttu-id="e803c-137">フェーズ 10: 従来のサイトを使用停止にする</span><span class="sxs-lookup"><span data-stu-id="e803c-137">Phase 10: Decommission legacy site</span></span>](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

