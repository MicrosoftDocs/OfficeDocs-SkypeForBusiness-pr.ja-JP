---
title: 'Lync Server 2013: 外部ユーザー アクセスに必要なコンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 895f2d4837eb465f0eead2b70cf1d603504699ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="cf0d4-102">Lync Server 2013 の外部ユーザー アクセスに必要なコンポーネント</span><span class="sxs-lookup"><span data-stu-id="cf0d4-102">Components required for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf0d4-103">_**最終更新日:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="cf0d4-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="cf0d4-104">ほとんどのエッジ コンポーネントは、境界ネットワークに展開されます。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-104">Most Edge components are deployed in a perimeter network.</span></span> <span data-ttu-id="cf0d4-105">次のコンポーネントは、境界ネットワークのエッジトポロジを構成します。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-105">The following components make up the edge topology of the perimeter network.</span></span> <span data-ttu-id="cf0d4-106">特に注記がない限り、コンポーネントは[Lync Server 2013 の外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)の一部であり、境界ネットワーク内にあります。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-106">Except where noted, the components are part of the [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and are in the perimeter network.</span></span> <span data-ttu-id="cf0d4-107">エッジ コンポーネントには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-107">Edge components include the following:</span></span>

  - <span data-ttu-id="cf0d4-108">Edge Servers</span><span class="sxs-lookup"><span data-stu-id="cf0d4-108">Edge Servers</span></span>

  - <span data-ttu-id="cf0d4-109">Reverse proxies</span><span class="sxs-lookup"><span data-stu-id="cf0d4-109">Reverse proxies</span></span>

  - <span data-ttu-id="cf0d4-110">Firewalls</span><span class="sxs-lookup"><span data-stu-id="cf0d4-110">Firewalls</span></span>

  - <span data-ttu-id="cf0d4-111">ディレクター (オプション、論理的には内部ネットワーク上にあります)</span><span class="sxs-lookup"><span data-stu-id="cf0d4-111">Directors (optional, and logically located on the internal network)</span></span>

  - <span data-ttu-id="cf0d4-112">拡張されたエッジ トポロジの負荷分散 (DNS 負荷分散またはハードウェア ロード バランサー)</span><span class="sxs-lookup"><span data-stu-id="cf0d4-112">Load balancing for Scaled Edge Topologies (either DNS load balancing or a hardware load balancer)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cf0d4-p102">1 つのインターフェイスでハードウェア負荷分散を使用し、もう 1 つのインターフェイスで DNS 負荷分散を使用することはできません。両方のインターフェイスでハードウェア負荷分散を使用するか、両方で DNS 負荷分散を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>

    
    </div>

<div>

## <a name="edge-servers"></a><span data-ttu-id="cf0d4-115">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="cf0d4-115">Edge Servers</span></span>

<span data-ttu-id="cf0d4-116">エッジサーバーは、外部ユーザーによる内部展開によって提供されるサービスのネットワークトラフィックを送受信します。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-116">The Edge Servers send and receive network traffic for the services offered by internal deployment by external users.</span></span> <span data-ttu-id="cf0d4-117">エッジサーバーでは、次のサービスが実行されます。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-117">The Edge Server runs the following services:</span></span>

  - <span data-ttu-id="cf0d4-118">**エッジサービス**   へのアクセスアクセスエッジサービスは、送受信セッション開始プロトコル (SIP) トラフィックの単一の信頼できる接続ポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-118">**Access Edge service**   The Access Edge service provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>

  - <span data-ttu-id="cf0d4-119">**Web 会議エッジサービス**   web 会議エッジサービスを使うと、外部ユーザーは、社内の Lync Server 2013 展開でホストされている会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-119">**Web Conferencing Edge service**   The Web Conferencing Edge service enables external users to join meetings that are hosted on your internal Lync Server 2013 deployment.</span></span>

  - <span data-ttu-id="cf0d4-120">\*\*\*\*   A/v edge サービス a/v edge サービスにより、オーディオ、ビデオ、アプリケーション共有、ファイル転送を外部ユーザーが利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-120">**A/V Edge service**   The A/V Edge service makes audio, video, application sharing, and file transfer available to external users.</span></span> <span data-ttu-id="cf0d4-121">ユーザーは、外部の参加者が含まれている会議に音声やビデオを追加することができます。また、ポイントツーポイントのセッションで外部ユーザーと直接音声やビデオを使って通信できます。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-121">Your users can add audio and video to meetings that include external participants, and they can communicate using audio and/or video directly with an external user in point-to-point sessions.</span></span> <span data-ttu-id="cf0d4-122">また、A/V Edge サービスでは、デスクトップ共有とファイル転送をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-122">The A/V Edge service also provides support for desktop sharing and file transfer.</span></span>

  - <span data-ttu-id="cf0d4-123">**Xmpp プロキシサービス**   xmpp プロキシサービスは、構成済みの xmpp フェデレーションパートナーとの間で、拡張可能なメッセージングとプレゼンスプロトコル (xmpp) のメッセージを受け取り、送信します。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-123">**XMPP Proxy service**   The XMPP Proxy service accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>

