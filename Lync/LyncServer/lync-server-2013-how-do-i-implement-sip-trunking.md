---
title: 'Lync Server 2013: SIP トランキングの実装方法'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How do I implement SIP trunking?
ms:assetid: 273a22b1-8a4c-4187-acf8-c57d5c6598ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425743(v=OCS.15)
ms:contentKeyID: 48183666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ecd89ce28f1565e44c92ba543ccf992bb2a3c811
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504144"
---
# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="be0d7-102">Lync Server 2013 で SIP トランキングを実装するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="be0d7-102">How do I implement SIP trunking in Lync Server 2013?</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be0d7-103">_**トピックの最終更新日:** 2013-03-18_</span><span class="sxs-lookup"><span data-stu-id="be0d7-103">_**Topic Last Modified:** 2013-03-18_</span></span>

<span data-ttu-id="be0d7-104">SIP トランキングを実装するには、必要に応じて、Lync Server 2013 クライアントとサービスプロバイダーとコード変換メディア間の通信セッションのプロキシとして機能する仲介サーバーを経由して接続をルーティングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="be0d7-104">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider and transcodes media, when necessary.</span></span>

<span data-ttu-id="be0d7-105">各仲介サーバーには、内部ネットワークインターフェイスと外部ネットワークインターフェイスがあります。</span><span class="sxs-lookup"><span data-stu-id="be0d7-105">Each Mediation Server has an internal network interface and an external network interface.</span></span> <span data-ttu-id="be0d7-106">内部インターフェイスはフロントエンドサーバーに接続します。</span><span class="sxs-lookup"><span data-stu-id="be0d7-106">The internal interface connects to the Front End Servers.</span></span> <span data-ttu-id="be0d7-107">一般に、外部インターフェイスは、仲介サーバーを公衆交換電話網 (PSTN) ゲートウェイまたは ip-pbx に接続するために使用されていたため、ゲートウェイインターフェイスと呼ばれていました。</span><span class="sxs-lookup"><span data-stu-id="be0d7-107">The external interface is commonly called the gateway interface because it has traditionally been used to connect the Mediation Server to a public switched telephone network (PSTN) gateway or an IP-PBX.</span></span> <span data-ttu-id="be0d7-108">SIP トランクを実装するには、仲介サーバーの外部インターフェイスを ITSP の外部エッジコンポーネントに接続します。</span><span class="sxs-lookup"><span data-stu-id="be0d7-108">To implement a SIP trunk, you connect the external interface of the Mediation Server to the external edge component of the ITSP.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="be0d7-109">ITSP の外部エッジ コンポーネントとは、セッション ボーダー コントローラー (SBC)、ルーター、またはゲートウェイです。</span><span class="sxs-lookup"><span data-stu-id="be0d7-109">The external edge component of the ITSP could be a Session Border Controller (SBC), a router, or a gateway.</span></span>



</div>

