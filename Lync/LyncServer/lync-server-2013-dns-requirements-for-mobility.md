---
title: 'Lync Server 2013: モビリティの DNS 要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc11c79c291f7db7ad9e9e3228644ee27d42e555
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a><span data-ttu-id="808fa-102">Lync Server 2013 を使ったモビリティの DNS 要件</span><span class="sxs-lookup"><span data-stu-id="808fa-102">DNS requirements for mobility with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="808fa-103">_**最終更新日:** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="808fa-103">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="808fa-104">Lync Server 2013 モビリティ機能を展開するときに、Microsoft Lync Server 2013 自動検出サービスで利用できる新しい Url を使用したり、既存の Web サービスの Url を使用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="808fa-104">When you deploy the Lync Server 2013 mobility feature, you can use the new URLs that are available with the Microsoft Lync Server 2013 Autodiscover Service, or you can use your existing Web Services URLs.</span></span> <span data-ttu-id="808fa-105">既存の Url を使用している場合、ユーザーは自分のモバイルデバイス設定に Url を手動で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="808fa-105">If you use your existing URLs, users need to manually enter the URLs in their mobile device settings.</span></span> <span data-ttu-id="808fa-106">通常、このオプションはトラブルシューティングに使用されます。</span><span class="sxs-lookup"><span data-stu-id="808fa-106">This option is typically used for troubleshooting.</span></span> <span data-ttu-id="808fa-107">新しい Url を使用すると、モバイルクライアントは Lync Server 2013 のリソースを自動的に検出できます。</span><span class="sxs-lookup"><span data-stu-id="808fa-107">When you use the new URLs, mobile clients can automatically discover Lync Server 2013 resources.</span></span> <span data-ttu-id="808fa-108">自動検出をサポートしている場合は、新しいドメインネームシステム (DNS) レコードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="808fa-108">When you support automatic discovery, you need to add new Domain Name System (DNS) records.</span></span> <span data-ttu-id="808fa-109">このセクションでは、自動検出に必要な DNS レコードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="808fa-109">This section describes the DNS records that are required for automatic discovery.</span></span>

<span data-ttu-id="808fa-110">自動検出をサポートするには、SIP ドメインごとに次の DNS レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="808fa-110">To support automatic discovery, you need to create the following DNS records for each SIP domain:</span></span>

  - <span data-ttu-id="808fa-111">組織のネットワーク内から接続するモバイルユーザーをサポートするための内部 DNS レコード</span><span class="sxs-lookup"><span data-stu-id="808fa-111">An internal DNS record to support mobile users who connect from within your organization's network</span></span>

  - <span data-ttu-id="808fa-112">インターネットから接続するモバイルユーザーをサポートするための、外部またはパブリックの DNS レコード</span><span class="sxs-lookup"><span data-stu-id="808fa-112">An external, or public, DNS record to support mobile users who connect from the Internet</span></span>

<span data-ttu-id="808fa-113">内部の自動検出 URL は、ネットワークの外部からのアドレス指定を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="808fa-113">The internal automatic discovery URL should not be addressable from outside your network.</span></span> <span data-ttu-id="808fa-114">外部の自動検出 URL は、ネットワーク内からアドレス指定できません。</span><span class="sxs-lookup"><span data-stu-id="808fa-114">The external automatic discovery URL should not be addressable from within your network.</span></span> <span data-ttu-id="808fa-115">ただし、外部 URL に対してこの要件を満たしていない場合は、モバイルクライアントの機能が影響を受けないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="808fa-115">However, if you cannot meet this requirement for the external URL, mobile client functionally should not be affected.</span></span>

<span data-ttu-id="808fa-116">DNS レコードには、CNAME レコードまたは (ホスト) レコードのいずれかを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="808fa-116">The DNS records can be either CNAME records or A (host) records.</span></span>

<span data-ttu-id="808fa-117">**内部 DNS レコード**</span><span class="sxs-lookup"><span data-stu-id="808fa-117">**Internal DNS records**</span></span>

