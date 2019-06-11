---
title: 'Lync Server 2013: 自動検出サービスの要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ea9d9be05561d200696a5ad0256c0d5424cf9b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="autodiscover-service-requirements-for-lync-server-2013"></a><span data-ttu-id="0f2c0-102">Lync Server 2013 の自動検出サービスの要件</span><span class="sxs-lookup"><span data-stu-id="0f2c0-102">Autodiscover service requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f2c0-103">_**最終更新日:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="0f2c0-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="0f2c0-104">Microsoft Lync Server 2013 自動検出サービスは、監督およびフロントエンドプールサーバー上で実行され、DNS で公開されると、Lync Mobile を実行しているモバイルデバイスでモビリティサービスを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-104">The Microsoft Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by mobile devices running Lync Mobile to locate mobility services.</span></span> <span data-ttu-id="0f2c0-105">Lync Mobile を実行しているモバイルデバイスでは自動検出機能を利用できますが、自動検出サービスを実行しているディレクターおよびフロントエンドサーバーで証明書のサブジェクトの代替名の一覧を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-105">Before mobile devices running Lync Mobile can take advantage of automatic discovery, you need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="0f2c0-106">さらに、リバースプロキシの外部 web サービス公開ルールに使用されている証明書のサブジェクト代替名の一覧を変更することが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="0f2c0-107">ディレクター、フロントエンドサーバー、リバースプロキシに必要なサブジェクト代替名のエントリの詳細については、「モビリティの計画」の「 [Lync Server 2013 でのモビリティの技術要件](lync-server-2013-technical-requirements-for-mobility.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-107">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) in Planning for Mobility.</span></span>

<span data-ttu-id="0f2c0-108">リバースプロキシでのサブジェクト代替名の一覧の使用に関する決定は、自動検出サービスをポート80またはポート443のどちらに発行するかに基づきます。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-108">The decision about using subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="0f2c0-109">**ポート 80**   で公開自動検出サービスへの最初のクエリがポート80経由で発生した場合、証明書の変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-109">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="0f2c0-110">これは、Lync を実行しているモバイルデバイスは、ポート80の逆プロキシに外部からアクセスして、ポート8080の内部でディレクターまたはフロントエンドサーバーにリダイレクトされるためです。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="0f2c0-111">詳細については、このトピックの後半の「ポート80を使った最初の自動検出プロセス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-111">For details, see the “Initial Autodiscover Process Using Port 80” section later in this topic.</span></span>

  - <span data-ttu-id="0f2c0-112">**ポート 443**   で公開される外部 web サービス公開ルールで使われる証明書のサブジェクトの別名リストは、lyncdiscover を含む必要があり\*ます。\<組織\> \*内の各 SIP ドメインの sipdomain エントリ。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-112">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>

<span data-ttu-id="0f2c0-113">内部証明機関を使用した再発行証明書は、通常、単純なプロセスですが、web サービス公開ルールで使用される公開証明書の場合、複数のサブジェクト代替名エントリを追加すると、負荷が高くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-113">Reissuing certificates using an internal certificate authority is typically a simple process but for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="0f2c0-114">この問題を回避するには、ポート80経由の最初の自動検出接続をサポートします。その後、ディレクターまたはフロントエンドサーバー上のポート8080にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-114">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<span data-ttu-id="0f2c0-115">たとえば、Lync Mobile を実行しているモバイルクライアントが、最初の要求に対して HTTP を使用して自動検出機能を使用して Lync Server 2013 にサインインするように構成されていることを前提とします。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-115">For example, assume that a mobile client running Lync Mobile is configured to sign in to Lync Server 2013 using the automatic discovery feature using HTTP for the initial request.</span></span>

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a><span data-ttu-id="0f2c0-116">ポート80を使ったモバイルデバイスの初期自動検出プロセス</span><span class="sxs-lookup"><span data-stu-id="0f2c0-116">Initial Autodiscover Process for Mobile Devices Using Port 80</span></span>

1.  <span data-ttu-id="0f2c0-117">Lync Mobile を実行しているモバイルデバイスでは、DNS を使用して lyncdiscover.contoso.com を検索します。この場合、A レコードが存在します。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-117">Mobile device running Lync Mobile looks up lyncdiscover.contoso.com using DNS, where an A record exists.</span></span>

2.  <span data-ttu-id="0f2c0-118">外部 DNS は、外部 web サービスの IP アドレスをクライアントに返します。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-118">External DNS returns the IP address for the external web services to the client.</span></span>

