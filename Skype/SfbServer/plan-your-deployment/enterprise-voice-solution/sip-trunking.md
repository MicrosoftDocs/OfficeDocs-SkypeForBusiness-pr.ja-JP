---
title: Skype for Business Server の SIP トランキング
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
description: Skype for Business Server Enterprise Voice での SIP トランキングについて
ms.openlocfilehash: 229774ef976a08031da7892dec0088d78b954b24
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802417"
---
# <a name="sip-trunking-in-skype-for-business-server"></a><span data-ttu-id="0b261-103">Skype for Business Server の SIP トランキング</span><span class="sxs-lookup"><span data-stu-id="0b261-103">SIP trunking in Skype for Business Server</span></span>

<span data-ttu-id="0b261-104">Skype for Business Server Enterprise Voice での SIP トランキングについて</span><span class="sxs-lookup"><span data-stu-id="0b261-104">Learn about SIP trunking in Skype for Business Server Enterprise Voice</span></span>

<span data-ttu-id="0b261-105">セッション開始プロトコル (SIP) は、基本的な電話サービスおよび追加のリアルタイム通信サービス (インスタント メッセージング、会議、プレゼンス検出、マルチメディアなど) のボイス オーバー IP (VoIP) 通信セッションを開始および管理するために使用します。</span><span class="sxs-lookup"><span data-stu-id="0b261-105">Session Initiation Protocol (SIP) is used to initiate and manage Voice over IP (VoIP) communications sessions for basic telephone service and for additional real-time communication services, such as instant messaging, conferencing, presence detection, and multimedia.</span></span> <span data-ttu-id="0b261-106">ここでは、ローカル ネットワークの境界を越えて広がる種類の SIP 接続である、SIP トランクを実装するための計画情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="0b261-106">This section provides planning information for implementing SIP trunks, a type of SIP connection that extends beyond the boundary of your local network.</span></span>

## <a name="what-is-sip-trunking"></a><span data-ttu-id="0b261-107">SIP トランクとは</span><span class="sxs-lookup"><span data-stu-id="0b261-107">What is SIP Trunking?</span></span>

<span data-ttu-id="0b261-108">SIP トランクは、組織とファイアウォールの外側のインターネット テレフォニー サービス プロバイダー (ITSP) との間に SIP 通信リンクを確立する SIP 接続です。</span><span class="sxs-lookup"><span data-stu-id="0b261-108">A SIP trunk is an IP connection that establishes a SIP communications link between your organization and an Internet telephony service provider (ITSP) beyond your firewall.</span></span> <span data-ttu-id="0b261-109">通常、SIP トランクは、組織のセントラルサイトを ITSP に接続するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0b261-109">Typically, a SIP trunk is used to connect your organization's central site to an ITSP.</span></span> <span data-ttu-id="0b261-110">ブランチ サイトを ITSP に接続するために SIP トランキングを使用する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="0b261-110">In some cases, you may also opt to use SIP trunking to connect your branch site to an ITSP.</span></span>

<span data-ttu-id="0b261-111">SIP トランクの展開は、組織の通信を簡素化するための大きな一歩であり、リアルタイム通信に対する最新の拡張機能の準備にもなります。</span><span class="sxs-lookup"><span data-stu-id="0b261-111">Deploying SIP trunking can be a big step toward simplifying your organization's telecommunications and preparing for up-to-date enhancements to real-time communications.</span></span> <span data-ttu-id="0b261-112">SIP トランキングの主な利点の1つは、(通常は、タイムディビジョン多重化 (TDM) トランクというように、組織の接続をセントラルサイトで中央のサイトで統合できることです。各ブランチサイトからの個別のトランクが必要です。</span><span class="sxs-lookup"><span data-stu-id="0b261-112">One of the primary advantages of SIP trunking is that you can consolidate your organization's connections to the public switched telephone network (PSTN) at a central site, as opposed to its predecessor, time division multiplexing (TDM) trunking, which typically requires a separate trunk from each branch site.</span></span>

### <a name="cost-savings"></a><span data-ttu-id="0b261-113">費用の削減</span><span class="sxs-lookup"><span data-stu-id="0b261-113">Cost Savings</span></span>

<span data-ttu-id="0b261-114">SIP トランキングに関連する費用の削減はかなりのものです。</span><span class="sxs-lookup"><span data-stu-id="0b261-114">The cost savings associated with SIP trunking can be substantial:</span></span>

- <span data-ttu-id="0b261-115">長距離通話は、SIP トランクを介した場合よりもかなり安くすみます。</span><span class="sxs-lookup"><span data-stu-id="0b261-115">Long distance calls typically cost much less through a SIP trunk.</span></span>

