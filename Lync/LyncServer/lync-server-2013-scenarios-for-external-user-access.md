---
title: 'Lync Server 2013: 外部ユーザーアクセスのシナリオ'
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
ms.openlocfilehash: 3e9a2f60b2273cf8d43833226ede66a2a90478a6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="42f26-102">Lync Server 2013 での外部ユーザーアクセスのシナリオ</span><span class="sxs-lookup"><span data-stu-id="42f26-102">Scenarios for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42f26-103">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="42f26-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="42f26-104">Lync Server 2013 の外部ユーザーアクセスを提供するには、境界ネットワークに少なくとも1つのエッジサーバーと1つのリバースプロキシを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42f26-104">Providing external user access for Lync Server 2013 requires that you deploy at least one Edge Server and one reverse proxy in your perimeter network.</span></span> <span data-ttu-id="42f26-105">必要に応じて、ディレクターまたはディレクタープールを内部ネットワークに展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="42f26-105">Optionally, you may deploy a Director or Director pool in your internal network.</span></span>

<span data-ttu-id="42f26-106">1台のエッジサーバーが提供できるよりも多くの容量が必要な場合や、エッジサーバーの展開に高可用性が必要な場合は、負荷分散を構成し、複数のエッジサーバーを負荷分散プールに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="42f26-106">If you need greater capacity than a single Edge Server can provide, or if you need high availability for your Edge Server deployment, you can configure load balancing and deploy multiple Edge Servers in a load balanced pool.</span></span> <span data-ttu-id="42f26-107">組織に複数のデータセンターがある場合は、複数の場所にエッジサーバーまたはエッジプールを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="42f26-107">If your organization has multiple data centers, you can have Edge Server or Edge pool deployments at more than one location.</span></span> <span data-ttu-id="42f26-108">ただし、1つのエッジサーバー展開のみをフェデレーションルートとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="42f26-108">However, only one of the Edge Server deployments can be designated as the federation route.</span></span>

<span data-ttu-id="42f26-109">このセクションでは、エッジサーバー展開のシナリオを定義し、計画セクションを考えられるシナリオにマップします。</span><span class="sxs-lookup"><span data-stu-id="42f26-109">This section defines the scenarios for Edge Server deployments and maps the planning sections to the possible scenarios.</span></span> <span data-ttu-id="42f26-110">たとえば、高可用性、拡張可能なメッセージングとプレゼンス (XMPP) 連絡先、および Lync モビリティを必要とする展開では、次の表の一致するエントリを選択して、これらの要件を満たすことができます。次のフローチャートに示されているように、展開を定義するための計画セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="42f26-110">For example, if your deployment requires high availability, federation with extensible messaging and presence (XMPP) contacts, and Lync mobility, you would select the matching entries in the following table that would satisfy these requirements and use the referenced planning sections to define your deployment, as illustrated in the following flowchart.</span></span>

<span data-ttu-id="42f26-111">**エッジ サーバー展開シナリオの選択プロセス**</span><span class="sxs-lookup"><span data-stu-id="42f26-111">**Edge Server deployment scenario selection process**</span></span>

