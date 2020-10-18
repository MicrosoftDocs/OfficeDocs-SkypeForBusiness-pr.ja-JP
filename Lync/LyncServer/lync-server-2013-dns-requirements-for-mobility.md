---
title: 'Lync Server 2013: モビリティの DNS 要件'
description: 'Lync Server 2013: モビリティの DNS 要件。'
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
ms.openlocfilehash: e2a8377dc7c856bb7250817cb3b8b66ed7789d3b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574303"
---
# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a><span data-ttu-id="8f29f-103">Lync Server 2013 を使用したモビリティの DNS 要件</span><span class="sxs-lookup"><span data-stu-id="8f29f-103">DNS requirements for mobility with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f29f-104">_**トピックの最終更新日:** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="8f29f-104">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="8f29f-105">Lync Server 2013 モビリティ機能を展開する場合は、Microsoft Lync Server 2013 自動検出サービスで使用可能な新しい Url を使用するか、既存の Web サービスの Url を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="8f29f-105">When you deploy the Lync Server 2013 mobility feature, you can use the new URLs that are available with the Microsoft Lync Server 2013 Autodiscover Service, or you can use your existing Web Services URLs.</span></span> <span data-ttu-id="8f29f-106">既存の Url を使用する場合、ユーザーはモバイルデバイスの設定で Url を手動で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f29f-106">If you use your existing URLs, users need to manually enter the URLs in their mobile device settings.</span></span> <span data-ttu-id="8f29f-107">このオプションは、通常、トラブルシューティングに使用されます。</span><span class="sxs-lookup"><span data-stu-id="8f29f-107">This option is typically used for troubleshooting.</span></span> <span data-ttu-id="8f29f-108">新しい Url を使用すると、モバイルクライアントは Lync Server 2013 のリソースを自動的に検出できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8f29f-108">When you use the new URLs, mobile clients can automatically discover Lync Server 2013 resources.</span></span> <span data-ttu-id="8f29f-109">自動検出をサポートする場合は、新しいドメインネームシステム (DNS) レコードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f29f-109">When you support automatic discovery, you need to add new Domain Name System (DNS) records.</span></span> <span data-ttu-id="8f29f-110">このセクションでは、自動検出に必要な DNS レコードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8f29f-110">This section describes the DNS records that are required for automatic discovery.</span></span>

<span data-ttu-id="8f29f-111">自動検出をサポートするには、SIP ドメインごとに次の DNS レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f29f-111">To support automatic discovery, you need to create the following DNS records for each SIP domain:</span></span>

  - <span data-ttu-id="8f29f-112">組織のネットワーク内から接続するモバイル ユーザーをサポートするための内部 DNS レコード</span><span class="sxs-lookup"><span data-stu-id="8f29f-112">An internal DNS record to support mobile users who connect from within your organization's network</span></span>

  - <span data-ttu-id="8f29f-113">インターネットから接続するモバイル ユーザーをサポートするための外部 (パブリック) DNS レコード</span><span class="sxs-lookup"><span data-stu-id="8f29f-113">An external, or public, DNS record to support mobile users who connect from the Internet</span></span>

<span data-ttu-id="8f29f-114">内部の自動検出 URL は、ネットワークの外部からアドレス指定できません。</span><span class="sxs-lookup"><span data-stu-id="8f29f-114">The internal automatic discovery URL should not be addressable from outside your network.</span></span> <span data-ttu-id="8f29f-115">外部自動検出 URL は、ネットワーク内からアドレス指定できません。</span><span class="sxs-lookup"><span data-stu-id="8f29f-115">The external automatic discovery URL should not be addressable from within your network.</span></span> <span data-ttu-id="8f29f-116">ただし、外部 URL に対してこの要件を満たしていない場合、モバイルクライアントの機能は影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="8f29f-116">However, if you cannot meet this requirement for the external URL, mobile client functionally should not be affected.</span></span>

<span data-ttu-id="8f29f-117">DNS レコードは、CNAME レコードまたは A (ホスト) レコードとすることができます。</span><span class="sxs-lookup"><span data-stu-id="8f29f-117">The DNS records can be either CNAME records or A (host) records.</span></span>

<span data-ttu-id="8f29f-118">**内部 DNS レコード**</span><span class="sxs-lookup"><span data-stu-id="8f29f-118">**Internal DNS records**</span></span>

