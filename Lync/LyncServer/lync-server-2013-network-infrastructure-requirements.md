---
title: Lync Server 2013 のネットワークインフラストラクチャの要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea383a77ff8d6089e2a01d7fb00df434f6d805e5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42129380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="e6ec4-102">Lync Server 2013 のネットワークインフラストラクチャ要件</span><span class="sxs-lookup"><span data-stu-id="e6ec4-102">Network infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6ec4-103">_**トピックの最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="e6ec4-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="e6ec4-104">Lync Server 2013 トポロジ内の各サーバーのネットワークアダプターカードは、少なくとも 1 Gbps (ギガビット/秒) をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-104">The network adapter card of each server in the Lync Server 2013 topology must support at least 1 gigabit per second (Gbps).</span></span> <span data-ttu-id="e6ec4-105">通常、Lync Server トポロジ内のすべてのサーバーの役割は、低遅延および高帯域幅のローカルエリアネットワーク (LAN) を使用して接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-105">In general, you should connect all server roles within the Lync Server topology using a low latency and high bandwidth local area network (LAN).</span></span> <span data-ttu-id="e6ec4-106">LAN のサイズは、トポロジのサイズに依存します。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-106">The size of the LAN is dependent on the size of the topology:</span></span>

  - <span data-ttu-id="e6ec4-107">Standard Edition のトポロジでは、サーバーは 1 Gbps のイーサネットまたは同等のものをサポートするネットワーク内に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-107">In Standard Edition topologies, servers should be in a network that supports 1 Gbps Ethernet or equivalent.</span></span>

  - <span data-ttu-id="e6ec4-108">フロントエンドプールトポロジでは、特に音声ビデオ (A/V) 会議とアプリケーション共有をサポートする場合、多くのサーバーが 1 Gbps を超えるネットワークに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-108">In Front End pool topologies, most servers should be in a network that supports more than 1 Gbps, especially when supporting audio/video (A/V) conferencing and application sharing.</span></span>

<span data-ttu-id="e6ec4-109">公衆交換電話網 (PSTN) 統合については、T1 回線または E1 回線、あるいは SIP トランキングを使用することにより、統合を実行できます。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-109">For public switched telephone network (PSTN) integration, you can integrate by using either T1/E1 lines or SIP trunking.</span></span>

<div>

## <a name="audiovideo-network-requirements"></a><span data-ttu-id="e6ec4-110">音声ビデオのネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="e6ec4-110">Audio/Video Network Requirements</span></span>

<span data-ttu-id="e6ec4-111">Lync Server 展開での音声/ビデオ (A/V) のネットワーク要件には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-111">Network requirements for audio/video (A/V) in a Lync Server deployment include the following:</span></span>

  - <span data-ttu-id="e6ec4-112">DNS 負荷分散を使用して単一のエッジサーバーまたはエッジプールを展開する場合は、外部ファイアウォールを NAT として構成できます。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-112">If you are deploying a single Edge Server or an Edge pool using DNS load balancing, you can configure the external firewall as a NAT.</span></span> <span data-ttu-id="e6ec4-113">内部ファイアウォールは、NAT として構成できません。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-113">You cannot configure the internal firewall as a NAT.</span></span> <span data-ttu-id="e6ec4-114">これらの要件の詳細については、「計画」のドキュメントの「 [Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を決定](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-114">For details about these requirements, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) in the Planning documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e6ec4-115">エッジプールがあり、ハードウェアロードバランサーを使用している場合は、各エッジサーバーでパブリック IP アドレスを使用する必要があり、nat デバイスのサーバーまたはプール (たとえば、ファイアウォール、または nat デバイスやその他のインフラストラクチャデバイス) で NAT を使用できません。nd または発信トラフィック)。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-115">If you have an Edge pool and are using a hardware load balancer, you must use public IP addresses on each of the Edge Servers and you cannot use NAT for the servers or the pool at your NAT device (for example, the firewall, or other infrastructure device that would NAT inbound or outbound traffic).</span></span> <span data-ttu-id="e6ec4-116">詳細については、「Planning for External User Access documentation」の「 <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary-拡張統合エッジ (Lync Server 2013)</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-116">For details, see <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A> in the Planning for External User Access documentation.</span></span>

    
    </div>

  - <span data-ttu-id="e6ec4-117">組織でサービスの品質 (QoS) インフラストラクチャが使用されている場合、メディア サブシステムは、この既存のインフラストラクチャで機能するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-117">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span>

  - <span data-ttu-id="e6ec4-118">インターネット プロトコル セキュリティ (IPsec) を使用する場合は、A/V トラフィックに使用されるポート範囲に対する IPsec を無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-118">If you use Internet Protocol security (IPsec), we recommend disabling IPsec over the port ranges used for A/V traffic.</span></span> <span data-ttu-id="e6ec4-119">詳細については、「計画」のドキュメントの「 [IPsec 例外 (Lync Server 2013](lync-server-2013-ipsec-exceptions.md) )」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-119">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

