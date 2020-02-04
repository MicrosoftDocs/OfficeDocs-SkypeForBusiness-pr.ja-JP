---
title: 'Lync Server 2013: 簡易 URL の DNS 要件'
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
ms.openlocfilehash: bfc827a1cd48bdc6a7a15b8ba54f7ac451d1b352
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="c4578-102">Lync Server 2013 の簡易 URL の DNS 要件</span><span class="sxs-lookup"><span data-stu-id="c4578-102">DNS requirements for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4578-103">_**最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="c4578-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="c4578-104">Lync Server 2013 は、簡単な Url をサポートしており、ユーザーは会議に簡単に参加できます。また、管理者は Lync Server の管理ツールに簡単にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="c4578-104">Lync Server 2013 supports simple URLs, which make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span> <span data-ttu-id="c4578-105">単純な Url の詳細については、「 [Lync Server 2013 での単純な url の計画](lync-server-2013-planning-for-simple-urls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4578-105">For details about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span></span>

<span data-ttu-id="c4578-106">Lync Server では、次の3つの簡単な Url (会議、ダイヤルイン、管理) がサポートされています。会議とダイヤルインの簡単な url を設定する必要があります。管理者の単純な URL は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c4578-106">Lync Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="c4578-107">単純な Url をサポートするために必要なドメインネームシステム (DNS) レコードは、これらの単純な Url を定義した方法と、単純な Url の障害回復をサポートするかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="c4578-107">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span>

<div>

## <a name="simple-url-option-1"></a><span data-ttu-id="c4578-108">単純な URL オプション1</span><span class="sxs-lookup"><span data-stu-id="c4578-108">Simple URL Option 1</span></span>

<span data-ttu-id="c4578-109">オプション1では、各シンプル URL の新しいベース URL を作成します。</span><span class="sxs-lookup"><span data-stu-id="c4578-109">In Option 1, you create a new base URL for each simple URL.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="c4578-110">ユーザーが簡単な URL 会議リンクをクリックすると、DNS A レコードが解決するサーバーによって、開始する適切なクライアントソフトウェアが決定されます。</span><span class="sxs-lookup"><span data-stu-id="c4578-110">When a user clicks a simple URL meeting link, the server that the DNS A record resolves to determines the correct client software to start.</span></span> <span data-ttu-id="c4578-111">クライアントソフトウェアが開始されると、会議がホストされているプールと自動的に通信します。</span><span class="sxs-lookup"><span data-stu-id="c4578-111">After the client software is started, it automatically communicates with the pool where the conference is hosted.</span></span> <span data-ttu-id="c4578-112">こうすることで、ユーザーは、どのサーバーまたはプールでも、DNS A レコードが解決される単純な URL を使用するかに関係なく、会議コンテンツに適したサーバーに転送されます。</span><span class="sxs-lookup"><span data-stu-id="c4578-112">This way, users are directed to the appropriate server for meeting content no matter which server or pool the simple URL DNS A records resolve to.</span></span>



</div>

### <a name="simple-url-option-1"></a><span data-ttu-id="c4578-113">単純な URL オプション1</span><span class="sxs-lookup"><span data-stu-id="c4578-113">Simple URL Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4578-114"><strong>単純な URL</strong></span><span class="sxs-lookup"><span data-stu-id="c4578-114"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="c4578-115"><strong>例</strong></span><span class="sxs-lookup"><span data-stu-id="c4578-115"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4578-116">即時</span><span class="sxs-lookup"><span data-stu-id="c4578-116">Meet</span></span></p></td>
<td><p><span data-ttu-id="c4578-117">https://meet.contoso.com、 https://meet.fabrikam.comなどの場合 (組織の SIP ドメインごとに1つ)</span><span class="sxs-lookup"><span data-stu-id="c4578-117">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4578-118">ダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="c4578-118">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4578-119">同期</span><span class="sxs-lookup"><span data-stu-id="c4578-119">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c4578-120">オプション1を使用する場合は、次のように定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4578-120">If you use Option 1, you must define the following:</span></span>

  - <span data-ttu-id="c4578-121">両方の会議の単純 URL について、DNS A レコードが必要です。このレコードを使用している場合、ディレクターの IP アドレスに対して URL を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4578-121">For each Meet simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed.</span></span> <span data-ttu-id="c4578-122">それ以外の場合は、フロントエンドプールのロードバランサーの IP アドレスに解決される必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4578-122">Otherwise, it should resolve to the IP address of the load balancer of a Front End pool.</span></span> <span data-ttu-id="c4578-123">プールを展開しておらず、Standard Edition サーバーの展開を使用している場合、DNS A レコードは組織内の1つの Standard Edition サーバーの IP アドレスに解決される必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4578-123">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>
    
    <span data-ttu-id="c4578-124">組織内に複数の SIP ドメインがある場合にこのオプションを使用するには、各 SIP ドメインに対して単純な Url を指定する必要があります。また、各会議の単純な URL には DNS A レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="c4578-124">If you have more than one SIP domain in your organization and you use this option, you must create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="c4578-125">たとえば、contoso.com と fabrikam.com の両方がある場合は、とhttps://meet.contoso.com https://meet.fabrikam.comの両方の DNS A レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4578-125">For example, if you have both contoso.com and fabrikam.com, you will create DNS A records for both https://meet.contoso.com and https://meet.fabrikam.com.</span></span>
    
    <span data-ttu-id="c4578-126">または、複数の SIP ドメインがあり、これらの単純な Url の DNS レコードと証明書の要件を最小限に抑える必要がある場合は、このトピックの後半で説明するように、オプション3を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4578-126">Alternatively, if you have multiple SIP domains and you want to minimize the DNS record and certificate requirements for these simple URLs, use Option 3 as described later in this topic.</span></span>

  - <span data-ttu-id="c4578-127">ダイヤルインのシンプルな URL の場合は、DNS A レコードが必要です。これにより、ディレクターが展開されている場合は、その IP アドレスへの URL が解決されます。</span><span class="sxs-lookup"><span data-stu-id="c4578-127">For the Dial-in simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed.</span></span> <span data-ttu-id="c4578-128">それ以外の場合は、フロントエンドプールのロードバランサーの IP アドレスに解決される必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4578-128">Otherwise, it should resolve to the IP address of the load balancer of a Front End pool.</span></span> <span data-ttu-id="c4578-129">プールを展開しておらず、Standard Edition サーバーの展開を使用している場合、DNS A レコードは組織内の1つの Standard Edition サーバーの IP アドレスに解決される必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4578-129">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

  - <span data-ttu-id="c4578-130">管理者の簡易 URL は内部のみです。</span><span class="sxs-lookup"><span data-stu-id="c4578-130">The Admin simple URL is internal only.</span></span> <span data-ttu-id="c4578-131">展開されたディレクターの IP アドレスに URL を解決する DNS A レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="c4578-131">It requires a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed.</span></span> <span data-ttu-id="c4578-132">それ以外の場合は、フロントエンドプールのロードバランサーの IP アドレスに解決される必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4578-132">Otherwise, it should resolve to the IP address of the load balancer of a Front End pool.</span></span> <span data-ttu-id="c4578-133">プールを展開しておらず、Standard Edition サーバーの展開を使用している場合、DNS A レコードは組織内の1つの Standard Edition サーバーの IP アドレスに解決される必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4578-133">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

</div>

<div>

## <a name="simple-url-option-2"></a><span data-ttu-id="c4578-134">単純な URL オプション2</span><span class="sxs-lookup"><span data-stu-id="c4578-134">Simple URL Option 2</span></span>

<span data-ttu-id="c4578-135">オプション2では、[会議]、[ダイヤルイン]、および [管理者の単純な Url] には、lync.contoso.com などの共通のベース URL があります。</span><span class="sxs-lookup"><span data-stu-id="c4578-135">With Option 2, the Meet, Dial-in, and Admin simple URLs all have a common base URL, such as lync.contoso.com.</span></span> <span data-ttu-id="c4578-136">そのため、これらの単純な Url には1つの DNS A レコードのみが必要です。これにより、lync.contoso.com がディレクタープールまたはフロントエンドプールの IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="c4578-136">Therefore, you need only one DNS A record for these simple URLs, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span> <span data-ttu-id="c4578-137">プールを展開しておらず、Standard Edition サーバーの展開を使用している場合、DNS A レコードは組織内の1つの Standard Edition サーバーの IP アドレスに解決される必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4578-137">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

<span data-ttu-id="c4578-138">組織内に複数の SIP ドメインがある場合は、各 SIP ドメインについての単純な Url の会議を作成する必要があります。また、各会議の単純 URL には DNS A レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="c4578-138">Note that if you have more than one SIP domain in your organization, you must still create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="c4578-139">この例では、3つの単純な Url は lync.contoso.com に基づいていますが、fabrikam.com の追加の単純な URL は、別のベース URL で設定されています。</span><span class="sxs-lookup"><span data-stu-id="c4578-139">In this example, while three simple URLs are all based on lync.contoso.com, an additional Meet simple URL for fabrikam.com is set up with a different base URL.</span></span> <span data-ttu-id="c4578-140">この例では、とhttps://lync.contoso.com https://lync.fabrikam.comの両方の DNS A レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4578-140">In this example, you must create DNS A records for both https://lync.contoso.com and https://lync.fabrikam.com.</span></span> <span data-ttu-id="c4578-141">[シンプル URL] オプション3には、複数の SIP ドメインがある場合に、名前付けと DNS A レコードを処理する別の方法が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4578-141">Simple URL Option 3 shows another way to handle naming and DNS A records if you have multiple SIP domains.</span></span>

### <a name="simple-url-option-2"></a><span data-ttu-id="c4578-142">単純な URL オプション2</span><span class="sxs-lookup"><span data-stu-id="c4578-142">Simple URL Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4578-143"><strong>単純な URL</strong></span><span class="sxs-lookup"><span data-stu-id="c4578-143"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="c4578-144"><strong>例</strong></span><span class="sxs-lookup"><span data-stu-id="c4578-144"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4578-145">即時</span><span class="sxs-lookup"><span data-stu-id="c4578-145">Meet</span></span></p></td>
<td><p><span data-ttu-id="c4578-146">https://lync.contoso.com/Meet、 https://lync.fabrikam.com/Meetなどの場合 (組織の SIP ドメインごとに1つ)</span><span class="sxs-lookup"><span data-stu-id="c4578-146">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4578-147">ダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="c4578-147">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4578-148">同期</span><span class="sxs-lookup"><span data-stu-id="c4578-148">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a><span data-ttu-id="c4578-149">単純な URL オプション3</span><span class="sxs-lookup"><span data-stu-id="c4578-149">Simple URL Option 3</span></span>

<span data-ttu-id="c4578-150">オプション3は、多数の SIP ドメインを持っていて、それらのドメインに個別の単純な Url を持たせたいが、DNS レコードと証明書の要件を最小限に抑える必要がある場合に最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c4578-150">Option 3 is most useful if you have many SIP domains, and you want them to have separate simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span> <span data-ttu-id="c4578-151">この例では、lync.contoso.com がディレクタープールまたはフロントエンドプールの IP アドレスに解決される DNS A レコードが1つだけ必要です。</span><span class="sxs-lookup"><span data-stu-id="c4578-151">In this example, you need only one DNS A record, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span>

### <a name="simple-url-option-3"></a><span data-ttu-id="c4578-152">単純な URL オプション3</span><span class="sxs-lookup"><span data-stu-id="c4578-152">Simple URL Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4578-153"><strong>単純な URL</strong></span><span class="sxs-lookup"><span data-stu-id="c4578-153"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="c4578-154"><strong>例</strong></span><span class="sxs-lookup"><span data-stu-id="c4578-154"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4578-155">即時</span><span class="sxs-lookup"><span data-stu-id="c4578-155">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4578-156">ダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="c4578-156">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4578-157">同期</span><span class="sxs-lookup"><span data-stu-id="c4578-157">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="c4578-158">簡単な Url の障害回復オプション</span><span class="sxs-lookup"><span data-stu-id="c4578-158">Disaster Recovery Option for Simple URLs</span></span>

<span data-ttu-id="c4578-159">フロントエンドプールが含まれている複数のサイトがあり、DNS プロバイダーが GeoDNS をサポートしている場合は、フロントエンドプール全体が停止した場合でも、簡単な URL 機能が続行されるように、単純な URL の DNS レコードを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="c4578-159">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="c4578-160">この障害回復機能は、会議とダイヤルインのシンプルな Url をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c4578-160">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="c4578-161">これを構成するには、2つの GeoDNS アドレスを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4578-161">To configure this, create two GeoDNS addresses.</span></span> <span data-ttu-id="c4578-162">各アドレスには2つの DNS A レコードまたは CNAME レコードがあり、これらは1つのプールに対応しているため、それらは共に災害回復目的でペアリングされます。</span><span class="sxs-lookup"><span data-stu-id="c4578-162">Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes.</span></span> <span data-ttu-id="c4578-163">内部アクセスには1つの GeoDNS アドレスが使われ、2つのプールの内部 web FQDN またはロードバランサー IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="c4578-163">One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="c4578-164">その他の GeoDNS アドレスは、外部アクセスに使われ、2つのプールの外部 web FQDN またはロードバランサー IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="c4578-164">The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="c4578-165">次に示すのは、プールの Fqdn を使用した [simple URL の会議] の例です。</span><span class="sxs-lookup"><span data-stu-id="c4578-165">The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span>

   ```
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

<span data-ttu-id="c4578-166">次に、会議の単純な URL (meet.contoso.com など) を2つの GeoDNS アドレスに解決する CNAME レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4578-166">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="c4578-167">ネットワークで<EM>hairpinning</EM> (組織内のトラフィックを含む、すべての単純な url トラフィックをルーティングします) が使用されている場合は、外部 geodns アドレスを構成して、その外部アドレスのみを対象にした単純 url を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="c4578-167">If your network uses <EM>hairpinning</EM> (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>



</div>

<span data-ttu-id="c4578-168">この方法を使用する場合は、ラウンドロビン方式を使って要求を2つのプールに配布するか、主に1つのプール (地理的に近い場所にあるプールなど) に接続して、次の場合にのみ他のプールを使用するように、各 GeoDNS アドレスを構成できます。接続に失敗します。</span><span class="sxs-lookup"><span data-stu-id="c4578-168">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span>

<span data-ttu-id="c4578-169">ダイヤルインの単純な URL に同じ構成を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="c4578-169">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="c4578-170">これを行うには、前の例のように、DNS レコード`dialin`で`meet`の代用として、他のレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4578-170">To do so, create additional records like those in the previous example, substituting `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="c4578-171">管理者の簡易 URL については、このセクションで既に説明した3つのオプションのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="c4578-171">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="c4578-172">この構成が設定されたら、監視アプリケーションを使用して、エラーを監視するために HTTP 監視を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4578-172">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="c4578-173">外部アクセスの場合は、2つのプールの外部 web FQDN またはロードバランサー IP アドレスへの HTTPS GET autodiscovery 要求が成功したことを監視して確認します。</span><span class="sxs-lookup"><span data-stu-id="c4578-173">For external access, monitor to make sure that HTTPS GET autodiscovery requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="c4578-174">たとえば、次の要求には**ACCEPT**ヘッダーが含まれておらず、 **200 OK**を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4578-174">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root

<span data-ttu-id="c4578-175">内部アクセスの場合は、2つのプールの内部 web FQDN またはロードバランサー IP アドレスのポート5061を監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4578-175">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="c4578-176">接続エラーが検出された場合、これらのプールの VIP は、ポート80、443、444を閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4578-176">If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 444.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