<span data-ttu-id="be0d7-110">仲介サーバーの詳細については、「 [Lync server 2013 の仲介サーバーコンポーネント](lync-server-2013-mediation-server-component.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be0d7-110">For details about Mediation Servers, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md).</span></span>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="be0d7-111">集中型と分散型 SIP トランキングの比較</span><span class="sxs-lookup"><span data-stu-id="be0d7-111">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="be0d7-112">*一元* SIP トランキングは、ブランチサイトトラフィックを含むすべてのボイスオーバーインターネットプロトコル (VoIP) トラフィックを中央サイト経由でルーティングします。</span><span class="sxs-lookup"><span data-stu-id="be0d7-112">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your central site.</span></span> <span data-ttu-id="be0d7-113">一元展開モデルはシンプルで費用対効果があり、通常は、Lync Server 2013 を使用して SIP トランクを実装するために推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="be0d7-113">The centralized deployment model is simple, cost-effective, and is generally the recommended approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="be0d7-114">*Distributed* SIP トランキングは、1つ以上のブランチサイトにローカル SIP トランクを実装する展開モデルです。</span><span class="sxs-lookup"><span data-stu-id="be0d7-114">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites.</span></span> <span data-ttu-id="be0d7-115">その後、VoIP トラフィックは、中央サイトを経由することなく、ブランチサイトから直接サービスプロバイダーにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="be0d7-115">VoIP traffic is then routed from the branch site directly to a service provider without going through the central site.</span></span>

<span data-ttu-id="be0d7-116">分散型 SIP トランキングが必要なのは、次のケースだけです。</span><span class="sxs-lookup"><span data-stu-id="be0d7-116">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="be0d7-117">ブランチ サイトに存続可能な通話接続が必要な場合 (WAN がダウンした場合など)。</span><span class="sxs-lookup"><span data-stu-id="be0d7-117">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="be0d7-118">この要件は、ブランチサイトごとに分析する必要があります。ブランチの中には、冗長性とフェールオーバーを必要とするものもあれば、できないものもあります。</span><span class="sxs-lookup"><span data-stu-id="be0d7-118">This requirement should be analyzed for each branch site; some of your branches may require redundancy and failover, whereas others may not.</span></span>

  - <span data-ttu-id="be0d7-119">2つの中央サイト間で復元が必要です。</span><span class="sxs-lookup"><span data-stu-id="be0d7-119">Resiliency is required between two central sites.</span></span> <span data-ttu-id="be0d7-120">SIP トランクが各中央サイトで終了するようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="be0d7-120">You need to make sure that a SIP trunk terminates at each central site.</span></span> <span data-ttu-id="be0d7-121">たとえば、1つの中央サイトを使用していて、両方のサイトの SIP トランクのみを使用している場合、トランクが停止した場合、他のサイトのユーザーは PSTN 通話を行うことができません。</span><span class="sxs-lookup"><span data-stu-id="be0d7-121">For example, if you have Dublin and Tukwila central sites and both use only one site’s SIP trunk, if the trunk goes down, the other site’s users cannot make PSTN calls.</span></span>

  - <span data-ttu-id="be0d7-122">ブランチサイトと中央サイトが異なる国/地域にある。</span><span class="sxs-lookup"><span data-stu-id="be0d7-122">The branch site and central site are in different countries/regions.</span></span> <span data-ttu-id="be0d7-123">互換性と法律上の理由により、国/地域ごとに少なくとも 1 つの SIP トランクが必要です。</span><span class="sxs-lookup"><span data-stu-id="be0d7-123">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span> <span data-ttu-id="be0d7-124">たとえば EU では、通信は現地の中央ポイントで終了することなしに国/地域外にでることはできません。</span><span class="sxs-lookup"><span data-stu-id="be0d7-124">For example, in the European Union, communications cannot leave a country/region without terminating locally at a centralized point.</span></span>

<span data-ttu-id="be0d7-125">サイトの地理的な場所と企業内で予想されるトラフィックの量によっては、すべてのユーザーを中央 SIP トランク経由でルーティングしないようにしたり、一部のユーザーをブランチサイトの SIP トランクを介してルーティングすることを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="be0d7-125">Depending on the geographical location of sites and how much traffic you anticipate within your enterprise, you may not want to route all users through the central SIP trunk, or you may opt to route some users through a SIP trunk at their branch site.</span></span> <span data-ttu-id="be0d7-126">必要性を分析するために、次の質問に回答してください。</span><span class="sxs-lookup"><span data-stu-id="be0d7-126">To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="be0d7-127">各サイトの規模はどの程度ですか (つまり、エンタープライズ Voip が有効になっているユーザーの数)。</span><span class="sxs-lookup"><span data-stu-id="be0d7-127">How big is each site (that is, how many users are enabled for Enterprise Voice)?</span></span>

  - <span data-ttu-id="be0d7-128">各サイトで最も通話を受ける Direct Inward Dialing (DID) 番号はどれですか。</span><span class="sxs-lookup"><span data-stu-id="be0d7-128">Which direct inward dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="be0d7-129">集中型 SIP トランキングと分散型 SIP トランキングのどちらを展開するかを決定するには、費用便益分析が必要です。</span><span class="sxs-lookup"><span data-stu-id="be0d7-129">The decision whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="be0d7-130">必要のない場合にも分散型展開モデルを選択したほうが有益な場合があります。</span><span class="sxs-lookup"><span data-stu-id="be0d7-130">In some cases, it may be advantageous to opt for the distributed deployment model even if it is not required.</span></span> <span data-ttu-id="be0d7-131">完全な集中型展開では、すべてのブランチ サイトのトラフィックが WAN リンク経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="be0d7-131">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="be0d7-132">WAN リンクに必要な帯域幅に費用をかけるより、分散型 SIP トランキングを使用したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="be0d7-132">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span> <span data-ttu-id="be0d7-133">たとえば、中央サイトにフェデレーションがあるブランチサイトで Standard Edition サーバーを展開する場合や、小規模ゲートウェイを使用して存続可能 Branch Appliance または存続可能ブランチサーバーを展開する場合があります。</span><span class="sxs-lookup"><span data-stu-id="be0d7-133">For example, you may want to deploy a Standard Edition server at a branch site with federation to the central site, or you may want to deploy a Survivable Branch Appliance or a Survivable Branch Server with a small gateway.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="be0d7-134">分散型 SIP トランキングの詳細については、「 <A href="lync-server-2013-branch-site-sip-trunking.md">Lync Server 2013 のブランチサイト SIP トランキング</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be0d7-134">For details about distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="be0d7-135">サポートされている SIP トランキング接続の種類</span><span class="sxs-lookup"><span data-stu-id="be0d7-135">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="be0d7-136">Lync Server は、SIP トランキングに対して次の接続の種類をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="be0d7-136">Lync Server supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="be0d7-p109">Multiprotocol Label Switching (MPLS) は、ネットワーク ノード間でデータを伝送するプライベート ネットワークです。MPLS ネットワークの帯域幅は他のサブスクライバーと共有され、サブスクライバーのデータどうしを区別するためにデータ パケットごとにラベルが付けられます。この接続の種類に仮想プライベート ネットワーク (VPN) は必要ありません。潜在的な欠点は、VoIP トラフィックに優先度を与えないと、過剰な IP トラフィックが VoIP の処理に干渉する可能性があることです。</span><span class="sxs-lookup"><span data-stu-id="be0d7-p109">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next. The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s. This connection type does not require a virtual private network (VPN). A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="be0d7-p110">他のトラフィックを使用しないプライベート接続 (専用の光ファイバー接続、T1 回線など) は、通常、最も信頼できるセキュリティで保護された接続の種類です。 この接続の種類には、最高の通話伝送能力がありますが、通常最も費用がかかります。VPN は必要ありません。プライベート接続は、通話件数が多いか、セキュリティと可用性の要件が厳しい組織に適しています。</span><span class="sxs-lookup"><span data-stu-id="be0d7-p110">A private connection with no other traffic—for example, a leased fiber-optic connection or T1 line—is typically the most reliable and secure connection type. This connection type provides the highest call-carrying capacity, but it is typically the most expensive. VPN is not required. Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="be0d7-145">インターネットは、最も費用のかからない接続の種類ですが、最も信頼性が低いです。</span><span class="sxs-lookup"><span data-stu-id="be0d7-145">The Internet is the least expensive connection type, but it is also the least reliable.</span></span> <span data-ttu-id="be0d7-146">インターネット接続は、VPN を必要とする唯一の Lync Server SIP トランキング接続の種類です。</span><span class="sxs-lookup"><span data-stu-id="be0d7-146">Internet connection is the only Lync Server SIP trunking connection type that requires VPN.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="be0d7-147">接続の種類の選択</span><span class="sxs-lookup"><span data-stu-id="be0d7-147">Selecting a Connection Type</span></span>

<span data-ttu-id="be0d7-148">企業に最適な SIP トランキング接続の種類は、ニーズと予算によって異なります。</span><span class="sxs-lookup"><span data-stu-id="be0d7-148">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="be0d7-p112">中規模または比較的大規模な企業では、通常、MPLS ネットワークが最も費用対効果が高くなります。専用のプライベート ネットワークに比べて、必要な帯域幅が安価に提供されます。</span><span class="sxs-lookup"><span data-stu-id="be0d7-p112">For a mid-size or larger enterprise, an MPLS network usually provides the greatest value. It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="be0d7-151">大規模な企業には、プライベートな光ファイバー接続、T1、T3、またはそれ以上の接続が必要なことがあります (EU では E1、E3、またはそれ以上の接続)。</span><span class="sxs-lookup"><span data-stu-id="be0d7-151">Large enterprises may require a private fiber-optic, T1, T3 or higher connection (E1, E3 or higher in the European Union).</span></span>

  - <span data-ttu-id="be0d7-152">通話が少ない小規模な企業やブランチサイトでは、インターネットを介した SIP トランキングが最良の選択になることがあります。</span><span class="sxs-lookup"><span data-stu-id="be0d7-152">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="be0d7-153">この接続の種類は、中規模サイズあるいは比較的大規模なサイトには推奨されません。</span><span class="sxs-lookup"><span data-stu-id="be0d7-153">This connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a><span data-ttu-id="be0d7-154">帯域幅要件</span><span class="sxs-lookup"><span data-stu-id="be0d7-154">Bandwidth Requirements</span></span>

<span data-ttu-id="be0d7-p114">実装に必要となる帯域幅は、通話処理能力 (サポートされなければならない同時通話の数) によって異なります。代金を支払っている最大処理能力をできるだけ活用できるよう、使用可能な帯域幅を考慮に入れる必要があります。SIP トランクの最大帯域幅要件を計算するには次の式を使用してください。</span><span class="sxs-lookup"><span data-stu-id="be0d7-p114">The amount of bandwidth your implementation requires depends on call capacity (the number of concurrent calls you must be able to support). You need to consider bandwidth availability, so that you can take full advantage of the peak capacity that you have paid for. Use the following formula to calculate SIP trunk peak bandwidth requirement:</span></span>

<span data-ttu-id="be0d7-158">SIP トランク最大帯域幅 = 最大同時通話数 x (64 kbps + ヘッダー サイズ)</span><span class="sxs-lookup"><span data-stu-id="be0d7-158">SIP Trunk Peak Bandwidth = Max Simultaneous Calls x (64 kbps + header size)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="be0d7-159">ヘッダー サイズは最大で 20 バイトです。</span><span class="sxs-lookup"><span data-stu-id="be0d7-159">Header size is 20 bytes maximum.</span></span>



</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="be0d7-160">コーデックのサポート</span><span class="sxs-lookup"><span data-stu-id="be0d7-160">Codec Support</span></span>

<span data-ttu-id="be0d7-161">Lync Server 2013 でサポートされているコーデックは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="be0d7-161">Lync Server 2013 supports only the following codecs:</span></span>

  - <span data-ttu-id="be0d7-162">G.711 A-Law (主に北米以外で使用)</span><span class="sxs-lookup"><span data-stu-id="be0d7-162">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="be0d7-163">G.711 µ-Law (北米で使用)</span><span class="sxs-lookup"><span data-stu-id="be0d7-163">G.711 µ-law (used in North America)</span></span>

</div>

<div>

## <a name="internet-telephony-service-provider"></a><span data-ttu-id="be0d7-164">インターネット テレフォニー サービス プロバイダー</span><span class="sxs-lookup"><span data-stu-id="be0d7-164">Internet Telephony Service Provider</span></span>

<span data-ttu-id="be0d7-165">SIP トランク接続のサービス プロバイダー側の実装方法は、ITSP 間で異なります。</span><span class="sxs-lookup"><span data-stu-id="be0d7-165">How you implement the service provider side of a SIP trunk connection varies from one ITSP to another.</span></span> <span data-ttu-id="be0d7-166">展開の情報については、サービス プロバイダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="be0d7-166">For deployment information, contact your service provider.</span></span> <span data-ttu-id="be0d7-167">認定済み SIP トランキングサービスプロバイダーの一覧については、「 [Microsoft 統合コミュニケーションオープン相互運用性プログラム web サイト](https://go.microsoft.com/fwlink/?linkid=287029)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be0d7-167">For a list of certified SIP trunking service providers, see [Microsoft Unified Communications Open Interoperability Program website](https://go.microsoft.com/fwlink/?linkid=287029).</span></span>

<span data-ttu-id="be0d7-168">Microsoft 認定 SIP トランキング プロバイダーの詳細については、Microsoft 担当者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="be0d7-168">For details about Microsoft certified SIP trunking providers, contact your Microsoft representative.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="be0d7-p116">SIP トランクを通過するすべての機能を ITSP が確実にサポートするためには、Microsoft 認定のサービス プロバイダーを利用する必要があります (セッションのセットアップおよび管理、拡張 VoIP サービスの全機能のサポートなど)。Microsoft テクニカル サポートは、認定されていないプロバイダーを使用する構成には適用されません。現在、SIP トランキングに認定されていないインターネット サービス プロバイダーを使用している場合は、そのプロバイダーを ISP として使用し続け、SIP トランキングには Microsoft 認定プロバイダーを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="be0d7-p116">You must use a Microsoft certified service provider to ensure that your ITSP supports all of the functionality that traverses the SIP trunk (for example, setting up and managing sessions and supporting all of the extended VoIP services). Microsoft technical support does not extend to configurations that use noncertified providers. If you currently use an Internet service provider that is not certified for SIP trunking, you can opt to continue using that provider as your ISP and use a provider certified by Microsoft for SIP trunking.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

