---
title: 'Lync Server 2013: 組織のエンタープライズ VoIP 要件の定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0ce05c39e3433ff949d82f583207aebfba871fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="c4820-102">Lync Server 2013 での組織のエンタープライズ VoIP 要件の定義</span><span class="sxs-lookup"><span data-stu-id="c4820-102">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4820-103">_**最終更新日:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="c4820-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="c4820-104">このトピックでは、トポロジ内のサイトとサイト間のリンクについて考慮する必要がある考慮事項、およびエンタープライズ Voip を展開する際のそれらの重要性について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4820-104">This topic provides an overview of the considerations you need to make about the regions, sites, and the links between sites in your topology and how those are important when you deploy Enterprise Voice.</span></span> <span data-ttu-id="c4820-105">これらの決定を行うための詳細については、計画ドキュメントの「 [Lync Server 2013 の高度なエンタープライズ voip 機能のネットワーク設定](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4820-105">For details to help you make these decisions, see [Network settings for the advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) in the Planning documentation.</span></span>

<div>

## <a name="sites-and-regions"></a><span data-ttu-id="c4820-106">サイトと地域</span><span class="sxs-lookup"><span data-stu-id="c4820-106">Sites and Regions</span></span>

<span data-ttu-id="c4820-107">まず、エンタープライズボイスとそのサイトが属するネットワーク領域を展開するトポロジ内のサイトを特定します。</span><span class="sxs-lookup"><span data-stu-id="c4820-107">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="c4820-108">特に、それぞれのサイトにどのようにして公衆交換電話網 (PSTN) 接続を提供するかを考慮します。</span><span class="sxs-lookup"><span data-stu-id="c4820-108">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="c4820-109">管理上の理由から、これらのサイトが属する地域が決定的要素となります。</span><span class="sxs-lookup"><span data-stu-id="c4820-109">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="c4820-110">ゲートウェイがローカルで展開される場所を決定します。ここでは、Survivable Branch アプライアンス (SBAs) を展開し、SIP trunks (ローカルまたはセントラルサイト) をインターネットテレフォニーサービスプロバイダー (ITSP) に構成することができます。</span><span class="sxs-lookup"><span data-stu-id="c4820-110">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>

</div>

<div>

## <a name="network-links-between-sites"></a><span data-ttu-id="c4820-111">サイト間のネットワークリンク</span><span class="sxs-lookup"><span data-stu-id="c4820-111">Network Links Between Sites</span></span>

<span data-ttu-id="c4820-112">また、セントラルサイトとそのブランチサイト間のネットワークリンクで想定される帯域幅の使用状況についても考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4820-112">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="c4820-113">サイト間の WAN リンクがある場合、または展開を計画している場合は、各ブランチサイトにゲートウェイを展開して、それらのサイトのユーザーに対してローカル直接の内部ダイヤル (DID) の終了を提供することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c4820-113">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="c4820-114">回復可能な WAN リンクは存在するが、WAN リンクの帯域幅に制限がありそうな場合、そのリンクに通話受付管理を構成します。</span><span class="sxs-lookup"><span data-stu-id="c4820-114">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="c4820-115">回復可能な WAN リンクを持っておらず、ブランチサイトで1000ユーザー未満のホストを使用していて、ローカルでトレーニングした Lync Server 管理者がいない場合は、ブランチサイトで Survivable Branch Appliance を展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c4820-115">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="c4820-116">ブランチサイトで1000と5000の両方のユーザーをホストし、回復可能な WAN 接続を使用しておられ、Lync Server のトレーニングを利用できるようになっている場合は、ブランチサイトに小規模ゲートウェイを設定した Survivable ブランチサーバーを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c4820-116">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="c4820-117">メディア バイパスをサポートするゲートウェイ ピアが存在する場合は、制限のあるリンクでメディア バイパスを有効にすることも検討してください。</span><span class="sxs-lookup"><span data-stu-id="c4820-117">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c4820-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4820-118">See Also</span></span>


[<span data-ttu-id="c4820-119">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4820-119">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

