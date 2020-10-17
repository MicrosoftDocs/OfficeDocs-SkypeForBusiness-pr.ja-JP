---
title: 'Lync Server 2013: Location-Based ルーティングの計画'
description: 'Lync Server 2013: Location-Based ルーティングの計画。'
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
ms.openlocfilehash: 894a596e998fe07b97ad7911441eced670ba85b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553083"
---
# <a name="planning-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="2f083-103">Lync Server 2013 での Location-Based ルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="2f083-103">Planning for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f083-104">_**トピックの最終更新日:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="2f083-104">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="2f083-105">このトピックの情報は、Lync Server 2013 の累積的な更新プログラム (2013 年2月) に関連します。</span><span class="sxs-lookup"><span data-stu-id="2f083-105">The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>

<span data-ttu-id="2f083-106">Location-Based ルーティングを使用すると、通話の当事者の場所に基づいて VoIP エンドポイントと PSTN エンドポイント間の通話のルーティングを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="2f083-106">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="2f083-107">Location-Based ルーティングは、Lync Server 2013 エンタープライズ Voip インフラストラクチャの一部です。</span><span class="sxs-lookup"><span data-stu-id="2f083-107">Location-Based Routing is part of the Lync Server 2013 Enterprise Voice infrastructure.</span></span> <span data-ttu-id="2f083-108">Location-Based ルーティングは、Lync Server 2013 CU1 が通話をルーティングする方法を制御する通話管理機能です。</span><span class="sxs-lookup"><span data-stu-id="2f083-108">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="2f083-109">この方法では、Lync の発信者の地理的な場所に基づいて通話を PBX または PSTN エンドポイントにルーティングできるかどうかについて、通話承認規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="2f083-109">It enforces call authorization rules on whether calls can be routed to PBX or PSTN endpoints based on the Lync caller’s geographic location.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2f083-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2f083-110">In This Section</span></span>

  - [<span data-ttu-id="2f083-111">Lync Server 2013 での Location-Based ルーティングの概要</span><span class="sxs-lookup"><span data-stu-id="2f083-111">Overview of Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing.md)

  - [<span data-ttu-id="2f083-112">Lync Server 2013 での Location-Based ルーティングに関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="2f083-112">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)

  - [<span data-ttu-id="2f083-113">Lync Server 2013 での Location-Based ルーティングのシナリオ</span><span class="sxs-lookup"><span data-stu-id="2f083-113">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)

  - [<span data-ttu-id="2f083-114">Lync Server 2013 での Location-Based ルーティングに関する技術的考慮事項</span><span class="sxs-lookup"><span data-stu-id="2f083-114">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-technical-considerations-for-location-based-routing.md)

  - [<span data-ttu-id="2f083-115">Lync Server 2013 での Location-Based ルーティングのクライアントとサーバーのサポート</span><span class="sxs-lookup"><span data-stu-id="2f083-115">Client and server support for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-client-and-server-support-for-location-based-routing.md)

  - [<span data-ttu-id="2f083-116">Lync Server 2013 での Location-Based ルーティングでサポートされていない機能</span><span class="sxs-lookup"><span data-stu-id="2f083-116">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-capabilities-not-supported-by-location-based-routing.md)

  - [<span data-ttu-id="2f083-117">Lync Server 2013 での Location-Based ルーティングの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="2f083-117">Deployment process for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-location-based-routing.md)

  - [<span data-ttu-id="2f083-118">Lync Server 2013 での会議の場所に基づくルーティング</span><span class="sxs-lookup"><span data-stu-id="2f083-118">Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-for-conferencing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2f083-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f083-119">See Also</span></span>


[<span data-ttu-id="2f083-120">Lync Server 2013 でのエンタープライズ Voip の計画</span><span class="sxs-lookup"><span data-stu-id="2f083-120">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

