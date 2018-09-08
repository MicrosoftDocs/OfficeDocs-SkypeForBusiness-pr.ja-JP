---
title: ビジネスのサーバーに、Skype でエンタープライズ VoIP を計画します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: エンタープライズ VoIP の Skype の基本の Business Server の計画、サイト、地域、サイト間のネットワーク リンクを含むおよび音声の使用量のトラフィックを見積もるします。
ms.openlocfilehash: 3c5cad1b37b4f3bfe3fe73cad1d185b0116a68a0
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885338"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="07756-103">ビジネスのサーバーに、Skype でエンタープライズ VoIP を計画します。</span><span class="sxs-lookup"><span data-stu-id="07756-103">Plan for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="07756-104">エンタープライズ VoIP の Skype の基本の Business Server の計画、サイト、地域、サイト間のネットワーク リンクを含むおよび音声の使用量のトラフィックを見積もるします。</span><span class="sxs-lookup"><span data-stu-id="07756-104">Enterprise Voice planning basics in Skype for Business Server, including sites, regions, network links between sites, and estimating voice usage traffic.</span></span>
  
<span data-ttu-id="07756-105">エンタープライズ VoIP の展開プロセスは、既存のトポロジ、インフラストラクチャ、およびエンタープライズ VoIP 機能をサポートするかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="07756-105">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="07756-106">必要な手順は選択する機能によって異なりますが、計画に関して高レベルで考慮が必要なその他の事項があります。</span><span class="sxs-lookup"><span data-stu-id="07756-106">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>
  
<span data-ttu-id="07756-107">通常は、展開するサイトの種類と数および地理的な場所、各サイトの通話ボリューム、サイト間を接続するネットワーク リンクの種類、各サイトの音声機能に冗長性とフェールオーバーを持たせるかどうか、および既存の PBX 機器を使用するかどうかを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="07756-107">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="07756-108">ビジネス サーバー全体に Skype を計画するときに考慮する必要がありますが、高可用性などの特定の考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="07756-108">There are certain considerations, such as high availability, that you should consider when you plan for Skype for Business Server as a whole.</span></span> <span data-ttu-id="07756-109">これらの考慮事項については、このセクションのトピックで必要に応じて説明します。</span><span class="sxs-lookup"><span data-stu-id="07756-109">These considerations are discussed in topics throughout this section, as needed.</span></span>
  
## <a name="sites-and-regions"></a><span data-ttu-id="07756-110">サイトと地域</span><span class="sxs-lookup"><span data-stu-id="07756-110">Sites and regions</span></span>

<span data-ttu-id="07756-111">最初に、エンタープライズ VoIP とそれらのサイトに所属しているネットワーク領域を配置するトポロジでは、サイトを特定します。</span><span class="sxs-lookup"><span data-stu-id="07756-111">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="07756-112">特に、それぞれのサイトにどのようにして公衆交換電話網 (PSTN) 接続を提供するかを考慮します。</span><span class="sxs-lookup"><span data-stu-id="07756-112">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="07756-113">管理上の理由から、これらのサイトが属する地域が決定的要素となります。</span><span class="sxs-lookup"><span data-stu-id="07756-113">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="07756-114">ゲートウェイをローカルに配置されますが、リカバリ性に優れたブランチ アプライアンス (Sba) を配置する場所、および構成できる SIP トランク (ローカルまたはセントラル サイトで) インターネット テレフォニー サービス プロバイダー (ITSP) を決定します。</span><span class="sxs-lookup"><span data-stu-id="07756-114">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>
  
## <a name="network-links-between-sites"></a><span data-ttu-id="07756-115">サイト間のネットワーク リンク</span><span class="sxs-lookup"><span data-stu-id="07756-115">Network links between sites</span></span>

<span data-ttu-id="07756-116">セントラル サイトおよびそのブランチ サイト間のネットワーク リンクの必要な帯域幅の使用を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07756-116">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="07756-117">ある、またはサイト間での弾力性のある WAN リンクの展開を計画する場合は、それらのサイトでユーザーのローカル直接の内側のダイヤル (DID) の終了を提供するには、各ブランチ サイトでゲートウェイを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="07756-117">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="07756-118">回復可能な WAN リンクは存在するが、WAN リンクの帯域幅に制限がありそうな場合、そのリンクに通話受付管理を構成します。</span><span class="sxs-lookup"><span data-stu-id="07756-118">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="07756-119">弾力性のある WAN リンクを使用する必要はありません、する場合は、ブランチ サイトに 1000 未満のユーザーをホストし、ビジネス サーバーの管理者が使用可能なブランチ サイトでのリカバリ性に優れたブランチ アプライアンスを展開することをお勧めします。 ローカルのトレーニングを受けた Skype はありません。</span><span class="sxs-lookup"><span data-stu-id="07756-119">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="07756-120">1000、5000、ブランチ サイトのユーザーとの間のホストが、弾力性のある WAN 接続がないし、のビジネスのサーバーの管理者が使用できる場合は、Skype がトレーニングを受けた場合は、小規模ブランチ サイトでゲートウェイでの存続可能ブランチ サーバーを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="07756-120">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="07756-121">メディア バイパスをサポートするゲートウェイ ピアが存在する場合は、制限のあるリンクでメディア バイパスを有効にすることも検討してください。</span><span class="sxs-lookup"><span data-stu-id="07756-121">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>
  
