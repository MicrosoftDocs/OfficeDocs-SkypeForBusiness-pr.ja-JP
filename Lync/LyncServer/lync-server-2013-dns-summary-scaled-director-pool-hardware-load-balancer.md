---
title: 'Lync Server 2013: DNS の概要-拡張ディレクタープール、ハードウェアロードバランサー'
description: 'Lync Server 2013: DNS の概要-拡張ディレクタープール、ハードウェアロードバランサー。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled Director pool, hardware load balancer
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204655(v=OCS.15)
ms:contentKeyID: 48183340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7198e6a97feed8ce70cb16753ad1f21d58ef246c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555883"
---
# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="1bda9-103">DNS の概要-Lync Server 2013 の拡張ディレクタープール、ハードウェアロードバランサー</span><span class="sxs-lookup"><span data-stu-id="1bda9-103">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1bda9-104">_**トピックの最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="1bda9-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="1bda9-105">次の表に、ハードウェア負荷分散ディレクターをサポートするために必要な DNS レコードの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="1bda9-105">The following table contains a summary of the DNS records that are required to support the hardware load balanced Director.</span></span> <span data-ttu-id="1bda9-106">ディレクターの役割では、フロントエンドサーバーと同様の DNS レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="1bda9-106">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="1bda9-107">必要なレコード数は、ディレクター証明書で必要なサブジェクトの別名に反映されます。</span><span class="sxs-lookup"><span data-stu-id="1bda9-107">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="1bda9-108">フロントエンドサーバーとは異なり、ディレクタープールはユーザーアカウントをホストしたり、モビリティサービスをホストしたりしません。</span><span class="sxs-lookup"><span data-stu-id="1bda9-108">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a><span data-ttu-id="1bda9-109">ロードバランサー機器と DNS 負荷分散を使用してディレクタープールに必要な DNS レコード</span><span class="sxs-lookup"><span data-stu-id="1bda9-109">DNS Records Required for the Director pool using a Hardware Load Balancer and DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1bda9-110">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="1bda9-110">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="1bda9-111">FQDN/DNS レコード</span><span class="sxs-lookup"><span data-stu-id="1bda9-111">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="1bda9-112">IP アドレス/FQDN</span><span class="sxs-lookup"><span data-stu-id="1bda9-112">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="1bda9-113">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="1bda9-113">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1bda9-114">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1bda9-114">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1bda9-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="1bda9-115">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="1bda9-116">ディレクター</span><span class="sxs-lookup"><span data-stu-id="1bda9-116">Director</span></span></p></td>
<td><p><span data-ttu-id="1bda9-117">レプリケーションおよびサーバー間通信に使用されるディレクターホストレコード</span><span class="sxs-lookup"><span data-stu-id="1bda9-117">Director host record used for replication and server to server communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bda9-118">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1bda9-118">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1bda9-119">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="1bda9-119">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="1bda9-120">ディレクタープールの HLB VIP</span><span class="sxs-lookup"><span data-stu-id="1bda9-120">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="1bda9-121">DNS 負荷分散ディレクタープールのホストレコード</span><span class="sxs-lookup"><span data-stu-id="1bda9-121">Host record for the DNS load balanced Director pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bda9-122">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1bda9-122">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1bda9-123">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1bda9-123">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1bda9-124">ディレクタープールの HLB VIP</span><span class="sxs-lookup"><span data-stu-id="1bda9-124">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="1bda9-125">エッジサーバーの内部インターフェイスからの受信セッション開始プロトコル (SIP)</span><span class="sxs-lookup"><span data-stu-id="1bda9-125">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bda9-126">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1bda9-126">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1bda9-127">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1bda9-127">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1bda9-128">ディレクタープールの HLB VIP</span><span class="sxs-lookup"><span data-stu-id="1bda9-128">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="1bda9-129">リバースプロキシからのハードウェア負荷分散公開ダイヤルイン web サービス</span><span class="sxs-lookup"><span data-stu-id="1bda9-129">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bda9-130">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1bda9-130">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1bda9-131">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1bda9-131">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1bda9-132">ディレクタープールの HLB VIP</span><span class="sxs-lookup"><span data-stu-id="1bda9-132">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="1bda9-133">リバースプロキシからのハードウェア負荷分散公開会議 web サービス</span><span class="sxs-lookup"><span data-stu-id="1bda9-133">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bda9-134">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1bda9-134">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1bda9-135">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1bda9-135">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1bda9-136">ディレクタープールの HLB VIP</span><span class="sxs-lookup"><span data-stu-id="1bda9-136">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="1bda9-137">ハードウェア負荷分散が公開され、リバースプロキシによって、ディレクタープールの Web チケット外部 web サービスによって定義されている。</span><span class="sxs-lookup"><span data-stu-id="1bda9-137">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

