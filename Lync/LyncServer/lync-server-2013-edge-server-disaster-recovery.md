---
title: 'Lync Server 2013: エッジサーバーの障害復旧'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aad1ac0197c4f7755b334624e46f7cec096897f5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528824"
---
# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="bd5b2-102">Lync Server 2013 でのエッジサーバーの障害復旧</span><span class="sxs-lookup"><span data-stu-id="bd5b2-102">Edge Server disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd5b2-103">_**トピックの最終更新日:** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="bd5b2-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="bd5b2-p101">エッジ サーバーで高可用性を実現する最適な方法は、ほかのサーバーの役割の場合と同様に、各サイト内のプールに複数のエッジ サーバーを展開することです。あるエッジ サーバーがダウンしても、プール内のほかのエッジ サーバーによって引き続きエッジ サービスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="bd5b2-p101">As with other server roles, the best way for you to provide high availability for your Edge Servers is to deploy multiple Edge servers in pools in each site. If one Edge Server goes down, the other servers in the pool will continue to provide Edge services.</span></span>

<span data-ttu-id="bd5b2-p102">障害復旧の手順を有効にするには、サイトごとに個別のエッジ サーバー プールを展開する必要があります。フロントエンド プールの場合に行うような明示的なエッジ プールのペアリングは不要ですが、複数のエッジ プールによって、あるエッジ プール全体がダウンしても可用性を維持できるようにしておく必要があります。以降のセクションでは、エッジ サーバーの各種機能の障害復旧について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="bd5b2-p102">To enable disaster recovery procedures, you must have separate Edge Server pools deployed at separate sites. You do not need to explicitly pair Edge pools together as you do with Front End pools, but having multiple Edge pools still provides the availability to carry on if one entire Edge pool goes down. The following sections provide details on disaster recovery for the various functions of Edge Servers.</span></span>

<div>

## <a name="remote-access"></a><span data-ttu-id="bd5b2-109">リモート アクセス</span><span class="sxs-lookup"><span data-stu-id="bd5b2-109">Remote Access</span></span>

<span data-ttu-id="bd5b2-110">複数のサイトがあり、それぞれにエッジサーバーのプールがあり、エッジプール全体で障害が発生すると、リモートアクセスサービスは管理者の操作なしで引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="bd5b2-110">If you have multiple sites, each with a pool of Edge servers, and one entire Edge pool fails, the remote access services will continue to function without needing administrator action.</span></span> <span data-ttu-id="bd5b2-111">異なるサイトにエッジプールを作成する場合、同じ FQDN を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="bd5b2-111">When creating Edge pools in different sites, you cannot use the same FQDN.</span></span> <span data-ttu-id="bd5b2-112">各エッジプールには、固有の Fqdn (内部および外部) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd5b2-112">Each Edge pool must have unique FQDNs (internal and external).</span></span> <span data-ttu-id="bd5b2-113">エッジプールは、フロントエンドサーバーとの通信にリバースプロキシ公開ルールを使用しません。</span><span class="sxs-lookup"><span data-stu-id="bd5b2-113">The Edge pools do not use reverse proxy publishing rules to talk to the Front End servers.</span></span> <span data-ttu-id="bd5b2-114">自動フェールオーバーは、クライアントがリモートアクセス DNS サービスレコードを再照会し、リモートユーザーが別のサイトのエッジサーバーにルーティングされるときに発生します。</span><span class="sxs-lookup"><span data-stu-id="bd5b2-114">Automatic failover occurs when the client re-queries the remote access DNS service records, and remote users are routed to the Edge servers in another site.</span></span> <span data-ttu-id="bd5b2-115">クライアントは、DNS SRV レコードの優先度に従って各外部エッジ FQDN を試行します。</span><span class="sxs-lookup"><span data-stu-id="bd5b2-115">The client attempts each external Edge FQDN according to the priority of the DNS SRV records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bd5b2-116">フェールオーバーを円滑に動作させるには、ファイアウォールがすべてのプールのフロントエンドサーバーをすべてのエッジサーバーと通信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="bd5b2-116">For failover to work smoothly, ensure that the firewall allows the Front End servers from every pool to communicate with all Edge servers.</span></span>



