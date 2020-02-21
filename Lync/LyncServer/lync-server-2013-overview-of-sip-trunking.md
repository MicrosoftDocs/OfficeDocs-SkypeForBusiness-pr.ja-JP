---
title: 'Lync Server 2013: SIP トランキングの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of SIP trunking
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398285(v=OCS.15)
ms:contentKeyID: 48183601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e71a1f02fda14c2bcbb54aaec5e12307421090e4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="d69fc-102">Lync Server 2013 の SIP トランキングの概要</span><span class="sxs-lookup"><span data-stu-id="d69fc-102">Overview of SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d69fc-103">_**トピックの最終更新日:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="d69fc-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="d69fc-p101">SIP トランキングを展開することは、組織の通信方式を簡素化し、リアルタイム通信への最新の機能強化に備えるための大きなステップとなります。SIP トランキングの主な利点の 1 つは、一般に各ブランチ サイトからの個別のトランクを必要とする従来の時分割多重 (TDM) トランキングと異なり、組織の接続をセントラル サイトの公衆交換電話網 (PSTN) に集約できることです。</span><span class="sxs-lookup"><span data-stu-id="d69fc-p101">Deploying SIP trunking can be a big step toward simplifying your organization’s telecommunications and preparing for up-to-date enhancements to real-time communications. One of the primary advantages of SIP trunking is that you can consolidate your organization’s connections to the public switched telephone network (PSTN) at a central site, as opposed to its predecessor, time division multiplexing (TDM) trunking, which typically requires a separate trunk from each branch site.</span></span>

<div>

## <a name="sip-trunking-in-lync-server"></a><span data-ttu-id="d69fc-106">Lync Server の SIP トランキング</span><span class="sxs-lookup"><span data-stu-id="d69fc-106">SIP Trunking in Lync Server</span></span>

<span data-ttu-id="d69fc-107">Lync Server 2013 SIP トランキング機能により、次のことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="d69fc-107">The Lync Server 2013 SIP trunking capabilities enable the following:</span></span>

  - <span data-ttu-id="d69fc-108">エンタープライズ ユーザーは企業のファイアウォールの内側と外側のどちらにいても、E.164 準拠の番号で指定される市内通話や長距離通話を発信できます。この通話は、対応するサービス プロバイダーのサービスとして PSTN 上で終端されます。</span><span class="sxs-lookup"><span data-stu-id="d69fc-108">An enterprise user, whether inside or outside the corporate firewall, can make a local call or a long-distance call that is specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>

  - <span data-ttu-id="d69fc-109">PSTN サブスクライバーはだれでも、エンタープライズ ユーザーに関連付けられた Direct Inward Dialing (DID) 番号をダイヤルして、企業のファイアウォールの内側または外側にいるエンタープライズ ユーザーに連絡することができます。</span><span class="sxs-lookup"><span data-stu-id="d69fc-109">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number that is associated with that enterprise user.</span></span>

</div>

<div>

## <a name="cost-savings"></a><span data-ttu-id="d69fc-110">費用の削減</span><span class="sxs-lookup"><span data-stu-id="d69fc-110">Cost Savings</span></span>

