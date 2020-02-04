---
title: 'Lync Server 2013: DNS の概要 - 単一ディレクター'
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
ms.openlocfilehash: 71fb3052de36a92afb4ed9076820f7fcb2b54997
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="27158-102">DNS の概要 - Lync Server 2013 の単一ディレクター</span><span class="sxs-lookup"><span data-stu-id="27158-102">DNS summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27158-103">_**最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="27158-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="27158-104">次の表には、1つのディレクターをサポートするために必要な DNS レコードの概要が記載されています。</span><span class="sxs-lookup"><span data-stu-id="27158-104">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="27158-105">ディレクターの役割には、フロントエンドサーバーと同様の DNS レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="27158-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="27158-106">必要なレコードの数は、ディレクター証明書に必要なサブジェクトの代替名に反映されます。</span><span class="sxs-lookup"><span data-stu-id="27158-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="27158-107">フロントエンドサーバーとは異なり、ディレクターはユーザーアカウントをホストしないか、モビリティサービスをホストしません。</span><span class="sxs-lookup"><span data-stu-id="27158-107">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="27158-108">ディレクターに必要な DNS レコード</span><span class="sxs-lookup"><span data-stu-id="27158-108">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27158-109">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="27158-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="27158-110">FQDN/DNS レコード</span><span class="sxs-lookup"><span data-stu-id="27158-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="27158-111">IP アドレス/FQDN</span><span class="sxs-lookup"><span data-stu-id="27158-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="27158-112">マップ先/コメント</span><span class="sxs-lookup"><span data-stu-id="27158-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27158-113">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="27158-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="27158-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="27158-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="27158-115">ディレクター</span><span class="sxs-lookup"><span data-stu-id="27158-115">Director</span></span></p></td>
<td><p><span data-ttu-id="27158-116">レプリケーションとサーバー間で使用されるディレクターホストレコード</span><span class="sxs-lookup"><span data-stu-id="27158-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27158-117">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="27158-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="27158-118">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27158-118">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="27158-119">ディレクター</span><span class="sxs-lookup"><span data-stu-id="27158-119">Director</span></span></p></td>
<td><p><span data-ttu-id="27158-120">エッジサーバーの内部エッジインターフェイスからの受信セッション開始プロトコル (SIP)</span><span class="sxs-lookup"><span data-stu-id="27158-120">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27158-121">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="27158-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="27158-122">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27158-122">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="27158-123">ディレクター</span><span class="sxs-lookup"><span data-stu-id="27158-123">Director</span></span></p></td>
<td><p><span data-ttu-id="27158-124">リバースプロキシから公開されたダイヤルインの web サービス</span><span class="sxs-lookup"><span data-stu-id="27158-124">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27158-125">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="27158-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="27158-126">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27158-126">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="27158-127">ディレクター</span><span class="sxs-lookup"><span data-stu-id="27158-127">Director</span></span></p></td>
<td><p><span data-ttu-id="27158-128">リバースプロキシから発行された web サービス</span><span class="sxs-lookup"><span data-stu-id="27158-128">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27158-129">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="27158-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="27158-130">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27158-130">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="27158-131">ディレクター</span><span class="sxs-lookup"><span data-stu-id="27158-131">Director</span></span></p></td>
<td><p><span data-ttu-id="27158-132">リバースプロキシ Web チケットによって公開および定義されるディレクターの外部 web サービス</span><span class="sxs-lookup"><span data-stu-id="27158-132">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

