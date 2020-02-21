---
title: 'Lync Server 2013: フロントエンドプールの DNS 要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ae56cdf07ae76ca0499050574793421864de818
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a><span data-ttu-id="1170b-102">Lync Server 2013 のフロントエンドプールの DNS 要件</span><span class="sxs-lookup"><span data-stu-id="1170b-102">DNS requirements for Front End pools in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1170b-103">_**トピックの最終更新日:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="1170b-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="1170b-104">ここでは、フロント エンド プールの展開に必要なドメイン ネーム システム (DNS) レコードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1170b-104">This section describes the Domain Name System (DNS) records that are required for deployment of Front End pools.</span></span>

<div>

## <a name="dns-records-for-front-end-pools"></a><span data-ttu-id="1170b-105">フロント エンド プールの DNS レコード</span><span class="sxs-lookup"><span data-stu-id="1170b-105">DNS Records for Front End Pools</span></span>

<span data-ttu-id="1170b-106">次の表は、Lync Server 2013 フロントエンドプール展開の DNS 要件を示しています。</span><span class="sxs-lookup"><span data-stu-id="1170b-106">The following table specifies DNS requirements for a Lync Server 2013 Front End pool deployment.</span></span>

### <a name="dns-requirements-for-a-front-end-pool"></a><span data-ttu-id="1170b-107">フロント エンド プールでの DNS の要件</span><span class="sxs-lookup"><span data-stu-id="1170b-107">DNS Requirements for a Front End Pool</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1170b-108">展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="1170b-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="1170b-109">DNS 要件</span><span class="sxs-lookup"><span data-stu-id="1170b-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1170b-110">複数のフロント エンド サーバーと 1 つのロード バランサー機器で構成されるフロント エンド プール (DNS 負荷分散もそのプールで展開されているかどうかは無関係)</span><span class="sxs-lookup"><span data-stu-id="1170b-110">Front End pool with multiple Front End Servers and a hardware load balancer (whether or not DNS load balancing is also deployed on that pool)</span></span></p></td>
<td><p><span data-ttu-id="1170b-111">DNS 負荷分散とロード バランサー機器の両方を使用する場合、ホスト (A) レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="1170b-111">When using both DNS load balancing and a hardware load balancer, you need to Host (A) records.</span></span> <span data-ttu-id="1170b-112">DNS 負荷分散用にフロント エンド プールの完全修飾ドメイン名 (FQDN) を解決する内部 A レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="1170b-112">Create an internal A record that resolves the fully qualified domain name (FQDN) of the Front End pool for DNS load balancing.</span></span> <span data-ttu-id="1170b-113">ロード バランサーの仮想 IP (VIP) アドレスに解決する、内部 Web サービス用の内部ホスト (A) レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="1170b-113">Create an internal host (A) record for the internal Web services to the virtual IP (VIP) address of the load balancer.</span></span> <span data-ttu-id="1170b-114">トポロジビルダーで定義されているように、内部 Web サービスの名前を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1170b-114">You must use the internal Web services name as defined in Topology Builder.</span></span></p>
<p><span data-ttu-id="1170b-115">たとえば、DNS 負荷分散とハードウェア負荷分散の両方を使用する場合は、DNS 負荷分散用のプール内の各フロントエンドサーバー用の A レコードと、ロードバランサー機器の仮想 IP を指す内部 Web サービスの A レコードが存在します。:</span><span class="sxs-lookup"><span data-stu-id="1170b-115">For example, if you use both DNS load balancing and hardware load balancing, you would have an A record for each Front End Server in a pool for DNS load balancing, and an A record for the internal Web services pointing to the virtual IP of the hardware load balancer:</span></span></p>
<ul>
<li><p><span data-ttu-id="1170b-116">DNS 負荷分散:   Pool01.contoso.net   プールの IP アドレス   10.10.10.5</span><span class="sxs-lookup"><span data-stu-id="1170b-116">DNS load balancing:   Pool01.contoso.net   IP Address of pool   10.10.10.5</span></span></p>
<div>

> [!WARNING]  
> <span data-ttu-id="1170b-117">各フロントエンドサーバーには、個別の A レコードもあります。</span><span class="sxs-lookup"><span data-stu-id="1170b-117">Each Front End Server will also have a distinct A record:</span></span>


