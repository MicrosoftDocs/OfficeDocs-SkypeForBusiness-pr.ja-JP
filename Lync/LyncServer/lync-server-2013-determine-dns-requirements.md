---
title: 'Lync Server 2013: DNS の要件を確認する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e299f138a28ba4863250d2e0be1f31f705f4a173
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="1ed00-102">Lync Server 2013 の DNS の要件を確認する</span><span class="sxs-lookup"><span data-stu-id="1ed00-102">Determine DNS requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ed00-103">_**最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="1ed00-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="1ed00-104">次のフローチャートを使用して、ドメインネームシステム (DNS) の要件を確認します。</span><span class="sxs-lookup"><span data-stu-id="1ed00-104">Use the following flow chart to determine Domain Name System (DNS) requirements.</span></span> <span data-ttu-id="1ed00-105">Lync Server 2013 の累積更新プログラムの変更点については、2013年2月に、それらが適用される場所を示しています。</span><span class="sxs-lookup"><span data-stu-id="1ed00-105">Changes for the Cumulative Updates for Lync Server 2013: February 2013 are noted where they apply.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1ed00-106">Microsoft Lync Server 2013 では、IPv6 アドレスの使用がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1ed00-106">Microsoft Lync Server 2013 supports the use of IPv6 addressing.</span></span> <span data-ttu-id="1ed00-107">IPv6 アドレスを使用するには、IPv6 DNS のサポートも提供し、DNS host AAAA ("クアッドコア" と呼ばれます) レコードを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ed00-107">To use IPv6 addresses, you must also provide support for IPv6 DNS and configure DNS host AAAA (known as “quad-A”) records.</span></span> <span data-ttu-id="1ed00-108">IPv4 と IPv6 の両方が使用されている展開では、IPv4 のホスト A レコードと IPv6 用の host AAAA の両方を構成および管理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1ed00-108">In deployments where both IPv4 and IPv6 are being used, it is best to configure and maintain both host A records for IPv4 and host AAAA for IPv6.</span></span> <span data-ttu-id="1ed00-109">展開が IPv6 に完全に移行されている場合でも、外部ユーザーが IPv4 を使用している場合は IPv4 DNS ホストレコードが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="1ed00-109">Even if your deployment has transitioned fully to IPv6, IPv4 DNS host records may still be required when external users are still using IPv4.</span></span>



</div>

<span data-ttu-id="1ed00-110">**DNS 要件フローチャートを決定する**</span><span class="sxs-lookup"><span data-stu-id="1ed00-110">**Determining DNS Requirements Flow Chart**</span></span>

