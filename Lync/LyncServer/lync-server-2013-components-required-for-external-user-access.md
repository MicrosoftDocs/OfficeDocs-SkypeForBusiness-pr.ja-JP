---
title: 'Lync Server 2013: 外部ユーザーアクセスに必要なコンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31381edc58240d990096b47498b5c98845af5b2d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147310"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="5e260-102">Lync Server 2013 での外部ユーザーアクセスに必要なコンポーネント</span><span class="sxs-lookup"><span data-stu-id="5e260-102">Components required for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e260-103">_**トピックの最終更新日:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="5e260-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="5e260-104">ほとんどのエッジコンポーネントは、境界ネットワーク内に展開されます。</span><span class="sxs-lookup"><span data-stu-id="5e260-104">Most Edge components are deployed in a perimeter network.</span></span> <span data-ttu-id="5e260-105">境界ネットワークのエッジ トポロジは、次のコンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="5e260-105">The following components make up the edge topology of the perimeter network.</span></span> <span data-ttu-id="5e260-106">特に明記されていない限り、コンポーネントは[Lync Server 2013 の外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)の一部であり、境界ネットワークに存在します。</span><span class="sxs-lookup"><span data-stu-id="5e260-106">Except where noted, the components are part of the [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and are in the perimeter network.</span></span> <span data-ttu-id="5e260-107">エッジ コンポーネントには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e260-107">Edge components include the following:</span></span>

  - <span data-ttu-id="5e260-108">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="5e260-108">Edge Servers</span></span>

  - <span data-ttu-id="5e260-109">リバースプロキシ</span><span class="sxs-lookup"><span data-stu-id="5e260-109">Reverse proxies</span></span>

  - <span data-ttu-id="5e260-110">ファイアウォール</span><span class="sxs-lookup"><span data-stu-id="5e260-110">Firewalls</span></span>

  - <span data-ttu-id="5e260-111">ディレクター (オプション、および論理的に内部ネットワーク上に配置)</span><span class="sxs-lookup"><span data-stu-id="5e260-111">Directors (optional, and logically located on the internal network)</span></span>

  - <span data-ttu-id="5e260-112">拡張されたエッジ トポロジの負荷分散 (DNS 負荷分散またはハードウェア ロード バランサー)</span><span class="sxs-lookup"><span data-stu-id="5e260-112">Load balancing for Scaled Edge Topologies (either DNS load balancing or a hardware load balancer)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5e260-p102">1 つのインターフェイスでハードウェア負荷分散を使用し、もう 1 つのインターフェイスで DNS 負荷分散を使用することはできません。両方のインターフェイスでハードウェア負荷分散を使用するか、両方で DNS 負荷分散を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e260-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>

    
    </div>

<div>

## <a name="edge-servers"></a><span data-ttu-id="5e260-115">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="5e260-115">Edge Servers</span></span>

