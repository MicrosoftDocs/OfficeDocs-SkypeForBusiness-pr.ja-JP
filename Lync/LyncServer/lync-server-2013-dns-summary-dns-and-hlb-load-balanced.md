---
title: 'Lync Server 2013: DNS の概要 - DNS と HLB 負荷分散'
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
ms.openlocfilehash: c5b84ccab2b3074662016a19c5f0a51d0cb70405
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="14a00-102">DNS の概要 - Lync Server 2013 での DNS と HLB 負荷分散</span><span class="sxs-lookup"><span data-stu-id="14a00-102">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14a00-103">_**最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="14a00-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="14a00-104">次の表には、DNS の負荷分散とハードウェア負荷分散ディレクターをサポートするために必要な DNS レコードの概要が記載されています。</span><span class="sxs-lookup"><span data-stu-id="14a00-104">The following table contains a summary of the DNS records that are required to support the DNS load balanced and hardware load balanced Director.</span></span> <span data-ttu-id="14a00-105">ディレクターの役割には、フロントエンドサーバーと同様の DNS レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="14a00-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="14a00-106">必要なレコードの数は、ディレクター証明書に必要なサブジェクトの代替名に反映されます。</span><span class="sxs-lookup"><span data-stu-id="14a00-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="14a00-107">フロントエンドサーバーとは異なり、ディレクタープールでは、ユーザーアカウントをホストしたり、モビリティサービスをホストしたりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="14a00-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a><span data-ttu-id="14a00-108">DNS 負荷分散とハードウェアロードバランサーを使って、ディレクタープールに必要な DNS レコード</span><span class="sxs-lookup"><span data-stu-id="14a00-108">DNS Records Required for the Director Pool using DNS Load Balancing and Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14a00-109">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="14a00-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="14a00-110">FQDN/DNS レコード</span><span class="sxs-lookup"><span data-stu-id="14a00-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="14a00-111">IP アドレス/FQDN</span><span class="sxs-lookup"><span data-stu-id="14a00-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="14a00-112">マップ先/コメント</span><span class="sxs-lookup"><span data-stu-id="14a00-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14a00-113">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="14a00-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="14a00-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="14a00-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="14a00-115">ディレクター</span><span class="sxs-lookup"><span data-stu-id="14a00-115">Director</span></span></p></td>
<td><p><span data-ttu-id="14a00-116">レプリケーションとサーバー間で使用されるディレクターホストレコード</span><span class="sxs-lookup"><span data-stu-id="14a00-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a00-117">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="14a00-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="14a00-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="14a00-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="14a00-119">ディレクター プール</span><span class="sxs-lookup"><span data-stu-id="14a00-119">Director pool</span></span></p></td>
<td><p><span data-ttu-id="14a00-120">サーバー間の DNS 負荷分散ダイレクタプールのホストレコード</span><span class="sxs-lookup"><span data-stu-id="14a00-120">Host record for the DNS load balanced Director pool for server to server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a00-121">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="14a00-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="14a00-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14a00-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="14a00-123">ディレクター プール</span><span class="sxs-lookup"><span data-stu-id="14a00-123">Director pool</span></span></p></td>
<td><p><span data-ttu-id="14a00-124">エッジサーバーの内部インターフェイスからの受信セッション開始プロトコル (SIP)</span><span class="sxs-lookup"><span data-stu-id="14a00-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a00-125">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="14a00-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="14a00-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14a00-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="14a00-127">ディレクタープール HLB VIP</span><span class="sxs-lookup"><span data-stu-id="14a00-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="14a00-128">リバースプロキシから発行されたハードウェア負荷分散の web サービス</span><span class="sxs-lookup"><span data-stu-id="14a00-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a00-129">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="14a00-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="14a00-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14a00-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="14a00-131">ディレクタープール HLB VIP</span><span class="sxs-lookup"><span data-stu-id="14a00-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="14a00-132">リバースプロキシの web サービスによって発行されるハードウェア負荷分散</span><span class="sxs-lookup"><span data-stu-id="14a00-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a00-133">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="14a00-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="14a00-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14a00-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="14a00-135">ディレクタープール HLB VIP</span><span class="sxs-lookup"><span data-stu-id="14a00-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="14a00-136">ハードウェアの負荷分散が発行され、そのリバースプロキシ Web チケットによって定義されます。ディレクタープールの外部 web サービス</span><span class="sxs-lookup"><span data-stu-id="14a00-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

