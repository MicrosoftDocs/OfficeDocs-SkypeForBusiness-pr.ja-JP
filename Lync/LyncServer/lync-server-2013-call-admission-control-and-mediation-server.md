---
title: 'Lync Server 2013: 通話受付管理と仲介サーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control and Mediation Server
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398585(v=OCS.15)
ms:contentKeyID: 48184546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16158c8920279d95cfe3deed37f789eaedccc8b5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="5f03f-102">Lync Server 2013 での通話受付管理と仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="5f03f-102">Call admission control and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f03f-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="5f03f-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="5f03f-104">最初に Lync Server 2010 で導入された通話受付管理 (CAC) では、使用可能な帯域幅に基づいてリアルタイムセッションの確立を管理し、混雑したネットワーク上のユーザーに対する QoE (Quality of Experience) の低下を防ぎます。</span><span class="sxs-lookup"><span data-stu-id="5f03f-104">Call admission control (CAC), first introduced in Lync Server 2010, manages real-time session establishment, based on available bandwidth, to help prevent poor Quality of Experience (QoE) for users on congested networks.</span></span> <span data-ttu-id="5f03f-105">この機能をサポートするために、企業の音声インフラストラクチャとゲートウェイまたは SIP トランキングプロバイダー間でシグナリングとメディア変換を提供する仲介サーバーは、Lync での2つの相互作用について帯域幅管理を担当します。サーバー側とゲートウェイ側。</span><span class="sxs-lookup"><span data-stu-id="5f03f-105">To support this capability, the Mediation Server, which provides signaling and media translation between the Enterprise Voice infrastructure and a gateway or SIP trunking provider, is responsible for bandwidth management for its two interactions on the Lync Server side and on the gateway side.</span></span> <span data-ttu-id="5f03f-106">通話受付管理では、通話の終端エンティティが帯域幅の予約を処理します。</span><span class="sxs-lookup"><span data-stu-id="5f03f-106">In call admission control, the terminating entity for a call handles the bandwidth reservation.</span></span> <span data-ttu-id="5f03f-107">仲介サーバーがゲートウェイ側で対話するゲートウェイピア (PSTN ゲートウェイ、IP-PBX、SBC) は、Lync Server 2013 通話受付管理をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5f03f-107">The gateway peers (PSTN gateway, IP-PBX, SBC) that the Mediation Server interacts with on the gateway side do not support Lync Server 2013 call admission control.</span></span> <span data-ttu-id="5f03f-108">そのため、仲介サーバーは、ゲートウェイピアの代わりに帯域幅の相互作用を処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f03f-108">Thus, the Mediation Server has to handle bandwidth interactions on behalf of its gateway peer.</span></span> <span data-ttu-id="5f03f-109">可能な限り、仲介サーバーは事前に帯域幅を予約します。</span><span class="sxs-lookup"><span data-stu-id="5f03f-109">Whenever possible, the Mediation Server will reserve bandwidth in advance.</span></span> <span data-ttu-id="5f03f-110">予約できない場合 (たとえば、ゲートウェイ側の最終的なメディア エンドポイントのローカリティが、ゲートウェイ ピアへの発信通話に対して不明な場合)、帯域幅は通話が開始されたときに予約されます。</span><span class="sxs-lookup"><span data-stu-id="5f03f-110">If that is not possible (for example, if the locality of the ultimate media endpoint on the gateway side is unknown for an outgoing call to the gateway peer), bandwidth is reserved when the call is placed.</span></span> <span data-ttu-id="5f03f-111">この動作によって帯域幅のオーバーサブスクリプションが生じる可能性がありますが、これが誤着信を防ぐ唯一の方法です。</span><span class="sxs-lookup"><span data-stu-id="5f03f-111">This behavior can result in oversubscription of bandwidth, but it is the only way to prevent false rings.</span></span>

<span data-ttu-id="5f03f-112">メディア バイパスと帯域幅の予約は同時に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="5f03f-112">Media bypass and bandwidth reservation are mutually exclusive.</span></span> <span data-ttu-id="5f03f-113">メディア バイパスを通話で使用する場合、その通話で通話受付管理を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="5f03f-113">If a media bypass is employed for a call, call admission control is not performed for that call.</span></span> <span data-ttu-id="5f03f-114">この場合、その通話で、制限された帯域幅を使用するリンクが関わっていないことが前提となります。</span><span class="sxs-lookup"><span data-stu-id="5f03f-114">The assumption here is that there are no links with constrained bandwidth involved in the call.</span></span> <span data-ttu-id="5f03f-115">仲介サーバーを含む特定の呼び出しに対して通話受付管理を使用する場合、その呼び出しでメディアバイパスを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="5f03f-115">If call admission control is used for a particular call that involves the Mediation Server, that call cannot employ media bypass.</span></span>

<span data-ttu-id="5f03f-116">メディアバイパスまたは通話受付管理の詳細については、「計画」のドキュメントの「 [lync server 2013 でのメディアバイパスの計画](lync-server-2013-planning-for-media-bypass.md)」または「 [lync server 2013 での通話受付管理の計画](lync-server-2013-planning-for-call-admission-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f03f-116">For details about media bypass or call admission control, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) or [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