<span data-ttu-id="1ed00-111">![175782ace363e4-08 a8-912f2-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ace363e4-08 a8-912f2-8991bf152970")</span><span class="sxs-lookup"><span data-stu-id="1ed00-111">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1ed00-112">既定では、ドメインに参加していないコンピューターのコンピューター名は、完全修飾ドメイン名 (FQDN) ではなく、ホスト名です。</span><span class="sxs-lookup"><span data-stu-id="1ed00-112">By default the computer name of a computer that is not joined to a domain is a host name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="1ed00-113">トポロジビルダーでは、ホスト名ではなく Fqdn を使用します。</span><span class="sxs-lookup"><span data-stu-id="1ed00-113">Topology Builder uses FQDNs, not host names.</span></span> <span data-ttu-id="1ed00-114">そのため、エッジ サーバーとして展開する、ドメインに参加していないコンピューターの名前で DNS サフィックスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ed00-114">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="1ed00-115">Lync Server、エッジ サーバー、およびプールの FQDN を割り当てる場合に使用できる文字は、<STRONG>標準文字のみ</STRONG> (A ～ Z、a ～ z、0 ～ 9、およびハイフン) です。</span><span class="sxs-lookup"><span data-stu-id="1ed00-115"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="1ed00-116">Unicode 文字およびアンダースコアは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="1ed00-116">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="1ed00-117">一般に、外部 DNS および公的 CA では、FQDN に非標準文字はサポートされていません (証明書で FQDN を SN に割り当てることが必要になります)。</span><span class="sxs-lookup"><span data-stu-id="1ed00-117">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="1ed00-118">詳細については、「 <A href="lync-server-2013-configure-dns-host-records.md">Lync Server 2013 の DNS ホストレコードを構成する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ed00-118">For additional details, see <A href="lync-server-2013-configure-dns-host-records.md">Configure DNS Host records for Lync Server 2013</A></span></span>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a><span data-ttu-id="1ed00-119">Lync クライアントがサービスを見つける方法</span><span class="sxs-lookup"><span data-stu-id="1ed00-119">How Lync Clients Locate Services</span></span>

<span data-ttu-id="1ed00-120">Microsoft Lync 2010、Lync 2013、Lync Mobile は、クライアントが Lync Server 2013 でサービスを検索してアクセスする方法に似ています。</span><span class="sxs-lookup"><span data-stu-id="1ed00-120">Microsoft Lync 2010, Lync 2013, and Lync Mobile are similar in how the client finds and accesses services in Lync Server 2013.</span></span> <span data-ttu-id="1ed00-121">重要な例外として、別のサービスの場所のプロセスを使用する Lync Windows ストアアプリがあります。</span><span class="sxs-lookup"><span data-stu-id="1ed00-121">The notable exception is the Lync Windows Store app that uses a different service location process.</span></span> <span data-ttu-id="1ed00-122">このセクションでは、自動検出サービスレコードのみを使用して、クライアントがサービスを見つける方法、一連の SRV とホストレコードを使用する従来の方法について、2つのシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1ed00-122">This section details two scenarios of how the clients locate services, first the traditional method using a series of SRV and A host records, second using only the Autodiscover service records.</span></span> <span data-ttu-id="1ed00-123">デスクトップクライアントの累積更新プログラムによって、DNS の位置情報のプロセスが Lync Server 2010 から変更されるすべてのクライアントについて、DNS クエリのプロセスは、成功したクエリが返されるか、または可能な DNS レコードの一覧がなくなって、最終的なエラーが返されるまで、クライアント。</span><span class="sxs-lookup"><span data-stu-id="1ed00-123">Cumulative updates to the desktop clients change the DNS location process from Lync Server 2010 For all clients, the DNS query process continues until a successful query is returned, or the list of possible DNS records is exhausted, and the final error is returned to the client.</span></span>

<span data-ttu-id="1ed00-124">DNS 参照時に Lync Windows ストアアプリを**除く**すべてのクライアントで、SRV レコードが照会され、次の順序でクライアントに返されます。</span><span class="sxs-lookup"><span data-stu-id="1ed00-124">For all clients **except** for the Lync Windows Store app During DNS lookup, SRV records are queried and returned to the client in the following order:</span></span>

1.  <span data-ttu-id="1ed00-125">lyncdiscoverinternal.\<内部\> Web サービスの自動検出サービスのドメイン A (ホスト) レコード</span><span class="sxs-lookup"><span data-stu-id="1ed00-125">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="1ed00-126">lyncdiscover.\<外部\> Web サービスの自動検出サービスのドメイン A (ホスト) レコード</span><span class="sxs-lookup"><span data-stu-id="1ed00-126">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

3.  <span data-ttu-id="1ed00-127">\_sipinternaltls.\_tcp。\<内部\> TLS 接続のドメイン SRV (サービスロケーター) レコード</span><span class="sxs-lookup"><span data-stu-id="1ed00-127">\_sipinternaltls.\_tcp.\<domain\>   SRV (service locator) record for internal TLS connections</span></span>

4.  <span data-ttu-id="1ed00-128">\_sipinternal.\_tcp。\<内部\> tcp 接続のドメイン SRV (サービスロケーター) レコード (TCP が許可されている場合にのみ実行)</span><span class="sxs-lookup"><span data-stu-id="1ed00-128">\_sipinternal.\_tcp.\<domain\>   SRV (service locator) record for internal TCP connections (performed only if TCP is allowed)</span></span>

5.  <span data-ttu-id="1ed00-129">\_フェデレーション.\_tls。\<外部\> TLS 接続のドメイン SRV (サービスロケーター) レコード</span><span class="sxs-lookup"><span data-stu-id="1ed00-129">\_sip.\_tls.\<domain\>   SRV (service locator) record for external TLS connections</span></span>

6.  <span data-ttu-id="1ed00-130">sipinternal.\<フロント\>エンドプールまたはディレクターのドメイン A (ホスト) レコード。内部ネットワークでのみ解決可能</span><span class="sxs-lookup"><span data-stu-id="1ed00-130">sipinternal.\<domain\>   A (host) record for the Front End pool or Director, resolvable only on the internal network</span></span>

7.  <span data-ttu-id="1ed00-131">フェデレーション.\<内部\>ネットワーク上のフロントエンドプールまたはディレクターのドメイン A (ホスト) レコード、またはクライアントが外部の場合はアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="1ed00-131">sip.\<domain\>   A (host) record for the Front End pool or Director on the internal network, or the Access Edge service when the client is external</span></span>

8.  <span data-ttu-id="1ed00-132">sipexternal.\<クライアント\>が外部の場合のアクセスエッジサービスのドメイン A (ホスト) レコード</span><span class="sxs-lookup"><span data-stu-id="1ed00-132">sipexternal.\<domain\>   A (host) record for the Access Edge service when the client is external</span></span>

<span data-ttu-id="1ed00-133">Lync Windows ストアアプリでは、次の2つのレコードが使用されるため、そのプロセスが完全に変更されます。</span><span class="sxs-lookup"><span data-stu-id="1ed00-133">The Lync Windows Store app changes the process completely because it uses two records:</span></span>

1.  <span data-ttu-id="1ed00-134">lyncdiscoverinternal.\<内部\> Web サービスの自動検出サービスのドメイン A (ホスト) レコード</span><span class="sxs-lookup"><span data-stu-id="1ed00-134">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="1ed00-135">lyncdiscover.\<外部\> Web サービスの自動検出サービスのドメイン A (ホスト) レコード</span><span class="sxs-lookup"><span data-stu-id="1ed00-135">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

<span data-ttu-id="1ed00-136">他のレコードの種類にフォールバックすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1ed00-136">There is no fallback to the other record types.</span></span>

<span data-ttu-id="1ed00-137">古いクライアントと比較した場合の新しいクライアントで使用されるメソッドの違いは、自動検出サービスがすべてのサービスを見つけるために推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="1ed00-137">The difference between the methods used for newer clients as compared to older clients is that the Autodiscover service is becoming the preferred method to locate all services.</span></span>

<span data-ttu-id="1ed00-138">接続に成功すると、自動検出サービスは、ユーザーのホームプールのすべての Web サービスの Url (IIS のサービス用に作成された仮想ディレクトリによる Mcx と呼ばれます)、Microsoft Lync Web App、Web scheduler Url などを返します。</span><span class="sxs-lookup"><span data-stu-id="1ed00-138">When a connection is successful, the Autodiscover Service returns all the Web Services URLs for the user's home pool, including the Mobility Service (known as Mcx by the virtual directory created for the service in IIS), Microsoft Lync Web App and Web scheduler URLs.</span></span> <span data-ttu-id="1ed00-139">ただし、内部のモビリティーサービス URL と外部モビリティーサービスの URL は両方とも、外部 Web サービスの FQDN と関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="1ed00-139">However, both the internal Mobility Service URL and the external Mobility Service URL is associated with the external Web Services FQDN.</span></span> <span data-ttu-id="1ed00-140">そのため、モバイルデバイスがネットワークの内部と外部のどちらであるかに関係なく、デバイスは常にリバースプロキシ経由で外部のモビリティサービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="1ed00-140">Therefore, regardless of whether a mobile device is internal or external to the network, the device always connects to the Mobility Service externally through the reverse proxy.</span></span>

<span data-ttu-id="1ed00-141">Lync Server 2013 の累積更新プログラム (2013 年2月) がインストールされている場合、自動検出サービスは、内部/UCWA、外部/UCWA、UCWA への参照も返します。</span><span class="sxs-lookup"><span data-stu-id="1ed00-141">If the Cumulative Updates for Lync Server 2013: February 2013 has been installed, the Autodiscover Service also returns references to Internal/UCWA, External/UCWA and UCWA.</span></span> <span data-ttu-id="1ed00-142">これらのエントリは、ユニファイドコミュニケーション Web API (UCWA) web コンポーネントを参照します。</span><span class="sxs-lookup"><span data-stu-id="1ed00-142">These entries refer to the Unified Communications Web API (UCWA) web component.</span></span> <span data-ttu-id="1ed00-143">現時点では、エントリ "UCWA" のみが使われ、web コンポーネントの URL への参照が提供されています。</span><span class="sxs-lookup"><span data-stu-id="1ed00-143">Currently, only the entry UCWA is used and provides a reference to a URL for the web component.</span></span> <span data-ttu-id="1ed00-144">UCWA は、Lync 2010 モバイルクライアントで使用される Mcx Mobility サービスではなく、Lync 2013 モバイルクライアントによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="1ed00-144">UCWA is used by Lync 2013 Mobile clients instead of the Mcx Mobility Service used by the Lync 2010 Mobile clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ed00-145">SRV レコードを作成する場合は、dns SRV レコードが作成された同じドメインで DNS A と AAAA (IPv6 アドレス指定を使用している場合) を参照している必要があることに注意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="1ed00-145">When creating SRV records, it is important to remember that they must point to a DNS A and AAAA (if you are using IPv6 addressing) record in the same domain in which the DNS SRV record is created.</span></span> <span data-ttu-id="1ed00-146">たとえば、SRV レコードが contoso.com にある場合、A と AAAA (IPv6 アドレス指定を使用している場合) レコードは、fabrikam.com ではできません。</span><span class="sxs-lookup"><span data-stu-id="1ed00-146">For example, if the SRV record is in contoso.com, the A and AAAA (if you are using IPv6 addressing) record it points to cannot be in fabrikam.com.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="1ed00-147">既定の構成では、すべてのモバイルクライアントトラフィックが外部サイト経由で転送されます。</span><span class="sxs-lookup"><span data-stu-id="1ed00-147">The default configuration is to direct all mobile client traffic through the external site.</span></span> <span data-ttu-id="1ed00-148">必要に応じて、内部 URL のみを返すように設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="1ed00-148">You can modify settings to return only the internal URL, if this is more preferable for your requirements.</span></span> <span data-ttu-id="1ed00-149">この構成では、ユーザーは、企業ネットワーク内にいる場合にのみ、モバイルデバイスで Lync モバイルアプリケーションを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="1ed00-149">With this configuration, users can use Lync mobile applications on their mobile devices only when they are inside the corporate network.</span></span> <span data-ttu-id="1ed00-150">この構成を定義するには、 <STRONG>Set-CsMcxConfiguration</STRONG>コマンドレットを使います。</span><span class="sxs-lookup"><span data-stu-id="1ed00-150">To define this configuration, you use the <STRONG>Set-CsMcxConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1ed00-151">モバイルアプリケーションは、アドレス帳サービスなどの他の Lync Server 2013 サービスに接続することもできますが、内部のモバイルアプリケーション web 要求は、Mobility Service の場合にのみ外部 web FQDN に送信されます。</span><span class="sxs-lookup"><span data-stu-id="1ed00-151">Although mobile applications can also connect to other Lync Server 2013 services, such as Address Book Service, internal mobile application web requests go to the external web FQDN only for the Mobility Service.</span></span> <span data-ttu-id="1ed00-152">アドレス帳要求などの他のサービス要求では、この構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1ed00-152">Other service requests, such as Address Book requests, do not require this configuration.</span></span>



</div>

<span data-ttu-id="1ed00-153">モバイルデバイスでは、サービスの手動での検出がサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1ed00-153">Mobile devices support manual discovery of services.</span></span> <span data-ttu-id="1ed00-154">この場合、各ユーザーは、次のように、完全な内部および外部の自動検出サービスの Uri を使用して、モバイルデバイスの設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ed00-154">In this case, each user must configure the mobile device settings with the full internal and external Autodiscover Service URIs, including the protocol and path, as follows:</span></span>

  - <span data-ttu-id="1ed00-155">外部\<アクセス用の\>Https://extpoolfqdn/Autodiscover/autodiscoverservice.svc/Root</span><span class="sxs-lookup"><span data-stu-id="1ed00-155">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>

  - <span data-ttu-id="1ed00-156">内部\<アクセス用の\>Https://intpoolfqdn/AutoDiscover/AutoDiscover.svc/Root</span><span class="sxs-lookup"><span data-stu-id="1ed00-156">https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root for internal access</span></span>

<span data-ttu-id="1ed00-157">手動検出ではなく、自動検出を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1ed00-157">We recommend that you use automatic discovery, rather than manual discovery.</span></span> <span data-ttu-id="1ed00-158">ただし、手動の設定は、モバイルデバイスの接続問題のトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1ed00-158">However, manual settings can be useful for troubleshooting mobile device connectivity issues.</span></span>

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a><span data-ttu-id="1ed00-159">Lync Server でのスプリットブレイン DNS の構成</span><span class="sxs-lookup"><span data-stu-id="1ed00-159">Configuring Split-Brain DNS with Lync Server</span></span>

<span data-ttu-id="1ed00-160">スプリットブレイン dns は、複数の名前によって認識されます。たとえば、分割 DNS や分割ホライズン DNS などです。</span><span class="sxs-lookup"><span data-stu-id="1ed00-160">Split-brain DNS is known by a number of names, for example, split DNS or split-horizon DNS.</span></span> <span data-ttu-id="1ed00-161">単に、同じ名前空間を持ち、1つの DNS ゾーンサービスの内部専用要求と、他の DNS ゾーンサービスの外部専用要求を持つ2つの DNS ゾーンがある DNS 構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ed00-161">Simply, it describes a DNS configuration where there are two DNS zones with the same namespace – but one DNS zone services internal-only requests, and the other DNS zone services external-only requests.</span></span> <span data-ttu-id="1ed00-162">ただし、内部 DNS に含まれる DNS SRV と A レコードの多くは、外部 DNS には含まれておらず、逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="1ed00-162">However, many of the DNS SRV and A records contained in the internal DNS will not be contained in the external DNS, and the reverse is also true.</span></span> <span data-ttu-id="1ed00-163">内部と外部の両方の DNS (たとえば、www.contoso.com) に同じ DNS レコードが存在する場合、返される IP アドレスは、クエリが開始された場所 (内部または外部) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="1ed00-163">In cases where the same DNS record exists in both the internal and external DNS (for example, www.contoso.com), the IP address returned will be different based on where (internal or external) the query was initiated.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1ed00-164">現時点では、モビリティ、特に LyncDiscover と LyncDiscoverInternal の DNS レコードについては、スプリットブレイン DNS はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1ed00-164">Currently, Split-Brain DNS is not supported for the mobility, or more specifically, the LyncDiscover and LyncDiscoverInternal DNS records.</span></span> <span data-ttu-id="1ed00-165">LyncDiscover は外部 DNS サーバーで定義され、LyncDiscoverInternal は内部 DNS サーバーで定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ed00-165">LyncDiscover must be defined on an external DNS server and LyncDiscoverInternal must be defined on an internal DNS server.</span></span>



</div>

<span data-ttu-id="1ed00-166">これらのトピックでは、「split ブレインという用語を使用します。</span><span class="sxs-lookup"><span data-stu-id="1ed00-166">For the purposes of these topics, the term split-brain DNS will be used.</span></span>

<span data-ttu-id="1ed00-167">分割ブレイン DNS を構成している場合、次の内部と外部のゾーンには、各ゾーンで必要な DNS レコードの種類の概要が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1ed00-167">If you are configuring split-brain DNS, the following internal and external zone contain a summary of the types of DNS records required in each zone.</span></span> <span data-ttu-id="1ed00-168">詳細については、「 [Lync Server 2013 での外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ed00-168">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="1ed00-169">**内部 DNS:**</span><span class="sxs-lookup"><span data-stu-id="1ed00-169">**Internal DNS:**</span></span>

  - <span data-ttu-id="1ed00-170">権限のある contoso.com という名前の DNS ゾーンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1ed00-170">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="1ed00-171">内部 contoso.com ゾーンには、次の内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1ed00-171">The internal contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="1ed00-172">DNS A と AAAA (IPv6 アドレスを使用している場合)、および内部の Lync Server 2013 クライアント用の SRV レコード (オプション)</span><span class="sxs-lookup"><span data-stu-id="1ed00-172">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for internal Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="1ed00-173">Lync Server 2013 Web サービスを自動検出するための DNS A と AAAA (IPv6 アドレスを使用している場合) または CNAME レコード (オプション)</span><span class="sxs-lookup"><span data-stu-id="1ed00-173">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services (optional)</span></span>
    
      - <span data-ttu-id="1ed00-174">フロントエンドプール名、監督またはディレクターのプール名、および企業ネットワーク内の Lync Server 2013 を実行しているすべての内部サーバーについて、DNS A および AAAA (IPv6 アドレス指定を使用している場合)</span><span class="sxs-lookup"><span data-stu-id="1ed00-174">DNS A and AAAA (if you are using IPv6 addressing) records for Front End pool name, Director or Director pool name, and all internal servers running Lync Server 2013 in the corporate network</span></span>
    
      - <span data-ttu-id="1ed00-175">DNS A and AAAA (IPv6 アドレス指定を使用している場合) 境界ネットワークの各 Lync Server 2013 のエッジサーバーの Edge 内部インターフェイスのレコード</span><span class="sxs-lookup"><span data-stu-id="1ed00-175">DNS A and AAAA (if you are using IPv6 addressing) records for the Edge internal interface of each Lync Server 2013, Edge Server in the perimeter network</span></span>
    
      - <span data-ttu-id="1ed00-176">DNS A and AAAA (IPv6 アドレス指定を使用している場合) 境界ネットワーク内の各リバースプロキシサーバーの内部インターフェイスのレコード (リバースプロキシの場合はオプション)</span><span class="sxs-lookup"><span data-stu-id="1ed00-176">DNS A and AAAA (if you are using IPv6 addressing) records for the internal interface of each reverse proxy server in the perimeter network (optional for management of reverse proxy)</span></span>
    
      - <span data-ttu-id="1ed00-177">すべての Lync Server 2013 Edge Server 境界ネットワーク内の内部境界インターフェイスは、contoso.com へのクエリを解決するために内部 DNS ゾーンを使用します。</span><span class="sxs-lookup"><span data-stu-id="1ed00-177">All Lync Server 2013  Edge Server internal edge interfaces in the perimeter network use the internal DNS zone for resolving queries to contoso.com</span></span>
    
      - <span data-ttu-id="1ed00-178">企業ネットワークの lync 2013 を実行しているすべての2013サーバーは、contoso.com に対してクエリを解決するための内部 DNS サーバー、または各エッジサーバー上の HOSTS ファイルの使用をポイントします (IPv6 アドレス指定を使用している場合)次ホップサーバー、具体的にはディレクターまたはディレクター VIP、フロントエンドプール VIP、または Standard Edition サーバー</span><span class="sxs-lookup"><span data-stu-id="1ed00-178">All servers running Lync Server 2013 and clients running Lync 2013 in the corporate network point to the internal DNS servers for resolving queries to contoso.com, or use of HOSTS file on each Edge server and list A and AAAA (if you are using IPv6 addressing) records for next hop server, specifically the Director or Director VIP, Front End pool VIP, or Standard Edition server</span></span>

<span data-ttu-id="1ed00-179">**外部 DNS:**</span><span class="sxs-lookup"><span data-stu-id="1ed00-179">**External DNS:**</span></span>

  - <span data-ttu-id="1ed00-180">権限のある contoso.com という名前の DNS ゾーンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1ed00-180">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="1ed00-181">外部 contoso.com ゾーンには、次の内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1ed00-181">The external contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="1ed00-182">DNS A と AAAA (IPv6 アドレス指定を使用している場合)、および Lync Server 2013 クライアントの自動構成の SRV レコード (オプション)</span><span class="sxs-lookup"><span data-stu-id="1ed00-182">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="1ed00-183">DNS A および AAAA (IPv6 アドレスを使用している場合) または CNAME レコードを使って、モビリティで使用するために Lync Server 2013 Web サービスを自動的に検出する</span><span class="sxs-lookup"><span data-stu-id="1ed00-183">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services for use with mobility</span></span>
    
      - <span data-ttu-id="1ed00-184">境界ネットワークの各 Lync Server 2013、エッジサーバー、またはハードウェアロードバランサー仮想 IP (VIP) のエッジ外部インターフェイス用の DNS A および AAAA (IPv6 アドレス指定を使用している場合) および SRV レコード</span><span class="sxs-lookup"><span data-stu-id="1ed00-184">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for the Edge external interface of each Lync Server 2013, Edge Server or hardware load balancer virtual IP (VIP) in the perimeter network</span></span>
    
      - <span data-ttu-id="1ed00-185">DNS A and AAAA (IPv6 アドレス指定を使用している場合)、境界ネットワーク内のリバースプロキシサーバーのプールに対するリバースプロキシサーバーまたは VIP の外部インターフェイスのレコード</span><span class="sxs-lookup"><span data-stu-id="1ed00-185">DNS A and AAAA (if you are using IPv6 addressing) records for the external interface of the reverse proxy server or VIP for a pool of reverse proxy servers in the perimeter network</span></span>

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="1ed00-186">スプリットブレイン DNS なしの自動構成</span><span class="sxs-lookup"><span data-stu-id="1ed00-186">Automatic Configuration without Split-Brain DNS</span></span>

<span data-ttu-id="1ed00-187">内部の DNS ゾーンに\_sipinternaltls が含まれている場合は、スプリットブレイン DNS を使用して、内部でサインインしている Lync Server 2013 ユーザーは自動構成を利用できます。\_使用中の各 SIP ドメインの tcp SRV レコード。</span><span class="sxs-lookup"><span data-stu-id="1ed00-187">Using split-brain DNS, a Lync Server 2013 user that signs in internally can take advantage of automatic configuration if the internal DNS zone contains a \_sipinternaltls.\_tcp SRV record for each SIP domain in use.</span></span> <span data-ttu-id="1ed00-188">ただし、スプリットブレイン DNS を使っていない場合は、このセクションの後半で説明する回避策のいずれかが実装されていない限り、Lync を実行しているクライアントの内部自動構成は機能しません。</span><span class="sxs-lookup"><span data-stu-id="1ed00-188">However, if you do not use split-brain DNS, internal automatic configuration of clients running Lync will not work unless one of the workarounds described in later in this section is implemented.</span></span> <span data-ttu-id="1ed00-189">これは、Lync Server 2013 では、自動構成用に指定されたフロントエンドプールのドメインと一致するようにユーザーの SIP URI が必要であるためです。</span><span class="sxs-lookup"><span data-stu-id="1ed00-189">This is because Lync Server 2013 requires the user’s SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="1ed00-190">これは、以前のバージョンの Communicator の場合にも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="1ed00-190">This was also the case with earlier versions of Communicator.</span></span>

<span data-ttu-id="1ed00-191">たとえば、2つの SIP ドメインが使用されている場合、次の DNS サービス (SRV) レコードが必要になります。</span><span class="sxs-lookup"><span data-stu-id="1ed00-191">For example, if you have two SIP domains in use, the following DNS service (SRV) records would be required:</span></span>

  - <span data-ttu-id="1ed00-192">ユーザーが bob@contoso.com としてサインインした場合、ユーザーの SIP ドメイン (contoso.com) が自動構成のフロントエンドプールのドメインと一致するため、次の SRV レコードが自動構成で動作します。</span><span class="sxs-lookup"><span data-stu-id="1ed00-192">If a user signs in as bob@contoso.com the following SRV record will work for automatic configuration because the user’s SIP domain (contoso.com) matches the domain of automatic configuration Front End pool):</span></span>
    
     <span data-ttu-id="1ed00-193">\_sipinternaltls.\_tcp.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="1ed00-193">\_sipinternaltls.\_tcp.contoso.com.</span></span> <span data-ttu-id="1ed00-194">86400 IN SRV 0 0 5061 pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-194">86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>

  - <span data-ttu-id="1ed00-195">ユーザーが alice@fabrikam.com としてサインインした場合、次の DNS SRV レコードは、2つ目の SIP ドメインの自動構成に使用できます。</span><span class="sxs-lookup"><span data-stu-id="1ed00-195">If a user signs in as alice@fabrikam.com the following DNS SRV record will work for automatic configuration of the second SIP domain.</span></span>
    
     <span data-ttu-id="1ed00-196">\_sipinternaltls.\_tcp.fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="1ed00-196">\_sipinternaltls.\_tcp.fabrikam.com.</span></span> <span data-ttu-id="1ed00-197">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-197">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="1ed00-198">比較のために、ユーザーが tim@litwareinc.com としてサインインした場合、次の DNS SRV レコードは、プールが存在するドメイン (fabrikam.com) と一致しないため、自動構成では動作しません。</span><span class="sxs-lookup"><span data-stu-id="1ed00-198">For comparison, if a user signs in as tim@litwareinc.com the following DNS SRV record will not work for automatic configuration, because the client’s SIP domain (litwareinc.com) does not match the domain that the pool is in (fabrikam.com):</span></span>

 <span data-ttu-id="1ed00-199">\_sipinternaltls.\_tcp.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="1ed00-199">\_sipinternaltls.\_tcp.litwareinc.com.</span></span> <span data-ttu-id="1ed00-200">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-200">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="1ed00-201">Lync を実行しているクライアントで自動構成が必要な場合は、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="1ed00-201">If automatic configuration is required for clients running Lync, select one of the following options:</span></span>

  - <span data-ttu-id="1ed00-202">**グループポリシー**   オブジェクトでは、グループポリシーオブジェクト (gpo) を使って正しいサーバー値を入力します。</span><span class="sxs-lookup"><span data-stu-id="1ed00-202">**Group Policy Objects**   Use Group Policy objects (GPOs) to populate the correct server values.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1ed00-203">このオプションでは、自動構成は有効ではありませんが、手動構成のプロセスを自動化するため、この方法を使う場合、自動構成に関連付けられている SRV レコードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1ed00-203">This option does not enable automatic configuration, but it does automate the process of manual configuration, so if this approach is used, the SRV records associated with automatic configuration are not required.</span></span>

    
    </div>

  - <span data-ttu-id="1ed00-204">**一致する内部ゾーン**   外部 dns ゾーンと一致する内部 dns ゾーン (contoso.com など) にゾーンを作成し、自動で使用される Lync Server 2013 プールに対応するレコード (IPv6 アドレスを使用している場合) を作成します。構成.</span><span class="sxs-lookup"><span data-stu-id="1ed00-204">**Matching internal zone**   Create a zone in the internal DNS that matches the external DNS zone (for example, contoso.com) and create DNS A and AAAA (if you are using IPv6 addressing) records corresponding to the Lync Server 2013 pool used for automatic configuration.</span></span> <span data-ttu-id="1ed00-205">たとえば、ユーザーが pool01.contoso.net をホームにしていて、bob@contoso.com として Lync にサインインしている場合は、pool01.contoso.com の DNS A と AAAA (IPv6 アドレスが使用される場合) レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="1ed00-205">For example, if a user is homed on pool01.contoso.net but signs into Lync as bob@contoso.com, create an internal DNS zone called contoso.com and inside it, create a DNS A and AAAA (if IPv6 addressing is used) record for pool01.contoso.com.</span></span>

  - <span data-ttu-id="1ed00-206">**ピンポイントの内部ゾーン**   内部 DNS でゾーン全体を作成する場合は、自動構成に必要な SRV レコードに対応するピンポイント (専用) ゾーンを作成して、それらを設定することができます。(dnscmd を使用した) ゾーン。</span><span class="sxs-lookup"><span data-stu-id="1ed00-206">**Pin-point internal zone**   If you are creating an entire zone in the internal DNS is not an option, you can create pin-point (that is, dedicated) zones that correspond to the SRV records that are required for automatic configuration, and populate those zones using dnscmd.exe.</span></span> <span data-ttu-id="1ed00-207">DNS ユーザーインターフェイスでは、ピンポイントゾーンの作成がサポートされていないため、Dnscmd が必要です。</span><span class="sxs-lookup"><span data-stu-id="1ed00-207">Dnscmd.exe is required because the DNS user interface does not support creation of pin-point zones.</span></span> <span data-ttu-id="1ed00-208">たとえば、SIP ドメインが contoso.com で、2つのフロントエンドサーバーを含む pool01 というフロントエンドプールがある場合、次のピンポイントゾーンと内部 DNS 内のレコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="1ed00-208">For example, if the SIP domain is contoso.com and you have a Front End pool called pool01 that contains two Front End Servers, you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    <span data-ttu-id="1ed00-209">環境に2つ目の SIP ドメイン (たとえば、fabrikam.com) が含まれている場合は、次のピンポイントゾーンと内部 DNS 内のレコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="1ed00-209">If your environment contains a second SIP domain (for example, fabrikam.com), you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> <span data-ttu-id="1ed00-210">フロントエンドプールの FQDN は2回表示されますが、2つの異なる IP アドレスがあります。</span><span class="sxs-lookup"><span data-stu-id="1ed00-210">The Front End pool FQDN appears twice, but with two different IP addresses.</span></span> <span data-ttu-id="1ed00-211">これは、DNS の負荷分散が使用されるためですが、ハードウェアの負荷分散が使用されている場合は、1つのフロントエンドプールエントリしかありません。</span><span class="sxs-lookup"><span data-stu-id="1ed00-211">This is because DNS load balancing is used, but if hardware load balancing is used, there would be only a single Front End pool entry.</span></span> <span data-ttu-id="1ed00-212">また、contoso.com の例と fabrikam.com の例では、フロントエンドプールの FQDN 値が変更されますが、IP アドレスは変わりません。</span><span class="sxs-lookup"><span data-stu-id="1ed00-212">Also, the Front End pool FQDN values change between the contoso.com example and the fabrikam.com example, but the IP addresses remain the same.</span></span> <span data-ttu-id="1ed00-213">これは、ユーザーがいずれかの SIP ドメインからサインインしているため、自動構成で同じフロントエンドプールを使用しているためです。</span><span class="sxs-lookup"><span data-stu-id="1ed00-213">This is because users signing in from either SIP domain, use the same Front End pool for automatic configuration.</span></span>



