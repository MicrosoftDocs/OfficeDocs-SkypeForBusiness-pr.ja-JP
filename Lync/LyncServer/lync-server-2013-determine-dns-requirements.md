---
title: 'Lync Server 2013: DNS の要件を決定する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79f1c27f48beddd0c1fd3260193a71bb79b034bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="164f9-102">Lync Server 2013 の DNS 要件を決定する</span><span class="sxs-lookup"><span data-stu-id="164f9-102">Determine DNS requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="164f9-103">_**トピックの最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="164f9-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="164f9-104">次のフローチャートを使用して、ドメインネームシステム (DNS) の要件を決定します。</span><span class="sxs-lookup"><span data-stu-id="164f9-104">Use the following flow chart to determine Domain Name System (DNS) requirements.</span></span> <span data-ttu-id="164f9-105">Lync Server 2013 2013 の累積的な更新プログラムの変更点については、該当する場所について説明します。</span><span class="sxs-lookup"><span data-stu-id="164f9-105">Changes for the Cumulative Updates for Lync Server 2013: February 2013 are noted where they apply.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="164f9-106">Microsoft Lync Server 2013 は、IPv6 アドレスの使用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="164f9-106">Microsoft Lync Server 2013 supports the use of IPv6 addressing.</span></span> <span data-ttu-id="164f9-107">IPv6 アドレスを使用するには、IPv6 DNS のサポートを提供し、DNS ホスト AAAA ("クワッド-A") レコードを構成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="164f9-107">To use IPv6 addresses, you must also provide support for IPv6 DNS and configure DNS host AAAA (known as “quad-A”) records.</span></span> <span data-ttu-id="164f9-108">IPv4 と IPv6 の両方が使用されている展開では、IPv4 用のホスト A レコードと IPv6 用のホスト AAAA の両方を構成して管理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="164f9-108">In deployments where both IPv4 and IPv6 are being used, it is best to configure and maintain both host A records for IPv4 and host AAAA for IPv6.</span></span> <span data-ttu-id="164f9-109">展開が完全に IPv6 に移行している場合でも、外部ユーザーが依然として IPv4 を使用している場合は、IPv4 DNS ホストレコードが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="164f9-109">Even if your deployment has transitioned fully to IPv6, IPv4 DNS host records may still be required when external users are still using IPv4.</span></span>



</div>

<span data-ttu-id="164f9-110">**DNS 要件の判断フローチャート**</span><span class="sxs-lookup"><span data-stu-id="164f9-110">**Determining DNS Requirements Flow Chart**</span></span>

