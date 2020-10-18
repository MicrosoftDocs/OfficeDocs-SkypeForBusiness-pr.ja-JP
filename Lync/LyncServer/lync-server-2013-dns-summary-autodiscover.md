---
title: 'Lync Server 2013: DNS の概要-自動検出'
description: 'Lync Server 2013: DNS の概要-自動検出。'
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
ms.openlocfilehash: eef9bd6a2489561145718c7bbf2f710ab0b1f248
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574283"
---
# <a name="dns-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="7ebee-103">DNS の概要-Lync Server 2013 での自動検出</span><span class="sxs-lookup"><span data-stu-id="7ebee-103">DNS summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ebee-104">_**トピックの最終更新日:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="7ebee-104">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="7ebee-105">自動検出は、HTTP または HTTPS を経由した通信を受け付ける、柔軟なサービスです。</span><span class="sxs-lookup"><span data-stu-id="7ebee-105">Autodiscover is a flexible service in that it will accept communication over HTTP or HTTPS.</span></span> <span data-ttu-id="7ebee-106">これを実現するには、ドメインネームシステム (DNS) と自動検出サービスをホストするサーバーで使用される証明書が正しく構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ebee-106">To accomplish this, the domain name system (DNS) and the certificates used by servers that host the Autodiscover service must be configured correctly.</span></span> <span data-ttu-id="7ebee-107">証明書の要件は [、「証明書の概要-Lync Server 2013 での自動検出](lync-server-2013-certificate-summary-autodiscover.md)」で説明されています。</span><span class="sxs-lookup"><span data-stu-id="7ebee-107">Certificate requirements are covered in [Certificate summary - Autodiscover in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7ebee-108">Lync Server クライアントの DNS 参照ロジックでは、特定の順序で解決されます。</span><span class="sxs-lookup"><span data-stu-id="7ebee-108">DNS lookup logic for the Lync Server clients uses a specific order of resolution.</span></span> <span data-ttu-id="7ebee-109">常に lyncdiscoverinternal を含める必要があります。 &lt;ドメイン &gt; および lyncdiscover。 &lt;&gt;DNS のドメイン。</span><span class="sxs-lookup"><span data-stu-id="7ebee-109">You should always include both the lyncdiscoverinternal.&lt;domain&gt; and the lyncdiscover.&lt;domain&gt; in your DNS.</span></span> <span data-ttu-id="7ebee-110">Lyncdiscoverinternal を除外します。 &lt;ドメインレコードを使用すると &gt; 、内部クライアントは、目的のサービスへの接続を失敗させたり、誤った自動検出応答を受信したりします。</span><span class="sxs-lookup"><span data-stu-id="7ebee-110">Excluding the lyncdiscoverinternal.&lt;domain&gt; record will cause internal clients to fail to connect to the intended services or receive the incorrect Autodiscover response.</span></span>



</div>

### <a name="internal-dns-records"></a><span data-ttu-id="7ebee-111">内部 DNS レコード</span><span class="sxs-lookup"><span data-stu-id="7ebee-111">Internal DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7ebee-112">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="7ebee-112">Record type</span></span></th>
<th><span data-ttu-id="7ebee-113">ホスト名</span><span class="sxs-lookup"><span data-stu-id="7ebee-113">Host name</span></span></th>
<th><span data-ttu-id="7ebee-114">解決先</span><span class="sxs-lookup"><span data-stu-id="7ebee-114">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ebee-115">CNAME</span><span class="sxs-lookup"><span data-stu-id="7ebee-115">CNAME</span></span></p></td>
<td><p><span data-ttu-id="7ebee-116">Lyncdiscoverinternal。 &lt;内部ドメイン名&gt;</span><span class="sxs-lookup"><span data-stu-id="7ebee-116">Lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="7ebee-117">ディレクターを所有していない場合は、ディレクタープールの内部 Web サービスの FQDN、またはディレクターを持っていない場合はフロントエンドプール用。</span><span class="sxs-lookup"><span data-stu-id="7ebee-117">Internal Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ebee-118">A (IPv6 の場合は host、AAAA の場合)</span><span class="sxs-lookup"><span data-stu-id="7ebee-118">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="7ebee-119">lyncdiscoverinternal。 &lt;内部ドメイン名&gt;</span><span class="sxs-lookup"><span data-stu-id="7ebee-119">lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="7ebee-120">ディレクタープールがある場合、ディレクタープールの内部 Web サービス IP アドレス (ロードバランサーを使用する場合は仮想 IP (VIP) アドレス) (ディレクターを持っていない場合は、フロントエンドプールがある場合)。</span><span class="sxs-lookup"><span data-stu-id="7ebee-120">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7ebee-121">次の外部 DNS レコードの 1 つを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ebee-121">You need to create one of the following external DNS records:</span></span>

