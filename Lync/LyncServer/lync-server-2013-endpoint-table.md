---
title: 'Lync Server 2013: Endpoint テーブル'
description: 'Lync Server 2013: Endpoint テーブル。'
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
ms.openlocfilehash: 614872eee41b5d8e56da4b96cf5bbe3a4a1cf4d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575623"
---
# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="c0487-103">Lync Server 2013 のエンドポイントテーブル</span><span class="sxs-lookup"><span data-stu-id="c0487-103">Endpoint table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0487-104">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c0487-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c0487-105">エンドポイントテーブルは、データベースに記録されたセッションに参加しているエンドポイントに関する情報を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="c0487-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="c0487-106">テーブル内の各レコードは、1つのエンドポイントを表します。</span><span class="sxs-lookup"><span data-stu-id="c0487-106">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0487-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="c0487-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c0487-108"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="c0487-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c0487-109"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="c0487-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c0487-110"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="c0487-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0487-111"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="c0487-111"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="c0487-112">int</span><span class="sxs-lookup"><span data-stu-id="c0487-112">int</span></span></p></td>
<td><p><span data-ttu-id="c0487-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c0487-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="c0487-114">このエンドポイントを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="c0487-114">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0487-115"><strong>名前</strong></span><span class="sxs-lookup"><span data-stu-id="c0487-115"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="c0487-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c0487-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c0487-117">一意</span><span class="sxs-lookup"><span data-stu-id="c0487-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="c0487-118">エンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="c0487-118">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0487-119"><strong>OS</strong></span><span class="sxs-lookup"><span data-stu-id="c0487-119"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="c0487-120">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="c0487-120">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c0487-121">エンドポイントのオペレーティングシステム (OS)。</span><span class="sxs-lookup"><span data-stu-id="c0487-121">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0487-122"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="c0487-122"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="c0487-123">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="c0487-123">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0487-124">エンドポイントの CPU 名。</span><span class="sxs-lookup"><span data-stu-id="c0487-124">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0487-125"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="c0487-125"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="c0487-126">smallint</span><span class="sxs-lookup"><span data-stu-id="c0487-126">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0487-127">エンドポイントの CPU コアの数。</span><span class="sxs-lookup"><span data-stu-id="c0487-127">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0487-128"><strong>Cpu プロセッサ速度</strong></span><span class="sxs-lookup"><span data-stu-id="c0487-128"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="c0487-129">int</span><span class="sxs-lookup"><span data-stu-id="c0487-129">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0487-130">エンドポイントの CPU プロセッサ速度。</span><span class="sxs-lookup"><span data-stu-id="c0487-130">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0487-131"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="c0487-131"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="c0487-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="c0487-132">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0487-133">システムが仮想化環境で実行されているかどうかを示すビットフラグ。</span><span class="sxs-lookup"><span data-stu-id="c0487-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="c0487-134">0x0000 –なし</span><span class="sxs-lookup"><span data-stu-id="c0487-134">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="c0487-135">0x0001 – HyperV</span><span class="sxs-lookup"><span data-stu-id="c0487-135">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="c0487-136">0x0002 –ヴイエムウェア</span><span class="sxs-lookup"><span data-stu-id="c0487-136">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="c0487-137">0x0004 –仮想 PC</span><span class="sxs-lookup"><span data-stu-id="c0487-137">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="c0487-138">0x0008 – Xen PC</span><span class="sxs-lookup"><span data-stu-id="c0487-138">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