<span data-ttu-id="cf0d4-124">承認された外部ユーザーは、内部の Lync Server 2013 の展開に接続するためにエッジサーバーにアクセスできますが、エッジサーバーは、内部ネットワークへの他のアクセスの手段を提供しません。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-124">Authorized external users can access the Edge Servers in order to connect to your internal Lync Server 2013 deployment, but the Edge Servers do not provide a means for any other access to the internal network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cf0d4-125">エッジサーバーは、有効になっている Lync クライアントやその他の Microsoft Edge サーバー (フェデレーションシナリオの場合) への接続を提供するために展開されます。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-125">Edge servers are deployed to provide connections for enabled Lync clients and other Microsoft Edge servers (as in federation scenarios).</span></span> <span data-ttu-id="cf0d4-126">他のエンドポイントクライアントまたはサーバーの種類からの接続を許可するように設計されていません。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-126">They are not designed to allow connections from other end point client or server types.</span></span> <span data-ttu-id="cf0d4-127">XMPP ゲートウェイサーバーを展開して、構成済みの XMPP パートナーとの接続を許可することができます。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-127">The XMPP Gateway server can be deployed to allow connections with configured XMPP partners.</span></span> <span data-ttu-id="cf0d4-128">エッジサーバーと XMPP ゲートウェイは、これらのクライアントとフェデレーションの種類からのエンドポイント接続のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-128">The Edge server and XMPP Gateway can only support end point connections from these client and federation types.</span></span>



</div>

</div>

<div>

## <a name="reverse-proxy"></a><span data-ttu-id="cf0d4-129">リバース プロキシ</span><span class="sxs-lookup"><span data-stu-id="cf0d4-129">Reverse Proxy</span></span>

<span data-ttu-id="cf0d4-130">リバースプロキシは、次の場合に必要になります。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-130">The reverse proxy is required for the following:</span></span>

  - <span data-ttu-id="cf0d4-131">ユーザーが単純な Url を使用して会議またはダイヤルイン会議に接続できるようにするには</span><span class="sxs-lookup"><span data-stu-id="cf0d4-131">To allow users to connect to meetings or dial-in conferences using simple URLs</span></span>

  - <span data-ttu-id="cf0d4-132">外部ユーザーが会議コンテンツをダウンロードできるようにするには</span><span class="sxs-lookup"><span data-stu-id="cf0d4-132">To enable external users to download meeting content</span></span>

  - <span data-ttu-id="cf0d4-133">外部ユーザーが配布グループを展開できるようにするには</span><span class="sxs-lookup"><span data-stu-id="cf0d4-133">To enable external users to expand distribution groups</span></span>

  - <span data-ttu-id="cf0d4-134">クライアント証明書ベースの認証用にユーザーベースの証明書を取得することをユーザーに許可するには</span><span class="sxs-lookup"><span data-stu-id="cf0d4-134">To allow the user to obtain a user-based certificate for client certificate based authentication</span></span>

  - <span data-ttu-id="cf0d4-135">リモートユーザーがアドレス帳サーバーからファイルをダウンロードできるようにする、またはアドレス帳 Web クエリサービスにクエリを送信できるようにするには</span><span class="sxs-lookup"><span data-stu-id="cf0d4-135">To enable remote users to download files from the Address Book Server or to submit queries to the Address Book Web Query service</span></span>

  - <span data-ttu-id="cf0d4-136">リモートユーザーがクライアントとデバイスのソフトウェアの更新プログラムを入手できるようにするには</span><span class="sxs-lookup"><span data-stu-id="cf0d4-136">To enable remote users to obtain updates to client and device software</span></span>

  - <span data-ttu-id="cf0d4-137">モバイルデバイスでモビリティサービスを提供するフロントエンドサーバーを自動的に検出できるようにするには</span><span class="sxs-lookup"><span data-stu-id="cf0d4-137">To enable mobile devices to automatically discover Front End Servers offering mobility services</span></span>

  - <span data-ttu-id="cf0d4-138">Office 365 または Apple プッシュ通知サービスからモバイルデバイスへのプッシュ通知を有効にするには</span><span class="sxs-lookup"><span data-stu-id="cf0d4-138">To enable push notifications to mobile devices from the Office 365 or Apple push notification services</span></span>