<span data-ttu-id="d69fc-111">SIP トランキングに関連する費用の削減はかなりのものです。</span><span class="sxs-lookup"><span data-stu-id="d69fc-111">The cost savings associated with SIP trunking can be substantial:</span></span>

  - <span data-ttu-id="d69fc-112">長距離通話は、SIP トランクを介した場合よりもかなり安くすみます。</span><span class="sxs-lookup"><span data-stu-id="d69fc-112">Long distance calls typically cost much less through a SIP trunk.</span></span>

  - <span data-ttu-id="d69fc-113">管理コストを削減でき、展開を簡素化することが可能です。</span><span class="sxs-lookup"><span data-stu-id="d69fc-113">You can cut manageability costs and reduce the complexity of deployment.</span></span>

  - <span data-ttu-id="d69fc-p102">SIP トランクを大幅な低コストで直接 ITSP に接続した場合、ベーシック レート インターフェイス (BRI) およびプライマリ レート インターフェイス (PRI) の料金をなくすことができます。TDM トランキングでは、サービス プロバイダーは分単位で通話に課金します。SIP トランキングの料金は帯域幅の使用量に基づくので、より少ない、より経済的な単位で購入できます (実際の料金は、使用する ITSP のサービス モデルによって異なります)。</span><span class="sxs-lookup"><span data-stu-id="d69fc-p102">Basic rate interface (BRI) and primary rate interface (PRI) fees can be eliminated if you connect a SIP trunk directly to your ITSP at significantly lower cost. In TDM trunking, service providers charge for calls by the minute. The cost of SIP trunking may be based on bandwidth usage, which you can buy in smaller, more economical increments. (The actual cost depends on the service model of the ITSP you choose.)</span></span>

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a><span data-ttu-id="d69fc-118">SIP トランキング対 PSTN ゲートウェイまたは IP-PBX のホスト</span><span class="sxs-lookup"><span data-stu-id="d69fc-118">SIP Trunking vs. Hosting a PSTN Gateway or IP-PBX</span></span>

<span data-ttu-id="d69fc-p103">SIP トランクは直接サービス プロバイダーに接続されるため、PTSN ゲートウェイおよび管理費用を削除でき、接続が簡素化されます。SIP トランクを利用することでメンテナンス費用および管理費用を減らすことができ、相当な費用削減となります。</span><span class="sxs-lookup"><span data-stu-id="d69fc-p103">Because SIP trunks connect directly to your service provider, you can eliminate your PSTN gateways and their management cost and complexity. Using a SIP trunk can lead to substantial cost savings through reduced maintenance and administration.</span></span>

</div>

</div>

<div>

## <a name="expanded-voip-services"></a><span data-ttu-id="d69fc-121">VoIP サービスの拡張</span><span class="sxs-lookup"><span data-stu-id="d69fc-121">Expanded VoIP Services</span></span>

<span data-ttu-id="d69fc-122">多くの場合、音声機能が SIP トランキングを展開する主な動機ではありますが、音声サポートは最初のステップにすぎません。</span><span class="sxs-lookup"><span data-stu-id="d69fc-122">Voice features are often the primary motivation for deploying SIP trunking, but voice support is just the first step.</span></span> <span data-ttu-id="d69fc-123">SIP トランキングを使用すると、VoIP 機能を拡張し、Lync Server 2013 を有効にして、より豊富なサービスセットを提供できます。</span><span class="sxs-lookup"><span data-stu-id="d69fc-123">With SIP trunking, you can extend VoIP capabilities and enable Lync Server 2013 to deliver a richer set of services.</span></span> <span data-ttu-id="d69fc-124">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d69fc-124">For example:</span></span>

  - <span data-ttu-id="d69fc-125">Lync Server 2013 を実行していないデバイスの拡張プレゼンス検出を使用すると、携帯電話との統合が向上し、ユーザーが携帯電話で通話しているときに表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="d69fc-125">Enhanced presence detection for devices that are not running Lync Server 2013 can provide better integration with mobile phones, enabling you to see when a user is on a mobile phone call.</span></span>

  - <span data-ttu-id="d69fc-126">E9-1-1 緊急通話の場合、911 番の電話に出た当局者が、かかってきた電話番号から、その電話をかけた人物の場所を特定することが可能です。</span><span class="sxs-lookup"><span data-stu-id="d69fc-126">E9-1-1 emergency calling enables the authorities who answer 911 calls to determine the caller’s location from his or her telephone number.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d69fc-127">組織で利用できる、ITSP がサポートするサービスの内容については、ご利用の ITSP に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="d69fc-127">Contact your ITSP for a list of services that they support and can enable for your organization.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