## <a name="estimating-voice-usage-and-traffic"></a><span data-ttu-id="07756-122">音声の利用状況とトラフィックの予測</span><span class="sxs-lookup"><span data-stu-id="07756-122">Estimating voice usage and traffic</span></span>

<span data-ttu-id="07756-123">Microsoft Lync Server 2013、計画ツールは、ユーザーのトラフィックでは、各サイトおよびそのトラフィックをサポートするのにために必要なポートの数を推定するのには次のメトリックを使用します。</span><span class="sxs-lookup"><span data-stu-id="07756-123">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="07756-124">**軽度のトラフィック** (1 人あたり 1 時間に 1 PSTN 通話) の場合、1 ポートに対して 15 ユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="07756-124">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
    
> <span data-ttu-id="07756-125">**中度のトラフィック** (1 人あたり 1 時間に 2 PSTN 通話) の場合、1 ポートに対して 10 ユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="07756-125">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
    
> <span data-ttu-id="07756-126">**重度のトラフィック** (1 人あたり 1 時間に 3 以上の PSTN 通話) の場合、1 ポートに対して 5 ユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="07756-126">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="07756-127">ポートの数には、仲介サーバーとゲートウェイが必要になることの順番を決定します。</span><span class="sxs-lookup"><span data-stu-id="07756-127">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="07756-128">960 個のポートに 2 つのポートからのサイズの範囲を展開するほとんどの組織を検討している公衆交換電話網 (PSTN) ゲートウェイです。</span><span class="sxs-lookup"><span data-stu-id="07756-128">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="07756-129">(がさらに大きくゲートウェイがこれらの主にテレフォニー サービス プロバイダーによって使用されます)。</span><span class="sxs-lookup"><span data-stu-id="07756-129">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="07756-p106">たとえば、10,000 名のユーザーを擁する中度のトラフィックの組織の場合、1000 ポートが必要となります。必要となるゲートウェイ数は、ゲートウェイの総合した処理能力によって決まる、必要とされるポート数の合計と同じになります。</span><span class="sxs-lookup"><span data-stu-id="07756-p106">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  
## <a name="components-features-and-options-of-enterprise-voice"></a><span data-ttu-id="07756-132">コンポーネント、機能、およびエンタープライズ VoIP のオプション</span><span class="sxs-lookup"><span data-stu-id="07756-132">Components, features, and options of Enterprise Voice</span></span>

<span data-ttu-id="07756-133">エンタープライズ VoIP 展開の計画に関する詳細については次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="07756-133">See the following sections for more information on planning your Enterprise Voice deployment.</span></span>
  
- [<span data-ttu-id="07756-134">Skype でエンタープライズ VoIP のサーバーのビジネスに必要なコンポーネント</span><span class="sxs-lookup"><span data-stu-id="07756-134">Components required for Enterprise Voice in Skype for Business Server</span></span>](components-required-for-enterprise-voice.md)
    
- [<span data-ttu-id="07756-135">ビジネス サーバーに、Skype で PSTN への接続を計画します。</span><span class="sxs-lookup"><span data-stu-id="07756-135">Plan for PSTN connectivity in Skype for Business Server</span></span>](pstn-connectivity-0.md)
    
- [<span data-ttu-id="07756-136">Skype で高度なエンタープライズ VoIP 機能のビジネス サーバー用のネットワーク設定</span><span class="sxs-lookup"><span data-stu-id="07756-136">Network settings for the advanced Enterprise Voice features in Skype for Business Server</span></span>](network-settings-for-advanced-features.md)
    
- [<span data-ttu-id="07756-137">ビジネス サーバーに、Skype で通話受付制御を計画します。</span><span class="sxs-lookup"><span data-stu-id="07756-137">Plan for call admission control in Skype for Business Server</span></span>](call-admission-control.md)
    
- [<span data-ttu-id="07756-138">ビジネス サーバーに、Skype で緊急サービスを計画します。</span><span class="sxs-lookup"><span data-stu-id="07756-138">Plan for emergency services in Skype for Business Server</span></span>](emergency-services.md)
    
- [<span data-ttu-id="07756-139">ビジネス用の Skype でメディアをバイパスするための計画します。</span><span class="sxs-lookup"><span data-stu-id="07756-139">Plan for media bypass in Skype for Business</span></span>](media-bypass.md)
    
- [<span data-ttu-id="07756-140">ビジネス用の Skype でプライベート電話回線の計画</span><span class="sxs-lookup"><span data-stu-id="07756-140">Plan for private telephone lines with Skype for Business</span></span>](private-telephone-lines.md)
    
- [<span data-ttu-id="07756-141">Skype のビジネスの場所ベースのルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="07756-141">Plan for Location-Based Routing in Skype for Business</span></span>](location-based-routing.md)
    
- [<span data-ttu-id="07756-142">ビジネス用の Skype での通話管理機能の計画</span><span class="sxs-lookup"><span data-stu-id="07756-142">Plan for call management features in Skype for Business</span></span>](call-management-features.md)
    
- [<span data-ttu-id="07756-143">ビジネス サーバーに、Skype でエンタープライズ VoIP の復元を計画します。</span><span class="sxs-lookup"><span data-stu-id="07756-143">Plan for Enterprise Voice resiliency in Skype for Business Server</span></span>](enterprise-voice-resiliency.md)
    

