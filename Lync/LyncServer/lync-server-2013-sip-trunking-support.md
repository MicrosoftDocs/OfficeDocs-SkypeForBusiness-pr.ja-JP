---
title: 'Lync Server 2013: SIP トランキングのサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SIP trunking support
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399005(v=OCS.15)
ms:contentKeyID: 48185714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2bdcf814a62bed4954c77be76bef32e1b6807ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a><span data-ttu-id="d0580-102">Lync Server 2013 での SIP トランキングのサポート</span><span class="sxs-lookup"><span data-stu-id="d0580-102">SIP trunking support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0580-103">_**最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="d0580-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="d0580-104">SIP トランクでエンタープライズ Voip を使用する予定がある場合は、仲介サーバーを展開して、他のインフラストラクチャとコンポーネントが展開モデルに適したサポート要件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0580-104">If you plan to use Enterprise Voice with SIP trunking, you must deploy a Mediation Server and make sure that other infrastructure and components meet the support requirements appropriate to your deployment model.</span></span> <span data-ttu-id="d0580-105">SIP トランクを実装するかどうかを決定する方法の詳細については、計画ドキュメントの「 [Lync Server 2013 での sip トランクの概要](lync-server-2013-overview-of-sip-trunking.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0580-105">For details about determining whether to implement SIP trunking, see [Overview of SIP trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) in the Planning documentation.</span></span>

<span data-ttu-id="d0580-106">エンタープライズテレフォニーインフラストラクチャの Microsoft ユニファイドコミュニケーションプログラムを使用して、認定された公衆交換電話網 (PSTN) ゲートウェイ、IP Pbx、SIP トランクサービス (認定 IP テレフォニーを含む) を検索することができます。サービスプロバイダ。</span><span class="sxs-lookup"><span data-stu-id="d0580-106">You can use the Microsoft Unified Communications Open Interoperability Program for enterprise telephony infrastructure to find qualified public switched telephone network (PSTN) gateways, IP-PBXs, and SIP trunking services, including qualified IP telephony service providers.</span></span> <span data-ttu-id="d0580-107">詳細については、「Microsoft ユニファイド通信のオープン[http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)な相互運用性プログラム web サイト」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0580-107">For details, see the Microsoft Unified Communications Open Interoperability Program website at [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

<div>

## <a name="mediation-server-support"></a><span data-ttu-id="d0580-108">仲介サーバーのサポート</span><span class="sxs-lookup"><span data-stu-id="d0580-108">Mediation Server Support</span></span>

<span data-ttu-id="d0580-109">SIP トランクを実装するには、Lync Server 2013 クライアントとサービスプロバイダの間の通信セッションのプロキシとして機能する仲介サーバー経由で接続をルーティングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0580-109">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider.</span></span> <span data-ttu-id="d0580-110">仲介サーバーは、クライアントとサーバーからメディアトラフィックをデコードし、それを再エンコードしてからサービスプロバイダに送信します。</span><span class="sxs-lookup"><span data-stu-id="d0580-110">The Mediation Server decodes the media traffic from clients and servers and re-encodes it before sending it to the service provider.</span></span> <span data-ttu-id="d0580-111">SIP trunks は、ファイアウォールトラバーサルでのリアルタイムオーディオ (RTA) や対話型接続確立 (ICE) プロトコルのネゴシエーションなど、使用されている一部のコーデックをサポートしていないため、再エンコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="d0580-111">The re-encoding is needed because SIP trunks do not support some codecs used, such as Real Time Audio (RTA) or Interactive Connectivity Establishment (ICE) protocol negotiation for firewall traversal.</span></span>

