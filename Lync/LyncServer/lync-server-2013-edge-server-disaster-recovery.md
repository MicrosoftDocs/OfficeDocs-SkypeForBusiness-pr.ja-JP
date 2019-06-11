---
title: 'Lync Server 2013: エッジ サーバーの障害復旧'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d19e5a606c3217ad7653fd4c3c885a97aafdb5ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="45571-102">Lync Server 2013 でのエッジ サーバーの障害復旧</span><span class="sxs-lookup"><span data-stu-id="45571-102">Edge Server disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45571-103">_**最終更新日:** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="45571-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="45571-104">他のサーバーの役割と同様に、エッジサーバーの高可用性を実現する最良の方法は、各サイトのプールに複数のエッジサーバーを展開することです。</span><span class="sxs-lookup"><span data-stu-id="45571-104">As with other server roles, the best way for you to provide high availability for your Edge Servers is to deploy multiple Edge servers in pools in each site.</span></span> <span data-ttu-id="45571-105">1つのエッジサーバーがダウンした場合、プール内の他のサーバーは、引き続きエッジサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="45571-105">If one Edge Server goes down, the other servers in the pool will continue to provide Edge services.</span></span>

<span data-ttu-id="45571-106">障害回復手順を有効にするには、個別のサイトに別のエッジサーバープールを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45571-106">To enable disaster recovery procedures, you must have separate Edge Server pools deployed at separate sites.</span></span> <span data-ttu-id="45571-107">フロントエンドプールの場合と同様に、エッジプールを明示的にペアリングする必要はありませんが、エッジプールの1つが停止した場合でも、複数のエッジプールを使って実行できるかどうかが示されます。</span><span class="sxs-lookup"><span data-stu-id="45571-107">You do not need to explicitly pair Edge pools together as you do with Front End pools, but having multiple Edge pools still provides the availability to carry on if one entire Edge pool goes down.</span></span> <span data-ttu-id="45571-108">以下のセクションでは、エッジサーバーのさまざまな機能のディザスタリカバリの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="45571-108">The following sections provide details on disaster recovery for the various functions of Edge Servers.</span></span>

<div>

## <a name="remote-access"></a><span data-ttu-id="45571-109">リモートアクセス</span><span class="sxs-lookup"><span data-stu-id="45571-109">Remote Access</span></span>

<span data-ttu-id="45571-110">複数のサイトがあり、それぞれにエッジサーバーのプールがあり、1つのエッジプールが失敗した場合、リモートアクセスサービスは管理者の操作がなくても機能し続けます。</span><span class="sxs-lookup"><span data-stu-id="45571-110">If you have multiple sites, each with a pool of Edge servers, and one entire Edge pool fails, the remote access services will continue to function without needing administrator action.</span></span> <span data-ttu-id="45571-111">異なるサイトでエッジプールを作成する場合、同じ FQDN を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="45571-111">When creating Edge pools in different sites, you cannot use the same FQDN.</span></span> <span data-ttu-id="45571-112">各エッジプールには、固有の Fqdn (内部および外部) が必要です。</span><span class="sxs-lookup"><span data-stu-id="45571-112">Each Edge pool must have unique FQDNs (internal and external).</span></span> <span data-ttu-id="45571-113">エッジプールでは、フロントエンドサーバーとの通信にリバースプロキシの公開ルールは使用されません。</span><span class="sxs-lookup"><span data-stu-id="45571-113">The Edge pools do not use reverse proxy publishing rules to talk to the Front End servers.</span></span> <span data-ttu-id="45571-114">自動フェールオーバーは、クライアントがリモートアクセスの DNS サービスレコードを再照会したときに、リモートユーザーが別のサイトのエッジサーバーにルーティングされたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="45571-114">Automatic failover occurs when the client re-queries the remote access DNS service records, and remote users are routed to the Edge servers in another site.</span></span> <span data-ttu-id="45571-115">クライアントは、DNS SRV レコードの優先度に従って各外部エッジ FQDN を試します。</span><span class="sxs-lookup"><span data-stu-id="45571-115">The client attempts each external Edge FQDN according to the priority of the DNS SRV records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="45571-116">フェールオーバーがスムーズに動作するためには、すべてのプールのフロントエンドサーバーがすべてのエッジサーバーと通信できるように、ファイアウォールが有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="45571-116">For failover to work smoothly, ensure that the firewall allows the Front End servers from every pool to communicate with all Edge servers.</span></span>



