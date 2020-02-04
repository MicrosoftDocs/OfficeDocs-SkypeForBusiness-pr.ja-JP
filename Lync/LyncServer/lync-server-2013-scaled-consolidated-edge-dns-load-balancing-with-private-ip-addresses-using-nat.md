---
title: 'Lync Server 2013: 拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: c7ca4ca8-c639-4d93-86d7-8891170cacbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398823(v=OCS.15)
ms:contentKeyID: 48185369
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a61ba63ca71cb22ec4b526ab090b9ee7a55dc231
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="59645-102">Lync Server 2013 における拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="59645-102">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59645-103">_**最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="59645-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="59645-104">エッジサーバープールトポロジでは、2つ以上のエッジサーバーが、データセンターの境界ネットワークの負荷分散プールとして展開されます。</span><span class="sxs-lookup"><span data-stu-id="59645-104">In the Edge Server pool topology, two or more Edge Servers are deployed as a load-balanced pool in the perimeter network of the data center.</span></span> <span data-ttu-id="59645-105">ドメインネームシステム (DNS) 負荷分散は、外部と内部のエッジインターフェイスの両方へのトラフィックに使用されます。</span><span class="sxs-lookup"><span data-stu-id="59645-105">Domain Name System (DNS) load balancing is used for traffic to both the external and internal Edge interfaces.</span></span>

<span data-ttu-id="59645-106">15000アクセスエッジサービスのクライアント接続のサポートが必要な場合、1000のアクティブな Lync Server Web 会議サービスクライアント接続、500または microsoft Edge Server の高可用性のサポートが重要である場合は、このトポロジでスケーラビリティとフェールオーバーのサポートについての利点があります。</span><span class="sxs-lookup"><span data-stu-id="59645-106">If your organization requires support for more than 15,000 Access Edge service client connections, 1,000 active Lync Server Web Conferencing service client connections, or 500 concurrent A/V Edge sessions, and/or high availability of the Edge Server is important, this topology offers the advantages of scalability and failover support.</span></span>