<span data-ttu-id="5e260-116">エッジサーバーは、外部ユーザーによって内部展開によって提供されるサービスへのネットワークトラフィックを送受信します。</span><span class="sxs-lookup"><span data-stu-id="5e260-116">The Edge Servers send and receive network traffic for the services offered by internal deployment by external users.</span></span> <span data-ttu-id="5e260-117">エッジ サーバーは、次のサービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e260-117">The Edge Server runs the following services:</span></span>

  - <span data-ttu-id="5e260-118">**アクセスエッジサービス**   アクセスエッジサービスは、発信および受信のセッション開始プロトコル (SIP) トラフィックに対して、1つの信頼できる接続ポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="5e260-118">**Access Edge service**   The Access Edge service provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>

  - <span data-ttu-id="5e260-119">**Web 会議エッジサービス**   web 会議エッジサービスを使用すると、外部ユーザーは内部の Lync Server 2013 展開でホストされている会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="5e260-119">**Web Conferencing Edge service**   The Web Conferencing Edge service enables external users to join meetings that are hosted on your internal Lync Server 2013 deployment.</span></span>

  - <span data-ttu-id="5e260-120">\*\*\*\*   音声ビデオエッジサービス音声ビデオエッジサービスは、オーディオ、ビデオ、アプリケーション共有、およびファイル転送を外部ユーザーが使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5e260-120">**A/V Edge service**   The A/V Edge service makes audio, video, application sharing, and file transfer available to external users.</span></span> <span data-ttu-id="5e260-121">ユーザーは、外部の参加者を含む会議に音声とビデオを追加できます。また、音声やビデオを使用して、ポイントツーポイントのセッションで外部ユーザーと直接通信することもできます。</span><span class="sxs-lookup"><span data-stu-id="5e260-121">Your users can add audio and video to meetings that include external participants, and they can communicate using audio and/or video directly with an external user in point-to-point sessions.</span></span> <span data-ttu-id="5e260-122">また、音声ビデオ エッジ サービスはデスクトップ共有とファイル送信もサポートします。</span><span class="sxs-lookup"><span data-stu-id="5e260-122">The A/V Edge service also provides support for desktop sharing and file transfer.</span></span>

  - <span data-ttu-id="5e260-123">**Xmpp プロキシサービス**   xmpp プロキシサービスは、構成された xmpp フェデレーションパートナーとの間で、拡張可能なメッセージとプレゼンスプロトコル (xmpp) メッセージを送受信します。</span><span class="sxs-lookup"><span data-stu-id="5e260-123">**XMPP Proxy service**   The XMPP Proxy service accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>

<span data-ttu-id="5e260-124">許可された外部ユーザーは、内部の Lync Server 2013 展開に接続するためにエッジサーバーにアクセスできますが、エッジサーバーは、内部ネットワークへの他のアクセスに対する手段を提供しません。</span><span class="sxs-lookup"><span data-stu-id="5e260-124">Authorized external users can access the Edge Servers in order to connect to your internal Lync Server 2013 deployment, but the Edge Servers do not provide a means for any other access to the internal network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5e260-125">エッジサーバーは、有効になっている Lync クライアントおよびその他の Microsoft エッジサーバー (フェデレーションのシナリオなど) への接続を提供するために展開されます。</span><span class="sxs-lookup"><span data-stu-id="5e260-125">Edge servers are deployed to provide connections for enabled Lync clients and other Microsoft Edge servers (as in federation scenarios).</span></span> <span data-ttu-id="5e260-126">他の種類のエンド ポイント クライアントやサーバーからの接続を許可するようには設計されていません。</span><span class="sxs-lookup"><span data-stu-id="5e260-126">They are not designed to allow connections from other end point client or server types.</span></span> <span data-ttu-id="5e260-127">XMPP ゲートウェイ サーバーは、構成済み XMPP パートナーとの接続を許可するように展開できます。</span><span class="sxs-lookup"><span data-stu-id="5e260-127">The XMPP Gateway server can be deployed to allow connections with configured XMPP partners.</span></span> <span data-ttu-id="5e260-128">エッジ サーバーと XMPP ゲートウェイでは、これらの種類のクライアントおよびフェデレーションからのエンド ポイント接続のみをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="5e260-128">The Edge server and XMPP Gateway can only support end point connections from these client and federation types.</span></span>



</div>

</div>

<div>

## <a name="reverse-proxy"></a><span data-ttu-id="5e260-129">リバース プロキシ</span><span class="sxs-lookup"><span data-stu-id="5e260-129">Reverse Proxy</span></span>