3.  <span data-ttu-id="0f2c0-119">Lync Mobile を実行しているhttp://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.comモバイルデバイスは、リバースプロキシに要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-119">Mobile device running Lync Mobile sends request http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com to the reverse proxy</span></span>

4.  <span data-ttu-id="0f2c0-120">Web 発行ルールによって、ポート80からの外部への要求が内部でポート8080にブリッジされ、ディレクターまたはフロントエンドサーバーにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-120">The web publishing rule will bridge the request from port 80 externally to port 8080 internally, which will then route it to either a Director or Front End Server.</span></span>
    
    <span data-ttu-id="0f2c0-121">要求は HTTP であり、HTTPS ではないため、自動検出サービスをサポートするために、外部 web サービス公開ルールの証明書に変更を加える必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-121">Since the request is HTTP and not HTTPS, no modifications are needed to the certificate on the external web service publishing rule to support the Autodiscover Service.</span></span>

5.  <span data-ttu-id="0f2c0-122">自動検出サービスは、外部 web サービスの Url (HTTPS 形式) を返します。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-122">The Autodiscover Service returns the external web service URLs (in HTTPS format).</span></span>

6.  <span data-ttu-id="0f2c0-123">Lync Mobile を実行しているモバイルデバイスは、ポート443のリバースプロキシに再接続し、ユーザーのホームプールで実行されているモビリティサービスに4443経由でリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-123">The mobile device running Lync Mobile can then reconnect to the reverse proxy on port 443 and is redirected over 4443 to the mobility service running on the user’s home pool.</span></span>
    
    <span data-ttu-id="0f2c0-124">HTTPS クエリは、外部 web サービスの URL と自動検出サービスの URL の対比で行われるため、その証明書には、外部 web サービスの完全修飾ドメイン名 (Fqdn) に対するサブジェクト代替名のエントリが既に含まれているため、成功します。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-124">Since the HTTPS query is to the external web services URL vs. the Autodiscover Service URL, it succeeds because the certificate will already contain subject alternative name entries for the external web services fully qualified domain names (FQDNs).</span></span>
    
    <span data-ttu-id="0f2c0-125">このシナリオでは、モバイル機能をサポートするために必要な証明書の変更はありません。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-125">In this scenario, there are no certificate changes required to support mobility.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0f2c0-126">ターゲット web サーバーに、lyncdiscover.contoso.com の値が一致しない証明書がサブジェクトの代替名の一覧の値として含まれている場合:</span><span class="sxs-lookup"><span data-stu-id="0f2c0-126">If the target web server has a certificate that does not have a matching value for lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="0f2c0-127">&nbsp;は、"server Hello" と証明書を使って応答し&nbsp;&nbsp;ます。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-127">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server Hello” and no certificate.</span></span><BR><span data-ttu-id="0f2c0-128">b. Lync&nbsp;&nbsp;&nbsp;mobile を実行しているモバイルデバイスは、直ちにセッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-128">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile immediately terminates the session.</span></span><BR><span data-ttu-id="0f2c0-129">ターゲット web サーバーに、サブジェクトの代替名の一覧の値として lyncdiscover.contoso.com を含む証明書がある場合:</span><span class="sxs-lookup"><span data-stu-id="0f2c0-129">If the target web server has a certificate that includes lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="0f2c0-130">&nbsp;は、"server hello" と証明書を使って応答し&nbsp;&nbsp;ます。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-130">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server hello” and a certificate.</span></span><BR><span data-ttu-id="0f2c0-131">b. Lync mobile を実行している&nbsp;モバイルデバイス証明書を検証し、ハンドシェイクを完了します。&nbsp;&nbsp;</span><span class="sxs-lookup"><span data-stu-id="0f2c0-131">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile validates the certificate and completes the handshake.</span></span>

    
    </div>

<span data-ttu-id="0f2c0-132">リバースプロキシサーバーでポート80を使って自動検出サービスへの最初の接続をサポートするには、次の例のような http 発行ルールを作成できます。これは、Forefront Threat Management Gateway 2010 リバースプロキシ web 発行ルール</span><span class="sxs-lookup"><span data-stu-id="0f2c0-132">To support an initial connection to the Autodiscover Service using port 80 on your reverse proxy server, you can create an http publishing rule similar to this example for a Forefront Threat Management Gateway 2010 reverse proxy web publishing rule:</span></span>