</div>

</div>

<div>

## <a name="federation"></a><span data-ttu-id="45571-117">フェデレーション</span><span class="sxs-lookup"><span data-stu-id="45571-117">Federation</span></span>

<span data-ttu-id="45571-118">Lync Server を実行している他の組織とのフェデレーション関係の場合、Geo DNS GTM のような解決策がある限り、受信フェデレーション要求は引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="45571-118">For federation relationships with other organizations running Lync Server, inbound federation requests will continue to work as long as you have solutions like Geo-DNS GTM.</span></span> <span data-ttu-id="45571-119">フェデレーションフェールオーバーは、SRV レコードの優先順位によるフェールオーバーを提供しないことを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="45571-119">It’s important to understand that federation failover does not provide failover with priority in SRV records.</span></span> <span data-ttu-id="45571-120">前に説明した解決策は、受信フェデレーションの障害回復機能を提供するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="45571-120">A solution provided earlier can help you provide disaster recovery capabilities for inbound federation.</span></span>

<span data-ttu-id="45571-121">送信フェデレーションは、常に組織内の公開されたエッジプールまたはエッジサーバーによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="45571-121">Outbound federation is always set up through one published Edge pool or Edge Server in the organization.</span></span> <span data-ttu-id="45571-122">このエッジプールがダウンしている場合は、トポロジビルダーを使用して、送信フェデレーションルートを変更し、まだ実行中のエッジプールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45571-122">If this Edge pool has gone down, you must use Topology Builder to change the outbound federation route to use an Edge pool which is still running.</span></span> <span data-ttu-id="45571-123">詳細については、「lync server server[フェデレーションで使用されるエッジプールを Lync server 2013 でフェールオーバー](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45571-123">For details, see [Failing over the Edge pool used for Lync Server federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span></span>

</div>

<div>

## <a name="xmpp-federation"></a><span data-ttu-id="45571-124">XMPP フェデレーション</span><span class="sxs-lookup"><span data-stu-id="45571-124">XMPP Federation</span></span>

<span data-ttu-id="45571-125">XMPP フェデレーションの場合、xmpp フェデレーションゲートウェイとして指定されているエッジプールが停止すると、送信トラフィックと受信トラフィックの両方が失敗します。</span><span class="sxs-lookup"><span data-stu-id="45571-125">For XMPP federation, both outbound and inbound traffic will fail if the Edge pool which is designated as the XMPP federation gateway goes down.</span></span> <span data-ttu-id="45571-126">XMPP フェデレーションを再度有効にするには、別のエッジプールを使用するように XMPP フェデレーションを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45571-126">To make XMPP federation work again, you must change XMPP federation to use a different Edge pool.</span></span> <span data-ttu-id="45571-127">詳細については、「 [Lync Server 2013 で XMPP フェデレーションに使用されているエッジプールの障害](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)を確認する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45571-127">For details, see [Failing over the Edge pool used for XMPP federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span></span>

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a><span data-ttu-id="45571-128">エッジプールは失敗したが、フロントエンドプールがまだ実行されている</span><span class="sxs-lookup"><span data-stu-id="45571-128">Edge Pool Fails But Front End Pool Is Still Running</span></span>

<span data-ttu-id="45571-129">エッジプールがサイトで失敗しても、そのサイトのフロントエンドプールがまだ実行されている場合は、最初のエッジプールが停止している間に別のサイトで異なるエッジプールを使用するように、フロントエンドプールを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45571-129">If an Edge pool fails at a site, but the Front End pool at that site is still running, you will need to change the Front End pool to use a different Edge pool at a different site while that first Edge pool is down.</span></span> <span data-ttu-id="45571-130">詳細については、「 [Lync Server 2013 でフロントエンドプールに関連付けられているエッジプールを変更する](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45571-130">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