<span data-ttu-id="5e260-130">リバース プロキシは以下のことのために必要です。</span><span class="sxs-lookup"><span data-stu-id="5e260-130">The reverse proxy is required for the following:</span></span>

  - <span data-ttu-id="5e260-131">ユーザーが簡単な URL を使用して会議またはダイヤルイン会議に接続できるようにする。</span><span class="sxs-lookup"><span data-stu-id="5e260-131">To allow users to connect to meetings or dial-in conferences using simple URLs</span></span>

  - <span data-ttu-id="5e260-132">外部ユーザーが会議コンテンツをダウンロードできるようにする。</span><span class="sxs-lookup"><span data-stu-id="5e260-132">To enable external users to download meeting content</span></span>

  - <span data-ttu-id="5e260-133">外部ユーザーが配布グループを拡張できるようにする。</span><span class="sxs-lookup"><span data-stu-id="5e260-133">To enable external users to expand distribution groups</span></span>

  - <span data-ttu-id="5e260-134">ユーザーが、クライアント証明書ベースの認証用のユーザーベースの証明書を取得できるようにする。</span><span class="sxs-lookup"><span data-stu-id="5e260-134">To allow the user to obtain a user-based certificate for client certificate based authentication</span></span>

  - <span data-ttu-id="5e260-135">リモート ユーザーがアドレス帳サーバーからファイルをダウンロードしたり、アドレス帳 Web クエリ サービスにクエリを送信したりできるようにする。</span><span class="sxs-lookup"><span data-stu-id="5e260-135">To enable remote users to download files from the Address Book Server or to submit queries to the Address Book Web Query service</span></span>

  - <span data-ttu-id="5e260-136">リモート ユーザーがクライアントおよびデバイス ソフトウェアの更新プログラムを取得できるようにする。</span><span class="sxs-lookup"><span data-stu-id="5e260-136">To enable remote users to obtain updates to client and device software</span></span>

  - <span data-ttu-id="5e260-137">モビリティ サービスを提供するフロント エンド サーバーをモバイル デバイスが自動的に検出できるようにする。</span><span class="sxs-lookup"><span data-stu-id="5e260-137">To enable mobile devices to automatically discover Front End Servers offering mobility services</span></span>

  - <span data-ttu-id="5e260-138">Office 365 または Apple のプッシュ通知サービスからモバイル デバイスへのプッシュ通知を有効にする。</span><span class="sxs-lookup"><span data-stu-id="5e260-138">To enable push notifications to mobile devices from the Office 365 or Apple push notification services</span></span>

<span data-ttu-id="5e260-139">リバースプロキシとリバースプロキシが満たす必要がある要件に関連する追加情報については、「 [Lync Server 2013 のリバースプロキシの構成要件](lync-server-2013-configuration-requirements-for-reverse-proxy.md)」の詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e260-139">For additional information related to reverse proxies and the requirements that reverse proxies must meet, see the details in [Configuration requirements for reverse proxy in Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5e260-140">外部ユーザーは、Lync Server 2013 を使用して通信に参加するために、組織への仮想プライベートネットワーク (VPN) 接続を必要としません。</span><span class="sxs-lookup"><span data-stu-id="5e260-140">External users do not need a virtual private network (VPN) connection to your organization in order to participate in communications using Lync Server 2013.</span></span> <span data-ttu-id="5e260-141">組織に VPN テクノロジを実装しており、ユーザーが Lync の VPN を使用している場合は、メディアトラフィック (ビデオ会議など) に悪影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5e260-141">If you have implemented VPN technology in your organization and your users use the VPN for Lync, media traffic (such as video conferencing) can be adversely affected.</span></span> <span data-ttu-id="5e260-142">メディアトラフィックが AV エッジサービスに直接接続し、VPN をバイパスするための手段を提供することを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e260-142">You should consider providing a means for media traffic to connect to the AV Edge service directly and bypass the VPN.</span></span> <span data-ttu-id="5e260-143">詳細については、「NextHop」のブログ記事「VPN トンネルをバイパスするように Lync <A href="https://go.microsoft.com/fwlink/p/?linkid=256532">https://go.microsoft.com/fwlink/p/?LinkId=256532</A>メディアを有効にする」 (を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e260-143">For details, see the NextHop Blog article, “Enabling Lync Media to Bypass a VPN Tunnel,” at <A href="https://go.microsoft.com/fwlink/p/?linkid=256532">https://go.microsoft.com/fwlink/p/?LinkId=256532</A>.</span></span>