- <span data-ttu-id="0b261-116">管理コストを削減でき、展開を簡素化することが可能です。</span><span class="sxs-lookup"><span data-stu-id="0b261-116">You can cut manageability costs and reduce the complexity of deployment.</span></span>

- <span data-ttu-id="0b261-p104">SIP トランクを大幅な低コストで直接 ITSP に接続した場合、ベーシック レート インターフェイス (BRI) およびプライマリ レート インターフェイス (PRI) の料金をなくすことができます。TDM トランキングでは、サービス プロバイダーは分単位で通話に課金します。SIP トランキングの料金は帯域幅の使用量に基づくので、より少ない、より経済的な単位で購入できます (実際の料金は、使用する ITSP のサービス モデルによって異なります)。</span><span class="sxs-lookup"><span data-stu-id="0b261-p104">Basic rate interface (BRI) and primary rate interface (PRI) fees can be eliminated if you connect a SIP trunk directly to your ITSP at significantly lower cost. In TDM trunking, service providers charge for calls by the minute. The cost of SIP trunking may be based on bandwidth usage, which you can buy in smaller, more economical increments. (The actual cost depends on the service model of the ITSP you choose.)</span></span>

#### <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a><span data-ttu-id="0b261-121">SIP トランキング対 PSTN ゲートウェイまたは IP-PBX のホスト</span><span class="sxs-lookup"><span data-stu-id="0b261-121">SIP Trunking vs. Hosting a PSTN Gateway or IP-PBX</span></span>

<span data-ttu-id="0b261-p105">SIP トランクは直接サービス プロバイダーに接続されるため、PTSN ゲートウェイおよび管理費用を削除でき、接続が簡素化されます。SIP トランクを利用することでメンテナンス費用および管理費用を減らすことができ、相当な費用削減となります。</span><span class="sxs-lookup"><span data-stu-id="0b261-p105">Because SIP trunks connect directly to your service provider, you can eliminate your PSTN gateways and their management cost and complexity. Using a SIP trunk can lead to substantial cost savings through reduced maintenance and administration.</span></span>

### <a name="expanded-voip-services"></a><span data-ttu-id="0b261-124">VoIP サービスの拡張</span><span class="sxs-lookup"><span data-stu-id="0b261-124">Expanded VoIP Services</span></span>

<span data-ttu-id="0b261-125">多くの場合、音声機能が SIP トランキングを展開する主な動機ではありますが、音声サポートは最初のステップにすぎません。</span><span class="sxs-lookup"><span data-stu-id="0b261-125">Voice features are often the primary motivation for deploying SIP trunking, but voice support is just the first step.</span></span> <span data-ttu-id="0b261-126">SIP トランクを使用すると、VoIP 機能を拡張し、Skype for Business Server がより充実したサービスを提供できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0b261-126">With SIP trunking, you can extend VoIP capabilities and enable Skype for Business Server to deliver a richer set of services.</span></span> <span data-ttu-id="0b261-127">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0b261-127">For example:</span></span>

- <span data-ttu-id="0b261-128">Skype for Business Server を実行していないデバイスのプレゼンス検出機能が強化され、携帯電話との統合性が向上しました。ユーザーが携帯電話に通話を発信したときに表示されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="0b261-128">Enhanced presence detection for devices that are not running Skype for Business Server can provide better integration with mobile phones, enabling you to see when a user is on a mobile phone call.</span></span>

- <span data-ttu-id="0b261-129">E9-1 緊急通話では、911の通話に応答する機関が電話番号から発信者の所在地を特定できます。</span><span class="sxs-lookup"><span data-stu-id="0b261-129">E9-1-1 emergency calling enables the authorities who answer 911 calls to determine the caller's location from his or her telephone number.</span></span>

> [!NOTE]
> <span data-ttu-id="0b261-130">組織で利用できる、ITSP がサポートするサービスの内容については、ご利用の ITSP に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="0b261-130">Contact your ITSP for a list of services that they support and can enable for your organization.</span></span>

### <a name="sip-trunks-vs-direct-sip-connections"></a><span data-ttu-id="0b261-131">SIP トランクと直接 SIP 接続の比較</span><span class="sxs-lookup"><span data-stu-id="0b261-131">SIP Trunks vs. Direct SIP Connections</span></span>

