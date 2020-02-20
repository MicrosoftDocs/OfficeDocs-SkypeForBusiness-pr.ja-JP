---
title: 'Lync Server 2013: エッジサーバーのネットワークインターフェイスの設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up network interfaces for Edge Servers
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412847(v=OCS.15)
ms:contentKeyID: 48185152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7e736a7782908479e670b7127c7518e044978ca
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a><span data-ttu-id="1c65a-102">Lync Server 2013 でのエッジサーバーのネットワークインターフェイスの設定</span><span class="sxs-lookup"><span data-stu-id="1c65a-102">Set up network interfaces for Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c65a-103">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="1c65a-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="1c65a-p101">各エッジ サーバーは、外部インターフェイスと内部インターフェイスを備えたマルチホーム コンピューターです。アダプターのドメイン ネーム システム (DNS) 設定は、境界ネットワークに DNS サーバーがあるかどうかによって異なります。境界に DNS サーバーが存在する場合は、次ホップのサーバーまたはプール (すなわち、ディレクターまたは指定されたフロントエンド プール) に対する 1 つ以上の DNS A レコードが含まれるゾーンが登録されている必要があります。外部クエリの場合は、名前参照を他のパブリック DNS サーバーに照会します。境界に DNS サーバーが存在しない場合、エッジ サーバーは外部 DNS サーバーを使用してインターネット上の名前参照を解決し、各エッジ サーバーは HOST ファイルを使用して次ホップ サーバーの名前を IP アドレスに解決します。</span><span class="sxs-lookup"><span data-stu-id="1c65a-p101">Each Edge Server is a multihomed computer with external and internal facing interfaces. The adapter Domain Name System (DNS) settings depend on whether there are DNS servers in the perimeter network. If DNS servers exist in the perimeter, they must have a zone containing one or more DNS A records for the next hop server or pool (that is, either a Director or a designated Front End pool), and for external queries they refer name lookups to other public DNS servers. If no DNS servers exist in the perimeter, the Edge Server(s) use external DNS servers to resolve Internet name lookups, and each Edge Server uses a HOST to resolve the next hop server names to IP addresses.</span></span>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="security" alt="security" /><span data-ttu-id="1c65a-109">セキュリティに関する注意事項:</span><span class="sxs-lookup"><span data-stu-id="1c65a-109">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="1c65a-110">セキュリティ上の理由から、エッジ サーバーから内部ネットワーク内の DNS サーバーにアクセスしないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1c65a-110">For security reasons, we recommend that you do not have your Edge Servers access a DNS server located in the internal network.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="1c65a-111">境界ネットワークの DNS サーバーのインターフェイスを構成するには</span><span class="sxs-lookup"><span data-stu-id="1c65a-111">To configure interfaces with DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="1c65a-112">各エッジ サーバーに、内部インターフェイス用と外部インターフェイス用の 2 つのネットワーク アダプターを取り付けます。</span><span class="sxs-lookup"><span data-stu-id="1c65a-112">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1c65a-113">内部サブネットと外部サブネット間のルーティングは許可しないでください。</span><span class="sxs-lookup"><span data-stu-id="1c65a-113">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="1c65a-p102">外部インターフェイスで、外部境界ネットワーク (DMZ、非武装地帯、またはスクリーン サブネットとも呼ばれる) のサブネット上の、3 つの静的 IP アドレスを構成し、さらにデフォルト ゲートウェイとして、外部ファイアウォールの内部インターフェイスを指すようにします。アダプターの DNS 設定では、2 つの境界 DNS サーバーを指すように構成します。</span><span class="sxs-lookup"><span data-stu-id="1c65a-p102">On the external interface, configure three static IP addresses on the external perimeter network (also known as DMZ, demilitarized zone, and screened subnet) subnet, and point the default gateway to the internal interface of the external firewall. Configure adapter DNS settings to point to a pair of perimeter DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1c65a-116">このインターフェイスで 1 つだけの IP アドレスを使用することも可能ですが、それにはポート割り当てを標準値以外に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c65a-116">It is possible to use as few as one IP address for this interface, but to do this you need to change the port assignments to non-standard values.</span></span> <span data-ttu-id="1c65a-117">トポロジビルダーでトポロジを作成するときに、これを決定します。</span><span class="sxs-lookup"><span data-stu-id="1c65a-117">You determine this when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="1c65a-p104">内部インターフェイスでは、内部境界ネットワークのサブネット上の静的 IP アドレスを 1 つ構成し、デフォルト ゲートウェイは設定しません。アダプターの DNS 設定では、少なくとも 1 つの DNS サーバー (推奨は 2 つの境界 DNS サーバー) を指すように構成します。</span><span class="sxs-lookup"><span data-stu-id="1c65a-p104">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway. Configure adapter DNS settings to point to at least one DNS server, preferably a pair of perimeter DNS servers.</span></span>