</div>

</div>

<div>

## <a name="firewall"></a><span data-ttu-id="5e260-144">ウォール</span><span class="sxs-lookup"><span data-stu-id="5e260-144">Firewall</span></span>

<span data-ttu-id="5e260-145">エッジトポロジは、外部ファイアウォールのみ、または外部および内部ファイアウォールの両方を使用して展開できます。</span><span class="sxs-lookup"><span data-stu-id="5e260-145">You can deploy your edge topology with only an external firewall or both external and internal firewalls.</span></span> <span data-ttu-id="5e260-146">シナリオアーキテクチャには2つのファイアウォールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5e260-146">The scenario architectures include two firewalls.</span></span> <span data-ttu-id="5e260-147">2つのファイアウォールを使用する方法をお勧めします。この方法は、1つのネットワークエッジからもう一方への厳密なルーティングを保証し、2つのレベルのファイアウォールの背後に内部展開を保護するために推奨されます。</span><span class="sxs-lookup"><span data-stu-id="5e260-147">Using two firewalls is the recommended approach because it ensures strict routing from one network edge to the other, and it protects your internal deployment behind two levels of firewall.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="5e260-148">ディレクター</span><span class="sxs-lookup"><span data-stu-id="5e260-148">Director</span></span>

<span data-ttu-id="5e260-149">ディレクターは、Lync Server 2013 の個別のオプションのサーバーの役割で、ユーザーアカウントをホームにしたり、プレゼンスや会議サービスを提供したりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="5e260-149">A Director is a separate, optional server role in Lync Server 2013 that does not home user accounts, or provide presence or conferencing services.</span></span> <span data-ttu-id="5e260-150">これは、エッジサーバーが内部サーバー宛ての受信 SIP トラフィックをルーティングする、内部の次ホップサーバーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="5e260-150">It serves as an internal next hop server to which an Edge Server routes inbound SIP traffic destined for internal servers.</span></span> <span data-ttu-id="5e260-151">ディレクターは、受信要求を事前認証し、ユーザーのホームプールまたはサーバーにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="5e260-151">The Director preauthenticates inbound requests and redirects them to the user’s home pool or server.</span></span> <span data-ttu-id="5e260-152">ディレクターで事前認証することで、展開において不明なユーザーアカウントからの要求をドロップできます。</span><span class="sxs-lookup"><span data-stu-id="5e260-152">By preauthenticating at the Director, you can drop requests from user accounts that are unknown to the deployment.</span></span>

<span data-ttu-id="5e260-153">ディレクターは、サービス拒否 (DoS) 攻撃などの悪意のあるトラフィックから、Enterprise Edition フロントエンドプールの Standard Edition サーバーとフロントエンドサーバーを分離するのに役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="5e260-153">A Director helps insulate Standard Edition servers and Front End Servers in Enterprise Edition Front End pools from malicious traffic such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="5e260-154">このような攻撃でネットワークに無効な外部トラフィックが殺到している場合、トラフィックはディレクターで終了します。</span><span class="sxs-lookup"><span data-stu-id="5e260-154">If the network is flooded with invalid external traffic in such an attack, the traffic ends at the Director.</span></span> <span data-ttu-id="5e260-155">ディレクターの使用の詳細については、「 [Lync Server 2013 のディレクターのシナリオ](lync-server-2013-scenarios-for-the-director.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e260-155">For details about the use of Directors, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5e260-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e260-156">See Also</span></span>


[<span data-ttu-id="5e260-157">Lync Server 2013 のハードウェアロードバランサーの要件</span><span class="sxs-lookup"><span data-stu-id="5e260-157">Hardware load balancer requirements for Lync Server 2013</span></span>](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