<span data-ttu-id="0b261-132">トランクという用語は、回路交換技術を基盤としています。</span><span class="sxs-lookup"><span data-stu-id="0b261-132">The term trunk is derived from circuit-switched technology.</span></span> <span data-ttu-id="0b261-133">電話交換機器を接続する専用の物理回線を指します。</span><span class="sxs-lookup"><span data-stu-id="0b261-133">It refers to a dedicated physical line that connects telephone switching equipment.</span></span> <span data-ttu-id="0b261-134">その先行タスクと同様に、time ディビジョンマルチプレクシング (TDM) trunks、SIP trunks は、Skype for Business Server enterprise と ITSP という2つの別々の SIP ネットワーク間の接続です。</span><span class="sxs-lookup"><span data-stu-id="0b261-134">Like their predecessor, time division multiplexing (TDM) trunks, SIP trunks are connections between two separate SIP networks—the Skype for Business Server enterprise and the ITSP.</span></span> <span data-ttu-id="0b261-135">サーキットスイッチ trunks とは異なり、SIP trunks は、サポートされている SIP トランク接続タイプのいずれかで確立できる仮想接続です。</span><span class="sxs-lookup"><span data-stu-id="0b261-135">Unlike circuit-switched trunks, SIP trunks are virtual connections that can be established over any of the supported SIP trunking connection types.</span></span>

