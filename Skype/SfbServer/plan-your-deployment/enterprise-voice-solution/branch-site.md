---
title: Skype for Business Server のブランチサイト SIP トランク
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Skype for Business Server Enterprise Voice のブランチサイトでの SIP トランクについて説明します。
ms.openlocfilehash: 14af9a096b368f310b0d4fbce425bf6d1c08696a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277112"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a><span data-ttu-id="1132f-103">Skype for Business Server のブランチサイト SIP トランク</span><span class="sxs-lookup"><span data-stu-id="1132f-103">Branch site SIP trunking in Skype for Business Server</span></span>
 
<span data-ttu-id="1132f-104">Skype for Business Server Enterprise Voice のブランチサイトでの SIP トランクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1132f-104">Learn about SIP trunking at branch sites in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="1132f-105">場合によっては、選択したブランチサイトに配布 SIP トランキングを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1132f-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="1132f-106">ブランチサイトに SIP トランクが必要かどうかを判断し、ブランチサイトで SIP trunks を展開するためにサポートされているトポロジーオプションの詳細については、「 [Skype For Business Server の sip トランク](sip-trunking.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1132f-106">To determine whether a SIP trunk is needed for a branch site, and for details about the supported topology options for deploying SIP trunks in branch sites, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="1132f-107">ブランチ サイト SIP トランク要件例の分析</span><span class="sxs-lookup"><span data-stu-id="1132f-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="1132f-108">ブランチサイト SIP トランクの展開を決定する際には、サイト固有のコスト分析を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1132f-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="1132f-109">たとえば、ニューヨークのレドモンド、ワシントン、支店にセントラルサイトがある企業では、ニューヨークサイトの SIP トランクをローカルサービスプロバイダに実装するかどうかを判断する分析を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="1132f-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>
  
<span data-ttu-id="1132f-110">ニューヨークでの分散型 SIP トランクの費用対効果が高いかどうかを判断するには、SIP トランクを使用する Direct Inward Dialing (DID) 番号を識別し、レドモンド (425) 以外の地域にニューヨークからかける電話の回数を分析します。</span><span class="sxs-lookup"><span data-stu-id="1132f-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="1132f-111">セントラルサイトでブランチサイトの終了ができました。</span><span class="sxs-lookup"><span data-stu-id="1132f-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="1132f-112">たとえば、Redmond のセントラルサイトでは、ニューヨーク支社のサイトの番号をホストできます。</span><span class="sxs-lookup"><span data-stu-id="1132f-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="1132f-113">分散 SIP トランクの実装のコストがこれらの通話のコストよりも少ない場合は、ニューヨーク支店のサイトで SIP トランクを実装することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="1132f-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span> 
  
## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="1132f-114">その他のブランチ サイト SIP トランク要件</span><span class="sxs-lookup"><span data-stu-id="1132f-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="1132f-115">ゲートウェイの代わりに SIP トランクを展開するには、各オプションの PSTN (公衆交換電話網) の長距離電話料金の差に基づいて選択することができます。</span><span class="sxs-lookup"><span data-stu-id="1132f-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="1132f-116">ブランチサイト SIP トランクを展開する場合は、回復性と帯域幅の要件を特定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="1132f-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="1132f-117">ブランチサイトとセントラルサイト間のリンクが回復可能であり、十分な帯域幅がある場合は、SIP トランクまたはゲートウェイを展開できます。</span><span class="sxs-lookup"><span data-stu-id="1132f-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="1132f-118">ブランチサイトに Survivable Branch Appliance を展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1132f-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="1132f-119">ブランチサイトとセントラルサイト間のリンクが復元できない場合は、Survivable Branch Appliance を展開するか、ゲートウェイまたは SIP トランクのいずれかでブランチサイトに Survivable ブランチサーバーを展開してください。</span><span class="sxs-lookup"><span data-stu-id="1132f-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span> 
  

