---
title: 'Lync Server 2013: バックアップと復元の戦略の確立'
description: 'Lync Server 2013: バックアップと復元の戦略を確立します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4fdefed873d1fd69d82f8ecebceeb92f06f65f7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555043"
---
# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a><span data-ttu-id="aa37d-103">Lync Server 2013 のバックアップと復元の戦略の確立</span><span class="sxs-lookup"><span data-stu-id="aa37d-103">Establishing a backup and restoration strategy for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa37d-104">_**トピックの最終更新日:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="aa37d-104">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="aa37d-105">Lync Server のバックアップと復元の計画を作成する前に、組織の目標に合った戦略を開発する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa37d-105">Before you can develop a backup and restoration plan for Lync Server, you need to develop a strategy that fits with your organization's goals.</span></span> <span data-ttu-id="aa37d-106">効果的なバックアップと復元の戦略を策定するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa37d-106">To develop an effective backup and restoration strategy, you will need to:</span></span>

  - <span data-ttu-id="aa37d-107">ビジネスの優先順位を確立します。</span><span class="sxs-lookup"><span data-stu-id="aa37d-107">Establish business priorities.</span></span>

  - <span data-ttu-id="aa37d-108">バックアップと復元の要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="aa37d-108">Identify backup and restoration requirements.</span></span>

<div>

## <a name="establishing-business-priorities"></a><span data-ttu-id="aa37d-109">ビジネスの優先順位の確立</span><span class="sxs-lookup"><span data-stu-id="aa37d-109">Establishing Business Priorities</span></span>

<span data-ttu-id="aa37d-p102">組織のビジネスの優先順位を評価します。一般に、ビジネスの主な優先順位のうちで、バックアップと復元の戦略に関係するものには以下があります。</span><span class="sxs-lookup"><span data-stu-id="aa37d-p102">Evaluate the business priorities of your organization. Typically, the primary business priorities that affect your backup and restoration strategy are the following:</span></span>

  - <span data-ttu-id="aa37d-112">業務継続の要件</span><span class="sxs-lookup"><span data-stu-id="aa37d-112">Business continuity requirements</span></span>

  - <span data-ttu-id="aa37d-113">データの完全性</span><span class="sxs-lookup"><span data-stu-id="aa37d-113">Data completeness</span></span>

  - <span data-ttu-id="aa37d-114">データの重要性</span><span class="sxs-lookup"><span data-stu-id="aa37d-114">Data criticality</span></span>

  - <span data-ttu-id="aa37d-115">ポータビリティの要件</span><span class="sxs-lookup"><span data-stu-id="aa37d-115">Portability requirements</span></span>

  - <span data-ttu-id="aa37d-116">コストの制約</span><span class="sxs-lookup"><span data-stu-id="aa37d-116">Cost constraints</span></span>

<span data-ttu-id="aa37d-117">お客様と一緒に開発するサービスレベル契約 (Sla) を決定するための、これらのヘルプなどのビジネスニーズ。</span><span class="sxs-lookup"><span data-stu-id="aa37d-117">Business needs such as these help to determine the service level agreements (SLAs) that you develop with your customers.</span></span> <span data-ttu-id="aa37d-118">サービス レベル アグリーメントはバックアップと復旧の戦略に大きな影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="aa37d-118">Service level agreements greatly influence your backup and recovery strategy.</span></span>

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a><span data-ttu-id="aa37d-119">バックアップと復元の要件の特定</span><span class="sxs-lookup"><span data-stu-id="aa37d-119">Identifying Backup and Restoration Requirements</span></span>

