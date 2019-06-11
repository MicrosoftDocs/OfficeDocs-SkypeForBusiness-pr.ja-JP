---
title: Lync Server 2013 ネットワークインフラストラクチャの要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc1f74705469bf3a024d84848942eae972e0a629
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="233bf-102">Lync Server 2013 のネットワークインフラストラクチャ要件</span><span class="sxs-lookup"><span data-stu-id="233bf-102">Network infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="233bf-103">_**最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="233bf-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="233bf-104">Lync Server 2013 トポロジの各サーバーのネットワークアダプターカードは、少なくとも 1 gb/秒 (Gbps) をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="233bf-104">The network adapter card of each server in the Lync Server 2013 topology must support at least 1 gigabit per second (Gbps).</span></span> <span data-ttu-id="233bf-105">通常、低レイテンシおよび高帯域幅のローカルエリアネットワーク (LAN) を使用して、Lync Server トポロジ内のすべてのサーバーの役割を接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="233bf-105">In general, you should connect all server roles within the Lync Server topology using a low latency and high bandwidth local area network (LAN).</span></span> <span data-ttu-id="233bf-106">LAN のサイズは、トポロジーのサイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="233bf-106">The size of the LAN is dependent on the size of the topology:</span></span>

  - <span data-ttu-id="233bf-107">Standard Edition のトポロジでは、サーバーは 1 Gbps のイーサネットまたは同等のネットワークに対応している必要があります。</span><span class="sxs-lookup"><span data-stu-id="233bf-107">In Standard Edition topologies, servers should be in a network that supports 1 Gbps Ethernet or equivalent.</span></span>

  - <span data-ttu-id="233bf-108">フロントエンドプールトポロジでは、ほとんどのサーバーは 1 Gbps をサポートするネットワークに存在する必要があります。特に、音声/ビデオ (A/V) 会議とアプリケーション共有をサポートしている場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="233bf-108">In Front End pool topologies, most servers should be in a network that supports more than 1 Gbps, especially when supporting audio/video (A/V) conferencing and application sharing.</span></span>

<span data-ttu-id="233bf-109">公衆交換電話網 (PSTN) 統合については、T1 回線か E1 回線、または SIP トランキングを使用して統合できます。</span><span class="sxs-lookup"><span data-stu-id="233bf-109">For public switched telephone network (PSTN) integration, you can integrate by using either T1/E1 lines or SIP trunking.</span></span>

<div>

## <a name="audiovideo-network-requirements"></a><span data-ttu-id="233bf-110">音声/ビデオネットワークの要件</span><span class="sxs-lookup"><span data-stu-id="233bf-110">Audio/Video Network Requirements</span></span>