<span data-ttu-id="808fa-118">次の内部 DNS レコードのいずれかを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="808fa-118">You need to create one of the following internal DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="808fa-119">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="808fa-119">Record type</span></span></th>
<th><span data-ttu-id="808fa-120">ホスト名または SRV 定義</span><span class="sxs-lookup"><span data-stu-id="808fa-120">Host name or SRV definition</span></span></th>
<th><span data-ttu-id="808fa-121">解決先</span><span class="sxs-lookup"><span data-stu-id="808fa-121">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="808fa-122">CNAME</span><span class="sxs-lookup"><span data-stu-id="808fa-122">CNAME</span></span></p></td>
<td><p><span data-ttu-id="808fa-123">lyncdiscoverinternal.&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="808fa-123">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="808fa-124">ディレクタープールの場合は、内部 Web サービスの完全修飾ドメイン名 (FQDN)、ディレクターを持っていない場合は、フロントエンドプールの FQDN</span><span class="sxs-lookup"><span data-stu-id="808fa-124">Internal Web Services fully qualified domain name (FQDN) for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="808fa-125">A (ホスト)</span><span class="sxs-lookup"><span data-stu-id="808fa-125">A (host)</span></span></p></td>
<td><p><span data-ttu-id="808fa-126">lyncdiscoverinternal.&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="808fa-126">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="808fa-127">ディレクターを持っていない場合は、ディレクタープールの内部 Web サービス IP アドレス (ロードバランサーを使用している場合は仮想 IP (VIP) アドレス) (ディレクターを持っていない場合は、フロントエンドプールを持っている場合)</span><span class="sxs-lookup"><span data-stu-id="808fa-127">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="808fa-128">**外部 DNS レコード**</span><span class="sxs-lookup"><span data-stu-id="808fa-128">**External DNS records**</span></span>

<span data-ttu-id="808fa-129">次のいずれかの外部 DNS レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="808fa-129">You need to create one of the following external DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="808fa-130">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="808fa-130">Record type</span></span></th>
<th><span data-ttu-id="808fa-131">ホスト名</span><span class="sxs-lookup"><span data-stu-id="808fa-131">Host name</span></span></th>
<th><span data-ttu-id="808fa-132">解決先</span><span class="sxs-lookup"><span data-stu-id="808fa-132">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="808fa-133">CNAME</span><span class="sxs-lookup"><span data-stu-id="808fa-133">CNAME</span></span></p></td>
<td><p><span data-ttu-id="808fa-134">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="808fa-134">lyncdiscover.</span></span> <span data-ttu-id="808fa-135">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="808fa-135">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="808fa-136">ディレクタープールを所有している場合は、そのディレクタープールの外部 Web サービス FQDN (ディレクターを持っていない場合は、フロントエンドプール用)</span><span class="sxs-lookup"><span data-stu-id="808fa-136">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="808fa-137">A (ホスト)</span><span class="sxs-lookup"><span data-stu-id="808fa-137">A (host)</span></span></p></td>
<td><p><span data-ttu-id="808fa-138">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="808fa-138">lyncdiscover.</span></span> <span data-ttu-id="808fa-139">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="808fa-139">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="808fa-140">リバースプロキシの外部またはパブリック IP アドレス (ロードバランサーを使用している場合は VIP アドレス)</span><span class="sxs-lookup"><span data-stu-id="808fa-140">External or public IP address (VIP address if you use a load balancer) of the reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="808fa-141">SRV</span><span class="sxs-lookup"><span data-stu-id="808fa-141">SRV</span></span></p></td>
<td><p><span data-ttu-id="808fa-142">_sipfederationtls._tcp.</span><span class="sxs-lookup"><span data-stu-id="808fa-142">_sipfederationtls._tcp.</span></span> <span data-ttu-id="808fa-143">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="808fa-143">&lt;sipdomain&gt;</span></span></p>
<p><span data-ttu-id="808fa-144">アクセスエッジサービスの host (A または AAAA) レコードに解決されます。</span><span class="sxs-lookup"><span data-stu-id="808fa-144">Resolves to host (A or AAAA) record for the Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="808fa-145">プッシュ通知サービスと Apple プッシュ通知サービスをサポートするには、Microsoft Lync モバイルクライアントを含む SIP ドメインごとに SRV レコードを1つ作成します。</span><span class="sxs-lookup"><span data-stu-id="808fa-145">To support Push Notification Service and Apple Push Notification service, you create one SRV record for each SIP domain that has Microsoft Lync Mobile clients.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="808fa-146">この要件は、Apple または Microsoft ベースのモバイルデバイス上の Microsoft Lync モバイルクライアントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="808fa-146">This requirement applies only to Microsoft Lync Mobile clients on Apple or Microsoft based mobile devices.</span></span> <span data-ttu-id="808fa-147">Andriod および Nokia Symbian デバイスでは、プッシュ通知は使用されません。</span><span class="sxs-lookup"><span data-stu-id="808fa-147">Andriod and Nokia Symbian devices do not use push notification.</span></span>


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="808fa-148">Lyncdiscover は、自動検出とも呼ばれます。トラフィックはリバースプロキシを通過します。</span><span class="sxs-lookup"><span data-stu-id="808fa-148">Lyncdiscover, also known as autodiscover, traffic goes through the reverse proxy.</span></span> <span data-ttu-id="808fa-149">SRV レコードは、アクセスエッジサービスを通じて解決されるレコードを指します。</span><span class="sxs-lookup"><span data-stu-id="808fa-149">SRV record points to a record that resolves through the Access Edge service.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

