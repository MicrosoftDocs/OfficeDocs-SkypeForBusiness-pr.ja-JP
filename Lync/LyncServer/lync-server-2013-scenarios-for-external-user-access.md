---
title: 'Lync Server 2013: 外部ユーザー アクセスのシナリオ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eab8323744615dc3f5d0b68f4325fbfb85bf911e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="fb39e-102">Lync Server 2013 の外部ユーザー アクセスのシナリオ</span><span class="sxs-lookup"><span data-stu-id="fb39e-102">Scenarios for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb39e-103">_**最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="fb39e-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="fb39e-104">Lync Server 2013 の外部ユーザーアクセスを提供するには、境界ネットワークに少なくとも1つのエッジサーバーと1つの逆プロキシを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb39e-104">Providing external user access for Lync Server 2013 requires that you deploy at least one Edge Server and one reverse proxy in your perimeter network.</span></span> <span data-ttu-id="fb39e-105">必要に応じて、内部ネットワークにディレクターまたはディレクタープールを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="fb39e-105">Optionally, you may deploy a Director or Director pool in your internal network.</span></span>

<span data-ttu-id="fb39e-106">1つのエッジサーバーでは提供できないキャパシティを確保する必要がある場合、またはエッジサーバーの展開に高可用性が必要な場合は、負荷分散プールで複数のエッジサーバーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="fb39e-106">If you need greater capacity than a single Edge Server can provide, or if you need high availability for your Edge Server deployment, you can configure load balancing and deploy multiple Edge Servers in a load balanced pool.</span></span> <span data-ttu-id="fb39e-107">組織に複数のデータセンターがある場合は、複数の場所でエッジサーバーまたはエッジプールの展開を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fb39e-107">If your organization has multiple data centers, you can have Edge Server or Edge pool deployments at more than one location.</span></span> <span data-ttu-id="fb39e-108">ただし、1エッジサーバーの展開のみをフェデレーションルートとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="fb39e-108">However, only one of the Edge Server deployments can be designated as the federation route.</span></span>

<span data-ttu-id="fb39e-109">このセクションでは、Edge Server の展開のシナリオを定義し、計画セクションを考えられるシナリオにマップします。</span><span class="sxs-lookup"><span data-stu-id="fb39e-109">This section defines the scenarios for Edge Server deployments and maps the planning sections to the possible scenarios.</span></span> <span data-ttu-id="fb39e-110">たとえば、高い可用性、拡張可能なメッセージングとプレゼンス (XMPP) の連絡先とのフェデレーション、および Lync のモバイル機能が必要な場合は、次の表で、これらの要件を満たす対応エントリを選択して、次のフローチャートに示すように、参照計画セクションで展開を定義します。</span><span class="sxs-lookup"><span data-stu-id="fb39e-110">For example, if your deployment requires high availability, federation with extensible messaging and presence (XMPP) contacts, and Lync mobility, you would select the matching entries in the following table that would satisfy these requirements and use the referenced planning sections to define your deployment, as illustrated in the following flowchart.</span></span>

<span data-ttu-id="fb39e-111">**エッジサーバーの展開シナリオの選択プロセス**</span><span class="sxs-lookup"><span data-stu-id="fb39e-111">**Edge Server deployment scenario selection process**</span></span>