4.  <span data-ttu-id="1c65a-120">クライアント、Lync Server 2013、および Exchange ユニファイドメッセージング (UM) サーバーが存在するすべての内部ネットワークへの内部インターフェイス上で永続的な静的ルートを作成します。</span><span class="sxs-lookup"><span data-stu-id="1c65a-120">Create persistent static routes on the internal interface to all internal networks where clients, Lync Server 2013, and Exchange Unified Messaging (UM) servers reside.</span></span>

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="1c65a-121">境界ネットワークに DNS サーバーがない場合にインターフェイスを構成するには</span><span class="sxs-lookup"><span data-stu-id="1c65a-121">To configure interfaces without DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="1c65a-122">各エッジ サーバーに、内部インターフェイス用と外部インターフェイス用の 2 つのネットワーク アダプターを取り付けます。</span><span class="sxs-lookup"><span data-stu-id="1c65a-122">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1c65a-123">内部サブネットと外部サブネット間のルーティングは許可しないでください。</span><span class="sxs-lookup"><span data-stu-id="1c65a-123">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="1c65a-p105">外部インターフェイスで、外部境界ネットワークのサブネット上の静的 IP アドレスを 3 つ構成します。また、外部インターエイス上にデフォルト ゲートウェイを構成します。たとえば、デフォルト ゲートウェイとしてインターネットに接続するルーターまたは外部ファイアウォールを定義します。1 つの DNS サーバー (推奨は 2 つの外部 DNS サーバー) を指すように DNS 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="1c65a-p105">On the external interface, configure three static IP addresses on the external perimeter network subnet. You also configure the default gateway on the external interface. For example, define the Internet-facing router or the external firewall as the default gateway. Configure DNS settings to point to a DNS server, preferably to a pair of external DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1c65a-128">外部インターフェイスで 1 つだけの IP アドレスを使用することも可能ですが、お勧めしません。</span><span class="sxs-lookup"><span data-stu-id="1c65a-128">It is possible, but not recommended, to use as few as one IP address for the external interface.</span></span> <span data-ttu-id="1c65a-129">それにはポート割り当てを標準値以外、かつ通常はクライアント通信に "ファイアウォール フレンドリ" な既定のポート 443 から離れた値に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c65a-129">To allow this to work, you need to change the port assignments to non-standard values, and away from the default port 443 that is typically “firewall friendly” for client communication.</span></span> <span data-ttu-id="1c65a-130">トポロジビルダーでトポロジを作成するときに、IP アドレスの設定とポートの設定を決定します。</span><span class="sxs-lookup"><span data-stu-id="1c65a-130">You determine the IP address setting and the port settings when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="1c65a-p107">内部インターフェイスでは、内部境界ネットワークのサブネット上の静的 IP アドレスを 1 つ構成し、デフォルト ゲートウェイは設定しません。アダプターの DNS 設定は空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="1c65a-p107">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway. Leave adapter DNS settings empty.</span></span>

4.  <span data-ttu-id="1c65a-133">Lync Server 2013 を実行している Lync クライアントまたはサーバーが存在するすべての内部ネットワークへの内部インターフェイス上で永続的な静的ルートを作成します。</span><span class="sxs-lookup"><span data-stu-id="1c65a-133">Create persistent static routes on the internal interface to all internal networks where Lync clients or servers running Lync Server 2013 reside.</span></span>

5.  <span data-ttu-id="1c65a-134">各エッジサーバーのホストファイルを編集して、次ホップサーバーまたは仮想 IP (VIP) のレコードが格納されるようにします (レコードは、ディレクター、Standard Edition サーバー、またはトポロジビルダーのエッジサーバーの次ホップアドレスとして構成されたフロントエンドプールになります)。</span><span class="sxs-lookup"><span data-stu-id="1c65a-134">Edit the HOST file on each Edge Server to contain a record for the next hop server or virtual IP (VIP) (the record will be the Director, Standard Edition server, or a Front End pool that was configured as the Edge Server next hop address in Topology Builder).</span></span> <span data-ttu-id="1c65a-135">DNS 負荷分散を使用している場合は、次ホップ プールの各メンバーに対して 1 回線を含めてください。</span><span class="sxs-lookup"><span data-stu-id="1c65a-135">If you are using DNS load balancing, include a line for each member of the next hop pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