### <a name="external-dns-records"></a><span data-ttu-id="7ebee-122">外部 DNS レコード</span><span class="sxs-lookup"><span data-stu-id="7ebee-122">External DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7ebee-123">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="7ebee-123">Record type</span></span></th>
<th><span data-ttu-id="7ebee-124">ホスト名</span><span class="sxs-lookup"><span data-stu-id="7ebee-124">Host name</span></span></th>
<th><span data-ttu-id="7ebee-125">解決先</span><span class="sxs-lookup"><span data-stu-id="7ebee-125">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ebee-126">CNAME</span><span class="sxs-lookup"><span data-stu-id="7ebee-126">CNAME</span></span></p></td>
<td><p><span data-ttu-id="7ebee-127">lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7ebee-127">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="7ebee-128">ディレクターが存在しない場合は、ディレクタープールの外部 Web サービスの FQDN、またはディレクターを持っていない場合はフロントエンドプール。</span><span class="sxs-lookup"><span data-stu-id="7ebee-128">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ebee-129">A (IPv6 の場合は host、AAAA の場合)</span><span class="sxs-lookup"><span data-stu-id="7ebee-129">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="7ebee-130">lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7ebee-130">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="7ebee-131">リバースプロキシの外部またはパブリック IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="7ebee-131">External or public IP address of the reverse proxy.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="7ebee-132">外部トラフィックはリバース プロキシを経由します。</span><span class="sxs-lookup"><span data-stu-id="7ebee-132">External traffic goes through the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="7ebee-133">モバイル デバイスのクライアントでは、異なるドメインからの複数の SSL (Secure Sockets Layer) 証明書がサポートされません。</span><span class="sxs-lookup"><span data-stu-id="7ebee-133">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="7ebee-134">つまり、HTTPS では、異なるドメインへの CNAME のリダイレクトがサポートされません。</span><span class="sxs-lookup"><span data-stu-id="7ebee-134">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="7ebee-135">たとえば、director.contoso.net のアドレスにリダイレクトされる lyncdiscover.contoso.com の DNS CNAME レコードは、HTTPS ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="7ebee-135">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="7ebee-136">このようなトポロジでは、CNAME のリダイレクトが HTTP で解決されるように、モバイル デバイスのクライアントは、最初の要求に対して HTTP を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ebee-136">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="7ebee-137">その後、以降の要求については HTTPS を使用します。</span><span class="sxs-lookup"><span data-stu-id="7ebee-137">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="7ebee-138">このシナリオをサポートするには、ポート 80 (HTTP) の Web 公開ルールを使用して、リバース プロキシを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ebee-138">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="7ebee-139">詳細については、「 <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 でモビリティのリバースプロキシを構成</A>する」の「ポート80の web 公開ルールを作成するには」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ebee-139">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span> <span data-ttu-id="7ebee-140">HTTPS では、同じドメインへの CNAME のリダイレクトはサポートされます。</span><span class="sxs-lookup"><span data-stu-id="7ebee-140">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="7ebee-141">この例では、宛先ドメインの証明書が元のドメインを対象としています。</span><span class="sxs-lookup"><span data-stu-id="7ebee-141">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7ebee-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ebee-142">See Also</span></span>


[<span data-ttu-id="7ebee-143">Lync Server 2013 でのモビリティのリバースプロキシの構成</span><span class="sxs-lookup"><span data-stu-id="7ebee-143">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[<span data-ttu-id="7ebee-144">証明書の概要-Lync Server 2013 での自動検出</span><span class="sxs-lookup"><span data-stu-id="7ebee-144">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

