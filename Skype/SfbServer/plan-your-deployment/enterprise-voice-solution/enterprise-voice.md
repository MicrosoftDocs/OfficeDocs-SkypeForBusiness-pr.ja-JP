---
title: Skype for Business Server エンタープライズ VoIPの計画
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: エンタープライズ VoIP、地域、サイト間のネットワーク リンクを含む Skype for Business Server の基本計画、および音声使用状況トラフィックの見積もりについて説明します。
ms.openlocfilehash: 8f10eed8dfcfa7a8878b673ab76fd4d1fd40cc29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825677"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="80aef-103">Skype for Business Server エンタープライズ VoIPの計画</span><span class="sxs-lookup"><span data-stu-id="80aef-103">Plan for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="80aef-104">エンタープライズ VoIP、地域、サイト間のネットワーク リンクを含む Skype for Business Server の基本計画、および音声使用状況トラフィックの見積もりについて説明します。</span><span class="sxs-lookup"><span data-stu-id="80aef-104">Enterprise Voice planning basics in Skype for Business Server, including sites, regions, network links between sites, and estimating voice usage traffic.</span></span>
  
<span data-ttu-id="80aef-105">展開プロセスはエンタープライズ VoIP、既存のトポロジ、インフラストラクチャ、およびサポートするエンタープライズ VoIP機能によって異なります。</span><span class="sxs-lookup"><span data-stu-id="80aef-105">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="80aef-106">必要な手順は選択する機能によって異なりますが、計画に関して高レベルで考慮が必要なその他の事項があります。</span><span class="sxs-lookup"><span data-stu-id="80aef-106">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>
  
<span data-ttu-id="80aef-107">通常は、展開するサイトの種類と数および地理的な場所、各サイトの通話ボリューム、サイト間を接続するネットワーク リンクの種類、各サイトの音声機能に冗長性とフェールオーバーを持たせるかどうか、および既存の PBX 機器を使用するかどうかを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="80aef-107">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="80aef-108">Skype for Business Server 全体を計画する際には、高可用性など、特定の考慮事項を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80aef-108">There are certain considerations, such as high availability, that you should consider when you plan for Skype for Business Server as a whole.</span></span> <span data-ttu-id="80aef-109">これらの考慮事項については、このセクションのトピックで必要に応じて説明します。</span><span class="sxs-lookup"><span data-stu-id="80aef-109">These considerations are discussed in topics throughout this section, as needed.</span></span>
  
## <a name="sites-and-regions"></a><span data-ttu-id="80aef-110">サイトと地域</span><span class="sxs-lookup"><span data-stu-id="80aef-110">Sites and regions</span></span>

<span data-ttu-id="80aef-111">最初に、展開するトポロジ内のサイトとエンタープライズ VoIPサイトが属するネットワーク地域を特定します。</span><span class="sxs-lookup"><span data-stu-id="80aef-111">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="80aef-112">特に、それぞれのサイトにどのようにして公衆交換電話網 (PSTN) 接続を提供するかを考慮します。</span><span class="sxs-lookup"><span data-stu-id="80aef-112">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="80aef-113">管理上の理由から、これらのサイトが属する地域が決定的要素となります。</span><span class="sxs-lookup"><span data-stu-id="80aef-113">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="80aef-114">ゲートウェイをローカルに展開する場所、存続可能ブランチ アプライアンス (SA) を展開する場所、および SIP トランク (ローカルまたは中央サイト) をインターネット テレフォニー サービス プロバイダー (ITSP) に構成できる場所を決定します。</span><span class="sxs-lookup"><span data-stu-id="80aef-114">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>
  
## <a name="network-links-between-sites"></a><span data-ttu-id="80aef-115">サイト間のネットワーク リンク</span><span class="sxs-lookup"><span data-stu-id="80aef-115">Network links between sites</span></span>

<span data-ttu-id="80aef-116">また、中央サイトとブランチ サイトの間のネットワーク リンクで予想される帯域幅使用量も考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80aef-116">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="80aef-117">サイト間の復元 WAN リンクを展開または展開する計画がある場合は、各ブランチ サイトにゲートウェイを展開して、それらのサイトのユーザーにローカルのダイレクト インワード ダイヤル (DID) 終端を提供することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="80aef-117">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="80aef-118">回復可能な WAN リンクは存在するが、WAN リンクの帯域幅に制限がありそうな場合、そのリンクに通話受付管理を構成します。</span><span class="sxs-lookup"><span data-stu-id="80aef-118">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="80aef-119">回復可能な WAN リンクを使用していない場合、ブランチ サイトでホストするユーザー数が 1000 未満で、ローカルのトレーニングを受けた Skype for Business Server 管理者が利用できない場合は、ブランチ サイトに存続可能ブランチ アプライアンスを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="80aef-119">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="80aef-120">ブランチ サイトで 1000 ~ 5,000 人のユーザーをホストし、回復力のある WAN 接続が不足し、トレーニングを受けた Skype for Business Server 管理者が利用できる場合は、ブランチ サイトに小さなゲートウェイを備える存続可能ブランチ サーバーを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="80aef-120">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="80aef-121">メディア バイパスをサポートするゲートウェイ ピアが存在する場合は、制限のあるリンクでメディア バイパスを有効にすることも考慮してください。</span><span class="sxs-lookup"><span data-stu-id="80aef-121">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>
  
