---
title: 'Lync Server 2013: DNS の概要-自動検出'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64e303ebecc42f03197f6502296c8a2708e97ebf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="e161c-102">DNS 概要-Lync Server 2013 での自動検出</span><span class="sxs-lookup"><span data-stu-id="e161c-102">DNS summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e161c-103">_**最終更新日:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="e161c-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="e161c-104">自動検出は、HTTP または HTTPS 経由での通信を受け付ける、柔軟なサービスです。</span><span class="sxs-lookup"><span data-stu-id="e161c-104">Autodiscover is a flexible service in that it will accept communication over HTTP or HTTPS.</span></span> <span data-ttu-id="e161c-105">これを実現するために、ドメインネームシステム (DNS) と自動検出サービスをホストするサーバーによって使われる証明書が正しく構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e161c-105">To accomplish this, the domain name system (DNS) and the certificates used by servers that host the Autodiscover service must be configured correctly.</span></span> <span data-ttu-id="e161c-106">証明書の要件については[、「証明書の概要-Lync Server 2013 での自動検出](lync-server-2013-certificate-summary-autodiscover.md)」で説明します。</span><span class="sxs-lookup"><span data-stu-id="e161c-106">Certificate requirements are covered in [Certificate summary - Autodiscover in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e161c-107">Lync Server クライアントの DNS 検索ロジックは、特定の解決方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="e161c-107">DNS lookup logic for the Lync Server clients uses a specific order of resolution.</span></span> <span data-ttu-id="e161c-108">常に lyncdiscoverinternal の両方が含まれている必要があります。&lt;ドメイン&gt;と lyncdiscover&lt;DNS&gt;でドメインを選びます。</span><span class="sxs-lookup"><span data-stu-id="e161c-108">You should always include both the lyncdiscoverinternal.&lt;domain&gt; and the lyncdiscover.&lt;domain&gt; in your DNS.</span></span> <span data-ttu-id="e161c-109">Lyncdiscoverinternal を除外します。&lt;ドメイン&gt;レコードを使用すると、内部クライアントは、目的のサービスに接続できないか、または正しくない自動検出応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="e161c-109">Excluding the lyncdiscoverinternal.&lt;domain&gt; record will cause internal clients to fail to connect to the intended services or receive the incorrect Autodiscover response.</span></span>



</div>

### <a name="internal-dns-records"></a><span data-ttu-id="e161c-110">内部 DNS レコード</span><span class="sxs-lookup"><span data-stu-id="e161c-110">Internal DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e161c-111">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="e161c-111">Record type</span></span></th>
<th><span data-ttu-id="e161c-112">ホスト名</span><span class="sxs-lookup"><span data-stu-id="e161c-112">Host name</span></span></th>
<th><span data-ttu-id="e161c-113">解決先</span><span class="sxs-lookup"><span data-stu-id="e161c-113">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e161c-114">CNAME</span><span class="sxs-lookup"><span data-stu-id="e161c-114">CNAME</span></span></p></td>
<td><p><span data-ttu-id="e161c-115">Lyncdiscoverinternal.&lt;内部ドメイン名&gt;</span><span class="sxs-lookup"><span data-stu-id="e161c-115">Lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="e161c-116">ディレクタープールがある場合は、そのディレクタープールの内部 Web サービス FQDN。ディレクターを持っていない場合は、フロントエンドプールにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="e161c-116">Internal Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e161c-117">A (IPv6 の場合は host、AAAA の場合)</span><span class="sxs-lookup"><span data-stu-id="e161c-117">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="e161c-118">lyncdiscoverinternal.&lt;内部ドメイン名&gt;</span><span class="sxs-lookup"><span data-stu-id="e161c-118">lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="e161c-119">ディレクターを持っていない場合は、ディレクタープールの内部 Web サービス IP アドレス (ロードバランサーを使用している場合は仮想 IP (VIP) のアドレス)。ディレクターを持っていない場合は、フロントエンドプールを所有している場合は、このアドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="e161c-119">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e161c-120">次のいずれかの外部 DNS レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e161c-120">You need to create one of the following external DNS records:</span></span>

### <a name="external-dns-records"></a><span data-ttu-id="e161c-121">外部 DNS レコード</span><span class="sxs-lookup"><span data-stu-id="e161c-121">External DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e161c-122">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="e161c-122">Record type</span></span></th>
<th><span data-ttu-id="e161c-123">ホスト名</span><span class="sxs-lookup"><span data-stu-id="e161c-123">Host name</span></span></th>
<th><span data-ttu-id="e161c-124">解決先</span><span class="sxs-lookup"><span data-stu-id="e161c-124">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e161c-125">CNAME</span><span class="sxs-lookup"><span data-stu-id="e161c-125">CNAME</span></span></p></td>
<td><p><span data-ttu-id="e161c-126">lyncdiscover.&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="e161c-126">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="e161c-127">ディレクタープールを所有している場合は、そのディレクタープールの外部 Web サービス FQDN。ディレクターを持っていない場合は、フロントエンドプールに対応する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e161c-127">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e161c-128">A (IPv6 の場合は host、AAAA の場合)</span><span class="sxs-lookup"><span data-stu-id="e161c-128">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="e161c-129">lyncdiscover.&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="e161c-129">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="e161c-130">リバースプロキシの外部またはパブリック IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="e161c-130">External or public IP address of the reverse proxy.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e161c-131">外部トラフィックはリバースプロキシ経由で送信されます。</span><span class="sxs-lookup"><span data-stu-id="e161c-131">External traffic goes through the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e161c-132">モバイルデバイスクライアントは、異なるドメインからの複数の Secure Sockets Layer (SSL) 証明書をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e161c-132">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="e161c-133">したがって、異なるドメインへの CNAME リダイレクションは HTTPS 経由ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="e161c-133">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="e161c-134">たとえば、director.contoso.net のアドレスにリダイレクトされる lyncdiscover.contoso.com の DNS CNAME レコードは HTTPS ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="e161c-134">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="e161c-135">このようなトポロジでは、モバイルデバイスクライアントは、最初の要求に対して HTTP を使う必要があるため、CNAME リダイレクションが HTTP で解決されます。</span><span class="sxs-lookup"><span data-stu-id="e161c-135">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="e161c-136">それ以降の要求では HTTPS を使用します。</span><span class="sxs-lookup"><span data-stu-id="e161c-136">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="e161c-137">このシナリオをサポートするには、ポート 80 (HTTP) 用の web 公開ルールを使用してリバースプロキシを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e161c-137">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="e161c-138">詳細については、「 <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 でモビリティのリバースプロキシを構成</A>する」の「ポート80用の web 公開ルールを作成するには」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e161c-138">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span> <span data-ttu-id="e161c-139">同じドメインへの CNAME リダイレクションは HTTPS 経由でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e161c-139">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="e161c-140">この場合、宛先ドメインの証明書は元のドメインを対象としています。</span><span class="sxs-lookup"><span data-stu-id="e161c-140">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e161c-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="e161c-141">See Also</span></span>


[<span data-ttu-id="e161c-142">Lync Server 2013 での、モビリティに合わせたリバース プロキシの構成</span><span class="sxs-lookup"><span data-stu-id="e161c-142">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[<span data-ttu-id="e161c-143">証明書の概要-Lync Server 2013 での自動検出</span><span class="sxs-lookup"><span data-stu-id="e161c-143">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