<span data-ttu-id="d0580-112">各仲介サーバーには、内部と外部のネットワークインターフェイスを提供する2つのネットワークアダプターを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d0580-112">Each Mediation Server can have two network adapters, which provide an internal and an external network interface.</span></span> <span data-ttu-id="d0580-113">一般的に、外部インターフェイスは、PSTN ゲートウェイまたは ip-pbx に接続するために使用されているため、ゲートウェイインターフェイスと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d0580-113">The external interface is commonly called the gateway interface because, traditionally, it has been used to connect to a PSTN gateway or an IP-PBX.</span></span> <span data-ttu-id="d0580-114">SIP トランクを実装するには、サービスプロバイダのセッションボーダーコントローラー (SBC) に外部インターフェイスを接続します。</span><span class="sxs-lookup"><span data-stu-id="d0580-114">To implement a SIP trunk, you connect the external interface to a Session Border Controller (SBC) at a service provider.</span></span>

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="d0580-115">集中型と分散型 SIP トランキングの比較</span><span class="sxs-lookup"><span data-stu-id="d0580-115">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="d0580-116">*一元管理*SIP トランキングは、ブランチサイトトラフィックを含むすべてのボイスオーバーインターネットプロトコル (VoIP) トラフィックをデータセンター経由でルーティングします。</span><span class="sxs-lookup"><span data-stu-id="d0580-116">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your data center.</span></span> <span data-ttu-id="d0580-117">一元展開モデルはシンプルでコスト効率が高いため、通常は Lync Server 2013 で SIP trunks を実装するための推奨されるアプローチです。</span><span class="sxs-lookup"><span data-stu-id="d0580-117">The centralized deployment model is simple, cost-effective, and is generally the preferred approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="d0580-118">企業内の使用パターンによっては、一元管理された SIP トランクを通じてすべてのユーザーをルーティングする必要がない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d0580-118">Depending on usage patterns within your enterprise, you may not want to route all users through the centralized SIP trunk.</span></span> <span data-ttu-id="d0580-119">必要性を分析するために、次の質問に回答してください。</span><span class="sxs-lookup"><span data-stu-id="d0580-119">To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="d0580-120">各サイトの規模</span><span class="sxs-lookup"><span data-stu-id="d0580-120">How big is each site?</span></span> <span data-ttu-id="d0580-121">ユーザ数は何人ですか?</span><span class="sxs-lookup"><span data-stu-id="d0580-121">How many users?</span></span>

  - <span data-ttu-id="d0580-122">各サイトで、最も多くの通話を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="d0580-122">Which Direct Inward Dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="d0580-123">*均等割り付け*SIP トランキングは、1つ以上のブランチサイトにローカル SIP トランクを実装する展開モデルです。</span><span class="sxs-lookup"><span data-stu-id="d0580-123">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites.</span></span> <span data-ttu-id="d0580-124">VoIP トラフィックは、データセンターを経由せずに、ブランチサイトからサービスプロバイダに直接ルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="d0580-124">VoIP traffic is then routed from the branch site directly to their service provider, without going through your data center.</span></span>

<span data-ttu-id="d0580-125">分散型 SIP トランキングが必要なのは、次のケースだけです。</span><span class="sxs-lookup"><span data-stu-id="d0580-125">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="d0580-126">ブランチサイトには、survivable の電話接続 (WAN がダウンした場合など) が必要です。</span><span class="sxs-lookup"><span data-stu-id="d0580-126">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="d0580-127">ブランチに冗長性とフェールオーバーが必要な場合、サービスプロバイダーはさらに料金を請求し、構成は長くなります。</span><span class="sxs-lookup"><span data-stu-id="d0580-127">If the branch does need redundancy and failover, the service provider will charge more and the configuration will take longer.</span></span> <span data-ttu-id="d0580-128">これは、ブランチサイトごとに分析する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0580-128">This should be analyzed for each branch site.</span></span> <span data-ttu-id="d0580-129">一部の支店では、冗長性とフェールオーバーが必要になる場合もありますが、そうでない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="d0580-129">Some of your branches may require redundancy and failover, while others may not.</span></span>

  - <span data-ttu-id="d0580-130">ブランチサイトとデータセンターは、国/地域によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d0580-130">The branch site and data center are in different countries/regions.</span></span> <span data-ttu-id="d0580-131">互換性と法律上の理由により、国/地域ごとに少なくとも 1 つの SIP トランクが必要です。</span><span class="sxs-lookup"><span data-stu-id="d0580-131">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span>