<span data-ttu-id="164f9-111">![175782ace363e4-08、912f2-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ace363e4-08、912f2-8991bf152970")</span><span class="sxs-lookup"><span data-stu-id="164f9-111">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="164f9-112">既定では、ドメインに参加していないコンピューターのコンピューター名は、完全修飾ドメイン名 (FQDN) ではなく、ホスト名です。</span><span class="sxs-lookup"><span data-stu-id="164f9-112">By default the computer name of a computer that is not joined to a domain is a host name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="164f9-113">トポロジビルダーでは、ホスト名ではなく Fqdn を使用します。</span><span class="sxs-lookup"><span data-stu-id="164f9-113">Topology Builder uses FQDNs, not host names.</span></span> <span data-ttu-id="164f9-114">そのため、エッジ サーバーとして展開する、ドメインに参加していないコンピューターの名前には、DNS サフィックスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="164f9-114">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="164f9-115">Lync Server、エッジ サーバー、およびプールの FQDN を割り当てる場合に使用できる文字は、<STRONG>標準文字のみ</STRONG> (A ～ Z、a ～ z、0 ～ 9、およびハイフン) です。</span><span class="sxs-lookup"><span data-stu-id="164f9-115"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="164f9-116">Unicode 文字およびアンダースコアは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="164f9-116">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="164f9-117">一般に、外部 DNS および公的 CA では、FQDN に非標準文字はサポートされていません (証明書で FQDN を SN に割り当てることが必要になります)。</span><span class="sxs-lookup"><span data-stu-id="164f9-117">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="164f9-118">詳細については、「 <A href="lync-server-2013-configure-dns-host-records.md">CONFIGURE DNS Host records For Lync Server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="164f9-118">For additional details, see <A href="lync-server-2013-configure-dns-host-records.md">Configure DNS Host records for Lync Server 2013</A></span></span>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a><span data-ttu-id="164f9-119">Lync クライアントがサービスを検索する方法</span><span class="sxs-lookup"><span data-stu-id="164f9-119">How Lync Clients Locate Services</span></span>

<span data-ttu-id="164f9-120">Microsoft Lync 2010、Lync 2013、Lync Mobile は、クライアントが Lync Server 2013 でサービスを検索してアクセスする方法に似ています。</span><span class="sxs-lookup"><span data-stu-id="164f9-120">Microsoft Lync 2010, Lync 2013, and Lync Mobile are similar in how the client finds and accesses services in Lync Server 2013.</span></span> <span data-ttu-id="164f9-121">注目すべき例外として、異なるサービスの場所のプロセスを使用する Lync Windows ストアアプリがあります。</span><span class="sxs-lookup"><span data-stu-id="164f9-121">The notable exception is the Lync Windows Store app that uses a different service location process.</span></span> <span data-ttu-id="164f9-122">このセクションでは、クライアントがサービスを検索する方法、最初に一連の SRV およびホストレコードを使用する従来の方法、さらには自動検出サービスレコードのみを使用して、2つのシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="164f9-122">This section details two scenarios of how the clients locate services, first the traditional method using a series of SRV and A host records, second using only the Autodiscover service records.</span></span> <span data-ttu-id="164f9-123">デスクトップクライアントへの累積的な更新プログラムを適用すると、すべてのクライアントに対して Lync Server 2010 から DNS の場所のプロセスが変更されます。クエリが正常に返されるか、または使用可能な DNS レコードの一覧が表示されなくなるまで、DNS クエリプロセスは続行され、最後のエラーが返されます。クライアント。</span><span class="sxs-lookup"><span data-stu-id="164f9-123">Cumulative updates to the desktop clients change the DNS location process from Lync Server 2010 For all clients, the DNS query process continues until a successful query is returned, or the list of possible DNS records is exhausted, and the final error is returned to the client.</span></span>

<span data-ttu-id="164f9-124">DNS 参照中に Lync Windows ストアアプリを**除く**すべてのクライアントについて、SRV レコードが照会され、次の順序でクライアントに返されます。</span><span class="sxs-lookup"><span data-stu-id="164f9-124">For all clients **except** for the Lync Windows Store app During DNS lookup, SRV records are queried and returned to the client in the following order:</span></span>

1.  <span data-ttu-id="164f9-125">lyncdiscoverinternal.\<内部\> Web サービスの自動検出サービスのドメイン A (ホスト) レコード</span><span class="sxs-lookup"><span data-stu-id="164f9-125">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="164f9-126">lyncdiscover.\<外部\> Web サービスの自動検出サービスのドメイン A (ホスト) レコード</span><span class="sxs-lookup"><span data-stu-id="164f9-126">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

3.  <span data-ttu-id="164f9-127">\_sipinternaltls.\_tcp。\<内部\> TLS 接続のドメイン SRV (サービスロケーター) レコード</span><span class="sxs-lookup"><span data-stu-id="164f9-127">\_sipinternaltls.\_tcp.\<domain\>   SRV (service locator) record for internal TLS connections</span></span>

4.  <span data-ttu-id="164f9-128">\_sipinternal.\_tcp。\<内部\> tcp 接続のドメイン SRV (サービスロケーター) レコード (tcp が許可されている場合にのみ実行)</span><span class="sxs-lookup"><span data-stu-id="164f9-128">\_sipinternal.\_tcp.\<domain\>   SRV (service locator) record for internal TCP connections (performed only if TCP is allowed)</span></span>

5.  <span data-ttu-id="164f9-129">\_sip.\_tls。\<外部\> TLS 接続のドメイン SRV (サービスロケーター) レコード</span><span class="sxs-lookup"><span data-stu-id="164f9-129">\_sip.\_tls.\<domain\>   SRV (service locator) record for external TLS connections</span></span>

6.  <span data-ttu-id="164f9-130">sipinternal.\<フロント\>エンドプールまたはディレクターのドメイン A (ホスト) レコード (内部ネットワーク上でのみ解決可能)</span><span class="sxs-lookup"><span data-stu-id="164f9-130">sipinternal.\<domain\>   A (host) record for the Front End pool or Director, resolvable only on the internal network</span></span>

7.  <span data-ttu-id="164f9-131">sip.\<内部\>ネットワーク上のフロントエンドプールまたはディレクターのドメイン A (ホスト) レコード、またはクライアントが外部にある場合はアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="164f9-131">sip.\<domain\>   A (host) record for the Front End pool or Director on the internal network, or the Access Edge service when the client is external</span></span>

8.  <span data-ttu-id="164f9-132">sipexternal.\<クライアント\>が外部にいる場合のアクセスエッジサービスのドメイン A (ホスト) レコード</span><span class="sxs-lookup"><span data-stu-id="164f9-132">sipexternal.\<domain\>   A (host) record for the Access Edge service when the client is external</span></span>

<span data-ttu-id="164f9-133">Lync Windows ストアアプリは、2つのレコードを使用するので、プロセスが完全に変更されます。</span><span class="sxs-lookup"><span data-stu-id="164f9-133">The Lync Windows Store app changes the process completely because it uses two records:</span></span>

1.  <span data-ttu-id="164f9-134">lyncdiscoverinternal.\<内部\> Web サービスの自動検出サービスのドメイン A (ホスト) レコード</span><span class="sxs-lookup"><span data-stu-id="164f9-134">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="164f9-135">lyncdiscover.\<外部\> Web サービスの自動検出サービスのドメイン A (ホスト) レコード</span><span class="sxs-lookup"><span data-stu-id="164f9-135">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

<span data-ttu-id="164f9-136">他のレコードの種類へのフォールバックはありません。</span><span class="sxs-lookup"><span data-stu-id="164f9-136">There is no fallback to the other record types.</span></span>

<span data-ttu-id="164f9-137">以前のクライアントと比較した新しいクライアントで使用される方法の違いは、自動検出サービスがすべてのサービスを特定するために推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="164f9-137">The difference between the methods used for newer clients as compared to older clients is that the Autodiscover service is becoming the preferred method to locate all services.</span></span>

<span data-ttu-id="164f9-138">接続が成功すると、自動検出サービスはユーザーのホームプールのすべての Web サービス Url を返します。これには、Mobility Service (IIS のサービスに対して作成された仮想ディレクトリによる Mcx を使用)、Microsoft Lync Web App、Web スケジューラの Url が含まれます。</span><span class="sxs-lookup"><span data-stu-id="164f9-138">When a connection is successful, the Autodiscover Service returns all the Web Services URLs for the user's home pool, including the Mobility Service (known as Mcx by the virtual directory created for the service in IIS), Microsoft Lync Web App and Web scheduler URLs.</span></span> <span data-ttu-id="164f9-139">ただし、内部 Mobility Service URL と外部 Mobility Service URL の両方が外部 Web サービスの FQDN に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="164f9-139">However, both the internal Mobility Service URL and the external Mobility Service URL is associated with the external Web Services FQDN.</span></span> <span data-ttu-id="164f9-140">そのため、モバイルデバイスがネットワークの内部と外部のどちらにあるかに関係なく、デバイスは常にリバースプロキシ経由でモビリティサービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="164f9-140">Therefore, regardless of whether a mobile device is internal or external to the network, the device always connects to the Mobility Service externally through the reverse proxy.</span></span>

<span data-ttu-id="164f9-141">Lync Server 2013 の累積的な更新プログラム (2 月 11 2013 日) がインストールされている場合、自動検出サービスは、Internal/UCWA、External/UCWA、UCWA への参照も返します。</span><span class="sxs-lookup"><span data-stu-id="164f9-141">If the Cumulative Updates for Lync Server 2013: February 2013 has been installed, the Autodiscover Service also returns references to Internal/UCWA, External/UCWA and UCWA.</span></span> <span data-ttu-id="164f9-142">これらのエントリは、統合コミュニケーション Web API (UCWA) web コンポーネントを参照します。</span><span class="sxs-lookup"><span data-stu-id="164f9-142">These entries refer to the Unified Communications Web API (UCWA) web component.</span></span> <span data-ttu-id="164f9-143">現時点では、エントリ UCWA のみが使用されており、web コンポーネントの URL への参照を提供しています。</span><span class="sxs-lookup"><span data-stu-id="164f9-143">Currently, only the entry UCWA is used and provides a reference to a URL for the web component.</span></span> <span data-ttu-id="164f9-144">UCWA は、lync 2010 モバイルクライアントで使用される Mcx Mobility Service ではなく、Lync 2013 モバイルクライアントによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="164f9-144">UCWA is used by Lync 2013 Mobile clients instead of the Mcx Mobility Service used by the Lync 2010 Mobile clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="164f9-145">SRV レコードを作成する場合、DNS SRV レコードが作成されるのと同じドメインで DNS A および AAAA (IPv6 アドレスを使用している場合) レコードを参照する必要があることを覚えておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="164f9-145">When creating SRV records, it is important to remember that they must point to a DNS A and AAAA (if you are using IPv6 addressing) record in the same domain in which the DNS SRV record is created.</span></span> <span data-ttu-id="164f9-146">たとえば、SRV レコードが contoso.com にある場合、A および AAAA (IPv6 アドレス指定を使用している場合) レコードは、fabrikam.com ではできません。</span><span class="sxs-lookup"><span data-stu-id="164f9-146">For example, if the SRV record is in contoso.com, the A and AAAA (if you are using IPv6 addressing) record it points to cannot be in fabrikam.com.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="164f9-147">既定の構成では、すべてのモバイルクライアントトラフィックを外部サイト経由で転送します。</span><span class="sxs-lookup"><span data-stu-id="164f9-147">The default configuration is to direct all mobile client traffic through the external site.</span></span> <span data-ttu-id="164f9-148">要件に適している場合は、設定を変更して内部 URL のみを返すようにできます。</span><span class="sxs-lookup"><span data-stu-id="164f9-148">You can modify settings to return only the internal URL, if this is more preferable for your requirements.</span></span> <span data-ttu-id="164f9-149">この構成では、ユーザーは企業ネットワークの内部にいる場合にのみ、モバイルデバイスで Lync mobile アプリケーションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="164f9-149">With this configuration, users can use Lync mobile applications on their mobile devices only when they are inside the corporate network.</span></span> <span data-ttu-id="164f9-150">この構成を定義するには、 <STRONG>Set-CsMcxConfiguration</STRONG>コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="164f9-150">To define this configuration, you use the <STRONG>Set-CsMcxConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="164f9-151">モバイルアプリケーションは、アドレス帳サービスなどの他の Lync Server 2013 サービスに接続することもできますが、内部モバイルアプリケーション web 要求は、Mobility Service に対してのみ外部 web FQDN に送られます。</span><span class="sxs-lookup"><span data-stu-id="164f9-151">Although mobile applications can also connect to other Lync Server 2013 services, such as Address Book Service, internal mobile application web requests go to the external web FQDN only for the Mobility Service.</span></span> <span data-ttu-id="164f9-152">その他のサービス要求 (アドレス帳要求など) では、この構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="164f9-152">Other service requests, such as Address Book requests, do not require this configuration.</span></span>



</div>

<span data-ttu-id="164f9-153">モバイルデバイスは、サービスの手動検出をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="164f9-153">Mobile devices support manual discovery of services.</span></span> <span data-ttu-id="164f9-154">この場合、各ユーザーは、次のように、完全な内部および外部の自動検出サービス Uri (プロトコルとパスを含む) でモバイルデバイスの設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="164f9-154">In this case, each user must configure the mobile device settings with the full internal and external Autodiscover Service URIs, including the protocol and path, as follows:</span></span>

  - <span data-ttu-id="164f9-155">外部\<アクセス用の\>Https://extpoolfqdn/autodiscover/autodiscoverservice.svc/root (</span><span class="sxs-lookup"><span data-stu-id="164f9-155">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>

  - <span data-ttu-id="164f9-156">内部\<アクセス用の\>Https://intpoolfqdn/AutoDiscover/AutoDiscover.svc/Root</span><span class="sxs-lookup"><span data-stu-id="164f9-156">https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root for internal access</span></span>

<span data-ttu-id="164f9-157">手動検出ではなく、自動検出を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="164f9-157">We recommend that you use automatic discovery, rather than manual discovery.</span></span> <span data-ttu-id="164f9-158">ただし、手動の設定は、モバイルデバイスの接続の問題のトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="164f9-158">However, manual settings can be useful for troubleshooting mobile device connectivity issues.</span></span>

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a><span data-ttu-id="164f9-159">Lync Server でのスプリットブレイン DNS の構成</span><span class="sxs-lookup"><span data-stu-id="164f9-159">Configuring Split-Brain DNS with Lync Server</span></span>

<span data-ttu-id="164f9-160">スプリットブレイン DNS は、分割 DNS またはスプリットホライズン DNS など、さまざまな名前で認識されます。</span><span class="sxs-lookup"><span data-stu-id="164f9-160">Split-brain DNS is known by a number of names, for example, split DNS or split-horizon DNS.</span></span> <span data-ttu-id="164f9-161">単純に、同じ名前空間を持つ2つの DNS ゾーンがあり、DNS ゾーンサービスの内部のみの要求、およびその他の DNS ゾーンサービスの外部専用要求がある DNS 構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="164f9-161">Simply, it describes a DNS configuration where there are two DNS zones with the same namespace – but one DNS zone services internal-only requests, and the other DNS zone services external-only requests.</span></span> <span data-ttu-id="164f9-162">ただし、内部 DNS に含まれる DNS SRV および A レコードの多くは、外部 DNS には含まれず、逆の場合も同様です。</span><span class="sxs-lookup"><span data-stu-id="164f9-162">However, many of the DNS SRV and A records contained in the internal DNS will not be contained in the external DNS, and the reverse is also true.</span></span> <span data-ttu-id="164f9-163">内部および外部 DNS の両方に同じ DNS レコードが存在する場合 (たとえば、www.contoso.com)、返される IP アドレスは、クエリが開始された場所 (内部または外部) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="164f9-163">In cases where the same DNS record exists in both the internal and external DNS (for example, www.contoso.com), the IP address returned will be different based on where (internal or external) the query was initiated.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="164f9-164">現時点では、LyncDiscover および LyncDiscoverInternal DNS レコードに対して、スプリットブレイン DNS はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="164f9-164">Currently, Split-Brain DNS is not supported for the mobility, or more specifically, the LyncDiscover and LyncDiscoverInternal DNS records.</span></span> <span data-ttu-id="164f9-165">LyncDiscover は、外部 DNS サーバーで定義されている必要があり、LyncDiscoverInternal は内部 DNS サーバーで定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="164f9-165">LyncDiscover must be defined on an external DNS server and LyncDiscoverInternal must be defined on an internal DNS server.</span></span>



</div>

<span data-ttu-id="164f9-166">これらのトピックでは、スプリットブレイン DNS という用語が使用されます。</span><span class="sxs-lookup"><span data-stu-id="164f9-166">For the purposes of these topics, the term split-brain DNS will be used.</span></span>

<span data-ttu-id="164f9-167">スプリットブレイン DNS を構成している場合は、次の内部および外部ゾーンに、各ゾーンで必要な DNS レコードの種類の概要が含まれています。</span><span class="sxs-lookup"><span data-stu-id="164f9-167">If you are configuring split-brain DNS, the following internal and external zone contain a summary of the types of DNS records required in each zone.</span></span> <span data-ttu-id="164f9-168">詳細については、「 [Lync Server 2013 の外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="164f9-168">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="164f9-169">**内部 DNS:**</span><span class="sxs-lookup"><span data-stu-id="164f9-169">**Internal DNS:**</span></span>

  - <span data-ttu-id="164f9-170">権限がある contoso.com という名前の DNS ゾーンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="164f9-170">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="164f9-171">内部 contoso.com ゾーンには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="164f9-171">The internal contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="164f9-172">内部 Lync Server 2013 クライアントの自動構成用の DNS A および AAAA (IPv6 アドレスを使用している場合) および SRV レコード (オプション)</span><span class="sxs-lookup"><span data-stu-id="164f9-172">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for internal Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="164f9-173">Lync Server 2013 Web サービスの自動検出用の DNS A および AAAA (IPv6 アドレスを使用している場合) または CNAME レコード (オプション)</span><span class="sxs-lookup"><span data-stu-id="164f9-173">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services (optional)</span></span>
    
      - <span data-ttu-id="164f9-174">フロントエンドプール名、ディレクターまたはディレクターのプール名、および企業ネットワークで Lync Server 2013 を実行しているすべての内部サーバーの DNS A および AAAA (IPv6 アドレス指定を使用している場合) レコード</span><span class="sxs-lookup"><span data-stu-id="164f9-174">DNS A and AAAA (if you are using IPv6 addressing) records for Front End pool name, Director or Director pool name, and all internal servers running Lync Server 2013 in the corporate network</span></span>
    
      - <span data-ttu-id="164f9-175">境界ネットワーク内の各 Lync Server 2013 のエッジ内部インターフェイスの DNS A および AAAA (IPv6 アドレスを使用している場合) レコード</span><span class="sxs-lookup"><span data-stu-id="164f9-175">DNS A and AAAA (if you are using IPv6 addressing) records for the Edge internal interface of each Lync Server 2013, Edge Server in the perimeter network</span></span>
    
      - <span data-ttu-id="164f9-176">境界ネットワーク内の各リバースプロキシサーバーの内部インターフェイスの DNS A および AAAA (IPv6 アドレスを使用している場合) レコード (リバースプロキシの管理の場合はオプション)</span><span class="sxs-lookup"><span data-stu-id="164f9-176">DNS A and AAAA (if you are using IPv6 addressing) records for the internal interface of each reverse proxy server in the perimeter network (optional for management of reverse proxy)</span></span>
    
      - <span data-ttu-id="164f9-177">境界ネットワーク内のすべての Lync Server 2013 エッジサーバー内部エッジインターフェイスは、contoso.com へのクエリを解決するために内部 DNS ゾーンを使用します。</span><span class="sxs-lookup"><span data-stu-id="164f9-177">All Lync Server 2013  Edge Server internal edge interfaces in the perimeter network use the internal DNS zone for resolving queries to contoso.com</span></span>
    
      - <span data-ttu-id="164f9-178">企業ネットワーク内の Lync Server 2013 を実行2013しているすべてのサーバーは、内部 DNS サーバーを参照して contoso.com へのクエリを解決するか、各エッジサーバーで HOSTS ファイルを使用し、リスト A と AAAA (IPv6 アドレス指定を使用している場合) レコードを参照します。次ホップサーバー、特にディレクターまたはディレクター VIP、フロントエンドプール VIP、または Standard Edition サーバー</span><span class="sxs-lookup"><span data-stu-id="164f9-178">All servers running Lync Server 2013 and clients running Lync 2013 in the corporate network point to the internal DNS servers for resolving queries to contoso.com, or use of HOSTS file on each Edge server and list A and AAAA (if you are using IPv6 addressing) records for next hop server, specifically the Director or Director VIP, Front End pool VIP, or Standard Edition server</span></span>

<span data-ttu-id="164f9-179">**外部 DNS:**</span><span class="sxs-lookup"><span data-stu-id="164f9-179">**External DNS:**</span></span>

  - <span data-ttu-id="164f9-180">権限がある contoso.com という名前の DNS ゾーンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="164f9-180">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="164f9-181">外部 contoso.com ゾーンには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="164f9-181">The external contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="164f9-182">Lync Server 2013 クライアントの自動構成用の DNS A および AAAA (IPv6 アドレスを使用している場合) および SRV レコード (オプション)</span><span class="sxs-lookup"><span data-stu-id="164f9-182">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="164f9-183">モビリティで使用する Lync Server 2013 Web サービスの自動検出用の DNS A および AAAA (IPv6 アドレスを使用している場合) または CNAME レコード</span><span class="sxs-lookup"><span data-stu-id="164f9-183">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services for use with mobility</span></span>
    
      - <span data-ttu-id="164f9-184">境界ネットワーク内の各 Lync Server 2013、エッジサーバーまたはハードウェアロードバランサー仮想 IP (VIP) のエッジ外部インターフェイスの DNS A および AAAA (IPv6 アドレスを使用している場合) および SRV レコード</span><span class="sxs-lookup"><span data-stu-id="164f9-184">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for the Edge external interface of each Lync Server 2013, Edge Server or hardware load balancer virtual IP (VIP) in the perimeter network</span></span>
    
      - <span data-ttu-id="164f9-185">境界ネットワーク内のリバースプロキシサーバーの外部インターフェイスの DNS A および AAAA (IPv6 アドレス指定を使用している場合)、または VIP の外部インターフェイスのレコード</span><span class="sxs-lookup"><span data-stu-id="164f9-185">DNS A and AAAA (if you are using IPv6 addressing) records for the external interface of the reverse proxy server or VIP for a pool of reverse proxy servers in the perimeter network</span></span>

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="164f9-186">スプリットブレイン DNS なしの自動構成</span><span class="sxs-lookup"><span data-stu-id="164f9-186">Automatic Configuration without Split-Brain DNS</span></span>

<span data-ttu-id="164f9-187">内部 DNS ゾーンに\_sipinternaltls が含まれている場合は、スプリットブレイン DNS を使用して内部にサインインする Lync Server 2013 ユーザーが自動構成を利用できます。\_使用中の各 SIP ドメインの tcp SRV レコード。</span><span class="sxs-lookup"><span data-stu-id="164f9-187">Using split-brain DNS, a Lync Server 2013 user that signs in internally can take advantage of automatic configuration if the internal DNS zone contains a \_sipinternaltls.\_tcp SRV record for each SIP domain in use.</span></span> <span data-ttu-id="164f9-188">ただし、スプリットブレイン DNS を使用しない場合は、このセクションで後述する回避策のいずれかが実装されていなければ、Lync を実行しているクライアントの内部自動構成は機能しません。</span><span class="sxs-lookup"><span data-stu-id="164f9-188">However, if you do not use split-brain DNS, internal automatic configuration of clients running Lync will not work unless one of the workarounds described in later in this section is implemented.</span></span> <span data-ttu-id="164f9-189">これは、Lync Server 2013 では、ユーザーの SIP URI が自動構成用に指定されたフロントエンドプールのドメインと一致する必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="164f9-189">This is because Lync Server 2013 requires the user’s SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="164f9-190">これは、以前のバージョンの Communicator の場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="164f9-190">This was also the case with earlier versions of Communicator.</span></span>

<span data-ttu-id="164f9-191">たとえば、2つの SIP ドメインが使用されている場合、次の DNS サービス (SRV) レコードが必要になります。</span><span class="sxs-lookup"><span data-stu-id="164f9-191">For example, if you have two SIP domains in use, the following DNS service (SRV) records would be required:</span></span>

  - <span data-ttu-id="164f9-192">ユーザーが bob@contoso.com としてサインインすると、ユーザーの SIP ドメイン (contoso.com) が自動構成フロントエンドプールのドメインと一致するため、次の SRV レコードが自動構成に対して機能します。</span><span class="sxs-lookup"><span data-stu-id="164f9-192">If a user signs in as bob@contoso.com the following SRV record will work for automatic configuration because the user’s SIP domain (contoso.com) matches the domain of automatic configuration Front End pool):</span></span>
    
     <span data-ttu-id="164f9-193">\_sipinternaltls.\_tcp.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="164f9-193">\_sipinternaltls.\_tcp.contoso.com.</span></span> <span data-ttu-id="164f9-194">SRV 0 0 5061 pool01.contoso.com の86400</span><span class="sxs-lookup"><span data-stu-id="164f9-194">86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>

  - <span data-ttu-id="164f9-195">ユーザーが alice@fabrikam.com としてサインインしている場合、次の DNS SRV レコードは、2番目の SIP ドメインの自動構成に使用できます。</span><span class="sxs-lookup"><span data-stu-id="164f9-195">If a user signs in as alice@fabrikam.com the following DNS SRV record will work for automatic configuration of the second SIP domain.</span></span>
    
     <span data-ttu-id="164f9-196">\_sipinternaltls.\_tcp.fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="164f9-196">\_sipinternaltls.\_tcp.fabrikam.com.</span></span> <span data-ttu-id="164f9-197">SRV 0 0 5061 pool01.fabrikam.com の86400</span><span class="sxs-lookup"><span data-stu-id="164f9-197">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="164f9-198">比較のために、ユーザーが tim@litwareinc.com としてサインインする場合、次の DNS SRV レコードは自動構成では機能しません。クライアントの SIP ドメイン (litwareinc.com) は、プールが存在するドメイン (fabrikam.com) と一致しないためです。</span><span class="sxs-lookup"><span data-stu-id="164f9-198">For comparison, if a user signs in as tim@litwareinc.com the following DNS SRV record will not work for automatic configuration, because the client’s SIP domain (litwareinc.com) does not match the domain that the pool is in (fabrikam.com):</span></span>

 <span data-ttu-id="164f9-199">\_sipinternaltls.\_tcp.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="164f9-199">\_sipinternaltls.\_tcp.litwareinc.com.</span></span> <span data-ttu-id="164f9-200">SRV 0 0 5061 pool01.fabrikam.com の86400</span><span class="sxs-lookup"><span data-stu-id="164f9-200">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="164f9-201">Lync を実行しているクライアントに対して自動構成が必要な場合は、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="164f9-201">If automatic configuration is required for clients running Lync, select one of the following options:</span></span>

  - <span data-ttu-id="164f9-202">**グループポリシーオブジェクト**   はグループポリシーオブジェクト (gpo) を使用して、適切なサーバーの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="164f9-202">**Group Policy Objects**   Use Group Policy objects (GPOs) to populate the correct server values.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="164f9-203">このオプションは自動構成を有効にしませんが、手動構成のプロセスを自動化するので、この方法を使用した場合、自動構成に関連付けられている SRV レコードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="164f9-203">This option does not enable automatic configuration, but it does automate the process of manual configuration, so if this approach is used, the SRV records associated with automatic configuration are not required.</span></span>

    
    </div>

  - <span data-ttu-id="164f9-204">**[内部ゾーン**   の一致] 外部 dns ゾーンに一致する内部 dns (contoso.com など) にゾーンを作成し、自動構成に使用される Lync Server 2013 プールに対応する DNS a および AAAA (IPv6 アドレスを使用している場合) のレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="164f9-204">**Matching internal zone**   Create a zone in the internal DNS that matches the external DNS zone (for example, contoso.com) and create DNS A and AAAA (if you are using IPv6 addressing) records corresponding to the Lync Server 2013 pool used for automatic configuration.</span></span> <span data-ttu-id="164f9-205">たとえば、ユーザーが pool01.contoso.net に所属しているが、bob@contoso.com として Lync にサインインしている場合は、pool01.contoso.com の DNS A および AAAA (IPv6 アドレスを使用する場合) レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="164f9-205">For example, if a user is homed on pool01.contoso.net but signs into Lync as bob@contoso.com, create an internal DNS zone called contoso.com and inside it, create a DNS A and AAAA (if IPv6 addressing is used) record for pool01.contoso.com.</span></span>

  - <span data-ttu-id="164f9-206">**ピンポイント内部ゾーン**   内部 DNS でゾーン全体を作成するのではない場合、自動構成に必要な SRV レコードに対応する pin ポイント (つまり専用) のゾーンを作成し、それらのゾーンに dnscmd を使用して設定することができます。</span><span class="sxs-lookup"><span data-stu-id="164f9-206">**Pin-point internal zone**   If you are creating an entire zone in the internal DNS is not an option, you can create pin-point (that is, dedicated) zones that correspond to the SRV records that are required for automatic configuration, and populate those zones using dnscmd.exe.</span></span> <span data-ttu-id="164f9-207">DNS ユーザーインターフェイスはピンポイントゾーンの作成をサポートしていないため、Dnscmd は必要です。</span><span class="sxs-lookup"><span data-stu-id="164f9-207">Dnscmd.exe is required because the DNS user interface does not support creation of pin-point zones.</span></span> <span data-ttu-id="164f9-208">たとえば、SIP ドメインが contoso.com、2台のフロントエンドサーバーを含む pool01 というフロントエンドプールがある場合は、次のピンポイントゾーンと内部 DNS 内のレコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="164f9-208">For example, if the SIP domain is contoso.com and you have a Front End pool called pool01 that contains two Front End Servers, you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    <span data-ttu-id="164f9-209">環境に2番目の SIP ドメイン (たとえば、fabrikam.com) が含まれている場合は、次のピンポイントゾーンと内部 DNS 内のレコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="164f9-209">If your environment contains a second SIP domain (for example, fabrikam.com), you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> <span data-ttu-id="164f9-210">フロントエンドプールの FQDN は2回表示されますが、2つの異なる IP アドレスがあります。</span><span class="sxs-lookup"><span data-stu-id="164f9-210">The Front End pool FQDN appears twice, but with two different IP addresses.</span></span> <span data-ttu-id="164f9-211">これは、DNS 負荷分散が使用されているためですが、ハードウェア負荷分散が使用されている場合は、フロントエンドプールのエントリが1つだけになります。</span><span class="sxs-lookup"><span data-stu-id="164f9-211">This is because DNS load balancing is used, but if hardware load balancing is used, there would be only a single Front End pool entry.</span></span> <span data-ttu-id="164f9-212">また、フロントエンドプールの FQDN 値は contoso.com の例と fabrikam.com の例で異なりますが、IP アドレスは同じままです。</span><span class="sxs-lookup"><span data-stu-id="164f9-212">Also, the Front End pool FQDN values change between the contoso.com example and the fabrikam.com example, but the IP addresses remain the same.</span></span> <span data-ttu-id="164f9-213">これは、ユーザーがどちらかの SIP ドメインからサインインし、自動構成に同じフロントエンドプールを使用するためです。</span><span class="sxs-lookup"><span data-stu-id="164f9-213">This is because users signing in from either SIP domain, use the same Front End pool for automatic configuration.</span></span>



</div>

<span data-ttu-id="164f9-214">詳細については、「DMTF のブログ記事、「Communicator 自動構成」、および「スプリット[http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707)ブレイン DNS」 () を参照してください。</span><span class="sxs-lookup"><span data-stu-id="164f9-214">For details, see the DMTF blog article, "Communicator Automatic Configuration and Split-Brain DNS," at [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="164f9-215">各ブログのコンテンツおよびその URL は予告なしに変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="164f9-215">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a><span data-ttu-id="164f9-216">障害復旧のためのドメインネームシステム (DNS) の構成</span><span class="sxs-lookup"><span data-stu-id="164f9-216">Configuring the domain name system (DNS) for Disaster Recovery</span></span>

<span data-ttu-id="164f9-217">Lync Server 2013 Web トラフィックを障害回復およびフェールオーバーサイトにリダイレクトするように DNS を構成するには、GeoDNS をサポートする DNS プロバイダーを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="164f9-217">To configure DNS to redirect Lync Server 2013 Web traffic to your disaster recovery and failover sites, you must be using a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="164f9-218">障害復旧をサポートするために Web 用の DNS レコードをセットアップすることができます。これにより、フロントエンドプール全体がダウンした場合でも、Web サービスを使用する機能が続行されます。</span><span class="sxs-lookup"><span data-stu-id="164f9-218">You can set up your DNS records for Web to support disaster recovery, so that features that use Web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="164f9-219">この障害復旧機能は、自動検出 (Lyncdiscover URL)、会議、およびダイヤルインの簡易 Url をサポートします。</span><span class="sxs-lookup"><span data-stu-id="164f9-219">This disaster recovery feature supports the Autodiscover (Lyncdiscover URL), Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="164f9-220">GeoDNS プロバイダーの Web サービスの内部および外部の解決に、追加の DNS ホスト (A および AAAA を使用している場合は AAAA) レコードを定義して構成します。</span><span class="sxs-lookup"><span data-stu-id="164f9-220">You define and configure additional DNS host (A and AAAA if using IPv6) records for internal and external resolution of Web services at your GeoDNS provider.</span></span> <span data-ttu-id="164f9-221">次の詳細は、ラウンドロビン DNS を使用してプロバイダーがサポートしているペアプール、地理的に分散されている、および GeoDNS を想定しているか、または Pool1 をプライマリとして使用するように構成するか、または通信の損失やハードウェアの障害が発生した場合に Pool2 にフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="164f9-221">The following details assume paired pools, geographically dispersed, and GeoDNS supported by your provider with either round-robin DNS, or configured to use Pool1 as primary, and fail over to Pool2 in the event of communications loss or hardware failure.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="164f9-222">GeoDNS レコード (例)</span><span class="sxs-lookup"><span data-stu-id="164f9-222">GeoDNS record (example)</span></span></th>
<th><span data-ttu-id="164f9-223">プールレコード (例)</span><span class="sxs-lookup"><span data-stu-id="164f9-223">Pool records (example)</span></span></th>
<th><span data-ttu-id="164f9-224">CNAME レコード (例)</span><span class="sxs-lookup"><span data-stu-id="164f9-224">CNAME records (example)</span></span></th>
<th><span data-ttu-id="164f9-225">DNS 設定 (1 つのオプションを選択)</span><span class="sxs-lookup"><span data-stu-id="164f9-225">DNS settings (select one option)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="164f9-226">Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-226">Meet-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="164f9-227">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-227">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="164f9-228">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-228">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="164f9-229">Meet.contoso.com alias から Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-229">Meet.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="164f9-230">Meet.contoso.com alias から Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-230">Meet.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="164f9-231">プール間のラウンドロビン</span><span class="sxs-lookup"><span data-stu-id="164f9-231">Round Robin between pools</span></span></p>
<p><span data-ttu-id="164f9-232">プライマリを使用し、障害が発生した場合はセカンダリに接続する</span><span class="sxs-lookup"><span data-stu-id="164f9-232">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="164f9-233">Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-233">Meet-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="164f9-234">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-234">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="164f9-235">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-235">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="164f9-236">Meet.contoso.com alias から Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-236">Meet.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="164f9-237">Meet.contoso.com alias から Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-237">Meet.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="164f9-238">プール間のラウンドロビン</span><span class="sxs-lookup"><span data-stu-id="164f9-238">Round Robin between pools</span></span></p>
<p><span data-ttu-id="164f9-239">プライマリを使用し、障害が発生した場合はセカンダリに接続する</span><span class="sxs-lookup"><span data-stu-id="164f9-239">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="164f9-240">Dialin-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-240">Dialin-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="164f9-241">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-241">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="164f9-242">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-242">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="164f9-243">Dialin.contoso.com alias から Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-243">Dialin.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="164f9-244">Dialin.contoso.com alias から Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-244">Dialin.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="164f9-245">プール間のラウンドロビン</span><span class="sxs-lookup"><span data-stu-id="164f9-245">Round Robin between pools</span></span></p>
<p><span data-ttu-id="164f9-246">プライマリを使用し、障害が発生した場合はセカンダリに接続する</span><span class="sxs-lookup"><span data-stu-id="164f9-246">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="164f9-247">Dialin-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-247">Dialin-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="164f9-248">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-248">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="164f9-249">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-249">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="164f9-250">Dialin.contoso.com alias から Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-250">Dialin.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="164f9-251">Dialin.contoso.com alias から Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-251">Dialin.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="164f9-252">プール間のラウンドロビン</span><span class="sxs-lookup"><span data-stu-id="164f9-252">Round Robin between pools</span></span></p>
<p><span data-ttu-id="164f9-253">プライマリを使用し、障害が発生した場合はセカンダリに接続する</span><span class="sxs-lookup"><span data-stu-id="164f9-253">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="164f9-254">Lyncdiscoverint-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-254">Lyncdiscoverint-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="164f9-255">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-255">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="164f9-256">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-256">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="164f9-257">Lyncdiscoverinternal.contoso.com alias から Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-257">Lyncdiscoverinternal.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="164f9-258">Lyncdiscoverinternal.contoso.com alias から Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-258">Lyncdiscoverinternal.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="164f9-259">プール間のラウンドロビン</span><span class="sxs-lookup"><span data-stu-id="164f9-259">Round Robin between pools</span></span></p>
<p><span data-ttu-id="164f9-260">プライマリを使用し、障害が発生した場合はセカンダリに接続する</span><span class="sxs-lookup"><span data-stu-id="164f9-260">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="164f9-261">Lyncdiscover-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-261">Lyncdiscover-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="164f9-262">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-262">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="164f9-263">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-263">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="164f9-264">Lyncdiscover.contoso.com alias から Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-264">Lyncdiscover.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="164f9-265">Lyncdiscover.contoso.com alias から Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-265">Lyncdiscover.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="164f9-266">プール間のラウンドロビン</span><span class="sxs-lookup"><span data-stu-id="164f9-266">Round Robin between pools</span></span></p>
<p><span data-ttu-id="164f9-267">プライマリを使用し、障害が発生した場合はセカンダリに接続する</span><span class="sxs-lookup"><span data-stu-id="164f9-267">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="164f9-268">Scheduler-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-268">Scheduler-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="164f9-269">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-269">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="164f9-270">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-270">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="164f9-271">Scheduler.contoso.com alias から Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-271">Scheduler.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="164f9-272">Scheduler.contoso.com alias から Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-272">Scheduler.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="164f9-273">プール間のラウンドロビン</span><span class="sxs-lookup"><span data-stu-id="164f9-273">Round Robin between pools</span></span></p>
<p><span data-ttu-id="164f9-274">プライマリを使用し、障害が発生した場合はセカンダリに接続する</span><span class="sxs-lookup"><span data-stu-id="164f9-274">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="164f9-275">Scheduler-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-275">Scheduler-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="164f9-276">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-276">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="164f9-277">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-277">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="164f9-278">Scheduler.contoso.com alias から Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-278">Scheduler.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="164f9-279">Scheduler.contoso.com alias から Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="164f9-279">Scheduler.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="164f9-280">プール間のラウンドロビン</span><span class="sxs-lookup"><span data-stu-id="164f9-280">Round Robin between pools</span></span></p>
<p><span data-ttu-id="164f9-281">プライマリを使用し、障害が発生した場合はセカンダリに接続する</span><span class="sxs-lookup"><span data-stu-id="164f9-281">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a><span data-ttu-id="164f9-282">DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="164f9-282">DNS Load Balancing</span></span>

<span data-ttu-id="164f9-283">DNS 負荷分散は、通常、アプリケーションレベルで実装されます。</span><span class="sxs-lookup"><span data-stu-id="164f9-283">DNS load balancing is typically implemented at the application level.</span></span> <span data-ttu-id="164f9-284">アプリケーション (たとえば、Lync を実行しているクライアント) は、プールの完全修飾ドメイン名 (FQDN) の DNS A および AAAA (IPv6 アドレスが使用されている場合) レコードクエリから返された IP アドレスの1つに接続して、プール内のサーバーへの接続を試行します。</span><span class="sxs-lookup"><span data-stu-id="164f9-284">The application (for example, a client running Lync), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="164f9-285">たとえば、pool01.contoso.com という名前のプールに3つのフロントエンドサーバーがある場合、次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="164f9-285">For example, if there are three front end servers in a pool named pool01.contoso.com, the following will happen:</span></span>

  - <span data-ttu-id="164f9-286">Pool01.contoso.com の Lync クエリ DNS を実行しているクライアント。</span><span class="sxs-lookup"><span data-stu-id="164f9-286">Clients running Lync query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="164f9-287">このクエリは3つの IP アドレスを返し、次のようにキャッシュします (この順序では必ずしも同じではありません)。</span><span class="sxs-lookup"><span data-stu-id="164f9-287">The query returns three IP addresses and caches them as follows (not necessarily in this order):</span></span>
    
    <span data-ttu-id="164f9-288">pool01.contoso.com 192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="164f9-288">pool01.contoso.com      192.168.10.90</span></span>
    
    <span data-ttu-id="164f9-289">pool01.contoso.com 192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="164f9-289">pool01.contoso.com      192.168.10.91</span></span>
    
    <span data-ttu-id="164f9-290">pool01.contoso.com 192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="164f9-290">pool01.contoso.com      192.168.10.92</span></span>

  - <span data-ttu-id="164f9-291">クライアントは、IP アドレスの1つに対して伝送制御プロトコル (TCP) 接続を確立しようとします。</span><span class="sxs-lookup"><span data-stu-id="164f9-291">The client attempts to establish a Transmission Control Protocol (TCP) connection to one of the IP addresses.</span></span> <span data-ttu-id="164f9-292">失敗した場合、クライアントはキャッシュ内の次の IP アドレスを試行します。</span><span class="sxs-lookup"><span data-stu-id="164f9-292">If that fails, the client tries the next IP address in the cache.</span></span>

  - <span data-ttu-id="164f9-293">TCP 接続が成功した場合、クライアントは TLS のネゴシエーションを行い、pool01.contoso.com 上のプライマリレジストラーに接続します。</span><span class="sxs-lookup"><span data-stu-id="164f9-293">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>

  - <span data-ttu-id="164f9-294">接続が正常に行われなかったすべてのエントリをクライアントが試行すると、その時点で Lync Server 2013 を実行しているサーバーが利用できないことがユーザーに通知されます。</span><span class="sxs-lookup"><span data-stu-id="164f9-294">If the client tries all cached entries without a successful connection, the user is notified that no servers running Lync Server 2013 are available at the moment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="164f9-295">Dns ベースの負荷分散は、通常、dns に依存して、プール内のサーバーに対応する異なる順序で IP アドレスを提供することによって負荷分散を参照する dns ラウンドロビン (DNS RR) とは異なります。</span><span class="sxs-lookup"><span data-stu-id="164f9-295">DNS-based load balancing is different from DNS round robin (DNS RR) which typically refers to load balancing by relying on DNS to provide a different order of IP addresses corresponding to the servers in a pool.</span></span> <span data-ttu-id="164f9-296">通常、DNS RR は負荷分散のみを有効にしますが、フェールオーバーを有効にしません。</span><span class="sxs-lookup"><span data-stu-id="164f9-296">Typically DNS RR only enables load distribution, but does not enable failover.</span></span> <span data-ttu-id="164f9-297">たとえば、DNS A および AAAA (IPv6 アドレス指定を使用している場合) によって返された1つの IP アドレスへの接続が失敗すると、接続は失敗します。</span><span class="sxs-lookup"><span data-stu-id="164f9-297">For example, if the connection to the one IP address returned by the DNS A and AAAA (if you are using IPv6 addressing) query fails, the connection fails.</span></span> <span data-ttu-id="164f9-298">そのため、DNS ラウンドロビン自体は、DNS ベースの負荷分散よりも信頼性が低くなります。</span><span class="sxs-lookup"><span data-stu-id="164f9-298">Therefore, DNS round robin by itself is less reliable than DNS-based load balancing.</span></span> <span data-ttu-id="164f9-299">Dns ラウンドロビンを DNS 負荷分散と組み合わせて使用することができます。</span><span class="sxs-lookup"><span data-stu-id="164f9-299">You can use DNS round robin in conjunction with DNS load balancing.</span></span>



</div>

<span data-ttu-id="164f9-300">DNS 負荷分散は次のように使用されます。</span><span class="sxs-lookup"><span data-stu-id="164f9-300">DNS load balancing is used for the following:</span></span>

  - <span data-ttu-id="164f9-301">エッジサーバーへのサーバー間 SIP の負荷分散</span><span class="sxs-lookup"><span data-stu-id="164f9-301">Load balancing server-to-server SIP to the Edge Servers</span></span>

  - <span data-ttu-id="164f9-302">会議の自動応答、応答グループ、コールパークなどの統合コミュニケーションアプリケーションサービス (UCAS) アプリケーションの負荷分散</span><span class="sxs-lookup"><span data-stu-id="164f9-302">Load balancing Unified Communications Application Services (UCAS) applications such as Conferencing Auto Attendant, Response Group, and Call Park</span></span>

  - <span data-ttu-id="164f9-303">アプリケーション ("ドレイン" とも呼ばれる) として UCAS の新しい接続を禁止する</span><span class="sxs-lookup"><span data-stu-id="164f9-303">Preventing new connections to UCAS applications (also known as "draining")</span></span>

  - <span data-ttu-id="164f9-304">クライアントとエッジサーバー間のクライアントとサーバー間のすべてのトラフィックの負荷分散</span><span class="sxs-lookup"><span data-stu-id="164f9-304">Load balancing all client-to-server traffic between clients and Edge Servers</span></span>

<span data-ttu-id="164f9-305">DNS 負荷分散は、次のような場合には使用できません。</span><span class="sxs-lookup"><span data-stu-id="164f9-305">DNS load balancing cannot be used for the following:</span></span>

  - <span data-ttu-id="164f9-306">ディレクターまたはフロントエンドサーバーへのクライアントからサーバーへの web トラフィック</span><span class="sxs-lookup"><span data-stu-id="164f9-306">Client-to-server web traffic to Director or Front End Servers</span></span>

<span data-ttu-id="164f9-307">DNS 負荷分散とフェデレーショントラフィック:</span><span class="sxs-lookup"><span data-stu-id="164f9-307">DNS load balancing and federated traffic:</span></span>

<span data-ttu-id="164f9-308">DNS SRV クエリによって複数の DNS レコードが返される場合、アクセスエッジサービスは常に、最も低い数値の優先度と最大の数値を持つ DNS SRV レコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="164f9-308">If multiple DNS records are returned by a DNS SRV query, the Access Edge service always picks the DNS SRV record with the lowest numeric priority and highest numeric weight.</span></span> <span data-ttu-id="164f9-309">「サービスの場所を指定するための DNS RR」というインターネット技術標準化のタスク強制ドキュメント<http://www.ietf.org/rfc/rfc2782.txt> 。複数の dns srv レコードが定義されている場合、優先度が最初に使用され、次に重みが設定されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="164f9-309">The Internet Engineering Task Force document “A DNS RR for specifying the location of services (DNS SRV)” <http://www.ietf.org/rfc/rfc2782.txt> specifies that if there are multiple DNS SRV records defined, priority is first used, then weight.</span></span> <span data-ttu-id="164f9-310">たとえば、DNS SRV レコード A の重みは20で、優先度は40、DNS SRV レコード B の重みは10、優先度は50です。</span><span class="sxs-lookup"><span data-stu-id="164f9-310">For example DNS SRV record A has a weight of 20 and a priority of 40 and DNS SRV record B has a weight of 10 and priority of 50.</span></span> <span data-ttu-id="164f9-311">優先度40の DNS SRV レコード A が選択されます。</span><span class="sxs-lookup"><span data-stu-id="164f9-311">DNS SRV record A with priority 40 will be selected.</span></span> <span data-ttu-id="164f9-312">DNS SRV レコードの選択には、次のルールが適用されます。</span><span class="sxs-lookup"><span data-stu-id="164f9-312">The following rules apply to DNS SRV record selection:</span></span>

  - <span data-ttu-id="164f9-313">優先度が最初に考慮されます。</span><span class="sxs-lookup"><span data-stu-id="164f9-313">Priority is considered first.</span></span> <span data-ttu-id="164f9-314">クライアントは、DNS SRV レコードによって定義されているターゲットホストに、到達可能な最小番号の優先度を持つ接続を試みる必要があります。</span><span class="sxs-lookup"><span data-stu-id="164f9-314">A client MUST attempt to contact the target host defined by the DNS SRV record with the lowest numbered priority it can reach.</span></span> <span data-ttu-id="164f9-315">同じ優先度を持つターゲットは、weight フィールドで定義された順序で試行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="164f9-315">Targets with the same priority SHOULD be tried in an order defined by the weight field.</span></span>

  - <span data-ttu-id="164f9-316">[重み] フィールドには、同じ優先度を持つエントリの相対的な重みを指定します。</span><span class="sxs-lookup"><span data-stu-id="164f9-316">The weight field specifies a relative weight for entries with the same priority.</span></span> <span data-ttu-id="164f9-317">重みが大きいほど、選択される可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="164f9-317">Larger weights SHOULD be given a proportionately higher probability of being selected.</span></span> <span data-ttu-id="164f9-318">DNS 管理者は、サーバーが選択されていない場合はウエイト0を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="164f9-318">DNS administrators SHOULD use Weight 0 when there isn’t any server selection to do.</span></span> <span data-ttu-id="164f9-319">0より大きい加重値を持つレコードが存在する場合、重み付けが0のレコードは、選択される可能性が非常に低くなります。</span><span class="sxs-lookup"><span data-stu-id="164f9-319">In the presence of records containing weights greater than 0, records with weight 0 should have a very small chance of being selected.</span></span>

<span data-ttu-id="164f9-320">優先度と重みが同じ複数の DNS SRV レコードが返された場合、アクセスエッジサービスは最初に DNS サーバーから受信した SRV レコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="164f9-320">If multiple DNS SRV records with equal priority and weight are returned, the Access Edge service will select the SRV record that was received first from the DNS server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

