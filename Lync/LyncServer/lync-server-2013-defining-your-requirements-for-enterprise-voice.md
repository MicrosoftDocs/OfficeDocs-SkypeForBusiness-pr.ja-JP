---
title: 'Lync Server 2013: エンタープライズ Voip の要件の定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0406286f4f9d8251743fe6ff3a4807dff277fe92
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="f6742-102">Lync Server 2013 でのエンタープライズ Voip の要件の定義</span><span class="sxs-lookup"><span data-stu-id="f6742-102">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6742-103">_**トピックの最終更新日:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="f6742-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="f6742-104">ここでは、トポロジ内のサイト、サイト、およびサイト間のリンクについての考慮事項について概説します。また、エンタープライズ Voip を展開するときにそれらがどのように重要であるかについても説明します。</span><span class="sxs-lookup"><span data-stu-id="f6742-104">This topic provides an overview of the considerations you need to make about the regions, sites, and the links between sites in your topology and how those are important when you deploy Enterprise Voice.</span></span> <span data-ttu-id="f6742-105">これらの決定を行うのに役立つ詳細については、「計画」のドキュメントの「 [Lync Server 2013 の高度なエンタープライズ voip 機能のネットワーク設定](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6742-105">For details to help you make these decisions, see [Network settings for the advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) in the Planning documentation.</span></span>

<div>

## <a name="sites-and-regions"></a><span data-ttu-id="f6742-106">サイトと地域</span><span class="sxs-lookup"><span data-stu-id="f6742-106">Sites and Regions</span></span>

<span data-ttu-id="f6742-107">最初に、エンタープライズ Voip を展開するトポロジ内のサイトと、それらのサイトが属するネットワーク地域を特定します。</span><span class="sxs-lookup"><span data-stu-id="f6742-107">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="f6742-108">特に、それぞれのサイトにどのようにして公衆交換電話網 (PSTN) 接続を提供するかを考慮します。</span><span class="sxs-lookup"><span data-stu-id="f6742-108">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="f6742-109">管理上の理由から、これらのサイトが属する地域が決定的要素となります。</span><span class="sxs-lookup"><span data-stu-id="f6742-109">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="f6742-110">存続可能 Branch アプライアンス (SBAs) が展開される場所、およびインターネットテレフォニーサービスプロバイダー (ITSP) に SIP トランク (ローカルまたは中央サイト) を構成できる場所を決定してください。</span><span class="sxs-lookup"><span data-stu-id="f6742-110">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>

</div>

<div>

## <a name="network-links-between-sites"></a><span data-ttu-id="f6742-111">サイト間のネットワーク リンク</span><span class="sxs-lookup"><span data-stu-id="f6742-111">Network Links Between Sites</span></span>

<span data-ttu-id="f6742-112">また、中央サイトとブランチサイト間のネットワークリンクに必要な帯域幅の使用状況についても検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6742-112">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="f6742-113">サイト間の WAN リンクを持っている、または展開する計画がある場合は、各ブランチサイトにゲートウェイを展開して、それらのサイトのユーザーのためにローカルの直接の中向きダイヤル (DID) の終了を提供することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f6742-113">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="f6742-114">回復可能な WAN リンクは存在するが、WAN リンクの帯域幅に制限がありそうな場合、そのリンクに通話受付管理を構成します。</span><span class="sxs-lookup"><span data-stu-id="f6742-114">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="f6742-115">回復可能な WAN リンクがない場合、ブランチサイトで1000ユーザー未満でホストされ、ローカルのトレーニングを受けた Lync Server 管理者がいない場合は、ブランチサイトで存続可能ブランチアプライアンスを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f6742-115">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="f6742-116">ブランチサイトで1000と5000のユーザーをホストし、回復可能な WAN 接続がなく、専任の Lync Server 管理者が利用できるようになっている場合は、ブランチサイトに小規模なゲートウェイを使用して存続可能ブランチサーバーを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f6742-116">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="f6742-117">メディア バイパスをサポートするゲートウェイ ピアが存在する場合は、制限のあるリンクでメディア バイパスを有効にすることも考慮してください。</span><span class="sxs-lookup"><span data-stu-id="f6742-117">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f6742-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6742-118">See Also</span></span>


[<span data-ttu-id="f6742-119">Lync Server 2013 の高度なエンタープライズ Voip 機能のネットワーク設定</span><span class="sxs-lookup"><span data-stu-id="f6742-119">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

