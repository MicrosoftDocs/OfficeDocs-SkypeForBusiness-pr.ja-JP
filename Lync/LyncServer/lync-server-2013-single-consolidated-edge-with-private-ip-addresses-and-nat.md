---
title: 'Lync Server 2013: プライベート IP アドレスと NAT を使用する単一統合エッジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Single consolidated edge with private IP addresses and NAT
ms:assetid: e1e5189e-f17d-45e9-b177-e0e6f97f8951
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399001(v=OCS.15)
ms:contentKeyID: 48185691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b18284a74c1825fddbd0f8dbc3e0aaa5e6c582b9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519784"
---
# <a name="single-consolidated-edge-with-private-ip-addresses-and-nat-in-lync-server-2013"></a><span data-ttu-id="6b8f4-102">Lync Server 2013 でのプライベート IP アドレスと NAT を使用する単一統合エッジ</span><span class="sxs-lookup"><span data-stu-id="6b8f4-102">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b8f4-103">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="6b8f4-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="6b8f4-104">組織で15000アクセスエッジサービスクライアント接続のサポートが必要な場合、1000アクティブな Lync Server Web 会議サービスクライアント接続、および500の同時音声ビデオエッジセッション、およびエッジサーバーの高可用性は重要ではないため、このトポロジでは、ハードウェアコストの削減と展開の簡素化という利点がありません。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-104">If your organization requires support for fewer than 15,000 Access Edge service client connections, 1,000 active Lync Server Web Conferencing service client connections, and 500 concurrent A/V Edge sessions, and high availability of the Edge Server is not important, this topology offers the advantages of lower hardware cost and simpler deployment.</span></span> <span data-ttu-id="6b8f4-105">より多くの容量が必要な場合、または高可用性が必要な場合は、拡張統合エッジサーバートポロジを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-105">If you need greater capacity or you require high availability, you need to deploy a scaled consolidated Edge Server topology.</span></span> <span data-ttu-id="6b8f4-106">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-106">For details, see one of the following:</span></span>

  - <span></span>  
    [<span data-ttu-id="6b8f4-107">Lync Server 2013 での拡張統合エッジ、NAT を使用したプライベート IP アドレスを使用した DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="6b8f4-107">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [<span data-ttu-id="6b8f4-108">Lync Server 2013 の拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="6b8f4-108">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [<span data-ttu-id="6b8f4-109">Lync Server 2013 での拡張統合エッジとロードバランサー機器</span><span class="sxs-lookup"><span data-stu-id="6b8f4-109">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<span data-ttu-id="6b8f4-110">この図は、エッジサーバーとフロントエンドプールまたはサーバーの間の内部ネットワークに展開されたオプションのサーバーの役割であるディレクターを示していません。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-110">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="6b8f4-111">ディレクターのトポロジの詳細については、「 [Lync Server 2013 でのディレクターに必要なコンポーネント](lync-server-2013-components-required-for-the-director.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-111">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span> <span data-ttu-id="6b8f4-112">この図は、単一のリバース プロキシを表しています。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-112">The figure represents a single reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6b8f4-113">以下の図には、方向と IP アドレス指定の例が示されていますが、正しい受信トラフィックと送信トラフィックを使用した実際の通信フローを表すことを目的としていません。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-113">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="6b8f4-114">図は、可能なトラフィックの大まかなビューを示しています。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-114">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="6b8f4-115">着信 (リッスン ポートへの) および発信 (宛先サーバーまたはクライアントへの) に関連するトラフィック フローの詳細は、各シナリオのポートの概要図に示されています。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-115">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="6b8f4-116">たとえば、実際には TCP 443 は着信 (エッジ プロキシまたはリバース プロキシへの) のみで、プロトコル (TCP) の観点から見た場合のみ双方向のフローになります。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-116">For example, TCP 443 is actually inbound (to the Edge or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="6b8f4-117">さらに、図は、ネットワーク アドレス変換 (NAT) が発生したとき (着信で宛先アドレスが変更され、発信で発信元アドレスが変更されます) に変化するトラフィックの特性を示しています。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-117">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="6b8f4-118">外部および内部ファイアウォールの例とサーバー インターフェイスは、参考としてのみ示されています。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-118">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="6b8f4-119">最後に、必要な場合のために、既定のゲートウェイとルートの関係の例が示されています。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-119">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="6b8f4-120">また、図では、リバースプロキシとエッジサーバーの両方の外部 DNS ゾーンを表すために <EM>.Com</EM> dns ゾーンを使用しており、 <EM>.net</EM> DNS ゾーンは内部 DNS ゾーンを参照していることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-120">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="6b8f4-121">Microsoft Lync Server 2013 の新規作成では、IPv6 アドレスのサポートがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-121">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="6b8f4-122">IPv4 アドレス指定と同じように、IPv6 アドレスを、割り当てられた IPv6 アドレス スペースの一部になるように割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-122">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="6b8f4-123">このトピックのアドレスは、例としてのみ使用されています。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-123">The addresses in this topic are for example only.</span></span> <span data-ttu-id="6b8f4-124">展開で機能する IPv6 アドレスを取得して正しいスコープを指定し、内部および外部アドレスと相互運用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-124">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="6b8f4-125">Windows Server では、二重化された IPv6 操作と IPv4 から IPv6 への通信にとって重要な機能が *デュアルスタック*と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-125">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="6b8f4-126">デュアル スタックは、IPv4 および IPv6 用の別個のネットワーク スタックです。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-126">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="6b8f4-127">デュアル スタックを使用すると、IPv4 および IPv6 用のアドレスを同時に割り当て、要件に基づいて、サーバーが他のホストやクライアントと通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-127">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="6b8f4-128">IPv6 アドレス指定に使用する一般的なアドレスの種類は、IPv6 グローバルアドレス (パブリック IPv4 アドレスと類似)、IPv6 の一意のローカルアドレス (プライベート IPv4 アドレスの範囲に似ている)、IPv6 リンクローカルアドレス (Windows Server の IPv4 では自動プライベート IP アドレスに似ています) です。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-128">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="6b8f4-129">IPv6 から IPv4 に変換 (一般に NAT64 と呼ばれます) したり、IPv6 から IPv6 に変換 (一般に NAT66 と呼ばれます) したりするネットワーク アドレス変換 (NAT) テクノロジが存在します。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-129">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="6b8f4-130">NAT テクノロジが存在することは、Lync Server エッジサーバーに提示された5つのシナリオが引き続き有効であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-130">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="6b8f4-131">IPv6 は複雑なトピックで、Windows server レベルおよび Lync Server 2013 レベルで割り当てたアドレスが期待どおりに機能するように、ネットワークチームとインターネットプロバイダーについて慎重に計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-131">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="6b8f4-132">IPv6 アドレス指定および計画に関するその他のリソースについては、このトピックの最後にあるリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-132">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="6b8f4-133">**単一統合エッジトポロジ**</span><span class="sxs-lookup"><span data-stu-id="6b8f4-133">**Single consolidated edge topology**</span></span>

<span data-ttu-id="6b8f4-134">![d9b889c1-587c-4732-9b68-841186ccff78](images/Gg399001.d9b889c1-587c-4732-9b68-841186ccff78(OCS.15).jpg "d9b889c1-587c-4732-9b68-841186ccff78")</span><span class="sxs-lookup"><span data-stu-id="6b8f4-134">![d9b889c1-587c-4732-9b68-841186ccff78](images/Gg399001.d9b889c1-587c-4732-9b68-841186ccff78(OCS.15).jpg "d9b889c1-587c-4732-9b68-841186ccff78")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6b8f4-135">通話受付管理 (CAC) を使用している場合でも、エッジサーバーの内部インターフェイスに IPv4 アドレスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-135">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="6b8f4-136">CAC は IPv4 アドレスを使用しており、動作可能な IPv4 アドレスが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b8f4-136">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6b8f4-137">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6b8f4-137">In This Section</span></span>

  - [<span data-ttu-id="6b8f4-138">証明書の概要-Lync Server 2013 で NAT を使用するプライベート IP アドレスを持つ単一統合エッジ</span><span class="sxs-lookup"><span data-stu-id="6b8f4-138">Certificate summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="6b8f4-139">ポートの概要-Lync Server 2013 で NAT を使用するプライベート IP アドレスを持つ単一統合エッジ</span><span class="sxs-lookup"><span data-stu-id="6b8f4-139">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="6b8f4-140">DNS の概要-Lync Server 2013 で NAT を使用するプライベート IP アドレスを持つ単一統合エッジ</span><span class="sxs-lookup"><span data-stu-id="6b8f4-140">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6b8f4-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b8f4-141">See Also</span></span>


[<span data-ttu-id="6b8f4-142">IP バージョン6アドレス指定アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="6b8f4-142">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="6b8f4-143">IPv6 グローバルユニキャストアドレス形式</span><span class="sxs-lookup"><span data-stu-id="6b8f4-143">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="6b8f4-144">一意のローカル IPv6 ユニキャストアドレス</span><span class="sxs-lookup"><span data-stu-id="6b8f4-144">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