## <a name="estimating-voice-usage-and-traffic"></a><span data-ttu-id="80aef-122">音声の使用状況とトラフィックの見積もり</span><span class="sxs-lookup"><span data-stu-id="80aef-122">Estimating voice usage and traffic</span></span>

<span data-ttu-id="80aef-123">Microsoft Lync Server 2013 計画ツールは、次の指標を使用して、各サイトのユーザー トラフィックと、そのトラフィックをサポートするために必要なポート数を見積もっています。</span><span class="sxs-lookup"><span data-stu-id="80aef-123">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="80aef-124">**軽度のトラフィック** (1 人あたり 1 時間に 1 PSTN 通話) の場合、1 ポートに対して 15 ユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="80aef-124">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="80aef-125">**中度のトラフィック** (1 人あたり 1 時間に 2 PSTN 通話) の場合、1 ポートに対して 10 ユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="80aef-125">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="80aef-126">**重度のトラフィック** (1 人あたり 1 時間に 3 以上の PSTN 通話) の場合、1 ポートに対して 5 ユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="80aef-126">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="80aef-127">その後のポート数によって、必要な仲介サーバーとゲートウェイの数が決まれます。</span><span class="sxs-lookup"><span data-stu-id="80aef-127">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="80aef-128">ほとんどの組織が 2 ポートから最大 960 ポートの範囲の展開を検討している公衆交換電話網 (PSTN) ゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="80aef-128">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="80aef-129">(ゲートウェイはさらに大きくなりますが、主にテレフォニー サービス プロバイダーによって使用されます)。</span><span class="sxs-lookup"><span data-stu-id="80aef-129">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="80aef-p106">たとえば、10,000 名のユーザーを擁する、中度のトラフィックの組織の場合、1000 ポートが必要となります。 必要となるゲートウェイ数は、ゲートウェイの総合した処理能力によって決まる、必要とされるポート数の合計と同じになります。</span><span class="sxs-lookup"><span data-stu-id="80aef-p106">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  
## <a name="components-features-and-options-of-enterprise-voice"></a><span data-ttu-id="80aef-132">アプリケーションのコンポーネント、機能、およびエンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="80aef-132">Components, features, and options of Enterprise Voice</span></span>

<span data-ttu-id="80aef-133">展開の計画の詳細については、以下のセクションエンタープライズ VoIPしてください。</span><span class="sxs-lookup"><span data-stu-id="80aef-133">See the following sections for more information on planning your Enterprise Voice deployment.</span></span>
  
- [<span data-ttu-id="80aef-134">Skype for Business Server のエンタープライズ VoIPに必要なコンポーネント</span><span class="sxs-lookup"><span data-stu-id="80aef-134">Components required for Enterprise Voice in Skype for Business Server</span></span>](components-required-for-enterprise-voice.md)
    
- [<span data-ttu-id="80aef-135">Skype for Business Server での PSTN 接続の計画</span><span class="sxs-lookup"><span data-stu-id="80aef-135">Plan for PSTN connectivity in Skype for Business Server</span></span>](pstn-connectivity-0.md)
    
- [<span data-ttu-id="80aef-136">Skype for Business Server の高度エンタープライズ VoIP機能のネットワーク設定</span><span class="sxs-lookup"><span data-stu-id="80aef-136">Network settings for the advanced Enterprise Voice features in Skype for Business Server</span></span>](network-settings-for-advanced-features.md)
    
- [<span data-ttu-id="80aef-137">Skype for Business Server で通話受付管理を計画する</span><span class="sxs-lookup"><span data-stu-id="80aef-137">Plan for call admission control in Skype for Business Server</span></span>](call-admission-control.md)
    
- [<span data-ttu-id="80aef-138">Skype for Business Server で緊急サービスを計画する</span><span class="sxs-lookup"><span data-stu-id="80aef-138">Plan for emergency services in Skype for Business Server</span></span>](emergency-services.md)
    
- [<span data-ttu-id="80aef-139">Skype for Business でのメディア バイパスの計画</span><span class="sxs-lookup"><span data-stu-id="80aef-139">Plan for media bypass in Skype for Business</span></span>](media-bypass.md)
    
- [<span data-ttu-id="80aef-140">Skype for Business を使用してプライベート電話回線を計画する</span><span class="sxs-lookup"><span data-stu-id="80aef-140">Plan for private telephone lines with Skype for Business</span></span>](private-telephone-lines.md)
    
- [<span data-ttu-id="80aef-141">Skype for Business Location-Basedルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="80aef-141">Plan for Location-Based Routing in Skype for Business</span></span>](location-based-routing.md)
    
- [<span data-ttu-id="80aef-142">Skype for Business の通話管理機能を計画する</span><span class="sxs-lookup"><span data-stu-id="80aef-142">Plan for call management features in Skype for Business</span></span>](call-management-features.md)
    
- [<span data-ttu-id="80aef-143">Skype for Business Server エンタープライズ VoIP回復性を計画する</span><span class="sxs-lookup"><span data-stu-id="80aef-143">Plan for Enterprise Voice resiliency in Skype for Business Server</span></span>](enterprise-voice-resiliency.md)
    