<span data-ttu-id="59645-107">この図には、エッジサーバーとフロントエンドプールまたはサーバー間の内部ネットワークに展開されたオプションのサーバー役割であるダイレクタは表示されません。</span><span class="sxs-lookup"><span data-stu-id="59645-107">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="59645-108">ディレクターのトポロジの詳細については、「 [Lync Server 2013 でディレクターに必要なコンポーネント](lync-server-2013-components-required-for-the-director.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59645-108">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span> <span data-ttu-id="59645-109">この図は、単一の逆プロキシを示しています。</span><span class="sxs-lookup"><span data-stu-id="59645-109">The figure represents a single reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="59645-110">次の図は、向きと IP アドレス指定の例を示していますが、正しい着信トラフィックと発信トラフィックでの実際の通信フローを示すものではありません。</span><span class="sxs-lookup"><span data-stu-id="59645-110">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="59645-111">この図は、可能なトラフィックの高レベルビューを示しています。</span><span class="sxs-lookup"><span data-stu-id="59645-111">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="59645-112">着信 (リッスンするポート) に関連するトラフィックフローと送信 (送信先サーバーまたはクライアント) は、各シナリオの [ポートの概要] ダイアグラムで表されます。</span><span class="sxs-lookup"><span data-stu-id="59645-112">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="59645-113">たとえば、TCP 443 は実際には (エッジまたは逆プロキシに対する) 受信のみであり、プロトコル (TCP) の観点からの双方向のフローにすぎません。</span><span class="sxs-lookup"><span data-stu-id="59645-113">For example, TCP 443 is actually inbound (to the Edge or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="59645-114">また、この図では、NAT (ネットワークアドレス変換) が発生したときのトラフィックの性質を示しています (宛先のアドレスが受信時に変更されると、送信時にソースアドレスが変更されます)。</span><span class="sxs-lookup"><span data-stu-id="59645-114">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="59645-115">外部および内部ファイアウォールの例とサーバーインターフェイスは、参照目的でのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="59645-115">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="59645-116">最後に、既定のゲートウェイとルートリレーションシップの例を示します (該当する場合)。</span><span class="sxs-lookup"><span data-stu-id="59645-116">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="59645-117">また、図では、リバースプロキシとエッジサーバーの両方の外部 DNS ゾーンを示すために<EM>.Com</EM> dns ゾーンを使用し、 <EM>.net</EM> DNS ゾーンは内部 dns ゾーンを参照していることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="59645-117">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="59645-118">Microsoft Lync Server 2013 の新機能は、IPv6 アドレス指定をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="59645-118">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="59645-119">IPv4 アドレス指定と同じように、IPv6 アドレスは、割り当てられている IPv6 アドレス空間の一部であるため、アドレスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="59645-119">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="59645-120">このトピックの住所は、例としてのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="59645-120">The addresses in this topic are for example only.</span></span> <span data-ttu-id="59645-121">展開で機能する IPv6 アドレスを取得し、適切なスコープを指定して、内部および外部のアドレス指定と相互運用されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="59645-121">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="59645-122">Windows Server では、2つの*スタック*と呼ばれる、ipv6 操作と IPv4 から ipv6 への通信に重要な機能が提供されています。</span><span class="sxs-lookup"><span data-stu-id="59645-122">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="59645-123">デュアルスタックは、IPv4 と IPv6 のための独立した個別のネットワークスタックです。</span><span class="sxs-lookup"><span data-stu-id="59645-123">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="59645-124">デュアルスタックでは、IPv4 と IPv6 のアドレスを同時に割り当てることができます。また、要件に基づいてサーバーが他のホストやクライアントと通信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="59645-124">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="59645-125">IPv6 アドレス指定に使用する一般的なアドレスの種類は、IPv6 のグローバルアドレス (パブリック IPv4 アドレスに似ています)、ipv6 固有のローカルアドレス (プライベート IPv4 アドレスの範囲に似ています)、IPv6 リンクローカルアドレス (自動プライベート IP に類似) です。IPv4 用 Windows Server のアドレス</span><span class="sxs-lookup"><span data-stu-id="59645-125">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="59645-126">IPv6 向けのネットワークアドレス変換技術 (NAT) が存在します。これにより、NAT IPv6 (通常は、NAT64 とも呼ばれます) と NAT IPv6 (通常は NAT66 と呼ばれます) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="59645-126">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="59645-127">NAT 技術が存在することは、Lync Server Edge サーバーに対して提示された5つのシナリオが有効であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="59645-127">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="59645-128">IPv6 は複雑なトピックであり、ネットワークチームとインターネットプロバイダーによる慎重な計画を行う必要があります。これにより、Windows server レベルで割り当てるアドレスと Lync Server 2013 レベルで割り当てたアドレスが予期したとおりに動作するようになります。</span><span class="sxs-lookup"><span data-stu-id="59645-128">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="59645-129">IPv6 のアドレス指定と計画に関するその他のリソースについては、このトピックの最後にあるリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="59645-129">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="59645-130">![899546d4-2eef4-4d2-8317-51c5f699cd2a](images/Gg398823.899546d4-2eef-44d2-8317-51c5f699cd2a(OCS.15).jpg "899546d4-2eef4-4d2-8317-51c5f699cd2a")</span><span class="sxs-lookup"><span data-stu-id="59645-130">![899546d4-2eef-44d2-8317-51c5f699cd2a](images/Gg398823.899546d4-2eef-44d2-8317-51c5f699cd2a(OCS.15).jpg "899546d4-2eef-44d2-8317-51c5f699cd2a")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="59645-131">通話受付制御 (CAC) を使用している場合でも、エッジサーバーの内部インターフェイスに IPv4 アドレスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="59645-131">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="59645-132">CAC は IPv4 アドレスを使用し、操作には使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="59645-132">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="59645-133">このセクション中</span><span class="sxs-lookup"><span data-stu-id="59645-133">In This Section</span></span>

  - [<span data-ttu-id="59645-134">証明書の概要 - Lync Server 2013 での拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="59645-134">Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)

  - [<span data-ttu-id="59645-135">ポートの概要 - Lync Server 2013 における拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="59645-135">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="59645-136">DNS の概要 - Lync Server 2013 での拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="59645-136">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="59645-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="59645-137">See Also</span></span>


[<span data-ttu-id="59645-138">IP バージョン6アドレス体系</span><span class="sxs-lookup"><span data-stu-id="59645-138">IP Version 6 Addressing Architecture</span></span>](http://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="59645-139">IPv6 グローバルユニキャストアドレス形式</span><span class="sxs-lookup"><span data-stu-id="59645-139">IPv6 Global Unicast Address Format</span></span>](http://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="59645-140">一意のローカル IPv6 ユニキャストアドレス</span><span class="sxs-lookup"><span data-stu-id="59645-140">Unique Local IPv6 Unicast Addresses</span></span>](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