<span data-ttu-id="aa37d-120">ビジネスの優先度とサービスレベル契約によって、Lync Server のバックアップと復元に関する組織の要件を決定することができます。</span><span class="sxs-lookup"><span data-stu-id="aa37d-120">Your business priorities and service level agreements act in determining your organizations' requirements for backing up and restoring Lync Server.</span></span> <span data-ttu-id="aa37d-121">以下についての要件を特定し、文書化します。</span><span class="sxs-lookup"><span data-stu-id="aa37d-121">Identify and document your requirements for the following:</span></span>

  - <span data-ttu-id="aa37d-122">**バックアップ**     の頻度バックアップの頻度に関するベストプラクティスの詳細については、「 [Lync Server 2013 のバックアップと復元のベストプラクティス](lync-server-2013-best-practices-for-backup-and-restoration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa37d-122">**Frequency of backups**   For details about best practices for backup frequency, see [Best practices for backup and restoration for Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span></span>

  - <span data-ttu-id="aa37d-123">**バックアップと復元のツール**    ツールを使用するユーザーと、どのコンピューターを使用するかを含めます。</span><span class="sxs-lookup"><span data-stu-id="aa37d-123">**Backup and restoration tools**   Include who is to use the tools, and on which computers.</span></span> <span data-ttu-id="aa37d-124">このトピックで説明されているツールおよび必要なアクセス許可の詳細については、「 [Lync Server 2013 のバックアップと復元の要件](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)」を参照してください。ツールとアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="aa37d-124">For details about the tools discussed in this topic and necessary permissions, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span>

  - <span data-ttu-id="aa37d-125">**バックアップの場所**    バックアップがローカルまたはリモートのどちらで保持されているかを特定し、セキュリティとアクセシビリティを考慮に入れます。</span><span class="sxs-lookup"><span data-stu-id="aa37d-125">**Backup location**   Identify whether the backups are kept locally or remotely, taking security and accessibility into consideration.</span></span> <span data-ttu-id="aa37d-126">バックアップに使用するメディアを指定します。</span><span class="sxs-lookup"><span data-stu-id="aa37d-126">Specify the media to be used for the backups.</span></span>

  - <span data-ttu-id="aa37d-127">**ハードウェアとソフトウェアの要件**    バックアップの保存や、バックアップと復元をサポートするために必要なソフトウェアとネットワーク接続のハードウェアなど、特定のハードウェアおよびソフトウェア要件を特定し、文書化します。</span><span class="sxs-lookup"><span data-stu-id="aa37d-127">**Hardware and software requirements**   Identify and document your specific hardware and software requirements, including the hardware for backup storage and restoration of specific components and any software and network connectivity required to support backup and restoration.</span></span> <span data-ttu-id="aa37d-128">ハードウェアとソフトウェアの要件を開発する際には、次に示すさまざまな復元シナリオを念頭に置いてください。</span><span class="sxs-lookup"><span data-stu-id="aa37d-128">As you develop your hardware and software requirements, keep in mind the various restoration scenarios that follow.</span></span>

  - <span data-ttu-id="aa37d-129">**復元シナリオ**    ここでは、以下のシナリオの復元プロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="aa37d-129">**Restoration scenarios**   Here are the restoration processes for the following scenarios:</span></span>
    
      - <span data-ttu-id="aa37d-130">Lync Server プールで障害が発生します。</span><span class="sxs-lookup"><span data-stu-id="aa37d-130">A Lync Server pool fails.</span></span> <span data-ttu-id="aa37d-131">このシナリオでは、プール内の各サーバーを構築し直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa37d-131">This scenario requires rebuilding each server in the pool.</span></span>
    
      - <span data-ttu-id="aa37d-132">Standard Edition サーバーでエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="aa37d-132">A Standard Edition server fails.</span></span> <span data-ttu-id="aa37d-133">このシナリオでは、新しいコンピューターまたはクリーンな状態のコンピューターにサーバーを構築し直してデータベースを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa37d-133">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="aa37d-134">中央管理ストアの損失。</span><span class="sxs-lookup"><span data-stu-id="aa37d-134">Loss of the Central Management store.</span></span> <span data-ttu-id="aa37d-135">このシナリオでは、少なくとも、中央管理ストアを復元して発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa37d-135">At a minimum, this scenario requires restoring and publishing the Central Management store.</span></span>
    
      - <span data-ttu-id="aa37d-136">中央管理ストアが正常に機能している場合、バックエンドサーバーは失われます。</span><span class="sxs-lookup"><span data-stu-id="aa37d-136">Loss of a Back End Server when the Central Management store is still functioning normally.</span></span> <span data-ttu-id="aa37d-137">このシナリオでは、新しいコンピューターまたはクリーンな状態のコンピューターにサーバーを構築し直してデータベースを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa37d-137">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="aa37d-138">Lync Server プールのメンバーであるサーバーで障害が発生します。</span><span class="sxs-lookup"><span data-stu-id="aa37d-138">A server that is a member of a Lync Server pool fails.</span></span> <span data-ttu-id="aa37d-139">このシナリオでは、新しいコンピューターまたはクリーンな状態のコンピューターにサーバーを構築し直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa37d-139">This scenario requires rebuilding the server on a new or clean computer.</span></span>
    
      - <span data-ttu-id="aa37d-140">ファイルストアが失敗します。</span><span class="sxs-lookup"><span data-stu-id="aa37d-140">A File Store fails.</span></span> <span data-ttu-id="aa37d-141">このシナリオでは、ファイル サーバーまたはファイル クラスターを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa37d-141">This scenario requires restoring the file server or file cluster.</span></span>
    
      - <span data-ttu-id="aa37d-142">アーカイブ、監視、または常設チャットデータベースが失敗します。</span><span class="sxs-lookup"><span data-stu-id="aa37d-142">An Archiving, Monitoring, or Persistent Chat database fails.</span></span> <span data-ttu-id="aa37d-143">このシナリオでは、データベースを作成し直す必要があり、組織にとって重要なデータの場合にはデータの復元も必要です。</span><span class="sxs-lookup"><span data-stu-id="aa37d-143">This scenario requires recreating the databases, and, if the data is critical to your organization, restoring the data.</span></span> <span data-ttu-id="aa37d-144">Lync Server のバックアップと実行を取得するために、アーカイブ、監視、常設チャットデータは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="aa37d-144">Archiving, Monitoring, and Persistent Chat data is not required to get Lync Server back up and running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

