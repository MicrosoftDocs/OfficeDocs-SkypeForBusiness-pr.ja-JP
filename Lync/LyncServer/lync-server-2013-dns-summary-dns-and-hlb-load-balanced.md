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
ms.openlocfilehash: a6a3dc04856e1727c3982864995494cee751f457
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532154"
---
# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="fbb0e-102">DNS の概要-Lync Server 2013 での DNS および HLB の負荷分散</span><span class="sxs-lookup"><span data-stu-id="fbb0e-102">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbb0e-103">_**トピックの最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="fbb0e-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="fbb0e-104">次の表に、DNS 負荷分散およびハードウェア負荷分散ディレクターをサポートするために必要な DNS レコードの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="fbb0e-104">The following table contains a summary of the DNS records that are required to support the DNS load balanced and hardware load balanced Director.</span></span> <span data-ttu-id="fbb0e-105">ディレクターの役割では、フロントエンドサーバーと同様の DNS レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="fbb0e-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="fbb0e-106">必要なレコード数は、ディレクター証明書で必要なサブジェクトの別名に反映されます。</span><span class="sxs-lookup"><span data-stu-id="fbb0e-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="fbb0e-107">フロントエンドサーバーとは異なり、ディレクタープールはユーザーアカウントをホストしたり、モビリティサービスをホストしたりしません。</span><span class="sxs-lookup"><span data-stu-id="fbb0e-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a><span data-ttu-id="fbb0e-108">DNS 負荷分散とロードバランサー機器を使用したディレクタープールに必要な DNS レコード</span><span class="sxs-lookup"><span data-stu-id="fbb0e-108">DNS Records Required for the Director Pool using DNS Load Balancing and Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fbb0e-109">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="fbb0e-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="fbb0e-110">FQDN/DNS レコード</span><span class="sxs-lookup"><span data-stu-id="fbb0e-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="fbb0e-111">IP アドレス/FQDN</span><span class="sxs-lookup"><span data-stu-id="fbb0e-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="fbb0e-112">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="fbb0e-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fbb0e-113">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="fbb0e-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="fbb0e-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="fbb0e-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="fbb0e-115">ディレクター</span><span class="sxs-lookup"><span data-stu-id="fbb0e-115">Director</span></span></p></td>
<td><p><span data-ttu-id="fbb0e-116">レプリケーションおよびサーバー間で使用されるディレクターホストレコード</span><span class="sxs-lookup"><span data-stu-id="fbb0e-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbb0e-117">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="fbb0e-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="fbb0e-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="fbb0e-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="fbb0e-119">ディレクター プール</span><span class="sxs-lookup"><span data-stu-id="fbb0e-119">Director pool</span></span></p></td>
<td><p><span data-ttu-id="fbb0e-120">サーバーからサーバーへの DNS 負荷分散ディレクタープールのホストレコード</span><span class="sxs-lookup"><span data-stu-id="fbb0e-120">Host record for the DNS load balanced Director pool for server to server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbb0e-121">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="fbb0e-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="fbb0e-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fbb0e-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fbb0e-123">ディレクター プール</span><span class="sxs-lookup"><span data-stu-id="fbb0e-123">Director pool</span></span></p></td>
<td><p><span data-ttu-id="fbb0e-124">エッジサーバーの内部インターフェイスからの受信セッション開始プロトコル (SIP)</span><span class="sxs-lookup"><span data-stu-id="fbb0e-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbb0e-125">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="fbb0e-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="fbb0e-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fbb0e-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fbb0e-127">ディレクタープールの HLB VIP</span><span class="sxs-lookup"><span data-stu-id="fbb0e-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="fbb0e-128">リバースプロキシからのハードウェア負荷分散公開ダイヤルイン web サービス</span><span class="sxs-lookup"><span data-stu-id="fbb0e-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbb0e-129">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="fbb0e-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="fbb0e-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fbb0e-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fbb0e-131">ディレクタープールの HLB VIP</span><span class="sxs-lookup"><span data-stu-id="fbb0e-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="fbb0e-132">リバースプロキシからのハードウェア負荷分散公開会議 web サービス</span><span class="sxs-lookup"><span data-stu-id="fbb0e-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbb0e-133">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="fbb0e-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="fbb0e-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fbb0e-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fbb0e-135">ディレクタープールの HLB VIP</span><span class="sxs-lookup"><span data-stu-id="fbb0e-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="fbb0e-136">ハードウェア負荷分散が公開され、リバースプロキシによって、ディレクタープールの Web チケット外部 web サービスによって定義されている。</span><span class="sxs-lookup"><span data-stu-id="fbb0e-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

