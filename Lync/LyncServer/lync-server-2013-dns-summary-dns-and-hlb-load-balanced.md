---
title: 'Lync Server 2013: DNS の概要-DNS と HLB 負荷分散'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2c4b2df2200ecd7cc5af6e3aa651c18866c8924
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="c7355-102">DNS の概要-Lync Server 2013 での DNS および HLB の負荷分散</span><span class="sxs-lookup"><span data-stu-id="c7355-102">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7355-103">_**トピックの最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="c7355-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="c7355-104">次の表に、DNS 負荷分散およびハードウェア負荷分散ディレクターをサポートするために必要な DNS レコードの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="c7355-104">The following table contains a summary of the DNS records that are required to support the DNS load balanced and hardware load balanced Director.</span></span> <span data-ttu-id="c7355-105">ディレクターの役割では、フロントエンドサーバーと同様の DNS レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="c7355-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="c7355-106">必要なレコード数は、ディレクター証明書で必要なサブジェクトの別名に反映されます。</span><span class="sxs-lookup"><span data-stu-id="c7355-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="c7355-107">フロントエンドサーバーとは異なり、ディレクタープールはユーザーアカウントをホストしたり、モビリティサービスをホストしたりしません。</span><span class="sxs-lookup"><span data-stu-id="c7355-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a><span data-ttu-id="c7355-108">DNS 負荷分散とロードバランサー機器を使用したディレクタープールに必要な DNS レコード</span><span class="sxs-lookup"><span data-stu-id="c7355-108">DNS Records Required for the Director Pool using DNS Load Balancing and Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7355-109">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="c7355-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="c7355-110">FQDN/DNS レコード</span><span class="sxs-lookup"><span data-stu-id="c7355-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="c7355-111">IP アドレス/FQDN</span><span class="sxs-lookup"><span data-stu-id="c7355-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="c7355-112">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="c7355-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7355-113">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="c7355-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c7355-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c7355-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="c7355-115">ディレクター</span><span class="sxs-lookup"><span data-stu-id="c7355-115">Director</span></span></p></td>
<td><p><span data-ttu-id="c7355-116">レプリケーションおよびサーバー間で使用されるディレクターホストレコード</span><span class="sxs-lookup"><span data-stu-id="c7355-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7355-117">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="c7355-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c7355-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c7355-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="c7355-119">ディレクター プール</span><span class="sxs-lookup"><span data-stu-id="c7355-119">Director pool</span></span></p></td>
<td><p><span data-ttu-id="c7355-120">サーバーからサーバーへの DNS 負荷分散ディレクタープールのホストレコード</span><span class="sxs-lookup"><span data-stu-id="c7355-120">Host record for the DNS load balanced Director pool for server to server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7355-121">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="c7355-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c7355-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7355-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c7355-123">ディレクター プール</span><span class="sxs-lookup"><span data-stu-id="c7355-123">Director pool</span></span></p></td>
<td><p><span data-ttu-id="c7355-124">エッジサーバーの内部インターフェイスからの受信セッション開始プロトコル (SIP)</span><span class="sxs-lookup"><span data-stu-id="c7355-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7355-125">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="c7355-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c7355-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7355-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c7355-127">ディレクタープールの HLB VIP</span><span class="sxs-lookup"><span data-stu-id="c7355-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="c7355-128">リバースプロキシからのハードウェア負荷分散公開ダイヤルイン web サービス</span><span class="sxs-lookup"><span data-stu-id="c7355-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7355-129">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="c7355-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c7355-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7355-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c7355-131">ディレクタープールの HLB VIP</span><span class="sxs-lookup"><span data-stu-id="c7355-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="c7355-132">リバースプロキシからのハードウェア負荷分散公開会議 web サービス</span><span class="sxs-lookup"><span data-stu-id="c7355-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7355-133">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="c7355-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c7355-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7355-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c7355-135">ディレクタープールの HLB VIP</span><span class="sxs-lookup"><span data-stu-id="c7355-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="c7355-136">ハードウェア負荷分散が公開され、リバースプロキシによって、ディレクタープールの Web チケット外部 web サービスによって定義されている。</span><span class="sxs-lookup"><span data-stu-id="c7355-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

