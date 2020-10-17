---
title: 'Lync Server 2013: DNS の概要-自動検出'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc30b787d938825f229f28b10d54907ad26a4d35
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501324"
---
# <a name="dns-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="c3c75-102">DNS の概要-Lync Server 2013 での自動検出</span><span class="sxs-lookup"><span data-stu-id="c3c75-102">DNS summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3c75-103">_**トピックの最終更新日:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="c3c75-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="c3c75-104">自動検出は、HTTP または HTTPS を経由した通信を受け付ける、柔軟なサービスです。</span><span class="sxs-lookup"><span data-stu-id="c3c75-104">Autodiscover is a flexible service in that it will accept communication over HTTP or HTTPS.</span></span> <span data-ttu-id="c3c75-105">これを実現するには、ドメインネームシステム (DNS) と自動検出サービスをホストするサーバーで使用される証明書が正しく構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3c75-105">To accomplish this, the domain name system (DNS) and the certificates used by servers that host the Autodiscover service must be configured correctly.</span></span> <span data-ttu-id="c3c75-106">証明書の要件は [、「証明書の概要-Lync Server 2013 での自動検出](lync-server-2013-certificate-summary-autodiscover.md)」で説明されています。</span><span class="sxs-lookup"><span data-stu-id="c3c75-106">Certificate requirements are covered in [Certificate summary - Autodiscover in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c3c75-107">Lync Server クライアントの DNS 参照ロジックでは、特定の順序で解決されます。</span><span class="sxs-lookup"><span data-stu-id="c3c75-107">DNS lookup logic for the Lync Server clients uses a specific order of resolution.</span></span> <span data-ttu-id="c3c75-108">常に lyncdiscoverinternal を含める必要があります。 &lt;ドメイン &gt; および lyncdiscover。 &lt;&gt;DNS のドメイン。</span><span class="sxs-lookup"><span data-stu-id="c3c75-108">You should always include both the lyncdiscoverinternal.&lt;domain&gt; and the lyncdiscover.&lt;domain&gt; in your DNS.</span></span> <span data-ttu-id="c3c75-109">Lyncdiscoverinternal を除外します。 &lt;ドメインレコードを使用すると &gt; 、内部クライアントは、目的のサービスへの接続を失敗させたり、誤った自動検出応答を受信したりします。</span><span class="sxs-lookup"><span data-stu-id="c3c75-109">Excluding the lyncdiscoverinternal.&lt;domain&gt; record will cause internal clients to fail to connect to the intended services or receive the incorrect Autodiscover response.</span></span>



</div>

### <a name="internal-dns-records"></a><span data-ttu-id="c3c75-110">内部 DNS レコード</span><span class="sxs-lookup"><span data-stu-id="c3c75-110">Internal DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3c75-111">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="c3c75-111">Record type</span></span></th>
<th><span data-ttu-id="c3c75-112">ホスト名</span><span class="sxs-lookup"><span data-stu-id="c3c75-112">Host name</span></span></th>
<th><span data-ttu-id="c3c75-113">解決先</span><span class="sxs-lookup"><span data-stu-id="c3c75-113">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3c75-114">CNAME</span><span class="sxs-lookup"><span data-stu-id="c3c75-114">CNAME</span></span></p></td>
<td><p><span data-ttu-id="c3c75-115">Lyncdiscoverinternal。 &lt;内部ドメイン名&gt;</span><span class="sxs-lookup"><span data-stu-id="c3c75-115">Lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="c3c75-116">ディレクターを所有していない場合は、ディレクタープールの内部 Web サービスの FQDN、またはディレクターを持っていない場合はフロントエンドプール用。</span><span class="sxs-lookup"><span data-stu-id="c3c75-116">Internal Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3c75-117">A (IPv6 の場合は host、AAAA の場合)</span><span class="sxs-lookup"><span data-stu-id="c3c75-117">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="c3c75-118">lyncdiscoverinternal。 &lt;内部ドメイン名&gt;</span><span class="sxs-lookup"><span data-stu-id="c3c75-118">lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="c3c75-119">ディレクタープールがある場合、ディレクタープールの内部 Web サービス IP アドレス (ロードバランサーを使用する場合は仮想 IP (VIP) アドレス) (ディレクターを持っていない場合は、フロントエンドプールがある場合)。</span><span class="sxs-lookup"><span data-stu-id="c3c75-119">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c3c75-120">次の外部 DNS レコードの 1 つを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3c75-120">You need to create one of the following external DNS records:</span></span>

