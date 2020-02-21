---
title: Lync Server 2013 の負荷分散の要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Load balancing requirements
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615011(v=OCS.15)
ms:contentKeyID: 48184697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54e1e8e130374e296d18680cf5d82001e55b68af
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="load-balancing-requirements-for-lync-server-2013"></a><span data-ttu-id="31230-102">Lync Server 2013 の負荷分散の要件</span><span class="sxs-lookup"><span data-stu-id="31230-102">Load balancing requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31230-103">_**トピックの最終更新日:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="31230-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="31230-104">フロントエンドプール、ディレクタープール、またはエッジサーバープールを使用している場合は、これらのプールの負荷分散を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31230-104">If you have Front End pools, Director pools, or Edge Server pools, you need to deploy load balancing for these pools.</span></span> <span data-ttu-id="31230-105">ロード バランシングによって、プール内のすべてのサーバーにトラフィックが分散されます。</span><span class="sxs-lookup"><span data-stu-id="31230-105">Load balancing distributes the traffic among the servers in a pool.</span></span>

<span data-ttu-id="31230-106">Lync Server 2013 は、クライアントとサーバー間のトラフィックに対して、ドメインネームシステム (DNS) 負荷分散とハードウェア負荷分散という2種類の負荷分散ソリューションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="31230-106">Lync Server 2013 supports two types of load balancing solutions for client-to-server traffic: Domain Name System (DNS) load balancing and hardware load balancing.</span></span> <span data-ttu-id="31230-107">DNS 負荷分散には、管理の簡素化、効率的なトラブルシューティング、および潜在的なハードウェアロードバランサーの問題からの Lync Server のトラフィックの大部分を分離する機能など、いくつかの利点があります。</span><span class="sxs-lookup"><span data-stu-id="31230-107">DNS load balancing offers several advantages including simpler administration, more efficient troubleshooting, and the ability to isolate much of your Lync Server traffic from any potential hardware load balancer problems.</span></span>

<span data-ttu-id="31230-108">以下の制限事項を考慮して、展開内のプールごとに適切なロード バランシング ソリューションを決定します。</span><span class="sxs-lookup"><span data-stu-id="31230-108">Decide which load balancing solution is appropriate for each pool in your deployment, keeping in mind the following restrictions:</span></span>

  - <span data-ttu-id="31230-p103">内部エッジ インターフェイスと外部エッジ インターフェイスでは、同じ種類のロード バランシングを使用する必要があります。1 つのインターフェイスで DNS ロード バランシングを使用し、もう 1 つのインターフェイスでロード バランサー機器を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="31230-p103">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one interface and hardware load balancing on the other.</span></span>

  - <span data-ttu-id="31230-p104">一部の種類のトラフィックでは、ハードウェア ロード バランサーが必要です。たとえば、HTTP トラフィックでは、DNS ロード バランシングではなくハードウェア ロード バランサーが必要です。クライアントとサーバー間の Web トラフィックでは、DNS ロード バランシングは正常に機能しません。</span><span class="sxs-lookup"><span data-stu-id="31230-p104">Some types of traffic require a hardware load balancer. For example, HTTP traffic requires a hardware load balancer instead of DNS load balancing. DNS load balancing does not work with client-to-server web traffic.</span></span>

<span data-ttu-id="31230-114">ロードバランサー機器ソリューションの選択の詳細については、「 [Lync Server 2013 のハードウェアロードバランサーの要件](lync-server-2013-hardware-load-balancer-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31230-114">For more details about choosing a hardware load balancer solution, see [Hardware load balancer requirements for Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).</span></span>

<span data-ttu-id="31230-115">プールで DNS ロード バランシングを使用するように選択し、HTTP トラフィックなどのトラフィック用にハードウェア ロード バランサーも実装する必要がある場合、ハードウェア ロード バランサーの管理は非常に簡素化されます。</span><span class="sxs-lookup"><span data-stu-id="31230-115">If you choose to use DNS load balancing for a pool but still need to implement hardware load balancers for traffic such as HTTP traffic, the administration of the hardware load balancers is greatly simplified.</span></span> <span data-ttu-id="31230-116">たとえば、HTTP トラフィックと HTTPS トラフィックのみが管理され、他のすべてのプロトコルは DNS 負荷分散によって管理されるため、ハードウェアロードバランサーの構成はより簡単になります。</span><span class="sxs-lookup"><span data-stu-id="31230-116">For example, configuring the hardware load balancer will be simpler as it will only manage the HTTP and HTTPS traffic, while all other protocols will be managed by DNS load balancing.</span></span> <span data-ttu-id="31230-117">詳細については、「 [Lync Server 2013 の DNS 負荷分散](lync-server-2013-dns-load-balancing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31230-117">For details, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md).</span></span>

<span data-ttu-id="31230-118">サーバー間トラフィックの場合、Lync Server 2013 ではトポロジに対応した負荷分散が使用されます。</span><span class="sxs-lookup"><span data-stu-id="31230-118">For server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="31230-119">サーバーは、中央管理ストアで公開されているトポロジを読み取り、トポロジ内のサーバーの Fqdn を取得し、そのトラフィックをサーバー間で自動的に分配します。</span><span class="sxs-lookup"><span data-stu-id="31230-119">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="31230-120">管理者はこの種の負荷分散を設定または管理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="31230-120">Administrators do not need to set up or manage this type of load balancing.</span></span>

<span data-ttu-id="31230-121">DNS 負荷分散を使用していて、特定のコンピューターへのトラフィックをブロックする必要がある場合は、IP アドレスエントリをプールの FQDN から削除するだけで十分ではありません。</span><span class="sxs-lookup"><span data-stu-id="31230-121">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN.</span></span> <span data-ttu-id="31230-122">コンピューターの DNS エントリも削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31230-122">You must remove the DNS entry for the computer as well.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

