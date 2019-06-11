---
title: 'Lync Server 2013: モビリティの DNS 要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fb933e20b8da627ad48a30802ff86c7ed95faff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a><span data-ttu-id="71f21-102">Lync Server 2013 を使ったモビリティの DNS 要件</span><span class="sxs-lookup"><span data-stu-id="71f21-102">DNS requirements for mobility with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71f21-103">_**最終更新日:** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="71f21-103">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="71f21-104">Lync Server 2013 モビリティ機能を展開するときに、Microsoft Lync Server 2013 自動検出サービスで利用できる新しい Url を使用したり、既存の Web サービスの Url を使用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="71f21-104">When you deploy the Lync Server 2013 mobility feature, you can use the new URLs that are available with the Microsoft Lync Server 2013 Autodiscover Service, or you can use your existing Web Services URLs.</span></span> <span data-ttu-id="71f21-105">既存の Url を使用している場合、ユーザーは自分のモバイルデバイス設定に Url を手動で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f21-105">If you use your existing URLs, users need to manually enter the URLs in their mobile device settings.</span></span> <span data-ttu-id="71f21-106">通常、このオプションはトラブルシューティングに使用されます。</span><span class="sxs-lookup"><span data-stu-id="71f21-106">This option is typically used for troubleshooting.</span></span> <span data-ttu-id="71f21-107">新しい Url を使用すると、モバイルクライアントは Lync Server 2013 のリソースを自動的に検出できます。</span><span class="sxs-lookup"><span data-stu-id="71f21-107">When you use the new URLs, mobile clients can automatically discover Lync Server 2013 resources.</span></span> <span data-ttu-id="71f21-108">自動検出をサポートしている場合は、新しいドメインネームシステム (DNS) レコードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f21-108">When you support automatic discovery, you need to add new Domain Name System (DNS) records.</span></span> <span data-ttu-id="71f21-109">このセクションでは、自動検出に必要な DNS レコードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="71f21-109">This section describes the DNS records that are required for automatic discovery.</span></span>

<span data-ttu-id="71f21-110">自動検出をサポートするには、SIP ドメインごとに次の DNS レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f21-110">To support automatic discovery, you need to create the following DNS records for each SIP domain:</span></span>

  - <span data-ttu-id="71f21-111">組織のネットワーク内から接続するモバイルユーザーをサポートするための内部 DNS レコード</span><span class="sxs-lookup"><span data-stu-id="71f21-111">An internal DNS record to support mobile users who connect from within your organization's network</span></span>

  - <span data-ttu-id="71f21-112">インターネットから接続するモバイルユーザーをサポートするための、外部またはパブリックの DNS レコード</span><span class="sxs-lookup"><span data-stu-id="71f21-112">An external, or public, DNS record to support mobile users who connect from the Internet</span></span>

<span data-ttu-id="71f21-113">内部の自動検出 URL は、ネットワークの外部からのアドレス指定を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="71f21-113">The internal automatic discovery URL should not be addressable from outside your network.</span></span> <span data-ttu-id="71f21-114">外部の自動検出 URL は、ネットワーク内からアドレス指定できません。</span><span class="sxs-lookup"><span data-stu-id="71f21-114">The external automatic discovery URL should not be addressable from within your network.</span></span> <span data-ttu-id="71f21-115">ただし、外部 URL に対してこの要件を満たしていない場合は、モバイルクライアントの機能が影響を受けないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f21-115">However, if you cannot meet this requirement for the external URL, mobile client functionally should not be affected.</span></span>

<span data-ttu-id="71f21-116">DNS レコードには、CNAME レコードまたは (ホスト) レコードのいずれかを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="71f21-116">The DNS records can be either CNAME records or A (host) records.</span></span>

<span data-ttu-id="71f21-117">**内部 DNS レコード**</span><span class="sxs-lookup"><span data-stu-id="71f21-117">**Internal DNS records**</span></span>

