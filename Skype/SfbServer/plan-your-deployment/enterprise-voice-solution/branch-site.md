---
title: Skype for Business Server 2015 のブランチ サイトの SIP トランキング
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: ビジネス サーバーのエンタープライズ VoIP は、Skype でのブランチ サイトに SIP トランクについて説明します。
ms.openlocfilehash: 862a39e7472ab461725957cea6e5a89e0c156286
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server-2015"></a><span data-ttu-id="c7a95-103">Skype for Business Server 2015 のブランチ サイトの SIP トランキング</span><span class="sxs-lookup"><span data-stu-id="c7a95-103">Branch site SIP trunking in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c7a95-104">ビジネス サーバーのエンタープライズ VoIP は、Skype でのブランチ サイトに SIP トランクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c7a95-104">Learn about SIP trunking at branch sites in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="c7a95-105">場合によっては、選択したブランチ サイトでの分散型 SIP トランクを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7a95-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="c7a95-106">SIP かどうかを判断するのにはトランクがために必要なブランチ サイトとブランチ サイトで SIP トランクを展開するためのサポートされているトポロジ オプションの詳細については、 [SIP サーバー 2015 のビジネス用の Skype でトランク](sip-trunking.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7a95-106">To determine whether a SIP trunk is needed for a branch site, and for details about the supported topology options for deploying SIP trunks in branch sites, see [SIP trunking in Skype for Business Server 2015](sip-trunking.md).</span></span>
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="c7a95-107">ブランチ サイト SIP トランク要件例の分析</span><span class="sxs-lookup"><span data-stu-id="c7a95-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="c7a95-108">ブランチ サイトの SIP トランクを展開することを決定する際は、サイト固有のコスト分析を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7a95-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="c7a95-109">たとえば、ワシントン州レドモンドの中央サイトと、ニューヨークにブランチ サイトを持つ企業では、ニューヨーク サイトからローカル サービス プロバイダーへの SIP トランクを実装するかどうかを決定する分析を行ってください。</span><span class="sxs-lookup"><span data-stu-id="c7a95-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>
  
<span data-ttu-id="c7a95-110">ニューヨークでの分散型 SIP トランクの費用対効果が高いかどうかを判断するには、SIP トランクを使用する Direct Inward Dialing (DID) 番号を識別し、レドモンド (425) 以外の地域にニューヨークからかける電話の回数を分析します。</span><span class="sxs-lookup"><span data-stu-id="c7a95-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="c7a95-111">セントラル サイトでは、ブランチ サイトの DID 終了をことができます。</span><span class="sxs-lookup"><span data-stu-id="c7a95-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="c7a95-112">たとえば、レドモンドの中央サイトでは、ニューヨークのブランチ サイトの DID 番号をホストできます。</span><span class="sxs-lookup"><span data-stu-id="c7a95-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="c7a95-113">分散型 SIP トランクを実装するためのコストがこれらの呼び出しのコストよりも小さい場合は、ニューヨークのブランチ サイトに SIP トランクを実装することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="c7a95-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span> 
  
## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="c7a95-114">その他のブランチ サイト SIP トランク要件</span><span class="sxs-lookup"><span data-stu-id="c7a95-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="c7a95-115">ゲートウェイではなく、SIP トランクを展開する場合の選択肢は、各オプションの公衆交換電話網 (PSTN) の市外通話の通話料の差に基づいています。</span><span class="sxs-lookup"><span data-stu-id="c7a95-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="c7a95-116">ブランチ サイト SIP トランクを展開する場合は、復元性と帯域幅要件を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7a95-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="c7a95-117">ブランチ サイトと中央サイト間のリンクは、耐障害性、十分な帯域幅を持つ場合は、SIP トランクまたはゲートウェイを展開できます。</span><span class="sxs-lookup"><span data-stu-id="c7a95-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="c7a95-118">ブランチ サイトでのリカバリ性に優れたブランチ アプライアンスを展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c7a95-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="c7a95-119">ブランチ サイトと中央サイト間のリンクは、耐障害性は、か、リカバリ性に優れたブランチ アプライアンスを展開するブランチ サイトで SIP トランクまたはゲートウェイとの存続可能ブランチ サーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="c7a95-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span> 
  

