---
title: 'Lync Server 2013: 自動検出サービスの要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5cf4a26c9f0b36cd239daabbc2538716e2bcd3c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515774"
---
# <a name="autodiscover-service-requirements-for-lync-server-2013"></a><span data-ttu-id="0edcb-102">Lync Server 2013 の自動検出サービスの要件</span><span class="sxs-lookup"><span data-stu-id="0edcb-102">Autodiscover service requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0edcb-103">_**トピックの最終更新日:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="0edcb-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="0edcb-104">Microsoft Lync Server 2013 自動検出サービスは、ディレクターおよびフロントエンドプールサーバー上で実行され、DNS で公開されると、Lync Mobile を実行しているモバイルデバイスでモビリティサービスを検索するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="0edcb-104">The Microsoft Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by mobile devices running Lync Mobile to locate mobility services.</span></span> <span data-ttu-id="0edcb-105">Lync Mobile を実行しているモバイルデバイスが自動検出を利用できるようにするには、自動検出を利用する前に、自動検出サービスを実行しているすべてのディレクターおよびフロントエンドサーバーで証明書のサブジェクトの別名の一覧を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0edcb-105">Before mobile devices running Lync Mobile can take advantage of automatic discovery, you need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="0edcb-106">さらに、リバースプロキシの外部 web サービス公開ルールに使用される証明書のサブジェクトの別名の一覧を変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="0edcb-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="0edcb-107">ディレクター、フロントエンドサーバー、およびリバースプロキシに必要なサブジェクトの別名エントリの詳細については、「Planning for Mobility」の「 [Lync Server 2013 でのモビリティの技術要件](lync-server-2013-technical-requirements-for-mobility.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0edcb-107">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) in Planning for Mobility.</span></span>

<span data-ttu-id="0edcb-108">リバース プロキシでのサブジェクトの別名リストの使用については、自動検出サービスをポート 80 またはポート 443 のどちらで公開するかに基づいて決定します。</span><span class="sxs-lookup"><span data-stu-id="0edcb-108">The decision about using subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="0edcb-109">**ポート 80**     で公開自動検出サービスへの最初のクエリがポート80で行われる場合、証明書の変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="0edcb-109">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="0edcb-110">これは、Lync を実行しているモバイルデバイスがポート80のリバースプロキシに外部でアクセスし、内部でポート8080のディレクターまたはフロントエンドサーバーにリダイレクトされるためです。</span><span class="sxs-lookup"><span data-stu-id="0edcb-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="0edcb-111">詳細については、このトピックの後半の「ポート80を使用した最初の自動検出プロセス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0edcb-111">For details, see the “Initial Autodiscover Process Using Port 80” section later in this topic.</span></span>

  - <span data-ttu-id="0edcb-112">**ポート 443**     で公開外部 web サービス公開ルールで使用される証明書のサブジェクトの別名リストには、lyncdiscover が含まれている必要があり\*ます。 \<sipdomain\> \*</span><span class="sxs-lookup"><span data-stu-id="0edcb-112">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>*</span></span> <span data-ttu-id="0edcb-113">組織内の各 SIP ドメインのエントリ。</span><span class="sxs-lookup"><span data-stu-id="0edcb-113">entry for each SIP domain within your organization.</span></span>

<span data-ttu-id="0edcb-114">内部証明機関を使用した証明書の再発行は通常、単純なプロセスですが、web サービス公開ルールで使用されるパブリック証明書については、複数のサブジェクトの別名エントリを追加するとコストがかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0edcb-114">Reissuing certificates using an internal certificate authority is typically a simple process but for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="0edcb-115">この問題を回避するために、ポート80経由の最初の自動検出接続をサポートします。その後、ディレクターまたはフロントエンドサーバーのポート8080にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="0edcb-115">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<span data-ttu-id="0edcb-116">たとえば、Lync Mobile を実行しているモバイルクライアントが、最初の要求に HTTP を使用して自動検出機能を使用して Lync Server 2013 にサインインするように構成されているとします。</span><span class="sxs-lookup"><span data-stu-id="0edcb-116">For example, assume that a mobile client running Lync Mobile is configured to sign in to Lync Server 2013 using the automatic discovery feature using HTTP for the initial request.</span></span>

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a><span data-ttu-id="0edcb-117">ポート80を使用したモバイルデバイスの初期自動検出プロセス</span><span class="sxs-lookup"><span data-stu-id="0edcb-117">Initial Autodiscover Process for Mobile Devices Using Port 80</span></span>

1.  <span data-ttu-id="0edcb-118">Lync Mobile を実行しているモバイルデバイスは、A レコードが存在する DNS を使用して lyncdiscover.contoso.com を検索します。</span><span class="sxs-lookup"><span data-stu-id="0edcb-118">Mobile device running Lync Mobile looks up lyncdiscover.contoso.com using DNS, where an A record exists.</span></span>

2.  <span data-ttu-id="0edcb-119">外部 DNS は、外部 web サービスの IP アドレスをクライアントに返します。</span><span class="sxs-lookup"><span data-stu-id="0edcb-119">External DNS returns the IP address for the external web services to the client.</span></span>

