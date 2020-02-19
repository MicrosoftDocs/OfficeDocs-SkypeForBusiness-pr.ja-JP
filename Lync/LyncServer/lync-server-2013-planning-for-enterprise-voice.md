---
title: 'Lync Server 2013: エンタープライズ Voip の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Enterprise Voice
ms:assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413081(v=OCS.15)
ms:contentKeyID: 48185959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bac9e4020ae29ec7ff6ec85a42ae0ee5d30d3af
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="edd6f-102">Lync Server 2013 でのエンタープライズ Voip の計画</span><span class="sxs-lookup"><span data-stu-id="edd6f-102">Planning for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edd6f-103">_**トピックの最終更新日:** 2013-11-01_</span><span class="sxs-lookup"><span data-stu-id="edd6f-103">_**Topic Last Modified:** 2013-11-01_</span></span>

<span data-ttu-id="edd6f-104">エンタープライズ Voip の展開プロセスは、既存のトポロジ、インフラストラクチャ、およびサポートするエンタープライズ Voip 機能によって異なります。</span><span class="sxs-lookup"><span data-stu-id="edd6f-104">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="edd6f-105">必要な手順は選択する機能によって異なりますが、計画に関して高レベルで考慮が必要なその他の事項があります。</span><span class="sxs-lookup"><span data-stu-id="edd6f-105">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>

<span data-ttu-id="edd6f-106">通常は、展開するサイトの種類と数および地理的な場所、各サイトの通話ボリューム、サイト間を接続するネットワーク リンクの種類、各サイトの音声機能に冗長性とフェールオーバーを持たせるかどうか、および既存の PBX 機器を使用するかどうかを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="edd6f-106">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="edd6f-107">Lync Server communications software を全体として計画する際に考慮する必要がある、高可用性などの特定の考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="edd6f-107">There are certain considerations, such as high availability, that you should consider when you plan for Lync Server  communications software as a whole.</span></span> <span data-ttu-id="edd6f-108">これらの考慮事項については、このセクションのトピックで必要に応じて説明します。</span><span class="sxs-lookup"><span data-stu-id="edd6f-108">These considerations are discussed in topics throughout this section, as needed.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="edd6f-109">計画に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="edd6f-109">Planning Considerations</span></span>

<span data-ttu-id="edd6f-110">特定のエンタープライズ Voip 機能または展開シナリオまたはコンポーネントの展開に関連する計画の決定については、このセクションのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="edd6f-110">For planning decisions that pertain to the deployment of a particular Enterprise Voice capability or deployment scenario or component, consult the topics in this section.</span></span>

  - [<span data-ttu-id="edd6f-111">Lync Server 2013 でのエンタープライズ Voip の要件の定義</span><span class="sxs-lookup"><span data-stu-id="edd6f-111">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-enterprise-voice.md)

  - [<span data-ttu-id="edd6f-112">Lync Server 2013 の音声の使用状況とトラフィックの予測</span><span class="sxs-lookup"><span data-stu-id="edd6f-112">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="edd6f-113">Lync Server 2013 の高度なエンタープライズ Voip 機能のネットワーク設定</span><span class="sxs-lookup"><span data-stu-id="edd6f-113">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)

  - [<span data-ttu-id="edd6f-114">Lync Server 2013 のエンタープライズ Voip に必要なコンポーネント</span><span class="sxs-lookup"><span data-stu-id="edd6f-114">Components required for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-components-required-for-enterprise-voice.md)

  - [<span data-ttu-id="edd6f-115">Lync Server 2013 でのエンタープライズ Voip の復元の計画</span><span class="sxs-lookup"><span data-stu-id="edd6f-115">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="edd6f-116">Lync Server 2013 での Exchange ユニファイドメッセージング統合の計画</span><span class="sxs-lookup"><span data-stu-id="edd6f-116">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)

  - [<span data-ttu-id="edd6f-117">Lync Server 2013 での通話受付管理の計画</span><span class="sxs-lookup"><span data-stu-id="edd6f-117">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="edd6f-118">Lync Server 2013 での緊急サービス (E9-1-1) の計画</span><span class="sxs-lookup"><span data-stu-id="edd6f-118">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="edd6f-119">Lync Server 2013 でのメディアバイパスの計画</span><span class="sxs-lookup"><span data-stu-id="edd6f-119">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

  - [<span data-ttu-id="edd6f-120">Lync Server 2013 を使用したプライベート電話回線の計画</span><span class="sxs-lookup"><span data-stu-id="edd6f-120">Planning for private telephone lines with Lync Server 2013</span></span>](lync-server-2013-planning-for-private-telephone-lines.md)

  - [<span data-ttu-id="edd6f-121">Lync Server 2013 での場所に基づくルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="edd6f-121">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)

  - [<span data-ttu-id="edd6f-122">Lync Server 2013 でのエンタープライズ Voip の復元の計画</span><span class="sxs-lookup"><span data-stu-id="edd6f-122">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="edd6f-123">Lync Server 2013 でのエンタープライズ Voip の展開ガイドライン</span><span class="sxs-lookup"><span data-stu-id="edd6f-123">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-enterprise-voice.md)

  - [<span data-ttu-id="edd6f-124">Lync Server 2013 でのエンタープライズ Voip の展開プロセスの概要</span><span class="sxs-lookup"><span data-stu-id="edd6f-124">Deployment process overview for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-process-overview-for-enterprise-voice.md)

  - [<span data-ttu-id="edd6f-125">Lync Server 2013 でのエンタープライズ Voip へのユーザーの移動</span><span class="sxs-lookup"><span data-stu-id="edd6f-125">Moving users to Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-moving-users-to-enterprise-voice.md)

  - [<span data-ttu-id="edd6f-126">Lync PreCall Diagnostics Tool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="edd6f-126">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>](lync-server-2013-lync-precall-diagnostics-tool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

