---
title: 'Lync Server 2013: 簡易 Url の DNS 要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for simple URLs
ms:assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425874(v=OCS.15)
ms:contentKeyID: 48183912
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98db338c48bbb764aefe3d5cab4bcba58b2b23c4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501374"
---
# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="163e1-102">Lync Server 2013 の簡易 Url の DNS 要件</span><span class="sxs-lookup"><span data-stu-id="163e1-102">DNS requirements for simple URLs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="163e1-103">_**トピックの最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="163e1-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="163e1-104">Lync Server 2013 は簡易 Url をサポートしており、ユーザーに対して会議に参加しやすくなります。また、管理者にとって Lync Server 管理ツールをより簡単に利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="163e1-104">Lync Server 2013 supports simple URLs, which make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span> <span data-ttu-id="163e1-105">簡易 Url の詳細については、「 [Lync Server 2013 の簡易 url の計画](lync-server-2013-planning-for-simple-urls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="163e1-105">For details about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span></span>

<span data-ttu-id="163e1-106">Lync Server は、次の3つの簡単な Url (会議、ダイヤルイン、および管理者) をサポートします。会議とダイヤルインの簡易 Url を設定する必要があり、管理者の簡易 URL はオプションです。</span><span class="sxs-lookup"><span data-stu-id="163e1-106">Lync Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="163e1-107">簡易 url をサポートするために必要なドメインネームシステム (DNS) レコードは、これらの簡易 Url の定義方法と、簡易 Url の障害復旧をサポートするかどうかによって決まります。</span><span class="sxs-lookup"><span data-stu-id="163e1-107">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span>

<div>

## <a name="simple-url-option-1"></a><span data-ttu-id="163e1-108">簡易 URL のオプション 1</span><span class="sxs-lookup"><span data-stu-id="163e1-108">Simple URL Option 1</span></span>

<span data-ttu-id="163e1-109">オプション 1 では、簡易 URL ごとに新しいベース URL を作成します。</span><span class="sxs-lookup"><span data-stu-id="163e1-109">In Option 1, you create a new base URL for each simple URL.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="163e1-p103">簡易 URL の会議リンクをクリックすると、DNS A レコードによってサーバーが解決され、起動する適切なクライアント ソフトウェアが決定されます。 クライアント ソフトウェアは、起動後に会議がホストされているプールと自動的に通信します。 こうして、DNS A レコードによってどのサーバーまたはプールの簡易 URL に解決されるかに関係なく、適切な会議コンテンツのサーバーに到達できます。</span><span class="sxs-lookup"><span data-stu-id="163e1-p103">When a user clicks a simple URL meeting link, the server that the DNS A record resolves to determines the correct client software to start. After the client software is started, it automatically communicates with the pool where the conference is hosted. This way, users are directed to the appropriate server for meeting content no matter which server or pool the simple URL DNS A records resolve to.</span></span>



</div>

### <a name="simple-url-option-1"></a><span data-ttu-id="163e1-113">簡易 URL のオプション 1</span><span class="sxs-lookup"><span data-stu-id="163e1-113">Simple URL Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="163e1-114"><strong>簡易 URL</strong></span><span class="sxs-lookup"><span data-stu-id="163e1-114"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="163e1-115"><strong>例</strong></span><span class="sxs-lookup"><span data-stu-id="163e1-115"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="163e1-116">満たせ</span><span class="sxs-lookup"><span data-stu-id="163e1-116">Meet</span></span></p></td>
<td><p><span data-ttu-id="163e1-117">https://meet.contoso.com、 https://meet.fabrikam.com など (組織内の SIP ドメインごとに1つずつ)</span><span class="sxs-lookup"><span data-stu-id="163e1-117">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="163e1-118">ダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="163e1-118">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="163e1-119">管理者</span><span class="sxs-lookup"><span data-stu-id="163e1-119">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="163e1-120">オプション 1 を使用する場合は、次の内容を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="163e1-120">If you use Option 1, you must define the following:</span></span>

  - <span data-ttu-id="163e1-p104">簡単な会議 URL ごとに、URL をディレクターの IP アドレスに解決する DNS A レコードが必要です (ディレクターが展開されている場合)。 ディレクターが展開されていない場合は、フロントエンド プールのロード バランサーの IP アドレスに解決されます。 プールを展開しておらず、Standard Edition サーバーの展開を使用している場合、DNS A レコードは組織内の 1 台の Standard Edition サーバーの IP アドレスに解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="163e1-p104">For each Meet simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>
    
    <span data-ttu-id="163e1-124">組織内に複数の SIP ドメインがあり、このオプションを使用する場合は、各 SIP ドメインに対する会議の簡易 Url を作成する必要があります。また、各会議の簡単な URL の DNS A レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="163e1-124">If you have more than one SIP domain in your organization and you use this option, you must create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="163e1-125">たとえば、contoso.com と fabrikam.com の両方がある場合は、との両方の DNS A レコードを作成し https://meet.contoso.com https://meet.fabrikam.com ます。</span><span class="sxs-lookup"><span data-stu-id="163e1-125">For example, if you have both contoso.com and fabrikam.com, you will create DNS A records for both https://meet.contoso.com and https://meet.fabrikam.com.</span></span>
    
    <span data-ttu-id="163e1-126">また、複数の SIP ドメインがあり、これらの簡易 URL の DNS レコードおよび証明書の要件を最小限にする場合は、後で説明するオプション 3 を使用します。</span><span class="sxs-lookup"><span data-stu-id="163e1-126">Alternatively, if you have multiple SIP domains and you want to minimize the DNS record and certificate requirements for these simple URLs, use Option 3 as described later in this topic.</span></span>

  - <span data-ttu-id="163e1-p106">簡単なダイヤルイン URL の場合は、URL をディレクターの IP アドレスに解決する DNS A レコードが必要です (ディレクターが展開されている場合)。ディレクターが展開されていない場合は、フロントエンド プールのロード バランサーの IP アドレスに解決されます。プールを展開しておらず、Standard Edition サーバーの展開を使用している場合、DNS A レコードは組織内の 1 台の Standard Edition サーバーの IP アドレスに解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="163e1-p106">For the Dial-in simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

  - <span data-ttu-id="163e1-p107">簡単な管理 URL は、内部のみで使用します。 簡単な管理 URL では、URL をディレクターの IP アドレスに解決する DNS A レコードが必要です (ディレクターが展開されている場合)。ディレクターが展開されていない場合は、フロントエンド プールのロード バランサーの IP アドレスに解決されます。プールを展開しておらず、Standard Edition サーバーの展開を使用している場合、DNS A レコードは組織内の 1 台の Standard Edition サーバーの IP アドレスに解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="163e1-p107">The Admin simple URL is internal only. It requires a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