3.  <span data-ttu-id="0edcb-120">Lync Mobile を実行しているモバイルデバイスが http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com リバースプロキシに要求を送信する</span><span class="sxs-lookup"><span data-stu-id="0edcb-120">Mobile device running Lync Mobile sends request http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com to the reverse proxy</span></span>

4.  <span data-ttu-id="0edcb-121">Web 公開ルールは、ポート80からの要求を内部でポート8080にブリッジし、ディレクターまたはフロントエンドサーバーのいずれかにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="0edcb-121">The web publishing rule will bridge the request from port 80 externally to port 8080 internally, which will then route it to either a Director or Front End Server.</span></span>
    
    <span data-ttu-id="0edcb-122">要求は HTTP なので (HTTPS ではない)、自動検出サービスをサポートするように外部 Web サービス公開ルール上の証明書を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0edcb-122">Since the request is HTTP and not HTTPS, no modifications are needed to the certificate on the external web service publishing rule to support the Autodiscover Service.</span></span>

5.  <span data-ttu-id="0edcb-123">自動検出サービスは外部 Web サービスの URL (HTTPS 形式) を返します。</span><span class="sxs-lookup"><span data-stu-id="0edcb-123">The Autodiscover Service returns the external web service URLs (in HTTPS format).</span></span>

6.  <span data-ttu-id="0edcb-124">Lync Mobile を実行しているモバイルデバイスは、ポート443のリバースプロキシに再接続することができ、4443経由でユーザーのホームプールで実行されている mobility service にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="0edcb-124">The mobile device running Lync Mobile can then reconnect to the reverse proxy on port 443 and is redirected over 4443 to the mobility service running on the user’s home pool.</span></span>
    
    <span data-ttu-id="0edcb-125">HTTPS クエリは自動検出サービスの URL に対する外部 Web サービスの URL に送信されるため、この HTTPS クエリは成功します。これは、外部 Web サービスの完全修飾ドメイン名 (FQDN) に対するサブジェクトの別名エントリが証明書に既に含まれるためです。</span><span class="sxs-lookup"><span data-stu-id="0edcb-125">Since the HTTPS query is to the external web services URL vs. the Autodiscover Service URL, it succeeds because the certificate will already contain subject alternative name entries for the external web services fully qualified domain names (FQDNs).</span></span>
    
    <span data-ttu-id="0edcb-126">このシナリオでは、モビリティをサポートするように証明書を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0edcb-126">In this scenario, there are no certificate changes required to support mobility.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0edcb-127">対象の Web サーバーに含まれる証明書に、サブジェクトの別名リストの値として、lyncdiscover.contoso.com に一致する値が含まれない場合:</span><span class="sxs-lookup"><span data-stu-id="0edcb-127">If the target web server has a certificate that does not have a matching value for lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="0edcb-128">a。 &nbsp; &nbsp; &nbsp;Web サーバーは "サーバー Hello" で応答し、証明書は応答しません。</span><span class="sxs-lookup"><span data-stu-id="0edcb-128">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server Hello” and no certificate.</span></span><BR><span data-ttu-id="0edcb-129">b。 &nbsp; &nbsp; &nbsp;Lync Mobile を実行しているモバイルデバイスは、すぐにセッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="0edcb-129">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile immediately terminates the session.</span></span><BR><span data-ttu-id="0edcb-130">対象の Web サーバーに含まれる証明書に、サブジェクトの別名リストの値として、lyncdiscover.contoso.com が含まれる場合:</span><span class="sxs-lookup"><span data-stu-id="0edcb-130">If the target web server has a certificate that includes lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="0edcb-131">a。 &nbsp; &nbsp; &nbsp;Web サーバーは、"サーバー hello" と "証明書" で応答します。</span><span class="sxs-lookup"><span data-stu-id="0edcb-131">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server hello” and a certificate.</span></span><BR><span data-ttu-id="0edcb-132">b。 &nbsp; &nbsp; &nbsp;Lync Mobile を実行しているモバイルデバイスは、証明書を検証してハンドシェイクを完了します。</span><span class="sxs-lookup"><span data-stu-id="0edcb-132">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile validates the certificate and completes the handshake.</span></span>

    
    </div>

<span data-ttu-id="0edcb-133">リバース プロキシ サーバーのポート 80 を使用する、自動検出サービスへの初期接続をサポートするには、Forefront Threat Management Gateway 2010 リバース プロキシ Web 公開ルールに対して、この例に類似した http 公開ルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0edcb-133">To support an initial connection to the Autodiscover Service using port 80 on your reverse proxy server, you can create an http publishing rule similar to this example for a Forefront Threat Management Gateway 2010 reverse proxy web publishing rule:</span></span>

1.  <span data-ttu-id="0edcb-134">新しい Web 公開ルール (例: **Lync Server Autodiscover (HTTP)**) を作成します。</span><span class="sxs-lookup"><span data-stu-id="0edcb-134">Create a new web publishing rule (for example, **Lync Server Autodiscover (HTTP)**).</span></span>