<span data-ttu-id="42f26-112">![展開のフローチャートの例](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "展開のフローチャートの例")</span><span class="sxs-lookup"><span data-stu-id="42f26-112">![Sample deployment flowchart](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Sample deployment flowchart")</span></span>

<span data-ttu-id="42f26-113">このプロセスを使用すると、ユーザー用に展開する可能性があるすべての機能の構成を計画し、文書化することができます。</span><span class="sxs-lookup"><span data-stu-id="42f26-113">By using this process, you can plan for and document the configuration of all potential features that you intend to deploy for your users.</span></span> <span data-ttu-id="42f26-114">ただし、エッジサーバーを展開して、他の機能を追加する前に正しい操作を確認した後に、フェデレーションサービスとモビリティサービスを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="42f26-114">However, you can add federation and mobility services after you have deployed the Edge Server and have confirmed the correct operation before adding other features.</span></span> <span data-ttu-id="42f26-115">既存のエッジサーバー展開に機能を追加するプロセスについては、「展開」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="42f26-115">The process of adding features to an existing Edge Server deployment is covered in the Deployment section.</span></span> <span data-ttu-id="42f26-116">展開の詳細については、「 [Lync Server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。初期計画プロセスの際に、dns、ファイアウォール、および証明書の要件を計画することによって、追加された機能の dns、ファイアウォール、および証明書の要件を事前に準備できます。</span><span class="sxs-lookup"><span data-stu-id="42f26-116">For details on deployment, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) By including planning for these features during the initial planning process, you can prepare for the DNS, firewall, and certificate requirements for the added features, which enables you to acquire the certificates and configure DNS and port/protocol requirements in advance.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="42f26-117">エッジサーバーとリバースプロキシのインストールを計画していて、後で機能を追加する (たとえば、フェデレーションとモビリティ) 場合は、展開後にすべてのサービスに必要な証明書を決定します。</span><span class="sxs-lookup"><span data-stu-id="42f26-117">If you are planning to install the Edge Servers and reverse proxy and then add features later (for example, federation and mobility), determine what certificates you will require for all services after deployment.</span></span> <span data-ttu-id="42f26-118">事前に展開されているすべての機能の証明書を計画し、取得することにより、最初に展開したかしないかには、フェデレーションの要件 (つまりエッジサーバー) またはリバースプロキシ (つまりモビリティの場合) を満たす新しい証明書を注文する必要がなくなります。サービス)。</span><span class="sxs-lookup"><span data-stu-id="42f26-118">Planning for and acquiring the certificates for all features in advance, initially deployed or not, saves you from having to order new certificates to satisfy the requirements of federation (that is, on the Edge Servers) or the reverse proxy (that is, for mobility services).</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="42f26-119">各エッジサーバーですべてのエッジサービスが実行されます。</span><span class="sxs-lookup"><span data-stu-id="42f26-119">All edge services run on each Edge Server.</span></span> <span data-ttu-id="42f26-120">2つの異なるエッジサーバー間でサービスを分割することはできません。</span><span class="sxs-lookup"><span data-stu-id="42f26-120">Services cannot be split between two different Edge Servers.</span></span> <span data-ttu-id="42f26-121">スケーラビリティを確保するためにエッジプールを展開する場合は、すべてのエッジサービスがプール内の各エッジサーバーに展開されます。</span><span class="sxs-lookup"><span data-stu-id="42f26-121">If you deploy an Edge pool for scalability, all edge services are deployed on each Edge Server in the pool.</span></span> <span data-ttu-id="42f26-122">XMPP フェデレーション、Office Communications Server、Lync Server フェデレーション、パブリック IM 接続、およびクライアントモビリティは、最初のエッジサーバーまたはエッジプールを展開した後に展開できる追加のサービスです。</span><span class="sxs-lookup"><span data-stu-id="42f26-122">XMPP federation, Office Communications Server, and Lync Server federation, public IM connectivity and client mobility are additional services that can be deployed after you have deployed your first Edge Server or Edge pool.</span></span> <span data-ttu-id="42f26-123">モビリティ サービス機能では、リバース プロキシが使用されます。</span><span class="sxs-lookup"><span data-stu-id="42f26-123">Mobility services is a feature that uses the reverse proxy.</span></span> <span data-ttu-id="42f26-124">Mobility service をインストールしても、エッジサーバーに機能は追加されませんが、リバースプロキシの再構成が必要になります。</span><span class="sxs-lookup"><span data-stu-id="42f26-124">Installation of mobility services will not add features to your Edge Servers, but will require reconfiguration of your reverse proxy.</span></span> <span data-ttu-id="42f26-125">これらの機能を一覧表示する [<STRONG>インストールの目標</STRONG>] 列には、エッジサーバーをインストールして構成したときにこれらの機能を展開するための、<STRONG>エッジサーバーの計画セクションまたはセクション</STRONG>の下にある関連する列の計画ガイダンスが記載されています。</span><span class="sxs-lookup"><span data-stu-id="42f26-125">The <STRONG>Installation goal</STRONG> column that lists these features provides planning guidance in the associated column under <STRONG>Edge Server planning section or sections</STRONG> for concurrently planning these features to be deployed when the Edge Servers are installed and configured.</span></span>



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a><span data-ttu-id="42f26-126">展開の目標を見極めて対応付ける</span><span class="sxs-lookup"><span data-stu-id="42f26-126">Identifying and Mapping Your Deployment Goals</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42f26-127">インストールの目標</span><span class="sxs-lookup"><span data-stu-id="42f26-127">Installation goal</span></span></th>
<th><span data-ttu-id="42f26-128">エッジ サーバーの「計画」のドキュメント</span><span class="sxs-lookup"><span data-stu-id="42f26-128">Edge Server planning documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42f26-p107">現在のインフラストラクチャのエッジ サービスには、単一のサーバーで十分であると判断しました。また、エッジ サーバーの外部インターフェイスにはプライベート IP アドレスを使用し、NAT 経由でインターネットに接続する予定です。</span><span class="sxs-lookup"><span data-stu-id="42f26-p107">You have decided that a single server is sufficient for Edge services in your infrastructure. You also intend to use private IP addresses for the Edge server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="42f26-131">境界に単一エッジサーバーを展開する場合は、この計画セクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="42f26-131">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="42f26-132">エッジサーバーには、エッジサーバーに割り当てられたプライベート IP アドレスを使用してエッジサーバーを展開し、インターネット上の外部ユーザーのパブリック IP アドレスを提供するために NAT を使用します。</span><span class="sxs-lookup"><span data-stu-id="42f26-132">You will deploy an Edge Server with private IP addresses assigned to the Edge Server and will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="42f26-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Lync Server 2013 でのプライベート IP アドレスと NAT を使用する単一統合エッジ</a></span><span class="sxs-lookup"><span data-stu-id="42f26-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42f26-p109">現在のインフラストラクチャのエッジ サービスには、単一のサーバーで十分であると判断しました。また、エッジ サーバーの外部インターフェイスにはパブリック IP アドレスを使用してインターネットに接続する予定です。</span><span class="sxs-lookup"><span data-stu-id="42f26-p109">You have decided that a single server is sufficient for Edge services in your infrastructure. You also intend to use public IP addresses for the Edge server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="42f26-136">境界に単一エッジサーバーを展開する場合は、この計画セクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="42f26-136">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="42f26-137">エッジサーバーには、パブリック IP アドレスが割り当てられているエッジサーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="42f26-137">You will deploy an Edge Server with public IP addresses assigned to the Edge Server.</span></span> <span data-ttu-id="42f26-138">NAT の代わりに、このシナリオではルーティングを使用します。</span><span class="sxs-lookup"><span data-stu-id="42f26-138">Instead of NAT, you will use routing in this scenario.</span></span> <span data-ttu-id="42f26-139">エッジサーバーの実際のパブリック IP アドレスは、外部ユーザー接続に対して使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="42f26-139">The actual public IP address of the Edge Server are made available for external user connections.</span></span></p></td>
<td><p><span data-ttu-id="42f26-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Lync Server 2013 でのパブリック IP アドレスを使用する単一統合エッジ</a></span><span class="sxs-lookup"><span data-stu-id="42f26-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Single consolidated edge with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42f26-p111">ユーザーにとってエッジ サービスの高可用性が重要であると判断し、このプールに複数のエッジ サーバーを展開することにしました。また、エッジ サーバーの外部インターフェイスにはプライベート IP アドレスを使用し、NAT 経由でインターネットに接続する予定です。</span><span class="sxs-lookup"><span data-stu-id="42f26-p111">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool. You also intend to use private IP addresses for the Edge Server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="42f26-143">境界にエッジサーバーのプールを展開する場合は、この計画セクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="42f26-143">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="42f26-144">DNS 負荷分散を使用してプール間で通信を分散させるために、エッジサーバーに割り当てられたプライベート IP アドレスを使用してエッジサーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="42f26-144">You will deploy the Edge Servers with private IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="42f26-145">インターネット上の外部ユーザーには NAT を使用してパブリック IP アドレスを提供します。</span><span class="sxs-lookup"><span data-stu-id="42f26-145">You will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="42f26-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Lync Server 2013 での拡張統合エッジ、NAT を使用したプライベート IP アドレスを使用した DNS 負荷分散</a></span><span class="sxs-lookup"><span data-stu-id="42f26-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42f26-147">ユーザーにとってエッジ サービスの高可用性が重要であると判断し、このプールに複数のエッジ サーバーを展開することにしました。</span><span class="sxs-lookup"><span data-stu-id="42f26-147">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="42f26-148">また、エッジサーバーの外部インターフェイスのパブリック IP アドレスをインターネットにも使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="42f26-148">You also intend to use public IP addresses for the Edge Server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="42f26-149">境界にエッジサーバーのプールを展開する場合は、この計画セクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="42f26-149">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="42f26-150">DNS 負荷分散を使用してプール間で通信を分散させるために、エッジサーバーに割り当てられたパブリック IP アドレスを使用してエッジサーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="42f26-150">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="42f26-151">NAT の代わりにルーティングを使用して、インターネット上の外部ユーザーにパブリック IP アドレスを提供します。</span><span class="sxs-lookup"><span data-stu-id="42f26-151">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="42f26-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Lync Server 2013 の拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散</a></span><span class="sxs-lookup"><span data-stu-id="42f26-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42f26-153">エッジサービスの高可用性がユーザーにとって重要であると判断したため、このプールには、ロードバランサー機器を使用して2台以上のエッジサーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="42f26-153">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool using a hardware load balancer.</span></span></p>
<p><span data-ttu-id="42f26-154">境界にエッジサーバーのプールを展開する場合は、この計画セクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="42f26-154">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="42f26-155">エッジサーバーには、ハードウェアロードバランサーを使用してプール間で通信を分散させるパブリック IP アドレスを使用して、エッジサーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="42f26-155">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using hardware load balancers to distribute communication across the pool.</span></span> <span data-ttu-id="42f26-156">NAT の代わりにルーティングを使用して、インターネット上の外部ユーザーにパブリック IP アドレスを提供します。</span><span class="sxs-lookup"><span data-stu-id="42f26-156">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="42f26-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013 での拡張統合エッジとロードバランサー機器</a></span><span class="sxs-lookup"><span data-stu-id="42f26-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Scaled consolidated edge with hardware load balancers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42f26-158">フェデレーションのシナリオを使用すると、ユーザーが通信できるパートナーの種類を拡大する機能の計画を立てることができます。</span><span class="sxs-lookup"><span data-stu-id="42f26-158">The federation scenarios allow you to plan for the feature that will extend the types of partners that your users can communicate with.</span></span></p>
<ul>
<li><p><span data-ttu-id="42f26-159">Lync Server フェデレーション</span><span class="sxs-lookup"><span data-stu-id="42f26-159">Lync Server federation</span></span></p></li>
<li><p><span data-ttu-id="42f26-160">Office Communications Server のフェデレーション</span><span class="sxs-lookup"><span data-stu-id="42f26-160">Office Communications Server federation</span></span></p></li>
<li><p><span data-ttu-id="42f26-161">パブリック IM 接続</span><span class="sxs-lookup"><span data-stu-id="42f26-161">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="42f26-162">XMPP フェデレーション</span><span class="sxs-lookup"><span data-stu-id="42f26-162">XMPP federation</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="42f26-163">フェデレーションのシナリオの計画</span><span class="sxs-lookup"><span data-stu-id="42f26-163">Planning for Federation Scenarios</span></span></p>
<ul>
<li><p><span data-ttu-id="42f26-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Lync Server 2013 および Office Communications Server のフェデレーションの計画</a></span><span class="sxs-lookup"><span data-stu-id="42f26-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planning for Lync Server 2013 and Office Communications Server federation</a></span></span></p></li>
<li><p><span data-ttu-id="42f26-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセージング接続の計画</a></span><span class="sxs-lookup"><span data-stu-id="42f26-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planning for public instant messaging connectivity in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="42f26-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Lync Server 2013 での拡張メッセージングおよびプレゼンスプロトコル (XMPP) フェデレーションの計画</a></span><span class="sxs-lookup"><span data-stu-id="42f26-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42f26-167">モビリティ サービスはリバース プロキシを通じて提供されます。</span><span class="sxs-lookup"><span data-stu-id="42f26-167">Mobility services are offered through the reverse proxy.</span></span> <span data-ttu-id="42f26-168">外部ユーザーのモビリティを有効にするサービスは、フロントエンドサーバーまたはフロントエンドプールに展開されます。</span><span class="sxs-lookup"><span data-stu-id="42f26-168">Services that enable mobility for external users are deployed on the Front End Server or Front End pool.</span></span> <span data-ttu-id="42f26-169">リバース プロキシの公開ルールを作成または変更し、外部ユーザーに対してモビリティ サービスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="42f26-169">You create or modify existing publishing rules on the reverse proxy to enable mobility services for your external users.</span></span></p></td>
<td><p><span data-ttu-id="42f26-170"><a href="lync-server-2013-planning-for-mobility.md">Lync Server 2013 でのモビリティの計画</a></span><span class="sxs-lookup"><span data-stu-id="42f26-170"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> <span data-ttu-id="42f26-171">以下の「シナリオ」のセクションには、関連アーキテクチャ、DNS の例、ポート/プロトコルの定義、および証明書要件が記載されています。</span><span class="sxs-lookup"><span data-stu-id="42f26-171">In the following Scenarios sections are reference architectures, example DNS, port/protocol definitions, and certificate requirements.</span></span> <span data-ttu-id="42f26-172">また、DNS、ポート/プロトコルの定義、および証明書要件用の図表も含まれています。</span><span class="sxs-lookup"><span data-stu-id="42f26-172">Also included are diagrams for your DNS, port/protocol definitions and certificate needs.</span></span> <span data-ttu-id="42f26-173">この図表は、記入して他のチーム (組織のネットワーク チーム、公開キー基盤チーム、サーバー展開チームなど) に配布するためのテンプレートになります。</span><span class="sxs-lookup"><span data-stu-id="42f26-173">The diagrams will provide a template for you to fill in and distribute to other teams (for example, your organization’s Network Team, Public Key Infrastructure Team, and Server Deployment Team).</span></span> <span data-ttu-id="42f26-174">図の目的は、コミュニケーションを強化し、必要なエッジサーバー構成要素を実際の構成作業を行うユーザーに伝える際の成功を確実にすることです。</span><span class="sxs-lookup"><span data-stu-id="42f26-174">The goal of the diagrams is to enhance communication and to ensure success when communicating the required Edge Server configuration elements to the people who will do the actual configuration work.</span></span> <span data-ttu-id="42f26-175">展開を計画する際にはこの図表と関連アーキテクチャを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="42f26-175">We recommend that you use the diagrams and associated reference architectures to plan your deployment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

