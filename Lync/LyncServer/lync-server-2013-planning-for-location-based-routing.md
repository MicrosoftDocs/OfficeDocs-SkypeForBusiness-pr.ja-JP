---
title: 'Lync Server 2013: 場所に基づくルーティングの計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Location-Based Routing
ms:assetid: bb035924-6b52-4f0f-8e05-b76864fb9ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994068(v=OCS.15)
ms:contentKeyID: 51803979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34a2dc25aa80e45d7e24f3a91a18b2dd83a4d554
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="6cd5d-102">Lync Server 2013 での場所に基づくルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="6cd5d-102">Planning for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6cd5d-103">_**最終更新日:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="6cd5d-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="6cd5d-104">このトピックの情報は Lync Server 2013 の累積的な更新プログラム: 2013 年 2 月に関係します。</span><span class="sxs-lookup"><span data-stu-id="6cd5d-104">The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>

<span data-ttu-id="6cd5d-105">位置情報に基づくルーティングを使用すると、通話中の当事者の位置に基づいて、VoIP エンドポイントと PSTN エンドポイント間での通話のルーティングを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="6cd5d-105">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="6cd5d-106">場所に基づくルーティングは、Lync Server 2013 エンタープライズ Voip インフラストラクチャの一部です。</span><span class="sxs-lookup"><span data-stu-id="6cd5d-106">Location-Based Routing is part of the Lync Server 2013 Enterprise Voice infrastructure.</span></span> <span data-ttu-id="6cd5d-107">位置情報に基づくルーティングは、Lync Server 2013 CU1 による通話のルーティング方法を制御する通話管理機能です。</span><span class="sxs-lookup"><span data-stu-id="6cd5d-107">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="6cd5d-108">通話が、Lync の発信者の地理的な場所に基づいて PBX または PSTN エンドポイントにルーティングされるかどうかについて、通話承認規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="6cd5d-108">It enforces call authorization rules on whether calls can be routed to PBX or PSTN endpoints based on the Lync caller’s geographic location.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6cd5d-109">このセクション中</span><span class="sxs-lookup"><span data-stu-id="6cd5d-109">In This Section</span></span>

  - [<span data-ttu-id="6cd5d-110">Lync Server 2013 での位置情報に基づくルーティングの概要</span><span class="sxs-lookup"><span data-stu-id="6cd5d-110">Overview of Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing.md)

  - [<span data-ttu-id="6cd5d-111">Lync Server 2013 の場所に基づくルーティングのガイダンス</span><span class="sxs-lookup"><span data-stu-id="6cd5d-111">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)

  - [<span data-ttu-id="6cd5d-112">Lync Server 2013 の場所に基づくルーティングのシナリオ</span><span class="sxs-lookup"><span data-stu-id="6cd5d-112">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)

  - [<span data-ttu-id="6cd5d-113">場所に基づくルーティングに関する Lync Server 2013 の技術的考慮事項</span><span class="sxs-lookup"><span data-stu-id="6cd5d-113">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-technical-considerations-for-location-based-routing.md)

  - [<span data-ttu-id="6cd5d-114">Lync Server 2013 での場所に基づくルーティングに対するクライアントとサーバーのサポート</span><span class="sxs-lookup"><span data-stu-id="6cd5d-114">Client and server support for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-client-and-server-support-for-location-based-routing.md)

  - [<span data-ttu-id="6cd5d-115">Lync Server 2013 の場所に基づくルーティングでサポートされていない機能</span><span class="sxs-lookup"><span data-stu-id="6cd5d-115">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-capabilities-not-supported-by-location-based-routing.md)

  - [<span data-ttu-id="6cd5d-116">Lync Server 2013 の場所に基づくルーティングの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="6cd5d-116">Deployment process for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-location-based-routing.md)

  - [<span data-ttu-id="6cd5d-117">Lync Server 2013 での会議の位置情報に基づくルーティング</span><span class="sxs-lookup"><span data-stu-id="6cd5d-117">Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-for-conferencing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6cd5d-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="6cd5d-118">See Also</span></span>


[<span data-ttu-id="6cd5d-119">Lync Server 2013 でのエンタープライズ Voip の計画</span><span class="sxs-lookup"><span data-stu-id="6cd5d-119">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