</div>
<ol>
<li><p><span data-ttu-id="1170b-118">FE01.contoso.net 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="1170b-118">FE01.contoso.net    10.10.10.1</span></span></p></li>
<li><p><span data-ttu-id="1170b-119">FE02.contoso.net 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="1170b-119">FE02.contoso.net    10.10.10.2</span></span></p></li>
<li><p><span data-ttu-id="1170b-120">FE03.contoso.net 10.10.10.3</span><span class="sxs-lookup"><span data-stu-id="1170b-120">FE03.contoso.net    10.10.10.3</span></span></p></li>
<li><p><span data-ttu-id="1170b-121">FE04.contoso.net 10.10.10.4</span><span class="sxs-lookup"><span data-stu-id="1170b-121">FE04.contoso.net    10.10.10.4</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="1170b-122">ハードウェア負荷分散:   WebInternal.contoso.net   HLB VIP の IP アドレス   192.168.10.5</span><span class="sxs-lookup"><span data-stu-id="1170b-122">Hardware load balancing:   WebInternal.contoso.net   IP Address of HLB VIP   192.168.10.5</span></span></p></li>
</ul>
<p><span data-ttu-id="1170b-p102">HTTP/HTTPS トラフィックを除くすべてのトラフィックで Pool01.contoso.net レコードが使用されます。HTTP/HTTPS トラフィックでは、定義済みの内部 Web サービス アドレスの 192.168.10.5 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="1170b-p102">All traffic except for HTTP/HTTPS traffic will use the Pool01.contoso.net record. HTTP/HTTPS traffic will use the defined internal Web services address of 192.168.10.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1170b-125">DNS 負荷分散が展開されているフロント エンド プール</span><span class="sxs-lookup"><span data-stu-id="1170b-125">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="1170b-p103">プールの FQDN をそのプールの各サーバーの IP アドレスに解決する内部 A レコードのセット。プール内のサーバーごとに A レコードが 1 つ必要です。</span><span class="sxs-lookup"><span data-stu-id="1170b-p103">A set of internal A records that resolve the FQDN of the pool to the IP address of each server in the pool. There must one A record for each server in the pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1170b-128">DNS 負荷分散が展開されているフロント エンド プール</span><span class="sxs-lookup"><span data-stu-id="1170b-128">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="1170b-129">プール内の各サーバーの FQDN をそのサーバーの IP アドレスに解決する内部 A レコードのセット。</span><span class="sxs-lookup"><span data-stu-id="1170b-129">A set of internal A records that resolve the FQDN of each server in the pool to the IP address of that server.</span></span> <span data-ttu-id="1170b-130">詳細については、「計画」のドキュメントの「 <a href="lync-server-2013-dns-load-balancing.md">DNS load balancing In Lync Server 2013</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1170b-130">For details, see <a href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1170b-131">1 つのフロント エンド サーバーおよび専用のバックエンド データベースを備え、ロード バランサーは備えていないフロント エンド プール</span><span class="sxs-lookup"><span data-stu-id="1170b-131">Front End pool with a single Front End Server and a dedicated back-end database but no load balancer</span></span></p></td>
<td><p><span data-ttu-id="1170b-132">フロント エンド プールの FQDN を 1 つの Enterprise Edition フロント エンド サーバーの IP アドレスに解決する内部 A レコード。</span><span class="sxs-lookup"><span data-stu-id="1170b-132">An internal A record that resolves the FQDN of the Front End pool to the IP address of the single Enterprise Edition Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1170b-133">自動クライアント サインイン</span><span class="sxs-lookup"><span data-stu-id="1170b-133">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="1170b-134">サポートされている各 SIP ドメインについて、_sipinternaltls の SRV レコード。 _tcp。&lt;サインイン&gt;のためのクライアント要求を認証およびリダイレクトするフロントエンドプールの FQDN にマップされる、ドメインオーバーポート5061。</span><span class="sxs-lookup"><span data-stu-id="1170b-134">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Front End pool that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="1170b-135">詳細については、「 <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013 での自動クライアントサインインの DNS 要件</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1170b-135">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1170b-136">統合コミュニケーション (UC) デバイスによるデバイス更新 Web サービスの検出</span><span class="sxs-lookup"><span data-stu-id="1170b-136">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="1170b-137">Ucupdates-r2 という名前の内部 A レコード。&lt;デバイス更新&gt; Web サービスをホストするフロントエンドプールの IP アドレスに解決される SIP ドメイン。</span><span class="sxs-lookup"><span data-stu-id="1170b-137">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Front End pool that hosts the Device Update Web service.</span></span> <span data-ttu-id="1170b-138">UC デバイスが有効になっていても、ユーザーがデバイスにログインしたことがない場合、デバイスは、A レコードを使用して、デバイス更新 Web サービスをホストするフロント エンド プールを検出し、更新プログラムを取得できます。</span><span class="sxs-lookup"><span data-stu-id="1170b-138">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the Front End pool hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="1170b-139">この方法を実行しない場合、デバイスはユーザーが最初にログインしたときにインバンド プロビジョニングを通じてこの情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="1170b-139">Otherwise, devices obtain this information though in-band provisioning the first time a user logs in.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="1170b-140">Lync Server 2010 でのデバイス更新 Web サービスの既存の展開がある場合は、ucupdates という名前の内部 A レコードが既に作成されています。&lt;SIP ドメイン&gt;。</span><span class="sxs-lookup"><span data-stu-id="1170b-140">If you have an existing deployment of Device Update Web service in Lync Server 2010, you have already created an internal A record with the name ucupdates.&lt;SIP domain&gt;.</span></span> <span data-ttu-id="1170b-141">Microsoft Office Communications Server 2007 R2 の場合は、ucupdates-R2 という名前で追加の DNS A レコードを作成する必要があります。&lt;SIP ドメイン&gt;。</span><span class="sxs-lookup"><span data-stu-id="1170b-141">For Microsoft Office Communications Server 2007 R2, you must create an additional DNS A record with the name ucupdates-r2.&lt;SIP domain&gt;.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1170b-142">HTTP トラフィックをサポートするためのリバース プロキシ</span><span class="sxs-lookup"><span data-stu-id="1170b-142">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="1170b-143">Web ファームの外部 FQDN を、リバース プロキシの外部 IP アドレスに解決する外部 A レコード。</span><span class="sxs-lookup"><span data-stu-id="1170b-143">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="1170b-144">クライアントと UC デバイスは、このレコードを使用してリバース プロキシに接続します。</span><span class="sxs-lookup"><span data-stu-id="1170b-144">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="1170b-145">詳細については、「計画」のドキュメントの「 <a href="lync-server-2013-determine-dns-requirements.md">Lync Server 2013 の DNS 要件を決定</a>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1170b-145">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1170b-146">次の表に、内部 Web ファームの FQDN で必要な DNS レコードの例を示します。</span><span class="sxs-lookup"><span data-stu-id="1170b-146">The following table shows an example of the DNS records required for the internal web farm FQDN.</span></span>

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a><span data-ttu-id="1170b-147">内部 Web ファームの FQDN のための DNS レコードの例</span><span class="sxs-lookup"><span data-stu-id="1170b-147">Example DNS Records for Internal Web Farm FQDN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1170b-148">内部 Web ファームの FQDN</span><span class="sxs-lookup"><span data-stu-id="1170b-148">Internal web farm FQDN</span></span></th>
<th><span data-ttu-id="1170b-149">プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="1170b-149">Pool FQDN</span></span></th>
<th><span data-ttu-id="1170b-150">DNS A レコード</span><span class="sxs-lookup"><span data-stu-id="1170b-150">DNS A record(s)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1170b-151">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1170b-151">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1170b-152">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1170b-152">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1170b-153">フロント エンド サーバーが使用するロード バランサーの VIP アドレスに解決する ee-pool.contoso.com の DNS A レコード。</span><span class="sxs-lookup"><span data-stu-id="1170b-153">DNS A record for the ee-pool.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p>
<p><span data-ttu-id="1170b-154">フロント エンド サーバーが使用するロード バランサーの VIP アドレスに解決する webcon.contoso.com の DNS A レコード。</span><span class="sxs-lookup"><span data-stu-id="1170b-154">DNS A record for webcon.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1170b-155">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1170b-155">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1170b-156">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1170b-156">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1170b-157">フロント エンド プールの Enterprise Edition フロント エンド サーバーが使用するロード バランサーの仮想 IP (VIP) アドレスに解決する ee-pool.contoso.com の DNS A レコード。</span><span class="sxs-lookup"><span data-stu-id="1170b-157">DNS A record for ee-pool.contoso.com that resolves to the virtual IP (VIP) address of the load balancer used by the Enterprise Edition Front End Servers in the Front End pool.</span></span></p>
<p><span data-ttu-id="1170b-158">このプールで DNS 負荷分散を使用する場合は、フロント エンド プールと内部 Web ファームで同じ FQDN を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1170b-158">Note that if you are using DNS load balancing on this pool, your Front End pool and internal web farm cannot have the same FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

