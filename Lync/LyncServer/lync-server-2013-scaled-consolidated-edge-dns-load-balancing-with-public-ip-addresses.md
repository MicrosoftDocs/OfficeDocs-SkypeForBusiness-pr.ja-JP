---
title: 拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: 2b854f6d-3d3f-4961-a5f8-a03f47740df0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204761(v=OCS.15)
ms:contentKeyID: 48183698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8db90455704fcfd3337db3d5ade2bea7e32b844c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="68b89-102">Lync Server 2013 の拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="68b89-102">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68b89-103">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="68b89-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="68b89-p101">エッジ サーバー プール トポロジでは、複数のエッジ サーバーがデータ センターの境界ネットワークに負荷分散プールとして展開されます。 ドメイン ネーム システム (DNS) 負荷分散は、外部と内部両方のエッジ インターフェイスへのトラフィックに適用されます。</span><span class="sxs-lookup"><span data-stu-id="68b89-p101">In the Edge Server pool topology, two or more Edge Servers are deployed as a load-balanced pool in the perimeter network of the data center. Domain Name System (DNS) load balancing is used for traffic to both the external and internal Edge interfaces.</span></span>

<span data-ttu-id="68b89-106">組織で15000を超えるアクセスエッジサービスクライアント接続、1000アクティブ Lync Server Web 会議サービスクライアント接続、または500の同時音声ビデオエッジセッション、またはエッジサーバーの高可用性をサポートする必要がある場合、このトポロジはスケーラビリティとフェールオーバーのサポートの利点を提供します。</span><span class="sxs-lookup"><span data-stu-id="68b89-106">If your organization requires support for more than 15,000 Access Edge service client connections, 1,000 active Lync Server Web Conferencing service client connections, or 500 concurrent A/V Edge sessions, and/or high availability of the Edge Server is important, this topology offers the advantages of scalability and failover support.</span></span>