<span data-ttu-id="0b261-136">これに対し、直接 SIP 接続は、ローカル ネットワークの境界を越えない SIP 接続です (つまり、内部ネットワーク内の公衆交換電話網 (PSTN) ゲートウェイまたは構内交換機 (PBX) に接続します)。</span><span class="sxs-lookup"><span data-stu-id="0b261-136">Direct SIP connections, on the other hand, are SIP connections that do not cross the local network boundary (that is, they connect to a public switched telephone network (PSTN) gateway or private branch exchange (PBX) within your internal network).</span></span> <span data-ttu-id="0b261-137">Skype for Business Server での直接 SIP 接続の使用方法の詳細については、「 [skype For Business server での直接 sip 接続](direct-sip.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b261-137">For details about how you can use direct SIP connections with Skype for Business Server, see [Direct SIP connections in Skype for Business Server](direct-sip.md).</span></span>

## <a name="how-do-i-implement-sip-trunking"></a><span data-ttu-id="0b261-138">SIP トランキングの実装方法</span><span class="sxs-lookup"><span data-stu-id="0b261-138">How do I implement SIP Trunking?</span></span>

<span data-ttu-id="0b261-139">SIP トランクを実装するには、必要に応じて、Skype for Business Server クライアントとサービスプロバイダと transcodes メディア間の通信セッションのプロキシとして機能する仲介サーバー経由で接続をルーティングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b261-139">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Skype for Business Server clients and the service provider and transcodes media, when necessary.</span></span>

<span data-ttu-id="0b261-140">各仲介サーバーには、内部ネットワークインターフェイスと外部ネットワークインターフェイスがあります。</span><span class="sxs-lookup"><span data-stu-id="0b261-140">Each Mediation Server has an internal network interface and an external network interface.</span></span> <span data-ttu-id="0b261-141">内部インターフェイスは、フロントエンドサーバーに接続します。</span><span class="sxs-lookup"><span data-stu-id="0b261-141">The internal interface connects to the Front End Servers.</span></span> <span data-ttu-id="0b261-142">外部インターフェイスは、一般的に、仲介サーバーを公衆交換電話網 (PSTN) ゲートウェイまたは IP PBX に接続するために使用されていたため、ゲートウェイインターフェイスと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="0b261-142">The external interface is commonly called the gateway interface because it has traditionally been used to connect the Mediation Server to a public switched telephone network (PSTN) gateway or an IP-PBX.</span></span> <span data-ttu-id="0b261-143">SIP トランクを実装するには、仲介サーバーの外部インターフェイスを ITSP の外部エッジコンポーネントに接続します。</span><span class="sxs-lookup"><span data-stu-id="0b261-143">To implement a SIP trunk, you connect the external interface of the Mediation Server to the external edge component of the ITSP.</span></span> <span data-ttu-id="0b261-144">ITSP の外部エッジ コンポーネントとは、セッション ボーダー コントローラー (SBC)、ルーター、またはゲートウェイです。</span><span class="sxs-lookup"><span data-stu-id="0b261-144">The external edge component of the ITSP could be a Session Border Controller (SBC), a router, or a gateway.</span></span>

<span data-ttu-id="0b261-145">仲介サーバーの詳細については、「 [Skype For Business server の仲介サーバーコンポーネント](mediation-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b261-145">For details about Mediation Servers, see [Mediation Server component in Skype for Business Server](mediation-server.md).</span></span>

### <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="0b261-146">集中型と分散型 SIP トランキングの比較</span><span class="sxs-lookup"><span data-stu-id="0b261-146">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="0b261-147">一元管理された SIP トランキングは、ブランチサイトトラフィックを含むすべての VoIP トラフィックをセントラルサイト経由でルーティングします。</span><span class="sxs-lookup"><span data-stu-id="0b261-147">Centralized SIP trunking routes all VoIP traffic, including branch site traffic, through your central site.</span></span> <span data-ttu-id="0b261-148">一元展開モデルはシンプルでコスト効率が高いため、通常は、Skype for Business Server と SIP trunks を実装するために推奨されるアプローチです。</span><span class="sxs-lookup"><span data-stu-id="0b261-148">The centralized deployment model is simple, cost-effective, and is generally the recommended approach for implementing SIP trunks with Skype for Business Server.</span></span>

<span data-ttu-id="0b261-149">分散 SIP トランクは、1つ以上のブランチサイトにローカル SIP trunks を実装する展開モデルです。</span><span class="sxs-lookup"><span data-stu-id="0b261-149">Distributed SIP trunking is a deployment model in which you implement local SIP trunks at one or more branch sites.</span></span> <span data-ttu-id="0b261-150">VoIP トラフィックは、セントラルサイトを経由せずに、ブランチサイトから直接サービスプロバイダにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="0b261-150">VoIP traffic is then routed from the branch site directly to a service provider without going through the central site.</span></span>

<span data-ttu-id="0b261-151">分散型 SIP トランキングが必要なのは、次のケースだけです。</span><span class="sxs-lookup"><span data-stu-id="0b261-151">Distributed SIP trunking is required only in the following cases:</span></span>

- <span data-ttu-id="0b261-152">ブランチサイトには、survivable の電話接続 (WAN がダウンした場合など) が必要です。</span><span class="sxs-lookup"><span data-stu-id="0b261-152">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="0b261-153">この要件は、ブランチサイトごとに分析する必要があります。一部の支店では、冗長性とフェールオーバーが必要となる場合がありますが、そうでない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="0b261-153">This requirement should be analyzed for each branch site; some of your branches may require redundancy and failover, whereas others may not.</span></span>

- <span data-ttu-id="0b261-154">2つのセントラルサイト間の回復性が必要です。</span><span class="sxs-lookup"><span data-stu-id="0b261-154">Resiliency is required between two central sites.</span></span> <span data-ttu-id="0b261-155">SIP トランクが各セントラルサイトで終了するようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b261-155">You need to make sure that a SIP trunk terminates at each central site.</span></span> <span data-ttu-id="0b261-156">たとえば、ダブリンと Tuがセントラルサイトを持っていて、どちらも1つのサイトの SIP トランクのみを使用している場合、その他のサイトのユーザーは PSTN 通話を行うことができません。</span><span class="sxs-lookup"><span data-stu-id="0b261-156">For example, if you have Dublin and Tukwila central sites and both use only one site's SIP trunk, if the trunk goes down, the other site's users cannot make PSTN calls.</span></span>

- <span data-ttu-id="0b261-157">ブランチサイトとセントラルサイトは、国/地域によって異なります。</span><span class="sxs-lookup"><span data-stu-id="0b261-157">The branch site and central site are in different countries/regions.</span></span> <span data-ttu-id="0b261-158">互換性と法律上の理由により、国/地域ごとに少なくとも 1 つの SIP トランクが必要です。</span><span class="sxs-lookup"><span data-stu-id="0b261-158">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span> <span data-ttu-id="0b261-159">たとえば EU では、通信は現地の中央ポイントで終了することなしに国/地域外に出ることはできません。</span><span class="sxs-lookup"><span data-stu-id="0b261-159">For example, in the European Union, communications cannot leave a country/region without terminating locally at a centralized point.</span></span>

<span data-ttu-id="0b261-160">サイトの地理的な場所や企業内で予想されるトラフィックの量によっては、すべてのユーザーを中央 SIP トランク経由でルーティングすることはできません。また、一部のユーザーをブランチサイトの SIP トランク経由でルーティングすることを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="0b261-160">Depending on the geographical location of sites and how much traffic you anticipate within your enterprise, you may not want to route all users through the central SIP trunk, or you may opt to route some users through a SIP trunk at their branch site.</span></span> <span data-ttu-id="0b261-161">必要性を分析するために、次の質問に回答してください。</span><span class="sxs-lookup"><span data-stu-id="0b261-161">To analyze your needs, answer the following questions:</span></span>

- <span data-ttu-id="0b261-162">各サイトの規模はどのくらいですか (つまり、エンタープライズ Voip に対して有効になっているユーザー数)?</span><span class="sxs-lookup"><span data-stu-id="0b261-162">How big is each site (that is, how many users are enabled for Enterprise Voice)?</span></span>

- <span data-ttu-id="0b261-163">各サイトで最も通話を受ける Direct Inward Dialing (DID) 番号はどれですか。</span><span class="sxs-lookup"><span data-stu-id="0b261-163">Which direct inward dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="0b261-164">集中型 SIP トランキングと分散型 SIP トランキングのどちらを展開するかを決定するには、費用便益分析が必要です。</span><span class="sxs-lookup"><span data-stu-id="0b261-164">The decision whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="0b261-165">必要のない場合にも分散型展開モデルを選択した方が有益な場合があります。</span><span class="sxs-lookup"><span data-stu-id="0b261-165">In some cases, it may be advantageous to opt for the distributed deployment model even if it is not required.</span></span> <span data-ttu-id="0b261-166">完全に一元管理された展開では、すべてのブランチサイトトラフィックが WAN リンクを介してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="0b261-166">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="0b261-167">WAN リンクに必要な帯域幅に費用をかけるより、分散型 SIP トランキングを使用したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="0b261-167">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span> <span data-ttu-id="0b261-168">たとえば、セントラルサイトとフェデレーションされているブランチサイトに Standard Edition サーバーを展開することもできます。または、小型のゲートウェイを使用して Survivable Branch Appliance または Survivable Branch Server を展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="0b261-168">For example, you may want to deploy a Standard Edition server at a branch site with federation to the central site, or you may want to deploy a Survivable Branch Appliance or a Survivable Branch Server with a small gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="0b261-169">分散 SIP トランクの詳細については、「 [Skype For Business Server のブランチサイト SIP トランク](branch-site.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b261-169">For details about distributed SIP trunking, see [Branch site SIP trunking in Skype for Business Server](branch-site.md).</span></span>

### <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="0b261-170">サポートされている SIP トランキング接続の種類</span><span class="sxs-lookup"><span data-stu-id="0b261-170">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="0b261-171">Skype for Business Server は、SIP トランクで次の接続の種類をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0b261-171">Skype for Business Server supports the following connection types for SIP trunking:</span></span>

- <span data-ttu-id="0b261-172">Multiprotocol Label Switching (MPLS) は、ネットワーク ノード間でデータを伝送するプライベート ネットワークです。</span><span class="sxs-lookup"><span data-stu-id="0b261-172">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next.</span></span> <span data-ttu-id="0b261-173">MPLS ネットワークの帯域幅は、他のサブスクライバーと共有され、各データパケットには別のサブスクライバーのデータを区別するためのラベルが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0b261-173">The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber's data from another's.</span></span> <span data-ttu-id="0b261-174">この接続の種類に仮想プライベート ネットワーク (VPN) は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="0b261-174">This connection type does not require a virtual private network (VPN).</span></span> <span data-ttu-id="0b261-175">潜在的な欠点は、VoIP トラフィックに優先度を与えないと、過剰な IP トラフィックが VoIP の処理に干渉する可能性があることです。</span><span class="sxs-lookup"><span data-stu-id="0b261-175">A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

- <span data-ttu-id="0b261-p118">他のトラフィックを使用しないプライベート接続 (専用の光ファイバー接続、T1 回線など) は、通常、最も信頼できるセキュリティで保護された接続の種類です。 この接続の種類には、最高の通話伝送能力がありますが、通常最も費用がかかります。VPN は必要ありません。プライベート接続は、通話件数が多いか、セキュリティと可用性の要件が厳しい組織に適しています。</span><span class="sxs-lookup"><span data-stu-id="0b261-p118">A private connection with no other traffic—for example, a leased fiber-optic connection or T1 line—is typically the most reliable and secure connection type. This connection type provides the highest call-carrying capacity, but it is typically the most expensive. VPN is not required. Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

- <span data-ttu-id="0b261-180">インターネットは、最も費用のかからない接続の種類ですが、最も信頼性が低くなります。</span><span class="sxs-lookup"><span data-stu-id="0b261-180">The Internet is the least expensive connection type, but it is also the least reliable.</span></span> <span data-ttu-id="0b261-181">インターネット接続は、VPN を必要とする唯一の Skype for Business Server SIP トランク接続の種類です。</span><span class="sxs-lookup"><span data-stu-id="0b261-181">Internet connection is the only Skype for Business Server SIP trunking connection type that requires VPN.</span></span>

#### <a name="selecting-a-connection-type"></a><span data-ttu-id="0b261-182">接続の種類の選択</span><span class="sxs-lookup"><span data-stu-id="0b261-182">Selecting a Connection Type</span></span>

<span data-ttu-id="0b261-183">企業に最適な SIP トランキング接続の種類は、ニーズと予算によって異なります。</span><span class="sxs-lookup"><span data-stu-id="0b261-183">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

- <span data-ttu-id="0b261-p120">中規模または比較的大規模な企業では、通常、MPLS ネットワークが最も費用対効果が高くなります。専用のプライベート ネットワークに比べて、必要な帯域幅が安価に提供されます。</span><span class="sxs-lookup"><span data-stu-id="0b261-p120">For a mid-size or larger enterprise, an MPLS network usually provides the greatest value. It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

- <span data-ttu-id="0b261-186">大規模な企業には、プライベートな光ファイバー接続、T1、T3、またはそれ以上の接続が必要なことがあります (EU では E1、E3、またはそれ以上の接続)。</span><span class="sxs-lookup"><span data-stu-id="0b261-186">Large enterprises may require a private fiber-optic, T1, T3 or higher connection (E1, E3 or higher in the European Union).</span></span>

- <span data-ttu-id="0b261-187">通話音量が低い小規模企業または支店の場合、インターネットを介した SIP トランクが最適な選択肢となることがあります。</span><span class="sxs-lookup"><span data-stu-id="0b261-187">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="0b261-188">この接続の種類は、中規模サイズあるいは比較的大規模なサイトには推奨されません。</span><span class="sxs-lookup"><span data-stu-id="0b261-188">This connection type is not recommended for mid-size or larger sites.</span></span>

### <a name="bandwidth-requirements"></a><span data-ttu-id="0b261-189">帯域幅要件</span><span class="sxs-lookup"><span data-stu-id="0b261-189">Bandwidth Requirements</span></span>

<span data-ttu-id="0b261-p122">実装に必要となる帯域幅は、通話処理能力 (サポートされなければならない同時通話の数) によって異なります。代金を支払っている最大処理能力をできるだけ活用できるよう、使用可能な帯域幅を考慮に入れる必要があります。SIP トランクの最大帯域幅要件を計算するには次の式を使用してください。</span><span class="sxs-lookup"><span data-stu-id="0b261-p122">The amount of bandwidth your implementation requires depends on call capacity (the number of concurrent calls you must be able to support). You need to consider bandwidth availability, so that you can take full advantage of the peak capacity that you have paid for. Use the following formula to calculate SIP trunk peak bandwidth requirement:</span></span>

<span data-ttu-id="0b261-193">SIP トランク最大帯域幅 = 最大同時通話数 x (64 kbps + ヘッダー サイズ)</span><span class="sxs-lookup"><span data-stu-id="0b261-193">SIP Trunk Peak Bandwidth = Max Simultaneous Calls x (64 kbps + header size)</span></span>

> [!NOTE]
> <span data-ttu-id="0b261-194">ヘッダー サイズは最大で 20 バイトです。</span><span class="sxs-lookup"><span data-stu-id="0b261-194">Header size is 20 bytes maximum.</span></span>

### <a name="codec-support"></a><span data-ttu-id="0b261-195">コーデックのサポート</span><span class="sxs-lookup"><span data-stu-id="0b261-195">Codec Support</span></span>

<span data-ttu-id="0b261-196">Skype for Business Server は、次のコーデックのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0b261-196">Skype for Business Server supports only the following codecs:</span></span>

- <span data-ttu-id="0b261-197">G.711 A-Law (主に北米以外で使用)</span><span class="sxs-lookup"><span data-stu-id="0b261-197">G.711 a-law (used primarily outside North America)</span></span>

- <span data-ttu-id="0b261-198">G.711 μ-Law (北米で使用)</span><span class="sxs-lookup"><span data-stu-id="0b261-198">G.711 µ-law (used in North America)</span></span>

### <a name="internet-telephony-service-provider"></a><span data-ttu-id="0b261-199">インターネット テレフォニー サービス プロバイダー</span><span class="sxs-lookup"><span data-stu-id="0b261-199">Internet Telephony Service Provider</span></span>

<span data-ttu-id="0b261-200">SIP トランク接続のサービス プロバイダー側の実装方法は、ITSP 間で異なります。</span><span class="sxs-lookup"><span data-stu-id="0b261-200">How you implement the service provider side of a SIP trunk connection varies from one ITSP to another.</span></span> <span data-ttu-id="0b261-201">展開の情報については、サービス プロバイダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="0b261-201">For deployment information, contact your service provider.</span></span> <span data-ttu-id="0b261-202">認定された SIP トランクサービスプロバイダのリストについては、「 [Microsoft ユニファイドコミュニケーションでオープンな相互運用性プログラム web サイト](https://go.microsoft.com/fwlink/p/?LinkId=287029)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0b261-202">For a list of certified SIP trunking service providers, see [Microsoft Unified Communications Open Interoperability Program website](https://go.microsoft.com/fwlink/p/?LinkId=287029).</span></span>

<span data-ttu-id="0b261-203">Microsoft 認定 SIP トランキング プロバイダーの詳細については、Microsoft 担当者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="0b261-203">For details about Microsoft certified SIP trunking providers, contact your Microsoft representative.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0b261-p124">SIP トランクを通過するすべての機能を ITSP が確実にサポートするためには、Microsoft 認定のサービス プロバイダーを利用する必要があります (セッションのセットアップおよび管理、拡張 VoIP サービスの全機能のサポートなど)。Microsoft テクニカル サポートは、認定されていないプロバイダーを使用する構成には適用されません。現在、SIP トランキングに認定されていないインターネット サービス プロバイダーを使用している場合は、そのプロバイダーを ISP として使用し続け、SIP トランキングには Microsoft 認定プロバイダーを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="0b261-p124">You must use a Microsoft certified service provider to ensure that your ITSP supports all of the functionality that traverses the SIP trunk (for example, setting up and managing sessions and supporting all of the extended VoIP services). Microsoft technical support does not extend to configurations that use noncertified providers. If you currently use an Internet service provider that is not certified for SIP trunking, you can opt to continue using that provider as your ISP and use a provider certified by Microsoft for SIP trunking.</span></span>

### <a name="topologies-and-components-for-sip-trunking"></a><span data-ttu-id="0b261-207">SIP トランキングのトポロジおよびコンポーネント</span><span class="sxs-lookup"><span data-stu-id="0b261-207">Topologies and Components for SIP Trunking</span></span>

<span data-ttu-id="0b261-208">次の図は、Skype for Business Server の SIP トランキングトポロジを示しています。</span><span class="sxs-lookup"><span data-stu-id="0b261-208">The following figure depicts the SIP trunking topology in Skype for Business Server.</span></span>

<span data-ttu-id="0b261-209">**SIP トランキングトポロジ**</span><span class="sxs-lookup"><span data-stu-id="0b261-209">**SIP trunking topology**</span></span>

![SIP トランキングのトポロジ](../../media/669fb55d-7c81-4e21-9421-fabc43d6e064.jpg)

<span data-ttu-id="0b261-p125">図に示すように、エンタープライズ ネットワークと公衆交換電話網 (PSTN) サービス プロバイダーの間の接続には、IP 仮想プライベート ネットワーク (VPN) が使用されます。このプライベート ネットワークの目的は、IP 接続を提供し、セキュリティを強化し、(必要に応じて) サービス品質 (QoS) 保証を得ることです。VPN の性質により、SIP 信号トラフィックにトランスポート層セキュリティ (TLS) を使用したり、メディア トラフィックにセキュア リアルタイム転送プロトコル (SRTP) を使用したりする必要はありません。このため、企業とサービス プロバイダーの間の接続は、IP VPN を通じてトンネリングされる可能性のある SIP 用の普通の TCP 接続と、メディア用の普通のリアルタイム転送プロトコル (RTP) (over UDP) で構成されます。VPM ルーター間のすべてのファイアウォールのポートが開いていて VPN ルーターが通信できること、および VPN ルーターの外部エッジの IP アドレスがパブリック ルーティング可能であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0b261-p125">As shown in the diagram, an IP virtual private network (VPN) is used for connectivity between the enterprise network and the public switched telephone network (PSTN) service provider. The purpose of this private network is to provide IP connectivity, enhance security, and (optionally) obtain Quality of Service (QoS) guarantees. Because of the nature of a VPN, you do not need to use Transport Layer Security (TLS) for SIP signaling traffic or secure real-time transport protocol (SRTP) for the media traffic. Connections between the enterprise and the service provider therefore consist of plain TCP connections for SIP and plain real-time transport protocol (RTP) (over UDP) for media tunneled through an IP VPN. Ensure that all firewalls between the VPN routers have ports open to allow the VPN routers to communicate, and that the IP addresses on the external edges of the VPN routers are publicly routable.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0b261-216">フェールオーバーを含め、高可用性のサポートを提供しているかどうかを確認するには、サービス プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="0b261-216">Contact your service provider to determine whether it provides support for high availability, including failover.</span></span> <span data-ttu-id="0b261-217">サポートしている場合、高可用性を設定する手順を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b261-217">If so, you will need to determine the procedures for setting it up.</span></span> <span data-ttu-id="0b261-218">たとえば、各仲介サーバーに1つの IP アドレスと1つの SIP トランクのみを構成する必要がある場合、または各仲介サーバーに複数の SIP trunks を構成する必要がある場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0b261-218">For example, do you need to configure only one IP address and one SIP trunk on each Mediation Server, or do you need to configure multiple SIP trunks on each Mediation Server?</span></span> <span data-ttu-id="0b261-219">> 複数のセントラルサイトがある場合は、別のセントラルサイトとの間の接続を可能にする機能がサービスプロバイダーにあるかどうかも確認します。</span><span class="sxs-lookup"><span data-stu-id="0b261-219">> If you have multiple central sites, also ask whether the service provider has the ability to enable connections to and from another central site.</span></span>

> [!NOTE]
> <span data-ttu-id="0b261-220">SIP トランクの場合は、スタンドアロンの仲介サーバーを展開することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0b261-220">For SIP trunking, we strongly recommend that you deploy stand-alone Mediation Servers.</span></span> <span data-ttu-id="0b261-221">詳細については、「展開」のドキュメントの「[Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b261-221">For details, see [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx) in the Deployment documentation.</span></span>

### <a name="securing-the-mediation-server-for-sip-trunking"></a><span data-ttu-id="0b261-222">SIP トランキングを行うための仲介サーバーのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="0b261-222">Securing the Mediation Server for SIP Trunking</span></span>

<span data-ttu-id="0b261-p128">セキュリティ上の理由から、2 つの VPN ルーター間の各接続に仮想 LAN (VLAN) を設定する必要があります。VLAN の実際の設定プロセスは、ルーターの製造元によって異なります。詳細については、ルーター ベンダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="0b261-p128">For security purposes, you should set up a virtual LAN (VLAN) for each connection between the two VPN routers. The actual process for setting up a VLAN varies from one router manufacturer to another. For details, contact your router vendor.</span></span>

<span data-ttu-id="0b261-226">次のガイドラインに従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0b261-226">We recommend that you follow these guidelines:</span></span>

- <span data-ttu-id="0b261-227">仲介サーバーと境界ネットワーク内の VPN ルーターの間に仮想 LAN (VLAN) を設定します (DMZ、非武装地帯、スクリーンサブネットとも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="0b261-227">Set up a virtual LAN (VLAN) between the Mediation Server and the VPN router in the perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span>

- <span data-ttu-id="0b261-228">ルーターから VLAN へのブロードキャストまたはマルチキャスト パケットの転送は許可しません。</span><span class="sxs-lookup"><span data-stu-id="0b261-228">Do not allow broadcast or multicast packets to be transferred from the router to the VLAN.</span></span>

- <span data-ttu-id="0b261-229">ルーターからのトラフィックを仲介サーバー以外の場所にルーティングするルーティングルールはブロックします。</span><span class="sxs-lookup"><span data-stu-id="0b261-229">Block any routing rules that route traffic from the router to anywhere but the Mediation Server.</span></span>

<span data-ttu-id="0b261-230">VPN サーバーを使用する場合、次のガイドラインに従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0b261-230">If you use a VPN server, we recommend that you follow these guidelines:</span></span>

- <span data-ttu-id="0b261-231">VPN サーバーと仲介サーバーの間に VLAN をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="0b261-231">Set up a VLAN between the VPN server and the Mediation Server.</span></span>

- <span data-ttu-id="0b261-232">VPN サーバーから VLAN へのブロードキャストまたはマルチキャスト パケットの転送は許可しません。</span><span class="sxs-lookup"><span data-stu-id="0b261-232">Do not allow broadcast or multicast packets to be transmitted from the VPN server to the VLAN.</span></span>

- <span data-ttu-id="0b261-233">VPN サーバートラフィックを仲介サーバー以外の場所にルーティングするルーティングルールをブロックします。</span><span class="sxs-lookup"><span data-stu-id="0b261-233">Block any routing rule that routes VPN server traffic to anywhere but the Mediation Server.</span></span>

- <span data-ttu-id="0b261-234">Generic Routing Encapsulation (GRE) を使用して VPN 上のデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="0b261-234">Encrypt data on the VPN by using generic routing encapsulation (GRE).</span></span>

## <a name="see-also"></a><span data-ttu-id="0b261-235">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b261-235">See also</span></span>

[<span data-ttu-id="0b261-236">Skype for Business Server のブランチサイト SIP トランク</span><span class="sxs-lookup"><span data-stu-id="0b261-236">Branch site SIP trunking in Skype for Business Server</span></span>](branch-site.md)

