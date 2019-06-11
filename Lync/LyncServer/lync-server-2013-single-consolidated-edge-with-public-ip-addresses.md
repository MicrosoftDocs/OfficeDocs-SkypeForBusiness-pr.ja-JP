---
title: 'Lync Server 2013: パブリック IP アドレスを使用する単一統合エッジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Single consolidated edge with public IP addresses
ms:assetid: a92d1179-6a1f-4efe-908a-f8dfc5024f30
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205148(v=OCS.15)
ms:contentKeyID: 48185035
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bf6655c596be657d1779a404c6f1f5b108f3251
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="bb63a-102">Lync Server 2013 のパブリック IP アドレスを使用する単一統合エッジ</span><span class="sxs-lookup"><span data-stu-id="bb63a-102">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb63a-103">_**最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="bb63a-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="bb63a-104">15000アクセスエッジサービスクライアント接続、1000アクティブな Lync Server Web 会議サービスクライアント接続、および500の同時 A/V Edge セッションのサポートが必要な場合、エッジサーバーの高可用性は重要ではありません。このトポロジでは、ハードウェアコストの削減と展開の簡素化という利点が提供されます。</span><span class="sxs-lookup"><span data-stu-id="bb63a-104">If your organization needs support for fewer than 15,000 Access Edge service client connections, 1,000 active Lync Server Web Conferencing service client connections, and 500 concurrent A/V Edge sessions, and high availability of the Edge Server is not important, this topology offers the advantages of lower hardware cost and simpler deployment.</span></span> <span data-ttu-id="bb63a-105">容量を増やす必要がある場合、または高可用性が必要な場合は、スケーリングされた統合エッジサーバートポロジを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb63a-105">If you need greater capacity or you require high availability, you should deploy a scaled consolidated Edge Server topology.</span></span>

  - <span></span>  
    [<span data-ttu-id="bb63a-106">Lync Server 2013 における拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="bb63a-106">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [<span data-ttu-id="bb63a-107">Lync Server 2013 での拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="bb63a-107">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [<span data-ttu-id="bb63a-108">Lync Server 2013 のハードウェア ロード バランサーによる拡張統合エッジ</span><span class="sxs-lookup"><span data-stu-id="bb63a-108">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bb63a-109">エッジサーバーでパブリック IP アドレスを使用している場合、エッジサーバー上の既定のゲートウェイは、ファイアウォールまたはルーターではなく、公開されている境界エッジのルーターまたはファイアウォールで、パブリックアドレスになります。</span><span class="sxs-lookup"><span data-stu-id="bb63a-109">When using public IP address on the Edge Server, the default gateway on the Edge Server is no longer your firewall or router, but the router or firewall at your public perimeter edge – which will be a public address.</span></span> <span data-ttu-id="bb63a-110">リバースプロキシは、外部境界ネットワークに関連付けられているルーターまたはファイアウォールを引き続き使用します。</span><span class="sxs-lookup"><span data-stu-id="bb63a-110">The reverse proxy continues to use the router or firewall associated with the outermost perimeter network.</span></span> <span data-ttu-id="bb63a-111">リバースプロキシとパブリック IP アドレスを使ったエッジサーバーの違いは、リバースプロキシが依然として NAT を使用していて、エッジサーバーがルートリレーションシップを使用していることです。</span><span class="sxs-lookup"><span data-stu-id="bb63a-111">The difference between the reverse proxy and the Edge Server with public IP addresses is that the reverse proxy is still using NAT and the Edge Server is using a route relationship.</span></span>



</div>

<span data-ttu-id="bb63a-112">この図には、エッジサーバーとフロントエンドプールまたはサーバー間の内部ネットワークに展開されたオプションのサーバー役割であるダイレクタは表示されません。</span><span class="sxs-lookup"><span data-stu-id="bb63a-112">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="bb63a-113">ディレクターのトポロジの詳細については、「 [Lync Server 2013 でディレクターに必要なコンポーネント](lync-server-2013-components-required-for-the-director.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb63a-113">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span> <span data-ttu-id="bb63a-114">この図は、単一の逆プロキシを示しています。</span><span class="sxs-lookup"><span data-stu-id="bb63a-114">The figure represents a single reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bb63a-115">次の図は、向きと IP アドレス指定の例を示していますが、正しい着信トラフィックと発信トラフィックでの実際の通信フローを示すものではありません。</span><span class="sxs-lookup"><span data-stu-id="bb63a-115">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="bb63a-116">この図は、可能なトラフィックの高レベルビューを示しています。</span><span class="sxs-lookup"><span data-stu-id="bb63a-116">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="bb63a-117">着信 (リッスンするポート) に関連するトラフィックフローと送信 (送信先サーバーまたはクライアント) は、各シナリオの [ポートの概要] ダイアグラムで表されます。</span><span class="sxs-lookup"><span data-stu-id="bb63a-117">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="bb63a-118">たとえば、TCP 443 は実際には (エッジまたは逆プロキシに対する) 受信のみであり、プロトコル (TCP) の観点からの双方向のフローにすぎません。</span><span class="sxs-lookup"><span data-stu-id="bb63a-118">For example, TCP 443 is actually inbound (to the Edge or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="bb63a-119">また、この図では、NAT (ネットワークアドレス変換) が発生したときのトラフィックの性質を示しています (宛先のアドレスが受信時に変更されると、送信時にソースアドレスが変更されます)。</span><span class="sxs-lookup"><span data-stu-id="bb63a-119">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="bb63a-120">外部および内部ファイアウォールの例とサーバーインターフェイスは、参照目的でのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb63a-120">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="bb63a-121">最後に、既定のゲートウェイとルートリレーションシップの例を示します (該当する場合)。</span><span class="sxs-lookup"><span data-stu-id="bb63a-121">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="bb63a-122">また、図では、リバースプロキシとエッジサーバーの両方の外部 DNS ゾーンを示すために<EM>.Com</EM> dns ゾーンを使用し、 <EM>.net</EM> DNS ゾーンは内部 dns ゾーンを参照していることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="bb63a-122">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="bb63a-123">Microsoft Lync Server 2013 の新機能は、IPv6 アドレス指定をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="bb63a-123">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="bb63a-124">IPv4 アドレス指定と同じように、IPv6 アドレスは、割り当てられている IPv6 アドレス空間の一部であるため、アドレスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb63a-124">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="bb63a-125">このトピックの住所は、例としてのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="bb63a-125">The addresses in this topic are for example only.</span></span> <span data-ttu-id="bb63a-126">展開で機能する IPv6 アドレスを取得し、適切なスコープを指定して、内部および外部のアドレス指定と相互運用されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb63a-126">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="bb63a-127">Windows Server では、2つの*スタック*と呼ばれる、ipv6 操作と IPv4 から ipv6 への通信に重要な機能が提供されています。</span><span class="sxs-lookup"><span data-stu-id="bb63a-127">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="bb63a-128">デュアルスタックは、IPv4 と IPv6 のための独立した個別のネットワークスタックです。</span><span class="sxs-lookup"><span data-stu-id="bb63a-128">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="bb63a-129">デュアルスタックでは、IPv4 と IPv6 のアドレスを同時に割り当てることができます。また、要件に基づいてサーバーが他のホストやクライアントと通信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="bb63a-129">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="bb63a-130">IPv6 アドレス指定に使用する一般的なアドレスの種類は、IPv6 のグローバルアドレス (パブリック IPv4 アドレスに似ています)、ipv6 固有のローカルアドレス (プライベート IPv4 アドレスの範囲に似ています)、IPv6 リンクローカルアドレス (自動プライベート IP に類似) です。IPv4 用 Windows Server のアドレス</span><span class="sxs-lookup"><span data-stu-id="bb63a-130">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="bb63a-131">IPv6 向けのネットワークアドレス変換技術 (NAT) が存在します。これにより、NAT IPv6 (通常は、NAT64 とも呼ばれます) と NAT IPv6 (通常は NAT66 と呼ばれます) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bb63a-131">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="bb63a-132">NAT 技術が存在することは、Lync Server Edge サーバーに対して提示された5つのシナリオが有効であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="bb63a-132">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="bb63a-133">IPv6 は複雑なトピックであり、ネットワークチームとインターネットプロバイダーによる慎重な計画を行う必要があります。これにより、Windows server レベルで割り当てるアドレスと Lync Server 2013 レベルで割り当てたアドレスが予期したとおりに動作するようになります。</span><span class="sxs-lookup"><span data-stu-id="bb63a-133">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="bb63a-134">IPv6 のアドレス指定と計画に関するその他のリソースについては、このトピックの最後にあるリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb63a-134">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="bb63a-135">**パブリック IP アドレスのトポロジを使った単一の統合エッジ**</span><span class="sxs-lookup"><span data-stu-id="bb63a-135">**Single Consolidated Edge with Public IP Addresses topology**</span></span>

<span data-ttu-id="bb63a-136">![2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d](images/JJ205148.2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d(OCS.15).jpg "2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d")</span><span class="sxs-lookup"><span data-stu-id="bb63a-136">![2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d](images/JJ205148.2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d(OCS.15).jpg "2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bb63a-137">通話受付制御 (CAC) を使用している場合でも、エッジサーバーの内部インターフェイスに IPv4 アドレスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb63a-137">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="bb63a-138">CAC は IPv4 アドレスを使用し、操作には使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb63a-138">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bb63a-139">このセクション中</span><span class="sxs-lookup"><span data-stu-id="bb63a-139">In This Section</span></span>

  - [<span data-ttu-id="bb63a-140">証明書の概要 - Lync Server 2013 のパブリック IP アドレスを使用する単一の統合エッジ</span><span class="sxs-lookup"><span data-stu-id="bb63a-140">Certificate summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="bb63a-141">ポートの概要 - Lync Server 2013 でパブリック IP アドレスを使用する単一の統合エッジ</span><span class="sxs-lookup"><span data-stu-id="bb63a-141">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="bb63a-142">DNS の概要 - Lync Server 2013 でパブリック IP アドレスを持つ単一統合エッジ</span><span class="sxs-lookup"><span data-stu-id="bb63a-142">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bb63a-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb63a-143">See Also</span></span>


[<span data-ttu-id="bb63a-144">IP バージョン6アドレス体系</span><span class="sxs-lookup"><span data-stu-id="bb63a-144">IP Version 6 Addressing Architecture</span></span>](http://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="bb63a-145">IPv6 グローバルユニキャストアドレス形式</span><span class="sxs-lookup"><span data-stu-id="bb63a-145">IPv6 Global Unicast Address Format</span></span>](http://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="bb63a-146">一意のローカル IPv6 ユニキャストアドレス</span><span class="sxs-lookup"><span data-stu-id="bb63a-146">Unique Local IPv6 Unicast Addresses</span></span>](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