</div>

</div>

<div>

## <a name="federation"></a><span data-ttu-id="bd5b2-117">フェデレーション</span><span class="sxs-lookup"><span data-stu-id="bd5b2-117">Federation</span></span>

<span data-ttu-id="bd5b2-118">Lync Server を実行している他の組織とのフェデレーション関係については、Geo DNS GTM のようなソリューションがある限り、受信フェデレーション要求は引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="bd5b2-118">For federation relationships with other organizations running Lync Server, inbound federation requests will continue to work as long as you have solutions like Geo-DNS GTM.</span></span> <span data-ttu-id="bd5b2-119">フェデレーションフェールオーバーでは、SRV レコードに優先度の高いフェールオーバーが提供されないことを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="bd5b2-119">It’s important to understand that federation failover does not provide failover with priority in SRV records.</span></span> <span data-ttu-id="bd5b2-120">以前提供したソリューションでは、受信フェデレーションの障害復旧機能を提供するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bd5b2-120">A solution provided earlier can help you provide disaster recovery capabilities for inbound federation.</span></span>

<span data-ttu-id="bd5b2-121">送信フェデレーションのセットアップは、必ず組織内の 1 つの公開エッジ プールまたはエッジ サーバーによって行われます。</span><span class="sxs-lookup"><span data-stu-id="bd5b2-121">Outbound federation is always set up through one published Edge pool or Edge Server in the organization.</span></span> <span data-ttu-id="bd5b2-122">このエッジ プールがダウンしている場合は、トポロジ ビルダーによって、動作しているエッジ プールが使用されるように送信フェデレーションのルートを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd5b2-122">If this Edge pool has gone down, you must use Topology Builder to change the outbound federation route to use an Edge pool which is still running.</span></span> <span data-ttu-id="bd5b2-123">詳細については、「lync server[フェデレーションで使用されるエッジプールのフェールオーバー (Lync server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md) )」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd5b2-123">For details, see [Failing over the Edge pool used for Lync Server federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span></span>

</div>

<div>

## <a name="xmpp-federation"></a><span data-ttu-id="bd5b2-124">XMPP フェデレーション</span><span class="sxs-lookup"><span data-stu-id="bd5b2-124">XMPP Federation</span></span>

<span data-ttu-id="bd5b2-125">XMPP フェデレーションでは、XMPP フェデレーション ゲートウェイとして指定されているエッジ プールがダウンすると、送信トラフィックと受信トラフィックの両方でエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="bd5b2-125">For XMPP federation, both outbound and inbound traffic will fail if the Edge pool which is designated as the XMPP federation gateway goes down.</span></span> <span data-ttu-id="bd5b2-126">XMPP フェデレーションを再び機能させるには、別のエッジ プールを使用するように XMPP フェデレーションを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd5b2-126">To make XMPP federation work again, you must change XMPP federation to use a different Edge pool.</span></span> <span data-ttu-id="bd5b2-127">詳細については、「 [Lync Server 2013 での XMPP フェデレーションに使用するエッジプールのフェールオーバー](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd5b2-127">For details, see [Failing over the Edge pool used for XMPP federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span></span>

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a><span data-ttu-id="bd5b2-128">エッジ プールで障害が発生してもフロントエンド プールが動作している場合</span><span class="sxs-lookup"><span data-stu-id="bd5b2-128">Edge Pool Fails But Front End Pool Is Still Running</span></span>

<span data-ttu-id="bd5b2-129">あるサイトでエッジ プールに障害が発生しても、そのサイトのフロントエンド プールが動作している場合は、障害の発生したエッジ プールがダウンしている間は異なるサイトにある別のエッジ プールを使用するようにフロントエンド プールを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd5b2-129">If an Edge pool fails at a site, but the Front End pool at that site is still running, you will need to change the Front End pool to use a different Edge pool at a different site while that first Edge pool is down.</span></span> <span data-ttu-id="bd5b2-130">詳細については、「 [Lync Server 2013 のフロントエンドプールに関連付けられたエッジプールの変更](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd5b2-130">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