<span data-ttu-id="8f29f-119">次の内部 DNS レコードの1つを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f29f-119">You need to create one of the following internal DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f29f-120">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="8f29f-120">Record type</span></span></th>
<th><span data-ttu-id="8f29f-121">ホスト名または SRV 定義</span><span class="sxs-lookup"><span data-stu-id="8f29f-121">Host name or SRV definition</span></span></th>
<th><span data-ttu-id="8f29f-122">解決先</span><span class="sxs-lookup"><span data-stu-id="8f29f-122">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f29f-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="8f29f-123">CNAME</span></span></p></td>
<td><p><span data-ttu-id="8f29f-124">lyncdiscoverinternal。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="8f29f-124">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="8f29f-125">ディレクタープールの内部 Web サービスの完全修飾ドメイン名 (FQDN) (ディレクターがない場合) またはフロントエンドプールの場合は、ディレクターが存在しない場合</span><span class="sxs-lookup"><span data-stu-id="8f29f-125">Internal Web Services fully qualified domain name (FQDN) for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f29f-126">A (ホスト)</span><span class="sxs-lookup"><span data-stu-id="8f29f-126">A (host)</span></span></p></td>
<td><p><span data-ttu-id="8f29f-127">lyncdiscoverinternal。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="8f29f-127">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="8f29f-128">ディレクタープールを使用する場合の内部 Web サービス IP アドレス (ロードバランサーを使用する場合は仮想 IP (VIP) アドレス、ディレクターを持っていない場合はフロントエンドプールのいずれか)</span><span class="sxs-lookup"><span data-stu-id="8f29f-128">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8f29f-129">**外部 DNS レコード**</span><span class="sxs-lookup"><span data-stu-id="8f29f-129">**External DNS records**</span></span>

<span data-ttu-id="8f29f-130">次の外部 DNS レコードの 1 つを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f29f-130">You need to create one of the following external DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f29f-131">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="8f29f-131">Record type</span></span></th>
<th><span data-ttu-id="8f29f-132">ホスト名</span><span class="sxs-lookup"><span data-stu-id="8f29f-132">Host name</span></span></th>
<th><span data-ttu-id="8f29f-133">解決先</span><span class="sxs-lookup"><span data-stu-id="8f29f-133">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f29f-134">CNAME</span><span class="sxs-lookup"><span data-stu-id="8f29f-134">CNAME</span></span></p></td>
<td><p><span data-ttu-id="8f29f-135">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="8f29f-135">lyncdiscover.</span></span> <span data-ttu-id="8f29f-136">&lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="8f29f-136">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="8f29f-137">ディレクターが存在しない場合は、ディレクタープールの外部 Web サービスの FQDN、またはディレクターを持っていない場合はフロントエンドプール。</span><span class="sxs-lookup"><span data-stu-id="8f29f-137">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f29f-138">A (ホスト)</span><span class="sxs-lookup"><span data-stu-id="8f29f-138">A (host)</span></span></p></td>
<td><p><span data-ttu-id="8f29f-139">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="8f29f-139">lyncdiscover.</span></span> <span data-ttu-id="8f29f-140">&lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="8f29f-140">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="8f29f-141">リバースプロキシの外部またはパブリック IP アドレス (ロードバランサーを使用する場合は VIP アドレス)</span><span class="sxs-lookup"><span data-stu-id="8f29f-141">External or public IP address (VIP address if you use a load balancer) of the reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f29f-142">SRV</span><span class="sxs-lookup"><span data-stu-id="8f29f-142">SRV</span></span></p></td>
<td><p><span data-ttu-id="8f29f-143">_sipfederationtls _sipfederationtls._tcp。</span><span class="sxs-lookup"><span data-stu-id="8f29f-143">_sipfederationtls._tcp.</span></span> <span data-ttu-id="8f29f-144">&lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="8f29f-144">&lt;sipdomain&gt;</span></span></p>
<p><span data-ttu-id="8f29f-145">アクセスエッジサービスのホスト (A または AAAA) レコードに解決されます。</span><span class="sxs-lookup"><span data-stu-id="8f29f-145">Resolves to host (A or AAAA) record for the Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8f29f-146">プッシュ通知サービスと Apple プッシュ通知サービスをサポートするには、Microsoft Lync Mobile クライアントが存在する各 SIP ドメインに対して1つの SRV レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="8f29f-146">To support Push Notification Service and Apple Push Notification service, you create one SRV record for each SIP domain that has Microsoft Lync Mobile clients.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="8f29f-147">この要件は、Apple または Microsoft ベースのモバイルデバイス上の Microsoft Lync モバイルクライアントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8f29f-147">This requirement applies only to Microsoft Lync Mobile clients on Apple or Microsoft based mobile devices.</span></span> <span data-ttu-id="8f29f-148">Andriod および Nokia Symbian デバイスは、プッシュ通知を使用しません。</span><span class="sxs-lookup"><span data-stu-id="8f29f-148">Andriod and Nokia Symbian devices do not use push notification.</span></span>


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="8f29f-149">Lyncdiscover (自動検出とも呼ばれます) は、トラフィックはリバースプロキシを通過します。</span><span class="sxs-lookup"><span data-stu-id="8f29f-149">Lyncdiscover, also known as autodiscover, traffic goes through the reverse proxy.</span></span> <span data-ttu-id="8f29f-150">SRV レコードは、アクセスエッジサービスを介して解決されるレコードを指します。</span><span class="sxs-lookup"><span data-stu-id="8f29f-150">SRV record points to a record that resolves through the Access Edge service.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