<span data-ttu-id="68b89-107">この図は、エッジサーバーとフロントエンドプールまたはサーバーの間の内部ネットワークに展開されたオプションのサーバーの役割であるディレクターを示していません。</span><span class="sxs-lookup"><span data-stu-id="68b89-107">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="68b89-108">ディレクターのトポロジの詳細については、「 [Lync Server 2013 でのディレクターに必要なコンポーネント](lync-server-2013-components-required-for-the-director.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68b89-108">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span> <span data-ttu-id="68b89-109">この図は、単一のリバース プロキシを表しています。</span><span class="sxs-lookup"><span data-stu-id="68b89-109">The figure represents a single reverse proxy.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="68b89-110">以下の図には、方向と IP アドレス指定の例が示されていますが、正しい受信トラフィックと送信トラフィックを使用した実際の通信フローを表すことを目的としていません。</span><span class="sxs-lookup"><span data-stu-id="68b89-110">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="68b89-111">図は、可能なトラフィックの大まかなビューを示しています。</span><span class="sxs-lookup"><span data-stu-id="68b89-111">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="68b89-112">着信 (リッスン ポートへの) および発信 (宛先サーバーまたはクライアントへの) に関連するトラフィック フローの詳細は、各シナリオのポートの概要図に示されています。</span><span class="sxs-lookup"><span data-stu-id="68b89-112">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="68b89-113">たとえば、実際には TCP 443 は着信 (エッジ プロキシまたはリバース プロキシへの) のみで、プロトコル (TCP) の観点から見た場合のみ双方向のフローになります。</span><span class="sxs-lookup"><span data-stu-id="68b89-113">For example, TCP 443 is actually inbound (to the Edge or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="68b89-114">さらに、図は、ネットワーク アドレス変換 (NAT) が発生したとき (着信で宛先アドレスが変更され、発信で発信元アドレスが変更されます) に変化するトラフィックの特性を示しています。</span><span class="sxs-lookup"><span data-stu-id="68b89-114">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="68b89-115">外部および内部ファイアウォールの例とサーバー インターフェイスは、参考としてのみ示されています。</span><span class="sxs-lookup"><span data-stu-id="68b89-115">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="68b89-116">最後に、必要な場合のために、既定のゲートウェイとルートの関係の例が示されています。</span><span class="sxs-lookup"><span data-stu-id="68b89-116">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="68b89-117">また、図では、リバースプロキシとエッジサーバーの両方の外部 DNS ゾーンを表すために<EM>.Com</EM> dns ゾーンを使用しており、 <EM>.net</EM> DNS ゾーンは内部 DNS ゾーンを参照していることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="68b89-117">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="68b89-118">Microsoft Lync Server 2013 の新規作成では、IPv6 アドレスのサポートがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="68b89-118">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="68b89-119">IPv4 アドレス指定と同じように、IPv6 アドレスを、割り当てられた IPv6 アドレス スペースの一部になるように割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="68b89-119">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="68b89-120">このトピックのアドレスは、例としてのみ使用されています。</span><span class="sxs-lookup"><span data-stu-id="68b89-120">The addresses in this topic are for example only.</span></span> <span data-ttu-id="68b89-121">展開で機能する IPv6 アドレスを取得して正しいスコープを指定し、内部および外部アドレスと相互運用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68b89-121">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="68b89-122">Windows Server では、二重化された IPv6 操作と IPv4 から IPv6 への通信にとって重要な機能が*デュアルスタック*と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="68b89-122">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="68b89-123">デュアル スタックは、IPv4 および IPv6 用の別個のネットワーク スタックです。</span><span class="sxs-lookup"><span data-stu-id="68b89-123">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="68b89-124">デュアル スタックを使用すると、IPv4 および IPv6 用のアドレスを同時に割り当て、要件に基づいて、サーバーが他のホストやクライアントと通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="68b89-124">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="68b89-125">IPv6 アドレス指定に使用する一般的なアドレスの種類は、IPv6 グローバルアドレス (パブリック IPv4 アドレスと類似)、IPv6 固有のローカルアドレス (プライベート IPv4 アドレスの範囲に類似)、IPv6 リンクローカルアドレス (自動プライベート IP に似ています) です。IPv4 用 Windows Server のアドレス)</span><span class="sxs-lookup"><span data-stu-id="68b89-125">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="68b89-126">IPv6 から IPv4 に変換 (一般に NAT64 と呼ばれます) したり、IPv6 から IPv6 に変換 (一般に NAT66 と呼ばれます) したりするネットワーク アドレス変換 (NAT) テクノロジが存在します。</span><span class="sxs-lookup"><span data-stu-id="68b89-126">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="68b89-127">NAT テクノロジが存在することは、Lync Server エッジサーバーに提示された5つのシナリオが引き続き有効であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="68b89-127">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]
> <span data-ttu-id="68b89-128">IPv6 は複雑なトピックで、Windows server レベルおよび Lync Server 2013 レベルで割り当てたアドレスが期待どおりに機能するように、ネットワークチームとインターネットプロバイダーについて慎重に計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68b89-128">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="68b89-129">IPv6 アドレス指定および計画に関するその他のリソースについては、このトピックの最後にあるリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="68b89-129">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="68b89-130">![7c1e3e6b-9b1b-4ac6-b0e7-9c256dbc2537](images/JJ204761.7c1e3e6b-9b1b-4ac6-b0e7-9c256dbc2537(OCS.15).jpg "7c1e3e6b-9b1b-4ac6-b0e7-9c256dbc2537")</span><span class="sxs-lookup"><span data-stu-id="68b89-130">![7c1e3e6b-9b1b-4ac6-b0e7-9c256dbc2537](images/JJ204761.7c1e3e6b-9b1b-4ac6-b0e7-9c256dbc2537(OCS.15).jpg "7c1e3e6b-9b1b-4ac6-b0e7-9c256dbc2537")</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="68b89-131">通話受付管理 (CAC) を使用している場合でも、エッジサーバーの内部インターフェイスに IPv4 アドレスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="68b89-131">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="68b89-132">CAC は IPv4 アドレスを使用しており、動作可能な IPv4 アドレスが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68b89-132">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="68b89-133">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="68b89-133">In This Section</span></span>

  - [<span data-ttu-id="68b89-134">証明書の概要-Lync Server 2013 での拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="68b89-134">Certificate summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="68b89-135">ポートの概要-Lync Server 2013 での拡張統合エッジ、パブリック IP アドレスを使用した DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="68b89-135">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="68b89-136">DNS の概要-Lync Server 2013 での拡張統合エッジ、パブリック IP アドレスを使用した DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="68b89-136">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="68b89-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="68b89-137">See Also</span></span>


[<span data-ttu-id="68b89-138">IP バージョン6アドレス指定アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="68b89-138">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="68b89-139">IPv6 グローバルユニキャストアドレス形式</span><span class="sxs-lookup"><span data-stu-id="68b89-139">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="68b89-140">一意のローカル IPv6 ユニキャストアドレス</span><span class="sxs-lookup"><span data-stu-id="68b89-140">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

