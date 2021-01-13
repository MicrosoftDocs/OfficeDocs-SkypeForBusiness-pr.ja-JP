---
title: Skype for Business Server のブランチ サイト SIP トランキング
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
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Skype for Business Server のブランチ サイトでの SIP トランキングについてエンタープライズ VoIP。
ms.openlocfilehash: f8b875fca8adc1ac78c0b24cf3e53fab2ec2cd89
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813717"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a><span data-ttu-id="b0be3-103">Skype for Business Server のブランチ サイト SIP トランキング</span><span class="sxs-lookup"><span data-stu-id="b0be3-103">Branch site SIP trunking in Skype for Business Server</span></span>
 
<span data-ttu-id="b0be3-104">Skype for Business Server のブランチ サイトでの SIP トランキングについてエンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="b0be3-104">Learn about SIP trunking at branch sites in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="b0be3-105">場合によっては、選択したブランチ サイトで分散型 SIP トランキングの実装が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="b0be3-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="b0be3-106">ブランチ サイトに SIP トランクが必要かどうかを判断し、ブランチ サイトに SIP トランクを展開するためにサポートされるトポロジ オプションの詳細については [、「Skype for Business Server](sip-trunking.md)での SIP トランキング」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0be3-106">To determine whether a SIP trunk is needed for a branch site, and for details about the supported topology options for deploying SIP trunks in branch sites, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="b0be3-107">ブランチ サイト SIP トランク要件例の分析</span><span class="sxs-lookup"><span data-stu-id="b0be3-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="b0be3-108">ブランチ サイトの SIP トランクを展開する場合は、サイト固有のコスト分析を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0be3-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="b0be3-109">たとえば、ワシントン州レドモンドに中央サイトを持ち、ニューヨークのブランチ サイトを持つ企業は分析を行い、ニューヨーク サイトからローカル サービス プロバイダーに SIP トランクを実装するかどうかを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0be3-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>
  
<span data-ttu-id="b0be3-110">ニューヨークでの分散型 SIP トランクの費用対効果が高いかどうかを判断するには、SIP トランクを使用する Direct Inward Dialing (DID) 番号を識別し、レドモンド (425) 以外の地域にニューヨークからかける電話の回数を分析します。</span><span class="sxs-lookup"><span data-stu-id="b0be3-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="b0be3-111">中央サイトのブランチ サイトに対して DID ターミネーションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="b0be3-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="b0be3-112">たとえば、Redmond 中央サイトはニューヨークのブランチ サイトの DID 番号をホストできます。</span><span class="sxs-lookup"><span data-stu-id="b0be3-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="b0be3-113">分散型 SIP トランクの実装コストがそれらの通話のコストより低い場合は、ニューヨークブランチ サイトで SIP トランクを実装する方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="b0be3-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span> 
  
## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="b0be3-114">その他のブランチ サイト SIP トランク要件</span><span class="sxs-lookup"><span data-stu-id="b0be3-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="b0be3-115">ゲートウェイではなく SIP トランクを展開する方法の選択は、各オプションの公衆交換電話網 (PSTN) 長距離有料料金の違いに基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="b0be3-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="b0be3-116">ブランチ サイトの SIP トランクを展開する場合は、回復性と帯域幅の要件も決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0be3-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="b0be3-117">ブランチ サイトと中央サイトの間のリンクが回復力があり、十分な帯域幅を持つ場合は、SIP トランクまたはゲートウェイを展開できます。</span><span class="sxs-lookup"><span data-stu-id="b0be3-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="b0be3-118">ブランチ サイトに存続可能ブランチ アプライアンスを展開する必要はない。</span><span class="sxs-lookup"><span data-stu-id="b0be3-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="b0be3-119">ブランチ サイトと中央サイトの間のリンクが回復力を持たない場合は、存続可能ブランチ アプライアンスを展開するか、ブランチ サイトでゲートウェイまたは SIP トランクを使用して存続可能ブランチ サーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="b0be3-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span> 
  

