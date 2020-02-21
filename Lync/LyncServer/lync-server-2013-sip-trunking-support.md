---
title: Lync Server 2013 SIP トランキングのサポート
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking support
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399005(v=OCS.15)
ms:contentKeyID: 48185714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f31159a2d14facbdfed2f74f3567081699a7bde9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a><span data-ttu-id="ecafb-102">Lync Server 2013 での SIP トランキングのサポート</span><span class="sxs-lookup"><span data-stu-id="ecafb-102">SIP trunking support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ecafb-103">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="ecafb-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="ecafb-104">SIP トランキングでエンタープライズ Voip を使用する場合は、仲介サーバーを展開して、他のインフラストラクチャとコンポーネントが展開モデルに適したサポート要件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecafb-104">If you plan to use Enterprise Voice with SIP trunking, you must deploy a Mediation Server and make sure that other infrastructure and components meet the support requirements appropriate to your deployment model.</span></span> <span data-ttu-id="ecafb-105">SIP トランキングを実装するかどうかを決定する方法の詳細については、「計画」のドキュメントの「 [Lync Server 2013 の sip トランキングの概要](lync-server-2013-overview-of-sip-trunking.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecafb-105">For details about determining whether to implement SIP trunking, see [Overview of SIP trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) in the Planning documentation.</span></span>