<span data-ttu-id="cf0d4-139">リバースプロキシとリバースプロキシが満たす必要のある要件の詳細については、「 [Lync Server 2013 のリバースプロキシの構成要件](lync-server-2013-configuration-requirements-for-reverse-proxy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-139">For additional information related to reverse proxies and the requirements that reverse proxies must meet, see the details in [Configuration requirements for reverse proxy in Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cf0d4-140">外部ユーザーは、Lync Server 2013 を使って通信に参加するために、組織への仮想プライベートネットワーク (VPN) 接続を必要としません。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-140">External users do not need a virtual private network (VPN) connection to your organization in order to participate in communications using Lync Server 2013.</span></span> <span data-ttu-id="cf0d4-141">組織に VPN テクノロジを実装していて、ユーザーが Lync 用 VPN を使用している場合、メディアトラフィック (ビデオ会議など) に悪影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-141">If you have implemented VPN technology in your organization and your users use the VPN for Lync, media traffic (such as video conferencing) can be adversely affected.</span></span> <span data-ttu-id="cf0d4-142">メディアトラフィックが AV Edge サービスに直接接続し、VPN をバイパスするための手段を提供することを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-142">You should consider providing a means for media traffic to connect to the AV Edge service directly and bypass the VPN.</span></span> <span data-ttu-id="cf0d4-143">詳細については、「NextHop のブログ記事「VPN トンネルをバイパスするように Lync メディア<A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>を有効にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-143">For details, see the NextHop Blog article, “Enabling Lync Media to Bypass a VPN Tunnel,” at <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>.</span></span>



</div>

</div>

<div>

## <a name="firewall"></a><span data-ttu-id="cf0d4-144">ファイアウォール</span><span class="sxs-lookup"><span data-stu-id="cf0d4-144">Firewall</span></span>

<span data-ttu-id="cf0d4-145">外部ファイアウォールのみ、または外部ファイアウォールと内部ファイアウォールの両方を使用して、エッジトポロジを展開できます。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-145">You can deploy your edge topology with only an external firewall or both external and internal firewalls.</span></span> <span data-ttu-id="cf0d4-146">シナリオアーキテクチャには2つのファイアウォールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-146">The scenario architectures include two firewalls.</span></span> <span data-ttu-id="cf0d4-147">2つのファイアウォールを使用することは、1つのネットワーク境界から他方への厳密なルーティングを確実に行うため、また、2つのファイアウォールの背後にある内部展開を保護するためのアプローチとして推奨されます。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-147">Using two firewalls is the recommended approach because it ensures strict routing from one network edge to the other, and it protects your internal deployment behind two levels of firewall.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="cf0d4-148">ディレクター</span><span class="sxs-lookup"><span data-stu-id="cf0d4-148">Director</span></span>

<span data-ttu-id="cf0d4-149">ディレクターは、Lync Server 2013 で、ユーザーアカウントを持たない、またはプレゼンスまたは会議サービスを提供する、個別のオプションのサーバーの役割です。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-149">A Director is a separate, optional server role in Lync Server 2013 that does not home user accounts, or provide presence or conferencing services.</span></span> <span data-ttu-id="cf0d4-150">これは、内部サーバーに向けて、エッジサーバーが受信 SIP トラフィックをルーティングする、内部の次ホップサーバーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-150">It serves as an internal next hop server to which an Edge Server routes inbound SIP traffic destined for internal servers.</span></span> <span data-ttu-id="cf0d4-151">ディレクターは受信要求を事前に認証し、ユーザーのホームプールまたはサーバーにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-151">The Director preauthenticates inbound requests and redirects them to the user’s home pool or server.</span></span> <span data-ttu-id="cf0d4-152">ディレクターで事前認証することで、展開に対して不明なユーザーアカウントからの要求をドロップできます。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-152">By preauthenticating at the Director, you can drop requests from user accounts that are unknown to the deployment.</span></span>

<span data-ttu-id="cf0d4-153">ディレクターは、サービス拒否 (DoS) 攻撃などの悪意のあるトラフィックから、Enterprise Edition フロントエンドプールの標準エディションサーバーとフロントエンドサーバーを分離するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-153">A Director helps insulate Standard Edition servers and Front End Servers in Enterprise Edition Front End pools from malicious traffic such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="cf0d4-154">このような攻撃で無効な外部トラフィックがネットワークにあふれている場合、トラフィックはディレクターで終了します。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-154">If the network is flooded with invalid external traffic in such an attack, the traffic ends at the Director.</span></span> <span data-ttu-id="cf0d4-155">ディレクターの使用の詳細については、「 [Lync Server 2013 のディレクターのシナリオ](lync-server-2013-scenarios-for-the-director.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf0d4-155">For details about the use of Directors, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cf0d4-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf0d4-156">See Also</span></span>


[<span data-ttu-id="cf0d4-157">Lync Server 2013 のハードウェア ロード バランサーの要件</span><span class="sxs-lookup"><span data-stu-id="cf0d4-157">Hardware load balancer requirements for Lync Server 2013</span></span>](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

