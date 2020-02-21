---
title: 'Lync Server 2013: ハードウェアロードバランサーによる拡張統合エッジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled consolidated edge with hardware load balancers
ms:assetid: 6783e225-9677-415a-8731-0bf2e2c4cf8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398478(v=OCS.15)
ms:contentKeyID: 48184353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a961b6eabb85e135b1cfb36cf5738cbf757b547
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="2887e-102">Lync Server 2013 での拡張統合エッジとロードバランサー機器</span><span class="sxs-lookup"><span data-stu-id="2887e-102">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2887e-103">_**トピックの最終更新日:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="2887e-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="2887e-104">エッジプールトポロジでは、2つ以上のエッジサーバーが、データセンターの境界ネットワークの負荷分散プールとして展開されます。</span><span class="sxs-lookup"><span data-stu-id="2887e-104">In the Edge pool topology, two or more Edge Servers are deployed as a load-balanced pool in the perimeter network of the data center.</span></span> <span data-ttu-id="2887e-105">ハードウェア負荷分散は、外部および内部エッジサーバーインターフェイスの両方へのトラフィックに使用されます。</span><span class="sxs-lookup"><span data-stu-id="2887e-105">Hardware load balancing is used for traffic to both the external and internal Edge Server interfaces.</span></span>

<span data-ttu-id="2887e-106">組織で15000を超えるアクセスエッジサービスクライアント接続、1000アクティブ Web 会議エッジサービスクライアント接続、または500の同時音声ビデオエッジサービスセッションのサポートが必要であり、エッジサーバーの高可用性が重要な場合、このトポロジはスケーラビリティとフェールオーバーのサポートの利点を提供します。</span><span class="sxs-lookup"><span data-stu-id="2887e-106">If your organization requires support for more than 15,000 Access Edge service client connections, 1,000 active Web Conferencing Edge service client connections, or 500 concurrent A/V Edge service sessions, and high availability of the Edge Server is important, this topology offers the advantages of scalability and failover support.</span></span>