</div>

<div>

## <a name="simple-url-option-2"></a><span data-ttu-id="163e1-134">簡易 URL のオプション 2</span><span class="sxs-lookup"><span data-stu-id="163e1-134">Simple URL Option 2</span></span>

<span data-ttu-id="163e1-p108">オプション 2 では、会議、ダイヤルイン、および管理用の簡易 URL のベース URL がすべて共通です (lync.contoso.com など)。したがって、これらの簡易 URL に必要な DNS A レコードは 1 つだけです。この DNS A レコードによって、lync.contoso.com をディレクター プールまたはフロントエンド プールの IP アドレスに解決します。プールを展開しておらず、Standard Edition サーバーの展開を使用している場合、DNS A レコードは組織内の 1 台の Standard Edition サーバーの IP アドレスに解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="163e1-p108">With Option 2, the Meet, Dial-in, and Admin simple URLs all have a common base URL, such as lync.contoso.com. Therefore, you need only one DNS A record for these simple URLs, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

<span data-ttu-id="163e1-138">組織内に複数の SIP ドメインがある状態でも、SIP ドメインごとに簡単な会議 URL を作成する必要があり、簡単な会議 URL ごとに DNS A レコードが必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="163e1-138">Note that if you have more than one SIP domain in your organization, you must still create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="163e1-139">この例では、3 つの簡易 URL がすべて lync.contoso.com に基づいていますが、別のベース URL を使用して fabrikam.com の簡単な会議 URL を追加で設定します。</span><span class="sxs-lookup"><span data-stu-id="163e1-139">In this example, while three simple URLs are all based on lync.contoso.com, an additional Meet simple URL for fabrikam.com is set up with a different base URL.</span></span> <span data-ttu-id="163e1-140">この例では、との両方の DNS A レコードを作成する必要があり https://lync.contoso.com https://lync.fabrikam.com ます。</span><span class="sxs-lookup"><span data-stu-id="163e1-140">In this example, you must create DNS A records for both https://lync.contoso.com and https://lync.fabrikam.com.</span></span> <span data-ttu-id="163e1-141">簡易 URL のオプション 3 では、複数の SIP ドメインがある場合の、名前付けと DNS A レコードの処理方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="163e1-141">Simple URL Option 3 shows another way to handle naming and DNS A records if you have multiple SIP domains.</span></span>

### <a name="simple-url-option-2"></a><span data-ttu-id="163e1-142">簡易 URL のオプション 2</span><span class="sxs-lookup"><span data-stu-id="163e1-142">Simple URL Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="163e1-143"><strong>簡易 URL</strong></span><span class="sxs-lookup"><span data-stu-id="163e1-143"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="163e1-144"><strong>例</strong></span><span class="sxs-lookup"><span data-stu-id="163e1-144"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="163e1-145">満たせ</span><span class="sxs-lookup"><span data-stu-id="163e1-145">Meet</span></span></p></td>
<td><p><span data-ttu-id="163e1-146">https://lync.contoso.com/Meet、 https://lync.fabrikam.com/Meet など (組織内の SIP ドメインごとに1つずつ)</span><span class="sxs-lookup"><span data-stu-id="163e1-146">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="163e1-147">ダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="163e1-147">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="163e1-148">管理者</span><span class="sxs-lookup"><span data-stu-id="163e1-148">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a><span data-ttu-id="163e1-149">簡易 URL のオプション 3</span><span class="sxs-lookup"><span data-stu-id="163e1-149">Simple URL Option 3</span></span>