<span data-ttu-id="71f21-118">次の内部 DNS レコードのいずれかを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f21-118">You need to create one of the following internal DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71f21-119">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="71f21-119">Record type</span></span></th>
<th><span data-ttu-id="71f21-120">ホスト名または SRV 定義</span><span class="sxs-lookup"><span data-stu-id="71f21-120">Host name or SRV definition</span></span></th>
<th><span data-ttu-id="71f21-121">解決先</span><span class="sxs-lookup"><span data-stu-id="71f21-121">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71f21-122">CNAME</span><span class="sxs-lookup"><span data-stu-id="71f21-122">CNAME</span></span></p></td>
<td><p><span data-ttu-id="71f21-123">lyncdiscoverinternal.&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="71f21-123">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="71f21-124">ディレクタープールの場合は、内部 Web サービスの完全修飾ドメイン名 (FQDN)、ディレクターを持っていない場合は、フロントエンドプールの FQDN</span><span class="sxs-lookup"><span data-stu-id="71f21-124">Internal Web Services fully qualified domain name (FQDN) for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f21-125">A (ホスト)</span><span class="sxs-lookup"><span data-stu-id="71f21-125">A (host)</span></span></p></td>
<td><p><span data-ttu-id="71f21-126">lyncdiscoverinternal.&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="71f21-126">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="71f21-127">ディレクターを持っていない場合は、ディレクタープールの内部 Web サービス IP アドレス (ロードバランサーを使用している場合は仮想 IP (VIP) アドレス) (ディレクターを持っていない場合は、フロントエンドプールを持っている場合)</span><span class="sxs-lookup"><span data-stu-id="71f21-127">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="71f21-128">**外部 DNS レコード**</span><span class="sxs-lookup"><span data-stu-id="71f21-128">**External DNS records**</span></span>

<span data-ttu-id="71f21-129">次のいずれかの外部 DNS レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f21-129">You need to create one of the following external DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71f21-130">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="71f21-130">Record type</span></span></th>
<th><span data-ttu-id="71f21-131">ホスト名</span><span class="sxs-lookup"><span data-stu-id="71f21-131">Host name</span></span></th>
<th><span data-ttu-id="71f21-132">解決先</span><span class="sxs-lookup"><span data-stu-id="71f21-132">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71f21-133">CNAME</span><span class="sxs-lookup"><span data-stu-id="71f21-133">CNAME</span></span></p></td>
<td><p><span data-ttu-id="71f21-134">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="71f21-134">lyncdiscover.</span></span> <span data-ttu-id="71f21-135">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="71f21-135">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="71f21-136">ディレクタープールを所有している場合は、そのディレクタープールの外部 Web サービス FQDN (ディレクターを持っていない場合は、フロントエンドプール用)</span><span class="sxs-lookup"><span data-stu-id="71f21-136">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f21-137">A (ホスト)</span><span class="sxs-lookup"><span data-stu-id="71f21-137">A (host)</span></span></p></td>
<td><p><span data-ttu-id="71f21-138">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="71f21-138">lyncdiscover.</span></span> <span data-ttu-id="71f21-139">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="71f21-139">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="71f21-140">リバースプロキシの外部またはパブリック IP アドレス (ロードバランサーを使用している場合は VIP アドレス)</span><span class="sxs-lookup"><span data-stu-id="71f21-140">External or public IP address (VIP address if you use a load balancer) of the reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f21-141">SRV</span><span class="sxs-lookup"><span data-stu-id="71f21-141">SRV</span></span></p></td>
<td><p><span data-ttu-id="71f21-142">_sipfederationtls._tcp.</span><span class="sxs-lookup"><span data-stu-id="71f21-142">_sipfederationtls._tcp.</span></span> <span data-ttu-id="71f21-143">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="71f21-143">&lt;sipdomain&gt;</span></span></p>
<p><span data-ttu-id="71f21-144">アクセスエッジサービスの host (A または AAAA) レコードに解決されます。</span><span class="sxs-lookup"><span data-stu-id="71f21-144">Resolves to host (A or AAAA) record for the Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="71f21-145">プッシュ通知サービスと Apple プッシュ通知サービスをサポートするには、Microsoft Lync モバイルクライアントを含む SIP ドメインごとに SRV レコードを1つ作成します。</span><span class="sxs-lookup"><span data-stu-id="71f21-145">To support Push Notification Service and Apple Push Notification service, you create one SRV record for each SIP domain that has Microsoft Lync Mobile clients.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="71f21-146">この要件は、Apple または Microsoft ベースのモバイルデバイス上の Microsoft Lync モバイルクライアントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="71f21-146">This requirement applies only to Microsoft Lync Mobile clients on Apple or Microsoft based mobile devices.</span></span> <span data-ttu-id="71f21-147">Andriod および Nokia Symbian デバイスでは、プッシュ通知は使用されません。</span><span class="sxs-lookup"><span data-stu-id="71f21-147">Andriod and Nokia Symbian devices do not use push notification.</span></span>


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="71f21-148">Lyncdiscover は、自動検出とも呼ばれます。トラフィックはリバースプロキシを通過します。</span><span class="sxs-lookup"><span data-stu-id="71f21-148">Lyncdiscover, also known as autodiscover, traffic goes through the reverse proxy.</span></span> <span data-ttu-id="71f21-149">SRV レコードは、アクセスエッジサービスを通じて解決されるレコードを指します。</span><span class="sxs-lookup"><span data-stu-id="71f21-149">SRV record points to a record that resolves through the Access Edge service.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

