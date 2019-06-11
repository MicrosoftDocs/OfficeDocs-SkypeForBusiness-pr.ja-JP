---
title: 'Lync Server 2013: 通話受付管理の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1af07a3f0b067f4dae3835c682cb51e6fefdcf21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="5eab6-102">Lync Server 2013 での通話受付管理の計画</span><span class="sxs-lookup"><span data-stu-id="5eab6-102">Planning for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5eab6-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="5eab6-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="5eab6-104">テレフォニー、ビデオ、アプリケーション共有など、IP ベースの統合コミュニケーション (UC) アプリケーションでは、エンタープライズネットワークで利用可能な帯域幅は、通常、LAN 環境内の制限要素と見なされません。</span><span class="sxs-lookup"><span data-stu-id="5eab6-104">For unified communications (UC) applications that are IP-based, such as telephony, video, and application sharing, the available bandwidth of enterprise networks is not generally considered to be a limiting factor within LAN environments.</span></span> <span data-ttu-id="5eab6-105">ただし、サイトを相互に接続する WAN リンクでは、ネットワーク帯域幅を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="5eab6-105">However, on WAN links that interconnect sites, network bandwidth can be limited.</span></span> <span data-ttu-id="5eab6-106">ネットワークトラフィックの流入によって WAN リンクが受信されると、キュー、バッファリング、パケットドロップなどの現在のメカニズムが輻輳を解決するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5eab6-106">When an influx of network traffic oversubscribes a WAN link, current mechanisms such as queuing, buffering, and packet dropping are used to resolve the congestion.</span></span> <span data-ttu-id="5eab6-107">トラフィック量の増加は、ネットワークの輻輳が容易になるか、必要に応じてトラフィックが破棄されるまで遅延されます。</span><span class="sxs-lookup"><span data-stu-id="5eab6-107">The extra traffic is typically delayed until the network congestion eases or, if necessary, the traffic is dropped.</span></span> <span data-ttu-id="5eab6-108">このような状況での従来のデータトラフィックでは、受信側のクライアントで回復できます。</span><span class="sxs-lookup"><span data-stu-id="5eab6-108">For conventional data traffic in such situations, the receiving client can recover.</span></span> <span data-ttu-id="5eab6-109">ユニファイドコミュニケーションなどのリアルタイムトラフィックでは、この方法でネットワークの輻輳を解決することはできません。ユニファイドコミュニケーショントラフィックは待ち時間とパケット損失の両方に影響を及ぼすためです。</span><span class="sxs-lookup"><span data-stu-id="5eab6-109">For real-time traffic such as unified communications, network congestion cannot be resolved in this manner, because the unified communications traffic is sensitive to both latency and packet loss.</span></span> <span data-ttu-id="5eab6-110">WAN で渋滞すると、ユーザーにとって低品質 (QoE) が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5eab6-110">Congestion on the WAN can result in a poor Quality of Experience (QoE) for users.</span></span> <span data-ttu-id="5eab6-111">輻輳状態のリアルタイムトラフィックには、低品質の接続を提供するよりも、通話を拒否する方が適しています。</span><span class="sxs-lookup"><span data-stu-id="5eab6-111">For real-time traffic in congested conditions, it is better to deny calls than to provide connections with poor quality.</span></span>

<span data-ttu-id="5eab6-112">通話受付管理 (CAC) では、リアルタイム セッションを許容品質で確立するのに十分なネットワーク帯域幅があるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="5eab6-112">Call admission control (CAC) determines whether there is sufficient network bandwidth to establish a real-time session of acceptable quality.</span></span> <span data-ttu-id="5eab6-113">Lync Server 2013 では、CAC はオーディオとビデオについてのみリアルタイムのトラフィックを制御しますが、データトラフィックには影響しません。</span><span class="sxs-lookup"><span data-stu-id="5eab6-113">In Lync Server 2013, CAC controls real-time traffic only for audio and video, but it does not affect data traffic.</span></span> <span data-ttu-id="5eab6-114">既定の WAN パスで必要な帯域幅が確保されていない場合、CAC はインターネット パスまたは公衆交換電話網 (PSTN) を利用した通話のルーティングを試みることができます。</span><span class="sxs-lookup"><span data-stu-id="5eab6-114">If the default WAN path does not have the required bandwidth, CAC can attempt to route the call through an Internet path or the public switched telephone network (PSTN).</span></span> <span data-ttu-id="5eab6-115">CAC は、Lync Server でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="5eab6-115">CAC is available only in Lync Server.</span></span>

<span data-ttu-id="5eab6-116">ここでは、通話受付管理機能と CAC の計画方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="5eab6-116">This section describes the call admission control functionality and explains how to plan for CAC.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5eab6-117">Lync Server には、通話受付制御 (CAC)、緊急サービス (E9)、メディアバイパスという3つの高度なエンタープライズ Voip 機能があります。</span><span class="sxs-lookup"><span data-stu-id="5eab6-117">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="5eab6-118">これら3つの機能の計画情報の概要については、「 <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013 の高度なエンタープライズ voip 機能のネットワーク設定</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5eab6-118">For an overview of planning information that is common to all three of these features, see <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5eab6-119">このセクション中</span><span class="sxs-lookup"><span data-stu-id="5eab6-119">In This Section</span></span>

  - [<span data-ttu-id="5eab6-120">Lync Server 2013 の通話受付制御の概要</span><span class="sxs-lookup"><span data-stu-id="5eab6-120">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)

  - [<span data-ttu-id="5eab6-121">Lync Server 2013 での通話受付管理サービス要件の定義</span><span class="sxs-lookup"><span data-stu-id="5eab6-121">Defining your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="5eab6-122">例: Lync Server 2013 での通話受付制御の要件の収集</span><span class="sxs-lookup"><span data-stu-id="5eab6-122">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="5eab6-123">Lync Server 2013 の CAC のコンポーネントとトポロジ</span><span class="sxs-lookup"><span data-stu-id="5eab6-123">Components and topologies for CAC in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-cac.md)

  - [<span data-ttu-id="5eab6-124">Lync Server 2013 の通話受付管理のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="5eab6-124">Best practices for call admission control in Lync Server 2013</span></span>](lync-server-2013-best-practices-for-call-admission-control.md)

  - [<span data-ttu-id="5eab6-125">Lync Server 2013 の通話受付管理の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="5eab6-125">Deployment checklist for call admission control in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