<span data-ttu-id="e6ec4-120">最適なメディア品質を確保するには、以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-120">To ensure optimal media quality, do the following:</span></span>

  - <span data-ttu-id="e6ec4-p105">ストリームが有効になっている場合は、ピーク利用期間に音声ストリームにつき 65 Kbps (キロビット/秒) およびビデオ ストリームにつき 500 Kbps のスループットをサポートするようにネットワーク リンクのプロビジョニングを行います。双方向の音声またはビデオ セッションは、2 つのストリームから構成されます。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-p105">Provision your network links to support throughput of 65 kilobits per second (Kbps) per audio stream and 500 Kbps per video stream, if enabled, during peak usage periods. A bidirectional audio or video session consists of two streams.</span></span>

  - <span data-ttu-id="e6ec4-123">時間の経過とともに、このレベル以上のトラフィックに予期しないスパイクが発生し、使用率が増加した場合、Lync Server のメディアエンドポイントは、さまざまなネットワークの状態に適応し、オーディオとビデオのスループット (前の段落を参照) の3倍の負荷をサポートすることができます。許容できる品質を維持します。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-123">To cope with unexpected spikes in traffic above this level and increased usage over time, Lync Server media endpoints can adapt to varying network conditions and support loads of three times the throughput (see previous paragraph) for audio and video while still retaining acceptable quality.</span></span> <span data-ttu-id="e6ec4-124">ただし、その場合は、この適応性により、プロビジョニング不足のネットワークがサポートされると想定しないでください。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-124">However, do not assume that this adaptability will support an under-provisioned network.</span></span> <span data-ttu-id="e6ec4-125">一部のプロビジョニングされたネットワークでは、Lync Server のメディアエンドポイントがさまざまなネットワークの状態 (たとえば、一時的な高パケット損失など) を動的に処理する機能が低下しています。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-125">In an under-provisioned network, the ability of the Lync Server media endpoints to dynamically deal with varying network conditions (for example, temporary high packet loss) is reduced.</span></span>

  - <span data-ttu-id="e6ec4-126">プロビジョニングが非常に高価で困難なネットワークリンクの場合は、低音量のトラフィックのプロビジョニングを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-126">For network links where provisioning is extremely costly and difficult, you may need to consider provisioning for a lower volume of traffic.</span></span> <span data-ttu-id="e6ec4-127">このシナリオでは、Lync Server media エンドポイントの弾力性が、トラフィックボリュームとピーク時のトラフィックレベルの違いを吸収します。これにより、音声品質の一部が減少します。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-127">In this scenario, let the elasticity of the Lync Server media endpoints absorb the difference between the traffic volume and the peak traffic level, at the cost of some reduction in the voice quality.</span></span> <span data-ttu-id="e6ec4-128">また、トラフィックの急激なピークを吸収するには、ヘッドルームが減少しています。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-128">Also, there is a decrease in the headroom otherwise available to absorb sudden peaks in traffic.</span></span>

  - <span data-ttu-id="e6ec4-129">短期間では正しくプロビジョニングできないリンク (貧弱な WAN リンクを備えたサイトなど) の場合は、特定ユーザーについてはビデオを無効にすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-129">For links that cannot be correctly provisioned in the short term (for example, a site with very poor WAN links), consider disabling video for certain users.</span></span>

  - <span data-ttu-id="e6ec4-130">ピーク負荷でエンドツーエンドの最大遅延 (待ち時間) 150 ミリ秒 (ms) を保証するようにネットワークのプロビジョニングを行います。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-130">Provision your network to ensure a maximum end-to-end delay (latency) of 150 milliseconds (ms) under peak load.</span></span> <span data-ttu-id="e6ec4-131">待機時間は、Lync Server メディアコンポーネントによって削減できないネットワーク障害の1つであり、脆弱なポイントを見つけて除去することが重要です。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-131">Latency is the one network impairment that Lync Server media components cannot reduce, and it is important to find and eliminate the weak points.</span></span>

  - <span data-ttu-id="e6ec4-132">ウイルス対策ソフトウェアを実行しているサーバーでは、最適なパフォーマンスと音声品質を提供するために、Lync Server を実行しているすべてのサーバーを例外リストに含めます。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-132">For servers running antivirus software, include all servers running Lync Server in the exception list in order to provide optimal performance and audio quality.</span></span>

</div>

<div>

## <a name="conferencing-network-requirements"></a><span data-ttu-id="e6ec4-133">会議のネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="e6ec4-133">Conferencing Network Requirements</span></span>

<span data-ttu-id="e6ec4-134">インターネットインフォメーションサービス (IIS) サーバーから会議コンテンツをダウンロードするために使用される帯域幅は、アップロードされるコンテンツのサイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="e6ec4-134">The bandwidth that is used to download conference content from the Internet Information Services (IIS) server depends on the size of the content that is uploaded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