<span data-ttu-id="ecafb-106">エンタープライズテレフォニーインフラストラクチャの Microsoft ユニファイドコミュニケーションプログラムを使用して、正規の公衆交換電話網 (PSTN) ゲートウェイ、IP-Pbx、および SIP トランキングサービス (修飾 IP テレフォニーを含む) を検索できます。サービスプロバイダー。</span><span class="sxs-lookup"><span data-stu-id="ecafb-106">You can use the Microsoft Unified Communications Open Interoperability Program for enterprise telephony infrastructure to find qualified public switched telephone network (PSTN) gateways, IP-PBXs, and SIP trunking services, including qualified IP telephony service providers.</span></span> <span data-ttu-id="ecafb-107">詳細については、「Microsoft 統合コミュニケーションオープン相互運用性[https://go.microsoft.com/fwlink/p/?LinkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309)プログラム web サイト」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecafb-107">For details, see the Microsoft Unified Communications Open Interoperability Program website at [https://go.microsoft.com/fwlink/p/?LinkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

<div>

## <a name="mediation-server-support"></a><span data-ttu-id="ecafb-108">仲介サーバーのサポート</span><span class="sxs-lookup"><span data-stu-id="ecafb-108">Mediation Server Support</span></span>

<span data-ttu-id="ecafb-109">SIP トランキングを実装するには、仲介サーバーを経由して接続をルーティングする必要があります。これは、Lync Server 2013 クライアントとサービスプロバイダー間の通信セッションのプロキシとして機能します。</span><span class="sxs-lookup"><span data-stu-id="ecafb-109">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider.</span></span> <span data-ttu-id="ecafb-110">仲介サーバーは、クライアントとサーバーからメディアトラフィックをデコードし、それをサービスプロバイダーに送信する前に再エンコードします。</span><span class="sxs-lookup"><span data-stu-id="ecafb-110">The Mediation Server decodes the media traffic from clients and servers and re-encodes it before sending it to the service provider.</span></span> <span data-ttu-id="ecafb-111">この再エンコードは、SIP トランクが、ファイアウォールトラバーサルのリアルタイム音声 (RTA) または対話型接続確立 (ICE) プロトコルネゴシエーションなど、使用されている一部のコーデックをサポートしていないために必要です。</span><span class="sxs-lookup"><span data-stu-id="ecafb-111">The re-encoding is needed because SIP trunks do not support some codecs used, such as Real Time Audio (RTA) or Interactive Connectivity Establishment (ICE) protocol negotiation for firewall traversal.</span></span>

<span data-ttu-id="ecafb-112">仲介サーバーごとに、内部ネットワーク インターフェイスと外部ネットワーク インターフェイスを提供する、2 つのネットワーク アダプターを設定できます。</span><span class="sxs-lookup"><span data-stu-id="ecafb-112">Each Mediation Server can have two network adapters, which provide an internal and an external network interface.</span></span> <span data-ttu-id="ecafb-113">一般に、外部インターフェイスは、PSTN ゲートウェイまたは IP-PBX に接続するために使用されているため、ゲートウェイインターフェイスと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ecafb-113">The external interface is commonly called the gateway interface because, traditionally, it has been used to connect to a PSTN gateway or an IP-PBX.</span></span> <span data-ttu-id="ecafb-114">SIP トランクを実装するには、外部インターフェイスをサービス プロバイダーのセッション ボーダー コントローラー (SBC) と接続します。</span><span class="sxs-lookup"><span data-stu-id="ecafb-114">To implement a SIP trunk, you connect the external interface to a Session Border Controller (SBC) at a service provider.</span></span>

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="ecafb-115">集中型と分散型 SIP トランキングの比較</span><span class="sxs-lookup"><span data-stu-id="ecafb-115">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="ecafb-116">*一元*SIP トランキングは、データセンターを介して、ブランチサイトトラフィックを含むすべてのボイスオーバー Ip (VoIP) トラフィックをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="ecafb-116">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your data center.</span></span> <span data-ttu-id="ecafb-117">一元展開モデルはシンプルで費用対効果があり、通常は、Lync Server 2013 で SIP トランクを実装するために推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="ecafb-117">The centralized deployment model is simple, cost-effective, and is generally the preferred approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="ecafb-p106">企業での使用パターンによっては、すべてのユーザーに集中型 SIP トランクを使用したくない場合があります。 必要性を分析するために、次の質問に回答してください。</span><span class="sxs-lookup"><span data-stu-id="ecafb-p106">Depending on usage patterns within your enterprise, you may not want to route all users through the centralized SIP trunk. To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="ecafb-p107">各サイトの大きさは? ユーザーの数は?</span><span class="sxs-lookup"><span data-stu-id="ecafb-p107">How big is each site? How many users?</span></span>

  - <span data-ttu-id="ecafb-122">各サイトで最も通話を受ける Direct Inward Dialing (DID) 番号は?</span><span class="sxs-lookup"><span data-stu-id="ecafb-122">Which Direct Inward Dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="ecafb-p108">*分散型* SIP トランキングは、1 つまたは複数のブランチ サイトでローカルな SIP トランクを実装する展開モデルです。 その場合 VoIP トラフィックは、データ センターを経由せずに、ブランチ サイトから直接サービス プロバイダーにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="ecafb-p108">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites. VoIP traffic is then routed from the branch site directly to their service provider, without going through your data center.</span></span>

<span data-ttu-id="ecafb-125">分散型 SIP トランキングが必要なのは、次のケースだけです。</span><span class="sxs-lookup"><span data-stu-id="ecafb-125">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="ecafb-126">ブランチ サイトに存続可能な通話接続が必要な場合 (WAN がダウンした場合など)。</span><span class="sxs-lookup"><span data-stu-id="ecafb-126">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="ecafb-127">ブランチに冗長性とフェールオーバーが必要な場合、サービス プロバイダーの負担が高くなり、構成に時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="ecafb-127">If the branch does need redundancy and failover, the service provider will charge more and the configuration will take longer.</span></span> <span data-ttu-id="ecafb-128">このことについて、各ブランチ サイトで分析する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecafb-128">This should be analyzed for each branch site.</span></span> <span data-ttu-id="ecafb-129">ブランチの一部は、冗長性とフェールオーバーを必要とする場合がありますが、それ以外の場合もあります。</span><span class="sxs-lookup"><span data-stu-id="ecafb-129">Some of your branches may require redundancy and failover, while others may not.</span></span>

  - <span data-ttu-id="ecafb-p110">ブランチ サイトとデータ センターで国/地域が異なる場合。 互換性と法律上の理由により、国/地域ごとに少なくとも 1 つの SIP トランクが必要です。</span><span class="sxs-lookup"><span data-stu-id="ecafb-p110">The branch site and data center are in different countries/regions. For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span>

<span data-ttu-id="ecafb-132">集中化または分散 SIP トランキングを展開するかどうかを決定するには、費用便益分析が必要です。</span><span class="sxs-lookup"><span data-stu-id="ecafb-132">Deciding whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="ecafb-133">必要でない場合でも、分散展開モードを選択した方がよい場合があります。</span><span class="sxs-lookup"><span data-stu-id="ecafb-133">In some cases, it may be advantageous to opt for the distributed deployment mode, even if it is not required.</span></span> <span data-ttu-id="ecafb-134">完全な集中型展開では、すべてのブランチ サイトのトラフィックが WAN リンク経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="ecafb-134">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="ecafb-135">WAN リンクに必要な帯域幅に費用をかけるより、分散型 SIP トランキングを使用したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="ecafb-135">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ecafb-136">分散 SIP トランキングを使用する理由と方法の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-branch-site-sip-trunking.md">Branch SITE SIP トランキング In Lync Server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecafb-136">For details about why and how you might use distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="ecafb-137">サポートされている SIP トランキング接続の種類</span><span class="sxs-lookup"><span data-stu-id="ecafb-137">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="ecafb-138">Lync Server 2013 は、SIP トランキングに対して次の接続の種類をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ecafb-138">Lync Server 2013 supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="ecafb-p112">Multiprotocol Label Switching (MPLS) は、ネットワーク ノード間でデータを伝送するプライベート ネットワークです。 MPLS ネットワークの帯域幅は他のサブスクライバーと共有され、サブスクライバーのデータどうしを区別するためにデータ パケットごとにラベルが付けられます。この接続の種類に VPN は必要ありません。 潜在的な欠点は、VoIP トラフィックに優先度を与えないと、過剰な IP トラフィックが VoIP の処理に干渉する可能性があることです。</span><span class="sxs-lookup"><span data-stu-id="ecafb-p112">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next. The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s. This connection type does not require VPN. A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="ecafb-p113">他のトラフィックを使用しないプライベート接続は、通常、最も信頼できるセキュアな接続の種類です (専用の光ファイバー接続、T1 回線など)。 この接続の種類には、最高の通話伝送能力がありますが、通常最も費用がかかります。 VPN は必要ありません。 プライベート接続は、通話件数が多いか、セキュリティと可用性の要件が厳しい組織に適しています。</span><span class="sxs-lookup"><span data-stu-id="ecafb-p113">A private connection with no other traffic is typically the most reliable and secure connection type (for example, a leased fiber-optic connection or T1 line). This connection type provides the highest call-carrying capacity, but is typically the most expensive. VPN is not required. Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="ecafb-147">公共のインターネットは、最も費用のかからない接続の種類ですが、最も信頼性が低く、通話伝送能力も最低です。</span><span class="sxs-lookup"><span data-stu-id="ecafb-147">The public Internet is the least expensive connection type, but also the least reliable, and the one with the lowest call-carrying capacity.</span></span> <span data-ttu-id="ecafb-148">インターネットテレフォニーサービスプロバイダー (ITSP) は、トランスポート層セキュリティ (TLS) とセキュアリアルタイム転送プロトコル (SRTP) をサポートして、シグナリングとメディアトラフィックを暗号化する場合に、この SIP トランク接続の種類をセキュリティで保護するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ecafb-148">Your Internet Telephony Service Provider (ITSP) can help secure this SIP trunk connection type if it supports Transport Layer Security (TLS) and Secure Real-Time Transport Protocol (SRTP) to encrypt signaling and media traffic.</span></span> <span data-ttu-id="ecafb-149">TLS および SRTP を使用するようにインターネット経由の SIP トランク接続を構成できない場合は、VPN トンネルを使用していっそう安全な接続を提供することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ecafb-149">If you cannot configure a SIP trunk connection through the Internet to use TLS and SRTP, we strongly recommend that you use a VPN tunnel to provide a more secure connection.</span></span> <span data-ttu-id="ecafb-150">ITSP が TLS と SRTP のサポートを提供しているかどうかを確認するには、ITSP に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="ecafb-150">Contact your ITSP to determine whether it provides support for TLS with SRTP.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="ecafb-151">接続の種類の選択</span><span class="sxs-lookup"><span data-stu-id="ecafb-151">Selecting a Connection Type</span></span>

<span data-ttu-id="ecafb-152">企業に最適な SIP トランキング接続の種類は、ニーズと予算によって異なります。</span><span class="sxs-lookup"><span data-stu-id="ecafb-152">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="ecafb-153">中規模または大規模の企業の場合、通常、MPLS ネットワークは最大の価値を提供します。</span><span class="sxs-lookup"><span data-stu-id="ecafb-153">For a mid-size or larger enterprise, an MPLS network generally provides the most value.</span></span> <span data-ttu-id="ecafb-154">専用のプライベート ネットワークに比べて、必要な帯域幅が安価に提供されます。</span><span class="sxs-lookup"><span data-stu-id="ecafb-154">It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="ecafb-155">大規模な企業には、プライベートな光ファイバー接続または T1 接続が必要なことがあります。</span><span class="sxs-lookup"><span data-stu-id="ecafb-155">Large enterprises may require a private fiber-optic or T1 connection.</span></span>

  - <span data-ttu-id="ecafb-156">通話が少ない小規模な企業やブランチサイトでは、インターネットを介した SIP トランキングが最良の選択になることがあります。</span><span class="sxs-lookup"><span data-stu-id="ecafb-156">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="ecafb-157">ただし、この接続の種類は、中規模または大規模なサイトには推奨されません。</span><span class="sxs-lookup"><span data-stu-id="ecafb-157">However, this connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="ecafb-158">コーデックのサポート</span><span class="sxs-lookup"><span data-stu-id="ecafb-158">Codec Support</span></span>

<span data-ttu-id="ecafb-159">サービス プロバイダー プロキシでは、次のコーデックをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecafb-159">The service provider proxy must support the following codecs:</span></span>

  - <span data-ttu-id="ecafb-160">G.711 A-Law (主に北米以外で使用)</span><span class="sxs-lookup"><span data-stu-id="ecafb-160">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="ecafb-161">G.711 µ-Law (北米で使用)</span><span class="sxs-lookup"><span data-stu-id="ecafb-161">G.711 µ-law (used in North America)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