1.  <span data-ttu-id="0f2c0-133">新しい web 公開ルールを作成します (たとえば、 **Lync Server の自動検出 (HTTP)**)。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-133">Create a new web publishing rule (for example, **Lync Server Autodiscover (HTTP)**).</span></span>

2.  <span data-ttu-id="0f2c0-134">[**パブリック名**] に「lyncdiscover.contoso.com」と入力します。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-134">In **Public Name**, enter lyncdiscover.contoso.com.</span></span>

3.  <span data-ttu-id="0f2c0-135">[**ブリッジ**] タブで、ポート80からポート8080への要求をブリッジするオプションのみを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-135">On the **Bridging** tab, select only the option to bridge requests from Port 80 to Port 8080.</span></span>

4.  <span data-ttu-id="0f2c0-136">[**認証**] タブで、[**認証なし**] を選択し、**クライアントは直接認証を行うことはできません**。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-136">On the **Authentication** tab, select **No authentication**, and **Client cannot authenticate directly**.</span></span>

5.  <span data-ttu-id="0f2c0-137">変更をコミットし、Lync ルールの一覧の一番上 (最初の処理順序) にルールを移動します。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-137">Commit changes, and move the rule to the top of the list of Lync rules (first in processing order).</span></span>

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="0f2c0-138">分離ドメイン展開のモビリティ</span><span class="sxs-lookup"><span data-stu-id="0f2c0-138">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="0f2c0-139">共有 SIP アドレス空間 (*分割ドメイン*とも呼ばれます) または*ハイブリッド展開*とは、ユーザーがオンプレミスの展開とオンライン環境の間で展開される構成です。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-139">A shared SIP address space, also known as a *split-domain*, or a *hybrid deployment* is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="0f2c0-140">目的は、ホームサーバーが配置されている場所 (オンプレミスまたはオンライン) に関係なく、展開にログインし、ホームサーバーの場所にリダイレクトされるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-140">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), to log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="0f2c0-141">これを実現するために、Microsoft Lync Server 2013 の自動検出機能を使用して、オンラインユーザーをオンライントポロジにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-141">To accomplish this, the Autodiscover feature of Microsoft Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="0f2c0-142">これを行うには、Lync Server 管理シェルを使用して、自動検出の uri (URL) を構成します。また、コマンドレットは、「 **CsHostingProvider** 」と「 **Set-CsHostingProvider**」を選びます。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-142">This is done by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell and the cmdlets **Get-CsHostingProvider** and **Set-CsHostingProvider**.</span></span>

<span data-ttu-id="0f2c0-143">次の展開された属性を収集して記録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-143">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="0f2c0-144">Lync Server 管理シェルで、「</span><span class="sxs-lookup"><span data-stu-id="0f2c0-144">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="0f2c0-145">結果で、属性**Proxyfqdn**を含むオンラインプロバイダーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-145">In the results, find the online provider with the attribute **ProxyFQDN**.</span></span> <span data-ttu-id="0f2c0-146">たとえば、sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0f2c0-146">For example, sipfed.online.lync.com</span></span>

  - <span data-ttu-id="0f2c0-147">ProxyFQDN の値を記録する</span><span class="sxs-lookup"><span data-stu-id="0f2c0-147">Record the value of the ProxyFQDN</span></span>

  - <span data-ttu-id="0f2c0-148">オンプレミスの Lync Server コントロールパネルでフェデレーションを有効にして、オンラインプロバイダーとのフェデレーションを許可する</span><span class="sxs-lookup"><span data-stu-id="0f2c0-148">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider</span></span>

  - <span data-ttu-id="0f2c0-149">オンラインプロバイダーのフェデレーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-149">Enable federation for the online provider.</span></span> <span data-ttu-id="0f2c0-150">既定では、すべてのオンラインユーザーがドメインフェデレーションを有効にしており、すべてのドメインと通信できます。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-150">By default, all online users are enabled for domain federation and can communicate with all domains</span></span>

  - <span data-ttu-id="0f2c0-151">ブロックドメインと許可ドメインを定義する場合は、明示的に許可するか、明示的にブロックするドメインを決定します。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-151">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block</span></span>

  - <span data-ttu-id="0f2c0-152">オンラインフェデレーションの場合、ファイアウォールの例外、証明書と DNS ホスト (IPv6 を使用している場合は AAAA) を計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-152">For online federation, you must plan for firewall exceptions, certificates and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="0f2c0-153">さらに、フェデレーションポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-153">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="0f2c0-154">詳細については、「 [Lync server 2013 と Office Communications server フェデレーションの計画](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f2c0-154">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

