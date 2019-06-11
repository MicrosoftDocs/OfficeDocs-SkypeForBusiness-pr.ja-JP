---
title: 'Lync Server 2013: 通話受付管理と仲介サーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control and Mediation Server
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398585(v=OCS.15)
ms:contentKeyID: 48184546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 787e312bcdee289050f2147912e87ef542433db4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="23e27-102">Lync Server 2013 の通話受付管理と仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="23e27-102">Call admission control and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23e27-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="23e27-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="23e27-104">通話受付制御 (CAC) は、最初に Lync Server 2010 で導入されたものであり、使用可能な帯域幅に基づいてリアルタイムのセッションの確立を管理して、混雑したネットワーク上のユーザーに対して低品質のエクスペリエンス (QoE) を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="23e27-104">Call admission control (CAC), first introduced in Lync Server 2010, manages real-time session establishment, based on available bandwidth, to help prevent poor Quality of Experience (QoE) for users on congested networks.</span></span> <span data-ttu-id="23e27-105">この機能をサポートするために、企業のボイスインフラストラクチャとゲートウェイまたは SIP トランクプロバイダーの間でシグナリングとメディアの翻訳を提供する仲介サーバーが、Lync 上の2つの操作の帯域幅管理を担当しています。サーバー側とゲートウェイ側。</span><span class="sxs-lookup"><span data-stu-id="23e27-105">To support this capability, the Mediation Server, which provides signaling and media translation between the Enterprise Voice infrastructure and a gateway or SIP trunking provider, is responsible for bandwidth management for its two interactions on the Lync Server side and on the gateway side.</span></span> <span data-ttu-id="23e27-106">通話受付管理では、通話の終端エンティティが帯域幅の予約を処理します。</span><span class="sxs-lookup"><span data-stu-id="23e27-106">In call admission control, the terminating entity for a call handles the bandwidth reservation.</span></span> <span data-ttu-id="23e27-107">仲介サーバーがゲートウェイ側でやり取りするゲートウェイピア (PSTN ゲートウェイ、IP PBX、SBC) では、Lync Server 2013 の通話受付制御はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="23e27-107">The gateway peers (PSTN gateway, IP-PBX, SBC) that the Mediation Server interacts with on the gateway side do not support Lync Server 2013 call admission control.</span></span> <span data-ttu-id="23e27-108">そのため、仲介サーバーは、ゲートウェイピアの代わりに帯域幅の操作を処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23e27-108">Thus, the Mediation Server has to handle bandwidth interactions on behalf of its gateway peer.</span></span> <span data-ttu-id="23e27-109">可能な限り、仲介サーバーは事前に帯域幅を予約します。</span><span class="sxs-lookup"><span data-stu-id="23e27-109">Whenever possible, the Mediation Server will reserve bandwidth in advance.</span></span> <span data-ttu-id="23e27-110">予約できない場合 (たとえば、ゲートウェイ側の最終的なメディア エンドポイントのローカリティが、ゲートウェイ ピアへの発信通話に対して不明な場合)、帯域幅は通話が開始されたときに予約されます。</span><span class="sxs-lookup"><span data-stu-id="23e27-110">If that is not possible (for example, if the locality of the ultimate media endpoint on the gateway side is unknown for an outgoing call to the gateway peer), bandwidth is reserved when the call is placed.</span></span> <span data-ttu-id="23e27-111">この動作によって帯域幅のオーバーサブスクリプションが生じる可能性がありますが、これが誤着信を防ぐ唯一の方法です。</span><span class="sxs-lookup"><span data-stu-id="23e27-111">This behavior can result in oversubscription of bandwidth, but it is the only way to prevent false rings.</span></span>

<span data-ttu-id="23e27-112">メディア バイパスと帯域幅の予約は同時に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="23e27-112">Media bypass and bandwidth reservation are mutually exclusive.</span></span> <span data-ttu-id="23e27-113">通話にメディアバイパスが採用されている場合、通話受付制御はその通話に対して実行されません。</span><span class="sxs-lookup"><span data-stu-id="23e27-113">If a media bypass is employed for a call, call admission control is not performed for that call.</span></span> <span data-ttu-id="23e27-114">この場合、その通話で、制限された帯域幅を使用するリンクがかかわっていないことが前提となります。</span><span class="sxs-lookup"><span data-stu-id="23e27-114">The assumption here is that there are no links with constrained bandwidth involved in the call.</span></span> <span data-ttu-id="23e27-115">仲介サーバーに関連する特定の通話に通話受付制御が使われている場合、その呼び出しでメディアのバイパスを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="23e27-115">If call admission control is used for a particular call that involves the Mediation Server, that call cannot employ media bypass.</span></span>

<span data-ttu-id="23e27-116">メディアバイパスまたは通話受付制御の詳細については、「 [Lync server 2013 でのメディアのバイパスの計画](lync-server-2013-planning-for-media-bypass.md)」または「計画ドキュメントの[lync server 2013 での通話受付制御の計画](lync-server-2013-planning-for-call-admission-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23e27-116">For details about media bypass or call admission control, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) or [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