<span data-ttu-id="2887e-107">この図は、エッジサーバーとフロントエンドプールまたはサーバーの間の内部ネットワークに展開されたオプションのサーバーの役割であるディレクターを示していません。</span><span class="sxs-lookup"><span data-stu-id="2887e-107">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="2887e-108">.</span><span class="sxs-lookup"><span data-stu-id="2887e-108">.</span></span> <span data-ttu-id="2887e-109">ディレクターのトポロジの詳細については、「 [Lync Server 2013 でのディレクターに必要なコンポーネント](lync-server-2013-components-required-for-the-director.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2887e-109">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2887e-110">図は方向や IP アドレス指定の例を示すものであり、正確な着信および発信トラフィックがある実際の通信フローを表現することが目的ではありません。</span><span class="sxs-lookup"><span data-stu-id="2887e-110">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="2887e-111">図は、可能なトラフィックの大まかなビューを示しています。</span><span class="sxs-lookup"><span data-stu-id="2887e-111">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="2887e-112">リスニング ポートへの着信および宛先サーバーまたはクライアントへの発信に関連するトラフィック フローの詳細が、シナリオごとにポートの概要図で示されています。</span><span class="sxs-lookup"><span data-stu-id="2887e-112">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="2887e-113">たとえば、TCP 443 は実際には受信 (エッジサーバーまたはリバースプロキシ) のみであり、プロトコル (TCP) の観点からの双方向のフローに過ぎません。</span><span class="sxs-lookup"><span data-stu-id="2887e-113">For example, TCP 443 is actually inbound (to the Edge Server or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="2887e-114">さらに、図は、NAT (ネットワーク アドレス変換) の発生時に変更されるトラフィックの性質を示しています (宛先アドレスは受信時に変更され、ソース アドレスは送信時に変更されます)。</span><span class="sxs-lookup"><span data-stu-id="2887e-114">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="2887e-115">外部および内部ファイアウォールの例とサーバー インターフェイスは、参考としてのみ示されています。</span><span class="sxs-lookup"><span data-stu-id="2887e-115">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="2887e-116">最後に、必要な場合のために、既定のゲートウェイとルートの関係の例が示されています。</span><span class="sxs-lookup"><span data-stu-id="2887e-116">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="2887e-117">また、図では、リバースプロキシとエッジサーバーの両方の外部 DNS ゾーンを表すために<EM>.Com</EM> dns ゾーンを使用しており、 <EM>.net</EM> DNS ゾーンは内部 DNS ゾーンを参照していることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="2887e-117">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="2887e-118">Microsoft Lync Server 2013 の新規作成では、IPv6 アドレスのサポートがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2887e-118">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="2887e-119">IPv4 アドレス指定と同じように、IPv6 アドレスを、割り当てられた IPv6 アドレス スペースの一部になるように割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2887e-119">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="2887e-120">このトピックのアドレスは、例としてのみ使用されています。</span><span class="sxs-lookup"><span data-stu-id="2887e-120">The addresses in this topic are for example only.</span></span> <span data-ttu-id="2887e-121">展開で機能する IPv6 アドレスを取得して正しいスコープを指定し、内部および外部アドレスと相互運用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2887e-121">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="2887e-122">Windows Server では、二重化された IPv6 操作と IPv4 から IPv6 への通信にとって重要な機能が*デュアルスタック*と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="2887e-122">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="2887e-123">デュアル スタックは、IPv4 および IPv6 用の別個のネットワーク スタックです。</span><span class="sxs-lookup"><span data-stu-id="2887e-123">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="2887e-124">デュアル スタックを使用すると、IPv4 および IPv6 用のアドレスを同時に割り当て、要件に基づいて、サーバーが他のホストやクライアントと通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2887e-124">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="2887e-125">IPv6 アドレス指定に使用する一般的なアドレスの種類は、IPv6 グローバルアドレス (パブリック IPv4 アドレスと類似)、IPv6 固有のローカルアドレス (プライベート IPv4 アドレスの範囲に類似)、IPv6 リンクローカルアドレス (自動プライベート IP に似ています) です。IPv4 用 Windows Server のアドレス)</span><span class="sxs-lookup"><span data-stu-id="2887e-125">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="2887e-126">IPv6 から IPv4 に変換 (一般に NAT64 と呼ばれます) したり、IPv6 から IPv6 に変換 (一般に NAT66 と呼ばれます) したりするネットワーク アドレス変換 (NAT) テクノロジが存在します。</span><span class="sxs-lookup"><span data-stu-id="2887e-126">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="2887e-127">NAT テクノロジが存在することは、Lync Server エッジサーバーに提示された5つのシナリオが引き続き有効であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2887e-127">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="2887e-128">IPv6 は複雑なトピックで、Windows server レベルおよび Lync Server 2013 レベルで割り当てたアドレスが期待どおりに機能するように、ネットワークチームとインターネットプロバイダーについて慎重に計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2887e-128">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="2887e-129">IPv6 アドレス指定と計画に関するその他の技術情報については、このトピックの最後にあるリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2887e-129">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="2887e-130">**ハードウェア ロード バランサーの構成**</span><span class="sxs-lookup"><span data-stu-id="2887e-130">**Hardware Load Balancer Configuration**</span></span>

<span data-ttu-id="2887e-131">詳細については、「 [Lync Server 2013 の外部ユーザーアクセスに必要なコンポーネント](lync-server-2013-components-required-for-external-user-access.md)」の「音声ビデオエッジに対するハードウェアロードバランサーの要件」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2887e-131">For details, see the “Hardware Load Balancer Requirements for A/V Edge” section in [Components required for external user access in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span></span>

<span data-ttu-id="2887e-132">**拡張統合エッジ トポロジ (ハードウェア負荷分散)**</span><span class="sxs-lookup"><span data-stu-id="2887e-132">**Scaled consolidated edge topology (hardware load balanced)**</span></span>

<span data-ttu-id="2887e-133">![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")</span><span class="sxs-lookup"><span data-stu-id="2887e-133">![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2887e-134">通話受付管理 (CAC) を使用している場合でも、エッジサーバーの内部インターフェイスに IPv4 アドレスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2887e-134">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="2887e-135">CAC は IPv4 アドレスを使用しており、動作可能な IPv4 アドレスが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2887e-135">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2887e-136">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2887e-136">In This Section</span></span>

  - [<span data-ttu-id="2887e-137">証明書の概要-Lync Server 2013 でのハードウェアロードバランサーを使用した拡張統合エッジ</span><span class="sxs-lookup"><span data-stu-id="2887e-137">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="2887e-138">ポートの概要-Lync Server 2013 の拡張統合エッジ (ロードバランサー機器を含む)</span><span class="sxs-lookup"><span data-stu-id="2887e-138">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="2887e-139">DNS の概要-Lync Server 2013 でのハードウェアロードバランサーを使用した拡張統合エッジ</span><span class="sxs-lookup"><span data-stu-id="2887e-139">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2887e-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="2887e-140">See Also</span></span>


[<span data-ttu-id="2887e-141">IP バージョン6アドレス指定アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="2887e-141">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="2887e-142">IPv6 グローバルユニキャストアドレス形式</span><span class="sxs-lookup"><span data-stu-id="2887e-142">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="2887e-143">一意のローカル IPv6 ユニキャストアドレス</span><span class="sxs-lookup"><span data-stu-id="2887e-143">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

