---
title: 'Lync Server 2013: DNS の概要-単一ディレクター'
description: 'Lync Server 2013: DNS の概要-単一ディレクター。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78ef19383df45644ad951ca5da69ef893b231980
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553233"
---
# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="d41e8-103">DNS の概要-Lync Server 2013 の単一ディレクター</span><span class="sxs-lookup"><span data-stu-id="d41e8-103">DNS summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d41e8-104">_**トピックの最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="d41e8-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="d41e8-105">次の表に、単一ディレクターのサポートに必要な DNS レコードの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="d41e8-105">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="d41e8-106">ディレクターの役割では、フロントエンドサーバーと同様の DNS レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="d41e8-106">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="d41e8-107">必要なレコード数は、ディレクター証明書で必要なサブジェクトの別名に反映されます。</span><span class="sxs-lookup"><span data-stu-id="d41e8-107">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="d41e8-108">フロントエンドサーバーとは異なり、ディレクターはユーザーアカウントをホストしたり、モビリティサービスをホストしたりしません。</span><span class="sxs-lookup"><span data-stu-id="d41e8-108">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="d41e8-109">ディレクターに必要な DNS レコード</span><span class="sxs-lookup"><span data-stu-id="d41e8-109">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d41e8-110">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="d41e8-110">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="d41e8-111">FQDN/DNS レコード</span><span class="sxs-lookup"><span data-stu-id="d41e8-111">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="d41e8-112">IP アドレス/FQDN</span><span class="sxs-lookup"><span data-stu-id="d41e8-112">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="d41e8-113">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="d41e8-113">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d41e8-114">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="d41e8-114">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d41e8-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="d41e8-115">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="d41e8-116">ディレクター</span><span class="sxs-lookup"><span data-stu-id="d41e8-116">Director</span></span></p></td>
<td><p><span data-ttu-id="d41e8-117">レプリケーションおよびサーバー間で使用されるディレクターホストレコード</span><span class="sxs-lookup"><span data-stu-id="d41e8-117">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d41e8-118">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="d41e8-118">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d41e8-119">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d41e8-119">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d41e8-120">ディレクター</span><span class="sxs-lookup"><span data-stu-id="d41e8-120">Director</span></span></p></td>
<td><p><span data-ttu-id="d41e8-121">エッジサーバーの内部エッジインターフェイスからの受信セッション開始プロトコル (SIP)</span><span class="sxs-lookup"><span data-stu-id="d41e8-121">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d41e8-122">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="d41e8-122">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d41e8-123">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d41e8-123">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d41e8-124">ディレクター</span><span class="sxs-lookup"><span data-stu-id="d41e8-124">Director</span></span></p></td>
<td><p><span data-ttu-id="d41e8-125">リバース プロキシからの公開済みダイヤルイン Web サービス</span><span class="sxs-lookup"><span data-stu-id="d41e8-125">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d41e8-126">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="d41e8-126">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d41e8-127">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d41e8-127">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d41e8-128">ディレクター</span><span class="sxs-lookup"><span data-stu-id="d41e8-128">Director</span></span></p></td>
<td><p><span data-ttu-id="d41e8-129">リバース プロキシからの公開済みミーティング Web サービス</span><span class="sxs-lookup"><span data-stu-id="d41e8-129">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d41e8-130">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="d41e8-130">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d41e8-131">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d41e8-131">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d41e8-132">ディレクター</span><span class="sxs-lookup"><span data-stu-id="d41e8-132">Director</span></span></p></td>
<td><p><span data-ttu-id="d41e8-133">リバースプロキシの Web チケット外部 web サービスによって発行され、ディレクター用に定義される</span><span class="sxs-lookup"><span data-stu-id="d41e8-133">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

