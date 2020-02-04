---
title: 'Lync Server 2013: Endpoint テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Endpoint table
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48184098
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11da225da1a8120f5de7ac21b3beb318326601f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="aa10f-102">Lync Server 2013 の Endpoint テーブル</span><span class="sxs-lookup"><span data-stu-id="aa10f-102">Endpoint table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa10f-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="aa10f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="aa10f-104">エンドポイントテーブルは、データベースに記録されているセッションに参加しているエンドポイントに関する情報を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="aa10f-104">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="aa10f-105">テーブル内の各レコードは、1つのエンドポイントを表します。</span><span class="sxs-lookup"><span data-stu-id="aa10f-105">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa10f-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="aa10f-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="aa10f-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="aa10f-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="aa10f-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="aa10f-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="aa10f-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="aa10f-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa10f-110"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="aa10f-110"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="aa10f-111">int</span><span class="sxs-lookup"><span data-stu-id="aa10f-111">int</span></span></p></td>
<td><p><span data-ttu-id="aa10f-112">Primary</span><span class="sxs-lookup"><span data-stu-id="aa10f-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="aa10f-113">このエンドポイントを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="aa10f-113">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa10f-114"><strong>名前</strong></span><span class="sxs-lookup"><span data-stu-id="aa10f-114"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="aa10f-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="aa10f-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aa10f-116">一意</span><span class="sxs-lookup"><span data-stu-id="aa10f-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="aa10f-117">エンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="aa10f-117">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa10f-118"><strong>OS</strong></span><span class="sxs-lookup"><span data-stu-id="aa10f-118"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="aa10f-119">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="aa10f-119">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aa10f-120">エンドポイントのオペレーティングシステム (OS)。</span><span class="sxs-lookup"><span data-stu-id="aa10f-120">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa10f-121"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="aa10f-121"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="aa10f-122">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="aa10f-122">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aa10f-123">エンドポイントの CPU 名。</span><span class="sxs-lookup"><span data-stu-id="aa10f-123">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa10f-124"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="aa10f-124"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="aa10f-125">smallint</span><span class="sxs-lookup"><span data-stu-id="aa10f-125">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aa10f-126">エンドポイントの CPU コアの数。</span><span class="sxs-lookup"><span data-stu-id="aa10f-126">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa10f-127"><strong>プロセッサーの速度</strong></span><span class="sxs-lookup"><span data-stu-id="aa10f-127"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="aa10f-128">int</span><span class="sxs-lookup"><span data-stu-id="aa10f-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aa10f-129">エンドポイントの CPU プロセッサの速度。</span><span class="sxs-lookup"><span data-stu-id="aa10f-129">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa10f-130"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="aa10f-130"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="aa10f-131">tinyint</span><span class="sxs-lookup"><span data-stu-id="aa10f-131">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aa10f-132">システムが仮想環境で実行されているかどうかを示すビットフラグ。</span><span class="sxs-lookup"><span data-stu-id="aa10f-132">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="aa10f-133">0x0000 –なし</span><span class="sxs-lookup"><span data-stu-id="aa10f-133">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="aa10f-134">0x0001 – HyperV</span><span class="sxs-lookup"><span data-stu-id="aa10f-134">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="aa10f-135">0x0002 –ヴイエムウェア</span><span class="sxs-lookup"><span data-stu-id="aa10f-135">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="aa10f-136">0x0004 –仮想 PC</span><span class="sxs-lookup"><span data-stu-id="aa10f-136">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="aa10f-137">0x0008 – Xen PC</span><span class="sxs-lookup"><span data-stu-id="aa10f-137">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

