---
title: 'Lync Server 2013: エッジ サーバーのネットワーク インターフェイスの設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up network interfaces for Edge Servers
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412847(v=OCS.15)
ms:contentKeyID: 48185152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7263c2d7cad3cf1339351f2cb5f90b15a9fa0a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a><span data-ttu-id="729ce-102">Lync Server 2013 でのエッジ サーバーのネットワーク インターフェイスの設定</span><span class="sxs-lookup"><span data-stu-id="729ce-102">Set up network interfaces for Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="729ce-103">_**最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="729ce-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="729ce-104">各エッジサーバーは、外部および内部接続インターフェイスを備えたマルチホームコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="729ce-104">Each Edge Server is a multihomed computer with external and internal facing interfaces.</span></span> <span data-ttu-id="729ce-105">[Adapter Domain Name System (DNS)] の設定は、境界ネットワークに DNS サーバーがあるかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="729ce-105">The adapter Domain Name System (DNS) settings depend on whether there are DNS servers in the perimeter network.</span></span> <span data-ttu-id="729ce-106">DNS サーバーが境界内に存在する場合は、1つ以上の DNS A レコードと次ホップサーバーまたはプール (つまり、ディレクターまたは指定されたフロントエンドプール) が含まれているゾーンと、外部クエリが名前の参照を他のパブリック DNS サーバーに参照していることが必要です。</span><span class="sxs-lookup"><span data-stu-id="729ce-106">If DNS servers exist in the perimeter, they must have a zone containing one or more DNS A records for the next hop server or pool (that is, either a Director or a designated Front End pool), and for external queries they refer name lookups to other public DNS servers.</span></span> <span data-ttu-id="729ce-107">DNS サーバーが境界内に存在しない場合、エッジサーバーでは、外部 DNS サーバーを使ってインターネット名の参照を解決します。各エッジサーバーは、次ホップのサーバー名を IP アドレスに解決するためにホストを使用します。</span><span class="sxs-lookup"><span data-stu-id="729ce-107">If no DNS servers exist in the perimeter, the Edge Server(s) use external DNS servers to resolve Internet name lookups, and each Edge Server uses a HOST to resolve the next hop server names to IP addresses.</span></span>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="証券" alt="security" /><span data-ttu-id="729ce-109">セキュリティメモ:</span><span class="sxs-lookup"><span data-stu-id="729ce-109">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="729ce-110">セキュリティ上の理由から、内部ネットワーク内の DNS サーバーにエッジサーバーがアクセスしないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="729ce-110">For security reasons, we recommend that you do not have your Edge Servers access a DNS server located in the internal network.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="729ce-111">境界ネットワークの DNS サーバーとのインターフェイスを構成するには</span><span class="sxs-lookup"><span data-stu-id="729ce-111">To configure interfaces with DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="729ce-112">エッジサーバーごとに2つのネットワークアダプターをインストールします。1つは内部接続インターフェイス用、もう1つは外部向きインターフェイス用です。</span><span class="sxs-lookup"><span data-stu-id="729ce-112">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="729ce-113">内部サブネットと外部サブネット間のルーティングは許可しないでください。</span><span class="sxs-lookup"><span data-stu-id="729ce-113">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="729ce-114">外部インターフェイスで、外部境界ネットワーク上の3つの静的 IP アドレス (DMZ、非武装地帯、スクリーンサブネットとも呼ばれます) のサブネットを構成し、既定のゲートウェイを外部ファイアウォールの内部インターフェイスにポイントします。</span><span class="sxs-lookup"><span data-stu-id="729ce-114">On the external interface, configure three static IP addresses on the external perimeter network (also known as DMZ, demilitarized zone, and screened subnet) subnet, and point the default gateway to the internal interface of the external firewall.</span></span> <span data-ttu-id="729ce-115">境界 DNS サーバーのペアを指すように、アダプターの DNS 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="729ce-115">Configure adapter DNS settings to point to a pair of perimeter DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="729ce-116">このインターフェイスでは、IP アドレスを1つしか使用できませんが、そのためには、ポートの割り当てを標準以外の値に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="729ce-116">It is possible to use as few as one IP address for this interface, but to do this you need to change the port assignments to non-standard values.</span></span> <span data-ttu-id="729ce-117">これは、トポロジビルダーでトポロジを作成するときに決定します。</span><span class="sxs-lookup"><span data-stu-id="729ce-117">You determine this when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="729ce-118">内部インターフェイスで、内部境界ネットワークサブネット上の1つの静的 IP アドレスを構成し、既定のゲートウェイを設定しません。</span><span class="sxs-lookup"><span data-stu-id="729ce-118">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway.</span></span> <span data-ttu-id="729ce-119">少なくとも1つの DNS サーバーをポイントするようにアダプターの DNS 設定を構成します。できれば、境界 DNS サーバーのペアを指定します。</span><span class="sxs-lookup"><span data-stu-id="729ce-119">Configure adapter DNS settings to point to at least one DNS server, preferably a pair of perimeter DNS servers.</span></span>

