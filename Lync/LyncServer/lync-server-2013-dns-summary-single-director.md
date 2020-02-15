---
title: 'Lync Server 2013: DNS の概要-単一ディレクター'
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
ms.openlocfilehash: 44bcd52c2e7d13ef57e96e4ae5dc8841a58bc3d9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="11bb7-102">DNS の概要-Lync Server 2013 の単一ディレクター</span><span class="sxs-lookup"><span data-stu-id="11bb7-102">DNS summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11bb7-103">_**トピックの最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="11bb7-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="11bb7-104">次の表に、単一ディレクターのサポートに必要な DNS レコードの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="11bb7-104">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="11bb7-105">ディレクターの役割では、フロントエンドサーバーと同様の DNS レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="11bb7-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="11bb7-106">必要なレコード数は、ディレクター証明書で必要なサブジェクトの別名に反映されます。</span><span class="sxs-lookup"><span data-stu-id="11bb7-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="11bb7-107">フロントエンドサーバーとは異なり、ディレクターはユーザーアカウントをホストしたり、モビリティサービスをホストしたりしません。</span><span class="sxs-lookup"><span data-stu-id="11bb7-107">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="11bb7-108">ディレクターに必要な DNS レコード</span><span class="sxs-lookup"><span data-stu-id="11bb7-108">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11bb7-109">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="11bb7-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="11bb7-110">FQDN/DNS レコード</span><span class="sxs-lookup"><span data-stu-id="11bb7-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="11bb7-111">IP アドレス/FQDN</span><span class="sxs-lookup"><span data-stu-id="11bb7-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="11bb7-112">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="11bb7-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11bb7-113">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="11bb7-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="11bb7-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="11bb7-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="11bb7-115">ディレクター</span><span class="sxs-lookup"><span data-stu-id="11bb7-115">Director</span></span></p></td>
<td><p><span data-ttu-id="11bb7-116">レプリケーションおよびサーバー間で使用されるディレクターホストレコード</span><span class="sxs-lookup"><span data-stu-id="11bb7-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11bb7-117">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="11bb7-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="11bb7-118">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="11bb7-118">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="11bb7-119">ディレクター</span><span class="sxs-lookup"><span data-stu-id="11bb7-119">Director</span></span></p></td>
<td><p><span data-ttu-id="11bb7-120">エッジサーバーの内部エッジインターフェイスからの受信セッション開始プロトコル (SIP)</span><span class="sxs-lookup"><span data-stu-id="11bb7-120">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11bb7-121">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="11bb7-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="11bb7-122">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="11bb7-122">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="11bb7-123">ディレクター</span><span class="sxs-lookup"><span data-stu-id="11bb7-123">Director</span></span></p></td>
<td><p><span data-ttu-id="11bb7-124">リバース プロキシからの公開済みダイヤルイン Web サービス</span><span class="sxs-lookup"><span data-stu-id="11bb7-124">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11bb7-125">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="11bb7-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="11bb7-126">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="11bb7-126">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="11bb7-127">ディレクター</span><span class="sxs-lookup"><span data-stu-id="11bb7-127">Director</span></span></p></td>
<td><p><span data-ttu-id="11bb7-128">リバース プロキシからの公開済みミーティング Web サービス</span><span class="sxs-lookup"><span data-stu-id="11bb7-128">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11bb7-129">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="11bb7-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="11bb7-130">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="11bb7-130">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="11bb7-131">ディレクター</span><span class="sxs-lookup"><span data-stu-id="11bb7-131">Director</span></span></p></td>
<td><p><span data-ttu-id="11bb7-132">リバースプロキシの Web チケット外部 web サービスによって発行され、ディレクター用に定義される</span><span class="sxs-lookup"><span data-stu-id="11bb7-132">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