</div>

<span data-ttu-id="1ed00-214">詳細については、DMTF のブログ記事「Communicator の自動構成とスプリットブレイン DNS (英語[http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ed00-214">For details, see the DMTF blog article, "Communicator Automatic Configuration and Split-Brain DNS," at [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ed00-215">各ブログの内容と URL は、将来予告なしに変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="1ed00-215">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a><span data-ttu-id="1ed00-216">障害回復のためにドメインネームシステム (DNS) を構成する</span><span class="sxs-lookup"><span data-stu-id="1ed00-216">Configuring the domain name system (DNS) for Disaster Recovery</span></span>

<span data-ttu-id="1ed00-217">Lync Server 2013 Web トラフィックを災害回復とフェールオーバーサイトにリダイレクトするように DNS を構成するには、GeoDNS をサポートする DNS プロバイダーを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ed00-217">To configure DNS to redirect Lync Server 2013 Web traffic to your disaster recovery and failover sites, you must be using a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="1ed00-218">Web 用の DNS レコードを設定して、フロントエンドプール全体が停止している場合でも、Web サービスを使う機能が継続されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="1ed00-218">You can set up your DNS records for Web to support disaster recovery, so that features that use Web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="1ed00-219">この障害回復機能は、自動検出 (Lyncdiscover URL)、会議、ダイヤルインの単純な Url をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1ed00-219">This disaster recovery feature supports the Autodiscover (Lyncdiscover URL), Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="1ed00-220">GeoDNS プロバイダーの Web サービスの内部および外部の解決に、追加の DNS ホスト (IPv6 を使用する場合は A と AAAA) レコードを定義して構成します。</span><span class="sxs-lookup"><span data-stu-id="1ed00-220">You define and configure additional DNS host (A and AAAA if using IPv6) records for internal and external resolution of Web services at your GeoDNS provider.</span></span> <span data-ttu-id="1ed00-221">次の情報は、ラウンドロビン DNS を使用してプロバイダーがサポートしているペアリングプール、地理的に分散した GeoDNS、または Pool1 をプライマリとして使用するように構成されている場合、または通信の損失またはハードウェアの障害が発生した場合に、Pool2 にフェールオーバーすることを前提とします。</span><span class="sxs-lookup"><span data-stu-id="1ed00-221">The following details assume paired pools, geographically dispersed, and GeoDNS supported by your provider with either round-robin DNS, or configured to use Pool1 as primary, and fail over to Pool2 in the event of communications loss or hardware failure.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ed00-222">GeoDNS レコード (例)</span><span class="sxs-lookup"><span data-stu-id="1ed00-222">GeoDNS record (example)</span></span></th>
<th><span data-ttu-id="1ed00-223">プールレコード (例)</span><span class="sxs-lookup"><span data-stu-id="1ed00-223">Pool records (example)</span></span></th>
<th><span data-ttu-id="1ed00-224">CNAME レコード (例)</span><span class="sxs-lookup"><span data-stu-id="1ed00-224">CNAME records (example)</span></span></th>
<th><span data-ttu-id="1ed00-225">DNS 設定 (オプションを 1 つ選択する)</span><span class="sxs-lookup"><span data-stu-id="1ed00-225">DNS settings (select one option)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ed00-226">Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-226">Meet-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ed00-227">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-227">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1ed00-228">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-228">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ed00-229">エイリアス Meet.contoso.com を Pool1InternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="1ed00-229">Meet.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1ed00-230">エイリアス Meet.contoso.com を Pool2InternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="1ed00-230">Meet.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ed00-231">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="1ed00-231">Round Robin between pools</span></span></p>
<p><span data-ttu-id="1ed00-232">プライマリを使用し、障害が発生した場合はセカンダリに接続する</span><span class="sxs-lookup"><span data-stu-id="1ed00-232">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ed00-233">Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-233">Meet-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ed00-234">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-234">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1ed00-235">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-235">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ed00-236">エイリアス Meet.contoso.com を Pool1ExternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="1ed00-236">Meet.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1ed00-237">エイリアス Meet.contoso.com を Pool2ExternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="1ed00-237">Meet.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ed00-238">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="1ed00-238">Round Robin between pools</span></span></p>
<p><span data-ttu-id="1ed00-239">プライマリを使用し、障害が発生した場合はセカンダリに接続する</span><span class="sxs-lookup"><span data-stu-id="1ed00-239">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ed00-240">Dialin-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-240">Dialin-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ed00-241">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-241">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1ed00-242">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-242">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ed00-243">エイリアス Dialin.contoso.com を Pool1InternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="1ed00-243">Dialin.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1ed00-244">エイリアス Dialin.contoso.com を Pool2InternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="1ed00-244">Dialin.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ed00-245">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="1ed00-245">Round Robin between pools</span></span></p>
<p><span data-ttu-id="1ed00-246">プライマリを使用し、障害が発生した場合はセカンダリに接続する</span><span class="sxs-lookup"><span data-stu-id="1ed00-246">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ed00-247">Dialin-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-247">Dialin-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ed00-248">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-248">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1ed00-249">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-249">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ed00-250">エイリアス Dialin.contoso.com を Pool1ExternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="1ed00-250">Dialin.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1ed00-251">エイリアス Dialin.contoso.com を Pool2ExternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="1ed00-251">Dialin.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ed00-252">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="1ed00-252">Round Robin between pools</span></span></p>
<p><span data-ttu-id="1ed00-253">プライマリを使用し、障害が発生した場合はセカンダリに接続する</span><span class="sxs-lookup"><span data-stu-id="1ed00-253">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ed00-254">Lyncdiscoverint-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-254">Lyncdiscoverint-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ed00-255">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-255">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1ed00-256">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-256">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ed00-257">エイリアス Lyncdiscoverinternal.contoso.com を Pool1InternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="1ed00-257">Lyncdiscoverinternal.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1ed00-258">エイリアス Lyncdiscoverinternal.contoso.com を Pool2InternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="1ed00-258">Lyncdiscoverinternal.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ed00-259">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="1ed00-259">Round Robin between pools</span></span></p>
<p><span data-ttu-id="1ed00-260">プライマリを使用し、障害が発生した場合はセカンダリに接続する</span><span class="sxs-lookup"><span data-stu-id="1ed00-260">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ed00-261">Lyncdiscover-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-261">Lyncdiscover-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ed00-262">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-262">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1ed00-263">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-263">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ed00-264">エイリアス Lyncdiscover.contoso.com を Pool1ExternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="1ed00-264">Lyncdiscover.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1ed00-265">エイリアス Lyncdiscover.contoso.com を Pool2ExternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="1ed00-265">Lyncdiscover.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ed00-266">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="1ed00-266">Round Robin between pools</span></span></p>
<p><span data-ttu-id="1ed00-267">プライマリを使用し、障害が発生した場合はセカンダリに接続する</span><span class="sxs-lookup"><span data-stu-id="1ed00-267">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ed00-268">Scheduler-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-268">Scheduler-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ed00-269">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-269">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1ed00-270">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-270">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ed00-271">エイリアス Scheduler.contoso.com を Pool1InternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="1ed00-271">Scheduler.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1ed00-272">エイリアス Scheduler.contoso.com を Pool2InternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="1ed00-272">Scheduler.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ed00-273">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="1ed00-273">Round Robin between pools</span></span></p>
<p><span data-ttu-id="1ed00-274">プライマリを使用し、障害が発生した場合はセカンダリに接続する</span><span class="sxs-lookup"><span data-stu-id="1ed00-274">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ed00-275">Scheduler-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-275">Scheduler-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ed00-276">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-276">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1ed00-277">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ed00-277">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ed00-278">エイリアス Scheduler.contoso.com を Pool1ExternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="1ed00-278">Scheduler.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1ed00-279">エイリアス Scheduler.contoso.com を Pool2ExternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="1ed00-279">Scheduler.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ed00-280">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="1ed00-280">Round Robin between pools</span></span></p>
<p><span data-ttu-id="1ed00-281">プライマリを使用し、障害が発生した場合はセカンダリに接続する</span><span class="sxs-lookup"><span data-stu-id="1ed00-281">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a><span data-ttu-id="1ed00-282">DNS Load Balancing</span><span class="sxs-lookup"><span data-stu-id="1ed00-282">DNS Load Balancing</span></span>

<span data-ttu-id="1ed00-283">DNS の負荷分散は、通常、アプリケーションレベルで実装されます。</span><span class="sxs-lookup"><span data-stu-id="1ed00-283">DNS load balancing is typically implemented at the application level.</span></span> <span data-ttu-id="1ed00-284">アプリケーション (たとえば、Lync を実行しているクライアント) は、プールの完全修飾ドメイン名 (FQDN) に対する DNS A と AAAA (IPv6 アドレスが使用されている場合) から返される IP アドレスのいずれかに接続して、プール内のサーバーに接続しようとします。</span><span class="sxs-lookup"><span data-stu-id="1ed00-284">The application (for example, a client running Lync), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="1ed00-285">たとえば、pool01.contoso.com という名前のプールに3台のフロントエンドサーバーがある場合は、次のような処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="1ed00-285">For example, if there are three front end servers in a pool named pool01.contoso.com, the following will happen:</span></span>

  - <span data-ttu-id="1ed00-286">Lync を実行しているクライアントは、pool01.contoso.com に対して DNS を照会します。</span><span class="sxs-lookup"><span data-stu-id="1ed00-286">Clients running Lync query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="1ed00-287">このクエリでは、3つの IP アドレスが返され、次のようにキャッシュされます (この順序で行う必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="1ed00-287">The query returns three IP addresses and caches them as follows (not necessarily in this order):</span></span>
    
    <span data-ttu-id="1ed00-288">pool01.contoso.com 192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="1ed00-288">pool01.contoso.com      192.168.10.90</span></span>
    
    <span data-ttu-id="1ed00-289">pool01.contoso.com 192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="1ed00-289">pool01.contoso.com      192.168.10.91</span></span>
    
    <span data-ttu-id="1ed00-290">pool01.contoso.com 192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="1ed00-290">pool01.contoso.com      192.168.10.92</span></span>

  - <span data-ttu-id="1ed00-291">クライアントは、いずれかの IP アドレスへの伝送制御プロトコル (TCP) 接続を確立しようとします。</span><span class="sxs-lookup"><span data-stu-id="1ed00-291">The client attempts to establish a Transmission Control Protocol (TCP) connection to one of the IP addresses.</span></span> <span data-ttu-id="1ed00-292">この問題が発生した場合、クライアントはキャッシュ内の次の IP アドレスを試します。</span><span class="sxs-lookup"><span data-stu-id="1ed00-292">If that fails, the client tries the next IP address in the cache.</span></span>

  - <span data-ttu-id="1ed00-293">TCP 接続が成功した場合、クライアントは TLS のネゴシエーションを行い、pool01.contoso.com のプライマリ レジストラーに接続します。</span><span class="sxs-lookup"><span data-stu-id="1ed00-293">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>

  - <span data-ttu-id="1ed00-294">クライアントがすべてのキャッシュエントリを正常に接続していない場合、ユーザーには Lync Server 2013 を実行しているサーバーが現時点で利用できないことが通知されます。</span><span class="sxs-lookup"><span data-stu-id="1ed00-294">If the client tries all cached entries without a successful connection, the user is notified that no servers running Lync Server 2013 are available at the moment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ed00-295">DNS ベースの負荷分散は、通常は dns に依存して、プール内のサーバーに対応する異なる順序の IP アドレスを提供することによって、負荷分散を意味します。</span><span class="sxs-lookup"><span data-stu-id="1ed00-295">DNS-based load balancing is different from DNS round robin (DNS RR) which typically refers to load balancing by relying on DNS to provide a different order of IP addresses corresponding to the servers in a pool.</span></span> <span data-ttu-id="1ed00-296">通常、DNS RR では、読み込みの配布のみが可能ですが、フェールオーバーは有効になりません。</span><span class="sxs-lookup"><span data-stu-id="1ed00-296">Typically DNS RR only enables load distribution, but does not enable failover.</span></span> <span data-ttu-id="1ed00-297">たとえば、DNS A と AAAA によって返される1つの IP アドレスへの接続 (IPv6 アドレスを使っている場合) クエリが失敗すると、接続は失敗します。</span><span class="sxs-lookup"><span data-stu-id="1ed00-297">For example, if the connection to the one IP address returned by the DNS A and AAAA (if you are using IPv6 addressing) query fails, the connection fails.</span></span> <span data-ttu-id="1ed00-298">したがって、DNS によるラウンドロビンは、DNS ベースの負荷分散よりも信頼性が低くなります。</span><span class="sxs-lookup"><span data-stu-id="1ed00-298">Therefore, DNS round robin by itself is less reliable than DNS-based load balancing.</span></span> <span data-ttu-id="1ed00-299">Dns ラウンドロビンと DNS の負荷分散を併用できます。</span><span class="sxs-lookup"><span data-stu-id="1ed00-299">You can use DNS round robin in conjunction with DNS load balancing.</span></span>



</div>

<span data-ttu-id="1ed00-300">DNS の負荷分散は、次の場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1ed00-300">DNS load balancing is used for the following:</span></span>

  - <span data-ttu-id="1ed00-301">エッジサーバーへのサーバー間 SIP の負荷分散</span><span class="sxs-lookup"><span data-stu-id="1ed00-301">Load balancing server-to-server SIP to the Edge Servers</span></span>

  - <span data-ttu-id="1ed00-302">会議の自動応答、返信グループ、コールパークなどの統合コミュニケーションアプリケーションサービス (UCAS) アプリケーションのロードバランシング</span><span class="sxs-lookup"><span data-stu-id="1ed00-302">Load balancing Unified Communications Application Services (UCAS) applications such as Conferencing Auto Attendant, Response Group, and Call Park</span></span>

  - <span data-ttu-id="1ed00-303">アプリケーション ("ドレイン" とも呼ばれます) としての新しい接続の無効化</span><span class="sxs-lookup"><span data-stu-id="1ed00-303">Preventing new connections to UCAS applications (also known as "draining")</span></span>

  - <span data-ttu-id="1ed00-304">クライアントとエッジサーバー間のすべてのクライアント間トラフィックの負荷分散</span><span class="sxs-lookup"><span data-stu-id="1ed00-304">Load balancing all client-to-server traffic between clients and Edge Servers</span></span>

<span data-ttu-id="1ed00-305">DNS の負荷分散は、次の用途では使用できません。</span><span class="sxs-lookup"><span data-stu-id="1ed00-305">DNS load balancing cannot be used for the following:</span></span>

  - <span data-ttu-id="1ed00-306">ディレクターまたはフロントエンドサーバーへのクライアント対サーバー web トラフィック</span><span class="sxs-lookup"><span data-stu-id="1ed00-306">Client-to-server web traffic to Director or Front End Servers</span></span>

<span data-ttu-id="1ed00-307">DNS の負荷分散とフェデレーショントラフィック:</span><span class="sxs-lookup"><span data-stu-id="1ed00-307">DNS load balancing and federated traffic:</span></span>

<span data-ttu-id="1ed00-308">DNS SRV クエリによって複数の DNS レコードが返される場合、アクセスエッジサービスは常に、最も低い数値の優先度と最大の数値の重みで DNS SRV レコードを選びます。</span><span class="sxs-lookup"><span data-stu-id="1ed00-308">If multiple DNS records are returned by a DNS SRV query, the Access Edge service always picks the DNS SRV record with the lowest numeric priority and highest numeric weight.</span></span> <span data-ttu-id="1ed00-309">インターネットエンジニアリングタスクは、"サービスの場所を指定するための DNS RR" を強制します<http://www.ietf.org/rfc/rfc2782.txt> 。複数の DNS SRV レコードが定義されている場合は、priority が最初に使用され、次に重みが使われることを指定します。</span><span class="sxs-lookup"><span data-stu-id="1ed00-309">The Internet Engineering Task Force document “A DNS RR for specifying the location of services (DNS SRV)” <http://www.ietf.org/rfc/rfc2782.txt> specifies that if there are multiple DNS SRV records defined, priority is first used, then weight.</span></span> <span data-ttu-id="1ed00-310">たとえば、DNS SRV レコード A の配点は20で、優先度は40で、DNS SRV レコード B の重みは10で、もう1つは50の優先順位です。</span><span class="sxs-lookup"><span data-stu-id="1ed00-310">For example DNS SRV record A has a weight of 20 and a priority of 40 and DNS SRV record B has a weight of 10 and priority of 50.</span></span> <span data-ttu-id="1ed00-311">優先順位40の DNS SRV レコード A が選択されます。</span><span class="sxs-lookup"><span data-stu-id="1ed00-311">DNS SRV record A with priority 40 will be selected.</span></span> <span data-ttu-id="1ed00-312">DNS SRV レコードの選択には、次のルールが適用されます。</span><span class="sxs-lookup"><span data-stu-id="1ed00-312">The following rules apply to DNS SRV record selection:</span></span>

  - <span data-ttu-id="1ed00-313">優先度は最初に考慮されます。</span><span class="sxs-lookup"><span data-stu-id="1ed00-313">Priority is considered first.</span></span> <span data-ttu-id="1ed00-314">クライアントは、DNS SRV レコードによって定義されたターゲットホストに連絡して、到達可能な最も低い優先順位を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ed00-314">A client MUST attempt to contact the target host defined by the DNS SRV record with the lowest numbered priority it can reach.</span></span> <span data-ttu-id="1ed00-315">同じ優先順位のターゲットは、[加重] フィールドで定義された順序で試す必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ed00-315">Targets with the same priority SHOULD be tried in an order defined by the weight field.</span></span>

  - <span data-ttu-id="1ed00-316">[加重] フィールドでは、同じ優先度のエントリの相対的な重みを指定します。</span><span class="sxs-lookup"><span data-stu-id="1ed00-316">The weight field specifies a relative weight for entries with the same priority.</span></span> <span data-ttu-id="1ed00-317">重みを大きくすると、より高い確率で選択されます。</span><span class="sxs-lookup"><span data-stu-id="1ed00-317">Larger weights SHOULD be given a proportionately higher probability of being selected.</span></span> <span data-ttu-id="1ed00-318">サーバーが選択されていない場合、DNS 管理者はウエイト0を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ed00-318">DNS administrators SHOULD use Weight 0 when there isn’t any server selection to do.</span></span> <span data-ttu-id="1ed00-319">加重値が0より大きいレコードが存在する場合、重み付けが0のレコードは、非常に少ない確率で選択される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1ed00-319">In the presence of records containing weights greater than 0, records with weight 0 should have a very small chance of being selected.</span></span>

<span data-ttu-id="1ed00-320">優先度が同じ複数の DNS SRV レコードが返される場合、アクセスエッジサービスによって、DNS サーバーから最初に受信された SRV レコードが選択されます。</span><span class="sxs-lookup"><span data-stu-id="1ed00-320">If multiple DNS SRV records with equal priority and weight are returned, the Access Edge service will select the SRV record that was received first from the DNS server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