<span data-ttu-id="163e1-p110">多くの SIP ドメインがあり、SIP ドメインの簡易 URL を別々にして、これらの簡易 URL の DNS レコードおよび証明書の要件を最小限に抑える場合は、オプション 3 が最も便利です。 この例では、必要な DNS A レコードは 1 つだけです。この DNS A レコードにより、lync.contoso.com をディレクター プールまたはフロントエンド プールの IP アドレスに解決します。</span><span class="sxs-lookup"><span data-stu-id="163e1-p110">Option 3 is most useful if you have many SIP domains, and you want them to have separate simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs. In this example, you need only one DNS A record, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span>

### <a name="simple-url-option-3"></a><span data-ttu-id="163e1-152">簡易 URL のオプション 3</span><span class="sxs-lookup"><span data-stu-id="163e1-152">Simple URL Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="163e1-153"><strong>簡易 URL</strong></span><span class="sxs-lookup"><span data-stu-id="163e1-153"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="163e1-154"><strong>例</strong></span><span class="sxs-lookup"><span data-stu-id="163e1-154"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="163e1-155">満たせ</span><span class="sxs-lookup"><span data-stu-id="163e1-155">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="163e1-156">ダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="163e1-156">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="163e1-157">管理者</span><span class="sxs-lookup"><span data-stu-id="163e1-157">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="163e1-158">簡易 URL の障害復旧オプション</span><span class="sxs-lookup"><span data-stu-id="163e1-158">Disaster Recovery Option for Simple URLs</span></span>

<span data-ttu-id="163e1-159">フロントエンドプールを含む複数のサイトがあり、DNS プロバイダーが GeoDNS をサポートしている場合は、フロントエンドプール全体がダウンしても簡単な URL 機能が続行されるように、障害復旧をサポートするための簡単な URL の DNS レコードを設定できます。</span><span class="sxs-lookup"><span data-stu-id="163e1-159">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="163e1-160">この障害復旧機能は、会議とダイヤルインの簡易 Url をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="163e1-160">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="163e1-p112">これを構成するには、2 つの GeoDNS アドレスを作成します。各アドレスは、障害の復旧目的でペアになった 2 つのプールに解決される、2 つの DNS A または CNAME レコードを持っています。1 つの GeoDNS アドレスは内部アクセスに使用され、2 つのプールのロード バランサー IP アドレス、または内部 Web FQDN に解決されます。もう一つの GeoDNS アドレスは外部アクセスに使用され、2 つのプールのロード バランサー IP アドレス、または外部 Web FQDN に解決されます。以下は、プールの FQDN を使用した、会議簡易 URL の例です。</span><span class="sxs-lookup"><span data-stu-id="163e1-p112">To configure this, create two GeoDNS addresses. Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes. One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools. The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools. The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span>

   ```console
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```console
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

<span data-ttu-id="163e1-166">次に、(meet.contoso.com のような) 会議簡易 URL を 2 つの GeoDNS アドレスに解決する CNAME レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="163e1-166">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="163e1-167">ネットワークが<EM></EM>ヘアピン (組織内部からのトラフィックを含め、すべての簡易 URL トラフィックを外部リンク経由でルーティングすること) を使用している場合は、外部 GeoDNS アドレスを構成して、その外部アドレスのみに会議簡易 URL を解決できます。</span><span class="sxs-lookup"><span data-stu-id="163e1-167">If your network uses <EM>hairpinning</EM> (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>



</div>

<span data-ttu-id="163e1-168">この方式を使用するとき、2 つのプールに要求を配布するラウンドロビン方式か、または (地理的に近いプールなど) 1 つのプールに主に接続し、もう 1 つのプールは接続障害の場合にのみ使用するように、各 GeoDNS アドレスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="163e1-168">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span>

<span data-ttu-id="163e1-169">ダイヤルイン簡易 URL でも同じ構成をセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="163e1-169">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="163e1-170">これを行うには、前の例のようなレコードを作成し、 `dialin` `meet` DNS レコードでをに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="163e1-170">To do so, create additional records like those in the previous example, substituting `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="163e1-171">管理簡易 URL では、このセクションで以前に示した 3 つのオプションのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="163e1-171">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="163e1-172">この構成をセットアップした後に、監視アプリケーションを使用して、障害の監視用に HTTP 監視をセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="163e1-172">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="163e1-173">外部アクセスの場合、監視して、外部 web FQDN または2つのプールのロードバランサー IP アドレスに対する HTTPS の自動検出要求が成功していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="163e1-173">For external access, monitor to make sure that HTTPS GET autodiscovery requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="163e1-174">たとえば、以下の要求では、**ACCEPT** ヘッダーが含まれないようにし、**200 OK** を戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="163e1-174">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

```console
    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

<span data-ttu-id="163e1-p115">内部アクセスでは、内部 Web FQDN のポート 5061、または 2 つのプール用のロード バランサー IP アドレスを監視する必要があります。接続問題が検出された場合、これらのプールの VIP は、ポート 80、443、および 444 を閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="163e1-p115">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools. If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 444.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

