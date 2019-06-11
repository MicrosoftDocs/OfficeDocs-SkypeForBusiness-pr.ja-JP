---
title: 'Lync Server 2013: DNS の概要 - 拡張ディレクター プール、ハードウェア ロード バランサー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Scaled Director pool, hardware load balancer
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204655(v=OCS.15)
ms:contentKeyID: 48183340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ff76d69952d08db72e5647b58e38a43b4181c8e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="51c0d-102">DNS の概要 - Lync Server 2013 の拡張ディレクター プール、ハードウェア ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="51c0d-102">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51c0d-103">_**最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="51c0d-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="51c0d-104">次の表には、ハードウェア負荷分散ダイレクタをサポートするために必要な DNS レコードの概要が記載されています。</span><span class="sxs-lookup"><span data-stu-id="51c0d-104">The following table contains a summary of the DNS records that are required to support the hardware load balanced Director.</span></span> <span data-ttu-id="51c0d-105">ディレクターの役割には、フロントエンドサーバーと同様の DNS レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="51c0d-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="51c0d-106">必要なレコードの数は、ディレクター証明書に必要なサブジェクトの代替名に反映されます。</span><span class="sxs-lookup"><span data-stu-id="51c0d-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="51c0d-107">フロントエンドサーバーとは異なり、ディレクタープールでは、ユーザーアカウントをホストしたり、モビリティサービスをホストしたりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="51c0d-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a><span data-ttu-id="51c0d-108">ハードウェアロードバランサーと DNS の負荷分散を使用して、ディレクタープールに必要な DNS レコード</span><span class="sxs-lookup"><span data-stu-id="51c0d-108">DNS Records Required for the Director pool using a Hardware Load Balancer and DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51c0d-109">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="51c0d-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="51c0d-110">FQDN/DNS レコード</span><span class="sxs-lookup"><span data-stu-id="51c0d-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="51c0d-111">IP アドレス/FQDN</span><span class="sxs-lookup"><span data-stu-id="51c0d-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="51c0d-112">マップ先/コメント</span><span class="sxs-lookup"><span data-stu-id="51c0d-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51c0d-113">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="51c0d-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="51c0d-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="51c0d-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="51c0d-115">ディレクター</span><span class="sxs-lookup"><span data-stu-id="51c0d-115">Director</span></span></p></td>
<td><p><span data-ttu-id="51c0d-116">レプリケーションとサーバー間通信に使用されるディレクターホストレコード</span><span class="sxs-lookup"><span data-stu-id="51c0d-116">Director host record used for replication and server to server communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51c0d-117">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="51c0d-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="51c0d-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="51c0d-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="51c0d-119">ディレクタープール HLB VIP</span><span class="sxs-lookup"><span data-stu-id="51c0d-119">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="51c0d-120">DNS 負荷分散ダイレクタプールのホストレコード</span><span class="sxs-lookup"><span data-stu-id="51c0d-120">Host record for the DNS load balanced Director pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51c0d-121">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="51c0d-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="51c0d-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="51c0d-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="51c0d-123">ディレクタープール HLB VIP</span><span class="sxs-lookup"><span data-stu-id="51c0d-123">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="51c0d-124">エッジサーバーの内部インターフェイスからの受信セッション開始プロトコル (SIP)</span><span class="sxs-lookup"><span data-stu-id="51c0d-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51c0d-125">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="51c0d-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="51c0d-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="51c0d-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="51c0d-127">ディレクタープール HLB VIP</span><span class="sxs-lookup"><span data-stu-id="51c0d-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="51c0d-128">リバースプロキシから発行されたハードウェア負荷分散の web サービス</span><span class="sxs-lookup"><span data-stu-id="51c0d-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51c0d-129">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="51c0d-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="51c0d-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="51c0d-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="51c0d-131">ディレクタープール HLB VIP</span><span class="sxs-lookup"><span data-stu-id="51c0d-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="51c0d-132">リバースプロキシの web サービスによって発行されるハードウェア負荷分散</span><span class="sxs-lookup"><span data-stu-id="51c0d-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51c0d-133">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="51c0d-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="51c0d-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="51c0d-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="51c0d-135">ディレクタープール HLB VIP</span><span class="sxs-lookup"><span data-stu-id="51c0d-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="51c0d-136">ハードウェアの負荷分散が発行され、そのリバースプロキシ Web チケットによって定義されます。ディレクタープールの外部 web サービス</span><span class="sxs-lookup"><span data-stu-id="51c0d-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