<span data-ttu-id="233bf-111">Lync Server の展開における音声/ビデオ (A/V) のネットワーク要件には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="233bf-111">Network requirements for audio/video (A/V) in a Lync Server deployment include the following:</span></span>

  - <span data-ttu-id="233bf-112">DNS 負荷分散を使用して1つのエッジサーバーまたはエッジプールを展開する場合は、外部ファイアウォールを NAT として構成できます。</span><span class="sxs-lookup"><span data-stu-id="233bf-112">If you are deploying a single Edge Server or an Edge pool using DNS load balancing, you can configure the external firewall as a NAT.</span></span> <span data-ttu-id="233bf-113">内部ファイアウォールを NAT として構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="233bf-113">You cannot configure the internal firewall as a NAT.</span></span> <span data-ttu-id="233bf-114">これらの要件の詳細については、計画ドキュメントの「 [Lync Server 2013 の外部の A/V ファイアウォールとポートの要件を確認](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="233bf-114">For details about these requirements, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) in the Planning documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="233bf-115">エッジプールを使用していて、ハードウェアロードバランサーを使っている場合は、各エッジサーバーでパブリック IP アドレスを使用する必要があります。また、nat デバイス (たとえば、ファイアウォール、または nat で接続されている他のインフラストラクチャデバイスなど) で NAT を使用することはできません。nd または outbound トラフィック)。</span><span class="sxs-lookup"><span data-stu-id="233bf-115">If you have an Edge pool and are using a hardware load balancer, you must use public IP addresses on each of the Edge Servers and you cannot use NAT for the servers or the pool at your NAT device (for example, the firewall, or other infrastructure device that would NAT inbound or outbound traffic).</span></span> <span data-ttu-id="233bf-116">詳細については、「外部ユーザーアクセスの計画」の「<A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">ポートの概要-ハードウェアロードバランサーでのスケール統合エッジとハードウェアロード2013バランサーの統合エッジ</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="233bf-116">For details, see <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A> in the Planning for External User Access documentation.</span></span>

    
    </div>

  - <span data-ttu-id="233bf-117">組織でサービスの品質 (QoS) インフラストラクチャが使用されている場合、メディア サブシステムは、この既存のインフラストラクチャで機能するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="233bf-117">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span>

  - <span data-ttu-id="233bf-118">インターネット プロトコル セキュリティ (IPsec) を使用する場合は、A/V トラフィックに使用するポート範囲に対する IPsec を無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="233bf-118">If you use Internet Protocol security (IPsec), we recommend disabling IPsec over the port ranges used for A/V traffic.</span></span> <span data-ttu-id="233bf-119">詳細については、計画ドキュメントの「 [Lync Server 2013 での IPsec の例外](lync-server-2013-ipsec-exceptions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="233bf-119">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

<span data-ttu-id="233bf-120">最適なメディア品質を得るには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="233bf-120">To ensure optimal media quality, do the following:</span></span>

  - <span data-ttu-id="233bf-121">有効期間中に、1秒あたり65キロビット (Kbps) のオーディオストリームと 500 Kbps のビデオストリームのスループットをサポートするように、ネットワークリンクをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="233bf-121">Provision your network links to support throughput of 65 kilobits per second (Kbps) per audio stream and 500 Kbps per video stream, if enabled, during peak usage periods.</span></span> <span data-ttu-id="233bf-122">双方向音声またはビデオセッションは、2つのストリームで構成されています。</span><span class="sxs-lookup"><span data-stu-id="233bf-122">A bidirectional audio or video session consists of two streams.</span></span>

  - <span data-ttu-id="233bf-123">このレベル上のトラフィックの予期しないスパイクや、時間の経過に伴う使用量の増加に対処するために、Lync Server メディアエンドポイントは、さまざまなネットワークの状態に対応し、オーディオとビデオの3倍のスループット (前の段落を参照) をサポートしています。許容できる品質を維持します。</span><span class="sxs-lookup"><span data-stu-id="233bf-123">To cope with unexpected spikes in traffic above this level and increased usage over time, Lync Server media endpoints can adapt to varying network conditions and support loads of three times the throughput (see previous paragraph) for audio and video while still retaining acceptable quality.</span></span> <span data-ttu-id="233bf-124">ただし、この適応性が、プロビジョニングされたネットワークをサポートしているとは限りません。</span><span class="sxs-lookup"><span data-stu-id="233bf-124">However, do not assume that this adaptability will support an under-provisioned network.</span></span> <span data-ttu-id="233bf-125">[プロビジョニングされたネットワーク] では、Lync Server メディアエンドポイントがさまざまなネットワーク条件 (たとえば、一時的な高パケット損失など) を動的に処理する機能が減少します。</span><span class="sxs-lookup"><span data-stu-id="233bf-125">In an under-provisioned network, the ability of the Lync Server media endpoints to dynamically deal with varying network conditions (for example, temporary high packet loss) is reduced.</span></span>

  - <span data-ttu-id="233bf-126">プロビジョニングが非常に困難で困難なネットワークリンクの場合は、低トラフィック量のプロビジョニングを検討することが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="233bf-126">For network links where provisioning is extremely costly and difficult, you may need to consider provisioning for a lower volume of traffic.</span></span> <span data-ttu-id="233bf-127">このシナリオでは、Lync Server メディアエンドポイントの弾力性によって、音声品質の一部が削減された場合のトラフィックボリュームとピークトラフィックレベルの違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="233bf-127">In this scenario, let the elasticity of the Lync Server media endpoints absorb the difference between the traffic volume and the peak traffic level, at the cost of some reduction in the voice quality.</span></span> <span data-ttu-id="233bf-128">また、ヘッドルームでは、トラフィックの急激なピークを吸収できるということもあります。</span><span class="sxs-lookup"><span data-stu-id="233bf-128">Also, there is a decrease in the headroom otherwise available to absorb sudden peaks in traffic.</span></span>

  - <span data-ttu-id="233bf-129">短期的には適切にプロビジョニングできないリンク (たとえば、非常に脆弱な WAN リンクを持つサイトなど) については、特定のユーザーのビデオを無効にすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="233bf-129">For links that cannot be correctly provisioned in the short term (for example, a site with very poor WAN links), consider disabling video for certain users.</span></span>

  - <span data-ttu-id="233bf-130">エンドツーエンドの遅延 (ミリ秒) の最大値である150ミリ秒 (ミリ秒) の上限になるようにネットワークをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="233bf-130">Provision your network to ensure a maximum end-to-end delay (latency) of 150 milliseconds (ms) under peak load.</span></span> <span data-ttu-id="233bf-131">待ち時間は、Lync Server メディアコンポーネントが削減できない1つのネットワーク障碍であり、弱点を見つけて除去することが重要です。</span><span class="sxs-lookup"><span data-stu-id="233bf-131">Latency is the one network impairment that Lync Server media components cannot reduce, and it is important to find and eliminate the weak points.</span></span>

  - <span data-ttu-id="233bf-132">ウイルス対策ソフトウェアを実行しているサーバーの場合は、最適なパフォーマンスと音質を実現するために、Lync Server を実行しているすべてのサーバーを例外の一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="233bf-132">For servers running antivirus software, include all servers running Lync Server in the exception list in order to provide optimal performance and audio quality.</span></span>

</div>

<div>

## <a name="conferencing-network-requirements"></a><span data-ttu-id="233bf-133">会議のネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="233bf-133">Conferencing Network Requirements</span></span>

<span data-ttu-id="233bf-134">インターネットインフォメーションサービス (IIS) サーバーから会議コンテンツをダウンロードするために使用される帯域幅は、アップロードされたコンテンツのサイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="233bf-134">The bandwidth that is used to download conference content from the Internet Information Services (IIS) server depends on the size of the content that is uploaded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