4.  <span data-ttu-id="729ce-120">クライアント、Lync Server 2013、Exchange ユニファイドメッセージング (UM) サーバーが存在するすべての内部ネットワークへの内部インターフェイス上の常設静的ルートを作成します。</span><span class="sxs-lookup"><span data-stu-id="729ce-120">Create persistent static routes on the internal interface to all internal networks where clients, Lync Server 2013, and Exchange Unified Messaging (UM) servers reside.</span></span>

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="729ce-121">境界ネットワークに DNS サーバーのないインターフェイスを構成するには</span><span class="sxs-lookup"><span data-stu-id="729ce-121">To configure interfaces without DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="729ce-122">エッジサーバーごとに2つのネットワークアダプターをインストールします。1つは内部接続インターフェイス用、もう1つは外部向きインターフェイス用です。</span><span class="sxs-lookup"><span data-stu-id="729ce-122">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="729ce-123">内部サブネットと外部サブネット間のルーティングは許可しないでください。</span><span class="sxs-lookup"><span data-stu-id="729ce-123">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="729ce-124">外部インターフェイスで、外部境界ネットワークサブネット上の3つの静的 IP アドレスを構成します。</span><span class="sxs-lookup"><span data-stu-id="729ce-124">On the external interface, configure three static IP addresses on the external perimeter network subnet.</span></span> <span data-ttu-id="729ce-125">また、外部インターフェイスの既定のゲートウェイも構成します。</span><span class="sxs-lookup"><span data-stu-id="729ce-125">You also configure the default gateway on the external interface.</span></span> <span data-ttu-id="729ce-126">たとえば、インターネットに接続するルーターまたは外部ファイアウォールを既定のゲートウェイとして定義します。</span><span class="sxs-lookup"><span data-stu-id="729ce-126">For example, define the Internet-facing router or the external firewall as the default gateway.</span></span> <span data-ttu-id="729ce-127">DNS サーバーを指すように DNS 設定を構成します。1組の外部 DNS サーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="729ce-127">Configure DNS settings to point to a DNS server, preferably to a pair of external DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="729ce-128">外部インターフェイスに対しては、1つの IP アドレスを使用することはお勧めできませんが、お勧めしません。</span><span class="sxs-lookup"><span data-stu-id="729ce-128">It is possible, but not recommended, to use as few as one IP address for the external interface.</span></span> <span data-ttu-id="729ce-129">この機能を有効にするには、ポートの割り当てを標準以外の値に変更し、通常はクライアント通信用の既定のポート443から離します。</span><span class="sxs-lookup"><span data-stu-id="729ce-129">To allow this to work, you need to change the port assignments to non-standard values, and away from the default port 443 that is typically “firewall friendly” for client communication.</span></span> <span data-ttu-id="729ce-130">トポロジビルダーでトポロジを作成するときに、IP アドレス設定とポート設定を決定します。</span><span class="sxs-lookup"><span data-stu-id="729ce-130">You determine the IP address setting and the port settings when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="729ce-131">内部インターフェイスで、内部境界ネットワークサブネット上の1つの静的 IP アドレスを構成し、既定のゲートウェイを設定しません。</span><span class="sxs-lookup"><span data-stu-id="729ce-131">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway.</span></span> <span data-ttu-id="729ce-132">アダプターの DNS 設定は空のままにします。</span><span class="sxs-lookup"><span data-stu-id="729ce-132">Leave adapter DNS settings empty.</span></span>

4.  <span data-ttu-id="729ce-133">Lync クライアントまたは Lync Server 2013 が実行されているすべての内部ネットワークへの内部インターフェイスで永続的な静的ルートを作成します。</span><span class="sxs-lookup"><span data-stu-id="729ce-133">Create persistent static routes on the internal interface to all internal networks where Lync clients or servers running Lync Server 2013 reside.</span></span>

5.  <span data-ttu-id="729ce-134">各エッジサーバー上のホストファイルを編集して、次ホップサーバーまたは仮想 IP (VIP) のレコードが含まれるようにします (このレコードは、ディレクター、Standard Edition Server、またはトポロジビルダーで Edge Server の次ホップアドレスとして構成されたフロントエンドプールになります)。</span><span class="sxs-lookup"><span data-stu-id="729ce-134">Edit the HOST file on each Edge Server to contain a record for the next hop server or virtual IP (VIP) (the record will be the Director, Standard Edition server, or a Front End pool that was configured as the Edge Server next hop address in Topology Builder).</span></span> <span data-ttu-id="729ce-135">DNS 負荷分散を使用している場合は、次ホッププールの各メンバーに1行を追加します。</span><span class="sxs-lookup"><span data-stu-id="729ce-135">If you are using DNS load balancing, include a line for each member of the next hop pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

