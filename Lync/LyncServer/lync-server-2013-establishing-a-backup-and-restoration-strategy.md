---
title: 'Lync Server 2013: バックアップと復元の計画を立てる'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d378c66ae820ef0be7b7b3b0492b023863e977ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a><span data-ttu-id="46217-102">Lync Server 2013 のバックアップと復元の戦略を確立する</span><span class="sxs-lookup"><span data-stu-id="46217-102">Establishing a backup and restoration strategy for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46217-103">_**最終更新日:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="46217-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="46217-104">Lync Server のバックアップと復元の計画を作成するには、組織の目標に合った戦略を開発する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46217-104">Before you can develop a backup and restoration plan for Lync Server, you need to develop a strategy that fits with your organization's goals.</span></span> <span data-ttu-id="46217-105">効果的なバックアップと復元計画を作成するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="46217-105">To develop an effective backup and restoration strategy, you will need to:</span></span>

  - <span data-ttu-id="46217-106">業務上の優先度を設定します。</span><span class="sxs-lookup"><span data-stu-id="46217-106">Establish business priorities.</span></span>

  - <span data-ttu-id="46217-107">バックアップと復元の要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="46217-107">Identify backup and restoration requirements.</span></span>

<div>

## <a name="establishing-business-priorities"></a><span data-ttu-id="46217-108">業務上の優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="46217-108">Establishing Business Priorities</span></span>

<span data-ttu-id="46217-109">組織のビジネス優先順位を評価する。</span><span class="sxs-lookup"><span data-stu-id="46217-109">Evaluate the business priorities of your organization.</span></span> <span data-ttu-id="46217-110">通常、バックアップと復元の戦略に影響を与える主な業務上の優先順位は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="46217-110">Typically, the primary business priorities that affect your backup and restoration strategy are the following:</span></span>

  - <span data-ttu-id="46217-111">ビジネス継続性の要件</span><span class="sxs-lookup"><span data-stu-id="46217-111">Business continuity requirements</span></span>

  - <span data-ttu-id="46217-112">データの完全性</span><span class="sxs-lookup"><span data-stu-id="46217-112">Data completeness</span></span>

  - <span data-ttu-id="46217-113">データの重要度</span><span class="sxs-lookup"><span data-stu-id="46217-113">Data criticality</span></span>

  - <span data-ttu-id="46217-114">移植性の要件</span><span class="sxs-lookup"><span data-stu-id="46217-114">Portability requirements</span></span>

  - <span data-ttu-id="46217-115">コストの制約</span><span class="sxs-lookup"><span data-stu-id="46217-115">Cost constraints</span></span>

<span data-ttu-id="46217-116">顧客によって開発されたサービスレベルアグリーメント (Sla) を決定するために、このようなヘルプなどのビジネスニーズについて説明します。</span><span class="sxs-lookup"><span data-stu-id="46217-116">Business needs such as these help to determine the service level agreements (SLAs) that you develop with your customers.</span></span> <span data-ttu-id="46217-117">サービスレベル契約は、バックアップと復元戦略に大きく影響します。</span><span class="sxs-lookup"><span data-stu-id="46217-117">Service level agreements greatly influence your backup and recovery strategy.</span></span>

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a><span data-ttu-id="46217-118">バックアップと復元の要件を特定する</span><span class="sxs-lookup"><span data-stu-id="46217-118">Identifying Backup and Restoration Requirements</span></span>