<span data-ttu-id="d0580-132">一元管理または分散 SIP トランキングを展開するかどうかを決定するには、費用便益分析が必要です。</span><span class="sxs-lookup"><span data-stu-id="d0580-132">Deciding whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="d0580-133">場合によっては、必要でない場合でも、分散展開モードを選択した方が便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d0580-133">In some cases, it may be advantageous to opt for the distributed deployment mode, even if it is not required.</span></span> <span data-ttu-id="d0580-134">完全に一元管理された展開では、すべてのブランチサイトトラフィックが WAN リンクを介してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="d0580-134">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="d0580-135">WAN リンクに必要な帯域幅に費用をかけるより、分散型 SIP トランキングを使用したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="d0580-135">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d0580-136">分散 SIP トランクの使用の理由とその方法の詳細については、計画ドキュメントの「 <A href="lync-server-2013-branch-site-sip-trunking.md">Lync Server 2013 でのブランチサイト SIP トランク</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0580-136">For details about why and how you might use distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="d0580-137">サポートされている SIP トランキング接続の種類</span><span class="sxs-lookup"><span data-stu-id="d0580-137">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="d0580-138">Lync Server 2013 は、SIP トランクで次の接続の種類をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d0580-138">Lync Server 2013 supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="d0580-139">Multiprotocol Label Switching (MPLS) は、ネットワーク ノード間でデータを伝送するプライベート ネットワークです。</span><span class="sxs-lookup"><span data-stu-id="d0580-139">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next.</span></span> <span data-ttu-id="d0580-140">MPLS ネットワークの帯域幅は他のサブスクライバーと共有され、サブスクライバーのデータどうしを区別するためにデータ パケットごとにラベルが付けられます。</span><span class="sxs-lookup"><span data-stu-id="d0580-140">The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s.</span></span> <span data-ttu-id="d0580-141">この接続の種類は VPN を必要としません。</span><span class="sxs-lookup"><span data-stu-id="d0580-141">This connection type does not require VPN.</span></span> <span data-ttu-id="d0580-142">潜在的な欠点は、VoIP トラフィックに優先度を与えないと、過剰な IP トラフィックが VoIP の処理に干渉する可能性があることです。</span><span class="sxs-lookup"><span data-stu-id="d0580-142">A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="d0580-143">通常、他のトラフィックのないプライベート接続は、最も信頼性が高く安全な接続の種類 (たとえば、専用光ファイバー接続や T1 回線など) です。</span><span class="sxs-lookup"><span data-stu-id="d0580-143">A private connection with no other traffic is typically the most reliable and secure connection type (for example, a leased fiber-optic connection or T1 line).</span></span> <span data-ttu-id="d0580-144">この接続の種類では、通話転送の最大容量が提供されますが、通常は最もコストがかかります。</span><span class="sxs-lookup"><span data-stu-id="d0580-144">This connection type provides the highest call-carrying capacity, but is typically the most expensive.</span></span> <span data-ttu-id="d0580-145">VPN は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d0580-145">VPN is not required.</span></span> <span data-ttu-id="d0580-146">プライベート接続は、通話件数が多いか、セキュリティと可用性の要件が厳しい組織に適しています。</span><span class="sxs-lookup"><span data-stu-id="d0580-146">Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="d0580-147">公開インターネットとは、最も負荷の低い接続の種類であり、最も信頼性が低く、通話転送容量が最も低いインターネットです。</span><span class="sxs-lookup"><span data-stu-id="d0580-147">The public Internet is the least expensive connection type, but also the least reliable, and the one with the lowest call-carrying capacity.</span></span> <span data-ttu-id="d0580-148">インターネットテレフォニーサービスプロバイダ (ITSP) は、トランスポートレイヤーセキュリティ (TLS) とセキュアリアルタイムトランスポートプロトコル (SRTP) をサポートしている場合に、シグナリングとメディアトラフィックを暗号化するために、この SIP トランクの接続の種類を保護することができます。</span><span class="sxs-lookup"><span data-stu-id="d0580-148">Your Internet Telephony Service Provider (ITSP) can help secure this SIP trunk connection type if it supports Transport Layer Security (TLS) and Secure Real-Time Transport Protocol (SRTP) to encrypt signaling and media traffic.</span></span> <span data-ttu-id="d0580-149">TLS と SRTP を使用するためにインターネット経由で SIP トランク接続を構成できない場合は、セキュリティで保護された接続を提供するために VPN トンネルを使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d0580-149">If you cannot configure a SIP trunk connection through the Internet to use TLS and SRTP, we strongly recommend that you use a VPN tunnel to provide a more secure connection.</span></span> <span data-ttu-id="d0580-150">ITSP に連絡して、SRTP による TLS のサポートが提供されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0580-150">Contact your ITSP to determine whether it provides support for TLS with SRTP.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="d0580-151">接続の種類の選択</span><span class="sxs-lookup"><span data-stu-id="d0580-151">Selecting a Connection Type</span></span>

<span data-ttu-id="d0580-152">企業に最適な SIP トランキング接続の種類は、ニーズと予算によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d0580-152">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="d0580-153">大規模または大規模企業の場合、MPLS ネットワークは通常、最大値を提供します。</span><span class="sxs-lookup"><span data-stu-id="d0580-153">For a mid-size or larger enterprise, an MPLS network generally provides the most value.</span></span> <span data-ttu-id="d0580-154">専用のプライベート ネットワークに比べて、必要な帯域幅が安価に提供されます。</span><span class="sxs-lookup"><span data-stu-id="d0580-154">It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="d0580-155">大企業には、プライベートな光ファイバーまたは T1 接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="d0580-155">Large enterprises may require a private fiber-optic or T1 connection.</span></span>

  - <span data-ttu-id="d0580-156">通話音量が低い小規模企業または支店の場合、インターネットを介した SIP トランクが最適な選択肢となることがあります。</span><span class="sxs-lookup"><span data-stu-id="d0580-156">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="d0580-157">ただし、この接続の種類は、中規模または大規模のサイトではお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="d0580-157">However, this connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="d0580-158">コーデックのサポート</span><span class="sxs-lookup"><span data-stu-id="d0580-158">Codec Support</span></span>

<span data-ttu-id="d0580-159">サービスプロバイダーのプロキシは、次のコーデックをサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0580-159">The service provider proxy must support the following codecs:</span></span>

  - <span data-ttu-id="d0580-160">G.711 A-Law (主に北米以外で使用)</span><span class="sxs-lookup"><span data-stu-id="d0580-160">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="d0580-161">G.711 μ-Law (北米で使用)</span><span class="sxs-lookup"><span data-stu-id="d0580-161">G.711 µ-law (used in North America)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