<span data-ttu-id="fb39e-112">![展開例フローチャート](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "展開例フローチャート")</span><span class="sxs-lookup"><span data-stu-id="fb39e-112">![Sample deployment flowchart](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Sample deployment flowchart")</span></span>

<span data-ttu-id="fb39e-113">このプロセスを使用することで、ユーザーに展開する可能性があるすべての機能の構成を計画し、文書化することができます。</span><span class="sxs-lookup"><span data-stu-id="fb39e-113">By using this process, you can plan for and document the configuration of all potential features that you intend to deploy for your users.</span></span> <span data-ttu-id="fb39e-114">ただし、エッジサーバーを展開して、他の機能を追加する前に適切な操作を確認した後で、フェデレーションサービスとモバイルサービスを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="fb39e-114">However, you can add federation and mobility services after you have deployed the Edge Server and have confirmed the correct operation before adding other features.</span></span> <span data-ttu-id="fb39e-115">既存のエッジサーバー展開に機能を追加するプロセスについては、「展開」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb39e-115">The process of adding features to an existing Edge Server deployment is covered in the Deployment section.</span></span> <span data-ttu-id="fb39e-116">展開の詳細については、「 [Lync Server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。最初の計画プロセスでこれらの機能の計画を含めることによって、証明書を取得し、dns およびポート/プロトコルの要件を事前に構成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fb39e-116">For details on deployment, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) By including planning for these features during the initial planning process, you can prepare for the DNS, firewall, and certificate requirements for the added features, which enables you to acquire the certificates and configure DNS and port/protocol requirements in advance.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="fb39e-117">エッジサーバーとリバースプロキシをインストールし、後で機能を追加することを計画している場合 (たとえば、フェデレーションとモビリティ)、展開後にすべてのサービスに必要な証明書を決定します。</span><span class="sxs-lookup"><span data-stu-id="fb39e-117">If you are planning to install the Edge Servers and reverse proxy and then add features later (for example, federation and mobility), determine what certificates you will require for all services after deployment.</span></span> <span data-ttu-id="fb39e-118">事前にすべての機能の証明書を計画して取得する場合は、最初に展開されたかどうかにより、新しい証明書の順序を設定して、フェデレーション (つまりエッジサーバー上) またはリバースプロキシ (つまり、モビリティ) の要件を満たす必要があります。サービス)。</span><span class="sxs-lookup"><span data-stu-id="fb39e-118">Planning for and acquiring the certificates for all features in advance, initially deployed or not, saves you from having to order new certificates to satisfy the requirements of federation (that is, on the Edge Servers) or the reverse proxy (that is, for mobility services).</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="fb39e-119">エッジサービスは、各エッジサーバー上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="fb39e-119">All edge services run on each Edge Server.</span></span> <span data-ttu-id="fb39e-120">サービスは、2つの異なるエッジサーバー間で分割することはできません。</span><span class="sxs-lookup"><span data-stu-id="fb39e-120">Services cannot be split between two different Edge Servers.</span></span> <span data-ttu-id="fb39e-121">スケーラビリティのためにエッジプールを展開すると、すべてのエッジサービスがプールの各エッジサーバーに展開されます。</span><span class="sxs-lookup"><span data-stu-id="fb39e-121">If you deploy an Edge pool for scalability, all edge services are deployed on each Edge Server in the pool.</span></span> <span data-ttu-id="fb39e-122">XMPP フェデレーション、Office Communications Server、Lync Server federation、パブリック IM 接続、クライアントモビリティは、最初のエッジサーバーまたはエッジプールの展開後に展開できる追加サービスです。</span><span class="sxs-lookup"><span data-stu-id="fb39e-122">XMPP federation, Office Communications Server, and Lync Server federation, public IM connectivity and client mobility are additional services that can be deployed after you have deployed your first Edge Server or Edge pool.</span></span> <span data-ttu-id="fb39e-123">モビリティーサービスは、リバースプロキシを使用する機能です。</span><span class="sxs-lookup"><span data-stu-id="fb39e-123">Mobility services is a feature that uses the reverse proxy.</span></span> <span data-ttu-id="fb39e-124">モバイルサービスをインストールしても、エッジサーバーに機能は追加されませんが、リバースプロキシの再構成が必要になります。</span><span class="sxs-lookup"><span data-stu-id="fb39e-124">Installation of mobility services will not add features to your Edge Servers, but will require reconfiguration of your reverse proxy.</span></span> <span data-ttu-id="fb39e-125">これらの機能を記載した [<STRONG>インストールの目標</STRONG>] 列では、エッジサーバーのインストールと構成時にこれらの機能が展開されるように、これらの機能を同時に計画<STRONG>するための</STRONG>、関連する列にある関連列の計画ガイダンスを示しています。</span><span class="sxs-lookup"><span data-stu-id="fb39e-125">The <STRONG>Installation goal</STRONG> column that lists these features provides planning guidance in the associated column under <STRONG>Edge Server planning section or sections</STRONG> for concurrently planning these features to be deployed when the Edge Servers are installed and configured.</span></span>



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a><span data-ttu-id="fb39e-126">展開目標の特定とマッピング</span><span class="sxs-lookup"><span data-stu-id="fb39e-126">Identifying and Mapping Your Deployment Goals</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb39e-127">インストールの目標</span><span class="sxs-lookup"><span data-stu-id="fb39e-127">Installation goal</span></span></th>
<th><span data-ttu-id="fb39e-128">エッジサーバー計画のドキュメント</span><span class="sxs-lookup"><span data-stu-id="fb39e-128">Edge Server planning documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb39e-129">お客様は、インフラストラクチャのエッジサービスには1台のサーバーのみで十分であると判断しました。</span><span class="sxs-lookup"><span data-stu-id="fb39e-129">You have decided that a single server is sufficient for Edge services in your infrastructure.</span></span> <span data-ttu-id="fb39e-130">また、インターネットに NAT を使用して、エッジサーバーの外部インターフェイスに対してもプライベート IP アドレスを使用することを意図しています。</span><span class="sxs-lookup"><span data-stu-id="fb39e-130">You also intend to use private IP addresses for the Edge server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="fb39e-131">この計画セクションは、境界に単一エッジサーバーを展開する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="fb39e-131">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="fb39e-132">エッジサーバーに、プライベート IP アドレスが割り当てられたエッジサーバーを展開し、インターネット上の外部ユーザーに対して NAT を使用してパブリック IP アドレスを提供します。</span><span class="sxs-lookup"><span data-stu-id="fb39e-132">You will deploy an Edge Server with private IP addresses assigned to the Edge Server and will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="fb39e-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Lync Server 2013 におけるプライベート IP アドレスと NAT を用いた単一統合エッジ</a></span><span class="sxs-lookup"><span data-stu-id="fb39e-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb39e-134">お客様は、インフラストラクチャのエッジサービスには1台のサーバーのみで十分であると判断しました。</span><span class="sxs-lookup"><span data-stu-id="fb39e-134">You have decided that a single server is sufficient for Edge services in your infrastructure.</span></span> <span data-ttu-id="fb39e-135">また、エッジサーバーのインターネットへの外部インターフェイスにパブリック IP アドレスを使いたいと考えています。</span><span class="sxs-lookup"><span data-stu-id="fb39e-135">You also intend to use public IP addresses for the Edge server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="fb39e-136">この計画セクションは、境界に単一エッジサーバーを展開する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="fb39e-136">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="fb39e-137">エッジサーバーにパブリック IP アドレスが割り当てられたエッジサーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="fb39e-137">You will deploy an Edge Server with public IP addresses assigned to the Edge Server.</span></span> <span data-ttu-id="fb39e-138">NAT の代わりに、このシナリオでルーティングを使います。</span><span class="sxs-lookup"><span data-stu-id="fb39e-138">Instead of NAT, you will use routing in this scenario.</span></span> <span data-ttu-id="fb39e-139">エッジサーバーの実際のパブリック IP アドレスは、外部ユーザー接続に対して利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="fb39e-139">The actual public IP address of the Edge Server are made available for external user connections.</span></span></p></td>
<td><p><span data-ttu-id="fb39e-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Lync Server 2013 のパブリック IP アドレスを使用する単一統合エッジ</a></span><span class="sxs-lookup"><span data-stu-id="fb39e-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Single consolidated edge with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb39e-141">エッジサービスの高可用性がユーザーにとって重要であり、このプールに2つ以上のエッジサーバーを展開することを決定しました。</span><span class="sxs-lookup"><span data-stu-id="fb39e-141">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="fb39e-142">また、インターネットに NAT を使用して、エッジサーバーの外部インターフェイスに対してもプライベート IP アドレスを使用することを意図しています。</span><span class="sxs-lookup"><span data-stu-id="fb39e-142">You also intend to use private IP addresses for the Edge Server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="fb39e-143">境界にエッジサーバーのプールを展開する場合は、この計画セクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb39e-143">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="fb39e-144">DNS の負荷分散を使ってプール間で通信を分散する、エッジサーバーに割り当てられているプライベート IP アドレスを持つエッジサーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="fb39e-144">You will deploy the Edge Servers with private IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="fb39e-145">インターネット上の外部ユーザーに対してパブリック IP アドレスを提供するには、NAT を使用します。</span><span class="sxs-lookup"><span data-stu-id="fb39e-145">You will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="fb39e-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Lync Server 2013 における拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散</a></span><span class="sxs-lookup"><span data-stu-id="fb39e-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb39e-147">エッジサービスの高可用性がユーザーにとって重要であり、このプールに2つ以上のエッジサーバーを展開することを決定しました。</span><span class="sxs-lookup"><span data-stu-id="fb39e-147">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="fb39e-148">また、エッジサーバーのインターネットへの外部インターフェイスにパブリック IP アドレスを使いたいと考えています。</span><span class="sxs-lookup"><span data-stu-id="fb39e-148">You also intend to use public IP addresses for the Edge Server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="fb39e-149">境界にエッジサーバーのプールを展開する場合は、この計画セクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb39e-149">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="fb39e-150">DNS の負荷分散を使ってプール間で通信を分散する、エッジサーバーに割り当てられたパブリック IP アドレスを持つエッジサーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="fb39e-150">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="fb39e-151">NAT の代わりに、ルーティングを使用して、インターネット上の外部ユーザーに対してパブリック IP アドレスを提供します。</span><span class="sxs-lookup"><span data-stu-id="fb39e-151">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="fb39e-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Lync Server 2013 での拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散</a></span><span class="sxs-lookup"><span data-stu-id="fb39e-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb39e-153">エッジサービスの高可用性がユーザーにとって重要であると判断し、ハードウェアロードバランサーを使って、このプールに2つ以上のエッジサーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="fb39e-153">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool using a hardware load balancer.</span></span></p>
<p><span data-ttu-id="fb39e-154">境界にエッジサーバーのプールを展開する場合は、この計画セクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb39e-154">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="fb39e-155">ハードウェアロードバランサーを使ってプール間で通信を分散するエッジサーバーを、エッジサーバーに割り当てられたパブリック IP アドレスを使って展開します。</span><span class="sxs-lookup"><span data-stu-id="fb39e-155">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using hardware load balancers to distribute communication across the pool.</span></span> <span data-ttu-id="fb39e-156">NAT の代わりに、ルーティングを使用して、インターネット上の外部ユーザーに対してパブリック IP アドレスを提供します。</span><span class="sxs-lookup"><span data-stu-id="fb39e-156">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="fb39e-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013 のハードウェア ロード バランサーによる拡張統合エッジ</a></span><span class="sxs-lookup"><span data-stu-id="fb39e-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Scaled consolidated edge with hardware load balancers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb39e-158">フェデレーションシナリオでは、ユーザーが通信できるパートナーの種類を拡張する機能を計画することができます。</span><span class="sxs-lookup"><span data-stu-id="fb39e-158">The federation scenarios allow you to plan for the feature that will extend the types of partners that your users can communicate with.</span></span></p>
<ul>
<li><p><span data-ttu-id="fb39e-159">Lync Server フェデレーション</span><span class="sxs-lookup"><span data-stu-id="fb39e-159">Lync Server federation</span></span></p></li>
<li><p><span data-ttu-id="fb39e-160">Office Communications Server フェデレーション</span><span class="sxs-lookup"><span data-stu-id="fb39e-160">Office Communications Server federation</span></span></p></li>
<li><p><span data-ttu-id="fb39e-161">パブリック IM 接続</span><span class="sxs-lookup"><span data-stu-id="fb39e-161">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="fb39e-162">XMPP フェデレーション</span><span class="sxs-lookup"><span data-stu-id="fb39e-162">XMPP federation</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="fb39e-163">フェデレーションシナリオの計画</span><span class="sxs-lookup"><span data-stu-id="fb39e-163">Planning for Federation Scenarios</span></span></p>
<ul>
<li><p><span data-ttu-id="fb39e-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Lync Server 2013 と Office Communications Server フェデレーションの計画</a></span><span class="sxs-lookup"><span data-stu-id="fb39e-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planning for Lync Server 2013 and Office Communications Server federation</a></span></span></p></li>
<li><p><span data-ttu-id="fb39e-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセージング接続の計画</a></span><span class="sxs-lookup"><span data-stu-id="fb39e-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planning for public instant messaging connectivity in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="fb39e-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Lync Server 2013 での拡張メッセージングとプレゼンスプロトコル (XMPP) フェデレーションの計画</a></span><span class="sxs-lookup"><span data-stu-id="fb39e-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb39e-167">モビリティーサービスはリバースプロキシを通じて提供されます。</span><span class="sxs-lookup"><span data-stu-id="fb39e-167">Mobility services are offered through the reverse proxy.</span></span> <span data-ttu-id="fb39e-168">外部ユーザーに対するモビリティを有効にするサービスは、フロントエンドサーバーまたはフロントエンドプールに展開されます。</span><span class="sxs-lookup"><span data-stu-id="fb39e-168">Services that enable mobility for external users are deployed on the Front End Server or Front End pool.</span></span> <span data-ttu-id="fb39e-169">リバースプロキシで既存の公開ルールを作成または変更して、外部ユーザーのモビリティサービスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fb39e-169">You create or modify existing publishing rules on the reverse proxy to enable mobility services for your external users.</span></span></p></td>
<td><p><span data-ttu-id="fb39e-170"><a href="lync-server-2013-planning-for-mobility.md">Lync Server 2013 でのモビリティの計画</a></span><span class="sxs-lookup"><span data-stu-id="fb39e-170"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> <span data-ttu-id="fb39e-171">次のシナリオでは、リファレンスアーキテクチャ、DNS、ポート/プロトコル定義、証明書の要件などについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fb39e-171">In the following Scenarios sections are reference architectures, example DNS, port/protocol definitions, and certificate requirements.</span></span> <span data-ttu-id="fb39e-172">DNS、ポート/プロトコル定義、証明書のニーズに関する図も含まれています。</span><span class="sxs-lookup"><span data-stu-id="fb39e-172">Also included are diagrams for your DNS, port/protocol definitions and certificate needs.</span></span> <span data-ttu-id="fb39e-173">この図では、他のチーム (たとえば、組織のネットワークチーム、公開キー基盤チーム、サーバー展開チーム) に入力して配布するためのテンプレートを提供します。</span><span class="sxs-lookup"><span data-stu-id="fb39e-173">The diagrams will provide a template for you to fill in and distribute to other teams (for example, your organization’s Network Team, Public Key Infrastructure Team, and Server Deployment Team).</span></span> <span data-ttu-id="fb39e-174">図の目的は、コミュニケーションを強化し、必要なエッジサーバー構成要素を実際の構成作業を行うユーザーに伝えるときの成功を確実にすることです。</span><span class="sxs-lookup"><span data-stu-id="fb39e-174">The goal of the diagrams is to enhance communication and to ensure success when communicating the required Edge Server configuration elements to the people who will do the actual configuration work.</span></span> <span data-ttu-id="fb39e-175">図と関連付けられた参照アーキテクチャを使用して展開を計画することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fb39e-175">We recommend that you use the diagrams and associated reference architectures to plan your deployment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