<span data-ttu-id="46217-119">ビジネス優先度とサービスレベル契約によって、Lync Server のバックアップと復元に関する組織の要件を決定することができます。</span><span class="sxs-lookup"><span data-stu-id="46217-119">Your business priorities and service level agreements act in determining your organizations' requirements for backing up and restoring Lync Server.</span></span> <span data-ttu-id="46217-120">次の要件を特定して、文書化します。</span><span class="sxs-lookup"><span data-stu-id="46217-120">Identify and document your requirements for the following:</span></span>

  - <span data-ttu-id="46217-121">**バックアップの頻度バックアップの**   頻度に関するベストプラクティスの詳細については、「 [Lync Server 2013 のバックアップと復元のベストプラクティス](lync-server-2013-best-practices-for-backup-and-restoration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46217-121">**Frequency of backups**   For details about best practices for backup frequency, see [Best practices for backup and restoration for Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span></span>

  - <span data-ttu-id="46217-122">**バックアップと復元ツール**   には、ツールを使用するユーザーと、どのコンピューターを使用するかが含まれます。</span><span class="sxs-lookup"><span data-stu-id="46217-122">**Backup and restoration tools**   Include who is to use the tools, and on which computers.</span></span> <span data-ttu-id="46217-123">このトピックで説明しているツールと必要なアクセス許可について詳しくは、「 [Lync Server 2013 のバックアップと復元の要件](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)」をご覧ください。ツールと権限。</span><span class="sxs-lookup"><span data-stu-id="46217-123">For details about the tools discussed in this topic and necessary permissions, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span>

  - <span data-ttu-id="46217-124">**バックアップの場所**   ローカルまたはリモートでバックアップを保持するかどうかを指定し、セキュリティとアクセシビリティを考慮する。</span><span class="sxs-lookup"><span data-stu-id="46217-124">**Backup location**   Identify whether the backups are kept locally or remotely, taking security and accessibility into consideration.</span></span> <span data-ttu-id="46217-125">バックアップに使用するメディアを指定します。</span><span class="sxs-lookup"><span data-stu-id="46217-125">Specify the media to be used for the backups.</span></span>

  - <span data-ttu-id="46217-126">**ハードウェアとソフトウェアの要件**   特定のハードウェアおよびソフトウェア要件を特定して文書化します。これには、特定のコンポーネントのバックアップストレージと復元のためのハードウェア、またはに必要なソフトウェアとネットワーク接続が含まれます。バックアップと復元をサポートします。</span><span class="sxs-lookup"><span data-stu-id="46217-126">**Hardware and software requirements**   Identify and document your specific hardware and software requirements, including the hardware for backup storage and restoration of specific components and any software and network connectivity required to support backup and restoration.</span></span> <span data-ttu-id="46217-127">ハードウェアとソフトウェアの要件を開発する際には、次のようなさまざまな復元シナリオを念頭に置いてください。</span><span class="sxs-lookup"><span data-stu-id="46217-127">As you develop your hardware and software requirements, keep in mind the various restoration scenarios that follow.</span></span>

  - <span data-ttu-id="46217-128">**復元シナリオ**   ここでは、次のシナリオを対象とした復元プロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="46217-128">**Restoration scenarios**   Here are the restoration processes for the following scenarios:</span></span>
    
      - <span data-ttu-id="46217-129">Lync サーバープールは失敗します。</span><span class="sxs-lookup"><span data-stu-id="46217-129">A Lync Server pool fails.</span></span> <span data-ttu-id="46217-130">このシナリオでは、プール内の各サーバーを再構築する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46217-130">This scenario requires rebuilding each server in the pool.</span></span>
    
      - <span data-ttu-id="46217-131">Standard Edition サーバーで障害が発生します。</span><span class="sxs-lookup"><span data-stu-id="46217-131">A Standard Edition server fails.</span></span> <span data-ttu-id="46217-132">このシナリオでは、新規またはクリーンなコンピューターにサーバーを再構築し、データベースを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46217-132">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="46217-133">中央管理ストアが失われます。</span><span class="sxs-lookup"><span data-stu-id="46217-133">Loss of the Central Management store.</span></span> <span data-ttu-id="46217-134">少なくとも、このシナリオでは、一元管理ストアを復元して発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46217-134">At a minimum, this scenario requires restoring and publishing the Central Management store.</span></span>
    
      - <span data-ttu-id="46217-135">中央管理ストアが正常に機能している場合、バックエンドサーバーが失われます。</span><span class="sxs-lookup"><span data-stu-id="46217-135">Loss of a Back End Server when the Central Management store is still functioning normally.</span></span> <span data-ttu-id="46217-136">このシナリオでは、新規またはクリーンなコンピューターにサーバーを再構築し、データベースを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46217-136">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="46217-137">Lync Server プールのメンバーであるサーバーが失敗します。</span><span class="sxs-lookup"><span data-stu-id="46217-137">A server that is a member of a Lync Server pool fails.</span></span> <span data-ttu-id="46217-138">このシナリオでは、新しいコンピューターまたはクリーンコンピューターにサーバーを再構築する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46217-138">This scenario requires rebuilding the server on a new or clean computer.</span></span>
    
      - <span data-ttu-id="46217-139">ファイルストアが失敗します。</span><span class="sxs-lookup"><span data-stu-id="46217-139">A File Store fails.</span></span> <span data-ttu-id="46217-140">このシナリオでは、ファイルサーバーまたはファイルクラスターを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46217-140">This scenario requires restoring the file server or file cluster.</span></span>
    
      - <span data-ttu-id="46217-141">アーカイブ、監視、または永続的なチャットデータベースは失敗します。</span><span class="sxs-lookup"><span data-stu-id="46217-141">An Archiving, Monitoring, or Persistent Chat database fails.</span></span> <span data-ttu-id="46217-142">このシナリオでは、データベースを再作成する必要があります。データが組織にとって重要である場合は、データを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46217-142">This scenario requires recreating the databases, and, if the data is critical to your organization, restoring the data.</span></span> <span data-ttu-id="46217-143">Lync Server のバックアップと実行を取得するには、アーカイブ、監視、常設チャットデータは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="46217-143">Archiving, Monitoring, and Persistent Chat data is not required to get Lync Server back up and running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