### <a name="external-dns-records"></a><span data-ttu-id="c3c75-121">外部 DNS レコード</span><span class="sxs-lookup"><span data-stu-id="c3c75-121">External DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3c75-122">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="c3c75-122">Record type</span></span></th>
<th><span data-ttu-id="c3c75-123">ホスト名</span><span class="sxs-lookup"><span data-stu-id="c3c75-123">Host name</span></span></th>
<th><span data-ttu-id="c3c75-124">解決先</span><span class="sxs-lookup"><span data-stu-id="c3c75-124">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3c75-125">CNAME</span><span class="sxs-lookup"><span data-stu-id="c3c75-125">CNAME</span></span></p></td>
<td><p><span data-ttu-id="c3c75-126">lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="c3c75-126">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="c3c75-127">ディレクターが存在しない場合は、ディレクタープールの外部 Web サービスの FQDN、またはディレクターを持っていない場合はフロントエンドプール。</span><span class="sxs-lookup"><span data-stu-id="c3c75-127">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3c75-128">A (IPv6 の場合は host、AAAA の場合)</span><span class="sxs-lookup"><span data-stu-id="c3c75-128">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="c3c75-129">lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="c3c75-129">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="c3c75-130">リバースプロキシの外部またはパブリック IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="c3c75-130">External or public IP address of the reverse proxy.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c3c75-131">外部トラフィックはリバース プロキシを経由します。</span><span class="sxs-lookup"><span data-stu-id="c3c75-131">External traffic goes through the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c3c75-132">モバイル デバイスのクライアントでは、異なるドメインからの複数の SSL (Secure Sockets Layer) 証明書がサポートされません。</span><span class="sxs-lookup"><span data-stu-id="c3c75-132">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="c3c75-133">つまり、HTTPS では、異なるドメインへの CNAME のリダイレクトがサポートされません。</span><span class="sxs-lookup"><span data-stu-id="c3c75-133">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="c3c75-134">たとえば、director.contoso.net のアドレスにリダイレクトされる lyncdiscover.contoso.com の DNS CNAME レコードは、HTTPS ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="c3c75-134">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="c3c75-135">このようなトポロジでは、CNAME のリダイレクトが HTTP で解決されるように、モバイル デバイスのクライアントは、最初の要求に対して HTTP を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3c75-135">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="c3c75-136">その後、以降の要求については HTTPS を使用します。</span><span class="sxs-lookup"><span data-stu-id="c3c75-136">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="c3c75-137">このシナリオをサポートするには、ポート 80 (HTTP) の Web 公開ルールを使用して、リバース プロキシを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3c75-137">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="c3c75-138">詳細については、「 <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 でモビリティのリバースプロキシを構成</A>する」の「ポート80の web 公開ルールを作成するには」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3c75-138">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span> <span data-ttu-id="c3c75-139">HTTPS では、同じドメインへの CNAME のリダイレクトはサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c3c75-139">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="c3c75-140">この例では、宛先ドメインの証明書が元のドメインを対象としています。</span><span class="sxs-lookup"><span data-stu-id="c3c75-140">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c3c75-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3c75-141">See Also</span></span>


[<span data-ttu-id="c3c75-142">Lync Server 2013 でのモビリティのリバースプロキシの構成</span><span class="sxs-lookup"><span data-stu-id="c3c75-142">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[<span data-ttu-id="c3c75-143">証明書の概要-Lync Server 2013 での自動検出</span><span class="sxs-lookup"><span data-stu-id="c3c75-143">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

