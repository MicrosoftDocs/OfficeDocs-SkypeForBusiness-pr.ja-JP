---
title: Lync Server 2010 から Lync Server 2013 への移行
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4be42da09e14f91d82310258c728de4ed7976be2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a><span data-ttu-id="62c6c-102">Lync Server 2010 から Lync Server 2013 への移行</span><span class="sxs-lookup"><span data-stu-id="62c6c-102">Migration from Lync Server 2010 to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62c6c-103">_**最終更新日:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="62c6c-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="62c6c-104">このセクションのトピックでは、Lync Server 2010 から Lync Server 2013 への移行プロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="62c6c-104">The topics in this section guide you through the process of migrating from Lync Server 2010 to Lync Server 2013.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="62c6c-105">このドキュメントでは、移行の各フェーズを実行するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="62c6c-105">This document describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="62c6c-106">これは、すべてのレガシ展開トポロジまたは可能な移行シナリオには対応していません。</span><span class="sxs-lookup"><span data-stu-id="62c6c-106">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="62c6c-107">このため、説明されている手順をすべて実行する必要がない場合や、展開によっては追加の手順を実行する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="62c6c-107">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="62c6c-108">このドキュメントでは、確認手順の例についても説明します。</span><span class="sxs-lookup"><span data-stu-id="62c6c-108">This document also provides examples of verification steps.</span></span> <span data-ttu-id="62c6c-109">この確認手順は、移行の進行に合わせて各フェーズが正常に完了するために必要な情報を確認するために用意されています。</span><span class="sxs-lookup"><span data-stu-id="62c6c-109">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="62c6c-110">この確認手順は、特定の移行プロセスに合わせて調整してください。</span><span class="sxs-lookup"><span data-stu-id="62c6c-110">Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="62c6c-111">このガイドには、既存の展開のアップグレードに固有の情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="62c6c-111">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="62c6c-112">既存のトポロジを変更する方法については説明しません。</span><span class="sxs-lookup"><span data-stu-id="62c6c-112">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="62c6c-113">このガイドでは、新機能の実装については説明しません。</span><span class="sxs-lookup"><span data-stu-id="62c6c-113">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="62c6c-114">詳細な手順については、別のドキュメントまたはドキュメントの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62c6c-114">When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="62c6c-115">このドキュメントでは、次の一覧で指定された用語を定義しています。</span><span class="sxs-lookup"><span data-stu-id="62c6c-115">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="62c6c-116">*用*</span><span class="sxs-lookup"><span data-stu-id="62c6c-116">*migration*</span></span>  
    <span data-ttu-id="62c6c-117">以前のバージョンの Lync Server 2010 から Lync Server 2013 に運用展開を移行します。</span><span class="sxs-lookup"><span data-stu-id="62c6c-117">Moving your production deployment from a previous version of Lync Server 2010 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="62c6c-118">*アップグレード*</span><span class="sxs-lookup"><span data-stu-id="62c6c-118">*upgrade*</span></span>  
    <span data-ttu-id="62c6c-119">新しいバージョンのソフトウェアをサーバーまたはクライアントコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="62c6c-119">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="62c6c-120">*共存*</span><span class="sxs-lookup"><span data-stu-id="62c6c-120">*coexistence*</span></span>  
    <span data-ttu-id="62c6c-121">一部の機能が Lync Server 2013 に移行されていて、その他の機能が以前のバージョンの Lync Server 2010 に残っている場合、移行中に存在する一時的な環境。</span><span class="sxs-lookup"><span data-stu-id="62c6c-121">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Lync Server 2010.</span></span>

<!-- end list -->

  - <span data-ttu-id="62c6c-122">*運用性*</span><span class="sxs-lookup"><span data-stu-id="62c6c-122">*interoperability*</span></span>  
    <span data-ttu-id="62c6c-123">共存期間中に展開が正常に動作する能力。</span><span class="sxs-lookup"><span data-stu-id="62c6c-123">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="62c6c-124">このセクション中</span><span class="sxs-lookup"><span data-stu-id="62c6c-124">In This Section</span></span>

  - [<span data-ttu-id="62c6c-125">移行を始める前に</span><span class="sxs-lookup"><span data-stu-id="62c6c-125">Before you begin the migration</span></span>](before-you-begin-the-migration.md)

  - [<span data-ttu-id="62c6c-126">フェーズ 1: Lync Server 2010 からの移行を計画する</span><span class="sxs-lookup"><span data-stu-id="62c6c-126">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [<span data-ttu-id="62c6c-127">フェーズ 2: 移行の準備</span><span class="sxs-lookup"><span data-stu-id="62c6c-127">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

  - [<span data-ttu-id="62c6c-128">フェーズ 3: Lync Server 2013 パイロットプールの展開</span><span class="sxs-lookup"><span data-stu-id="62c6c-128">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="62c6c-129">フェーズ 4: テストユーザーをパイロットプールに移動する</span><span class="sxs-lookup"><span data-stu-id="62c6c-129">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="62c6c-130">フェーズ 5: Lync Server 2013 エッジサーバーをパイロットプールに追加する</span><span class="sxs-lookup"><span data-stu-id="62c6c-130">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="62c6c-131">フェーズ 6: パイロット展開から運用展開への移行</span><span class="sxs-lookup"><span data-stu-id="62c6c-131">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="62c6c-132">フェーズ 7: 移行後のタスクの実行</span><span class="sxs-lookup"><span data-stu-id="62c6c-132">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

  - [<span data-ttu-id="62c6c-133">フェーズ 8: レガシ プールの使用停止</span><span class="sxs-lookup"><span data-stu-id="62c6c-133">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