2.  <span data-ttu-id="0edcb-135">[**パブリック名**] に「lyncdiscover.contoso.com」と入力します。</span><span class="sxs-lookup"><span data-stu-id="0edcb-135">In **Public Name**, enter lyncdiscover.contoso.com.</span></span>

3.  <span data-ttu-id="0edcb-136">[**ブリッジ**] タブで、要求をポート 80 からポート 8080 に橋渡しするオプションのみを選択します。</span><span class="sxs-lookup"><span data-stu-id="0edcb-136">On the **Bridging** tab, select only the option to bridge requests from Port 80 to Port 8080.</span></span>

4.  <span data-ttu-id="0edcb-137">[**認証**] タブで、[**認証なし**] および [**クライアントは直接認証できません**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0edcb-137">On the **Authentication** tab, select **No authentication**, and **Client cannot authenticate directly**.</span></span>

5.  <span data-ttu-id="0edcb-138">変更を確定して、ルールを Lync ルールの一覧の先頭 (最初に処理する順序) に移動します。</span><span class="sxs-lookup"><span data-stu-id="0edcb-138">Commit changes, and move the rule to the top of the list of Lync rules (first in processing order).</span></span>

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="0edcb-139">分割ドメイン展開でのモビリティ</span><span class="sxs-lookup"><span data-stu-id="0edcb-139">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="0edcb-140">共有済みの SIP アドレス スペースは、"分割ドメイン"\*\* または "ハイブリッド展開"\*\* とも呼ばれる構成で、ユーザーは社内展開とオンライン展開をまたいで展開されます。</span><span class="sxs-lookup"><span data-stu-id="0edcb-140">A shared SIP address space, also known as a *split-domain*, or a *hybrid deployment* is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="0edcb-141">この構成では、ホーム サーバーの設置場所 (社内またはオンラインのどちらであるか) に関係なく、展開にログインしたユーザーは、そのホーム サーバーの設置場所にリダイレクトされることが望まれます。</span><span class="sxs-lookup"><span data-stu-id="0edcb-141">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), to log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="0edcb-142">これを実現するために、Microsoft Lync Server 2013 の自動検出機能を使用して、オンラインユーザーをオンライントポロジにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="0edcb-142">To accomplish this, the Autodiscover feature of Microsoft Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="0edcb-143">これを行うには、Lync Server 管理シェルを使用して自動検出の URL (uniform resource locator) を構成し、コマンドレットに **-cshostingprovider** および **Set-cshostingprovider**を使用します。</span><span class="sxs-lookup"><span data-stu-id="0edcb-143">This is done by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell and the cmdlets **Get-CsHostingProvider** and **Set-CsHostingProvider**.</span></span>

<span data-ttu-id="0edcb-144">次の展開属性を収集して記録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0edcb-144">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="0edcb-145">Lync Server 管理シェルで、と入力します。</span><span class="sxs-lookup"><span data-stu-id="0edcb-145">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="0edcb-p106">実行結果から、**ProxyFQDN** 属性を持つオンライン プロバイダー (たとえば、sipfed.online.lync.com) を見つけます。</span><span class="sxs-lookup"><span data-stu-id="0edcb-p106">In the results, find the online provider with the attribute **ProxyFQDN**. For example, sipfed.online.lync.com</span></span>

  - <span data-ttu-id="0edcb-148">ProxyFQDN の値を記録します。</span><span class="sxs-lookup"><span data-stu-id="0edcb-148">Record the value of the ProxyFQDN</span></span>

  - <span data-ttu-id="0edcb-149">オンプレミスの Lync Server コントロールパネルでフェデレーションを有効にして、オンラインプロバイダーとのフェデレーションを許可する</span><span class="sxs-lookup"><span data-stu-id="0edcb-149">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider</span></span>

  - <span data-ttu-id="0edcb-p107">オンライン プロバイダーに対してフェデレーションを有効にします。既定では、ドメイン フェデレーションに対してすべてのオンライン ユーザーが有効になり、すべてのドメインと通信できます。</span><span class="sxs-lookup"><span data-stu-id="0edcb-p107">Enable federation for the online provider. By default, all online users are enabled for domain federation and can communicate with all domains</span></span>

  - <span data-ttu-id="0edcb-152">禁止ドメインと許可ドメインを定義する場合は、明示的に許可するドメイン、または明示的に禁止するドメインを決めます。</span><span class="sxs-lookup"><span data-stu-id="0edcb-152">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block</span></span>

  - <span data-ttu-id="0edcb-153">オンライン フェデレーションの場合、ファイアウォールに期待する動作、証明書、および DNS ホスト (A、または IPv6 を使用する場合は AAAA) レコードを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0edcb-153">For online federation, you must plan for firewall exceptions, certificates and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="0edcb-154">また、フェデレーション ポリシーを構成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="0edcb-154">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="0edcb-155">詳細については、「 [Planning For Lync Server 2013 And Office Communications server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0edcb-155">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

