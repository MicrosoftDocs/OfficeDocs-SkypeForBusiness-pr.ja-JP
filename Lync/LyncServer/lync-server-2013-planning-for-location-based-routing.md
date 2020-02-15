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
ms.openlocfilehash: 307b4d696fdf4348649eb9363d252c7f1d0f8d12
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="31d9b-102">Lync Server 2013 での場所に基づくルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="31d9b-102">Planning for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31d9b-103">_**トピックの最終更新日:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="31d9b-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="31d9b-104">このトピックの情報は、Lync Server 2013 の累積的な更新プログラム (2013 年2月) に関連します。</span><span class="sxs-lookup"><span data-stu-id="31d9b-104">The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>

<span data-ttu-id="31d9b-105">場所に基づくルーティングを使用すると、通話の当事者の場所に基づいて、VoIP エンドポイントと PSTN エンドポイント間での通話のルーティングを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="31d9b-105">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="31d9b-106">場所に基づくルーティングは、Lync Server 2013 エンタープライズ Voip インフラストラクチャの一部です。</span><span class="sxs-lookup"><span data-stu-id="31d9b-106">Location-Based Routing is part of the Lync Server 2013 Enterprise Voice infrastructure.</span></span> <span data-ttu-id="31d9b-107">場所に基づくルーティングは、通話が Lync Server 2013 CU1 によってルーティングされる方法を制御する通話管理機能です。</span><span class="sxs-lookup"><span data-stu-id="31d9b-107">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="31d9b-108">この方法では、Lync の発信者の地理的な場所に基づいて通話を PBX または PSTN エンドポイントにルーティングできるかどうかについて、通話承認規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="31d9b-108">It enforces call authorization rules on whether calls can be routed to PBX or PSTN endpoints based on the Lync caller’s geographic location.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="31d9b-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="31d9b-109">In This Section</span></span>

  - [<span data-ttu-id="31d9b-110">Lync Server 2013 での場所に基づくルーティングの概要</span><span class="sxs-lookup"><span data-stu-id="31d9b-110">Overview of Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing.md)

  - [<span data-ttu-id="31d9b-111">Lync Server 2013 での場所に基づくルーティングのガイダンス</span><span class="sxs-lookup"><span data-stu-id="31d9b-111">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)

  - [<span data-ttu-id="31d9b-112">Lync Server 2013 での場所に基づくルーティングのシナリオ</span><span class="sxs-lookup"><span data-stu-id="31d9b-112">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)

  - [<span data-ttu-id="31d9b-113">Lync Server 2013 での場所に基づくルーティングに関する技術的考慮事項</span><span class="sxs-lookup"><span data-stu-id="31d9b-113">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-technical-considerations-for-location-based-routing.md)

  - [<span data-ttu-id="31d9b-114">Lync Server 2013 での場所に基づくルーティングに対するクライアントとサーバーのサポート</span><span class="sxs-lookup"><span data-stu-id="31d9b-114">Client and server support for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-client-and-server-support-for-location-based-routing.md)

  - [<span data-ttu-id="31d9b-115">Lync Server 2013 での場所に基づくルーティングでサポートされていない機能</span><span class="sxs-lookup"><span data-stu-id="31d9b-115">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-capabilities-not-supported-by-location-based-routing.md)

  - [<span data-ttu-id="31d9b-116">Lync Server 2013 での場所に基づくルーティングの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="31d9b-116">Deployment process for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-location-based-routing.md)

  - [<span data-ttu-id="31d9b-117">Lync Server 2013 での会議の場所に基づくルーティング</span><span class="sxs-lookup"><span data-stu-id="31d9b-117">Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-for-conferencing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="31d9b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="31d9b-118">See Also</span></span>


[<span data-ttu-id="31d9b-119">Lync Server 2013 でのエンタープライズ Voip の計画</span><span class="sxs-lookup"><span data-stu-id="31d9b-119">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

