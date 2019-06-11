---
title: 'Lync Server 2013: Endpoint テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Endpoint table
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48184098
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cedf4d85cefd8a9fefb9f0ee4608f4a290fdc09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="a0abe-102">Lync Server 2013 の Endpoint テーブル</span><span class="sxs-lookup"><span data-stu-id="a0abe-102">Endpoint table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0abe-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a0abe-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a0abe-104">エンドポイントテーブルは、データベースに記録されているセッションに参加しているエンドポイントに関する情報を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="a0abe-104">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="a0abe-105">テーブル内の各レコードは、1つのエンドポイントを表します。</span><span class="sxs-lookup"><span data-stu-id="a0abe-105">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0abe-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="a0abe-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a0abe-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="a0abe-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a0abe-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="a0abe-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a0abe-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="a0abe-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0abe-110"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="a0abe-110"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="a0abe-111">int</span><span class="sxs-lookup"><span data-stu-id="a0abe-111">int</span></span></p></td>
<td><p><span data-ttu-id="a0abe-112">Primary</span><span class="sxs-lookup"><span data-stu-id="a0abe-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="a0abe-113">このエンドポイントを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="a0abe-113">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0abe-114"><strong>名前</strong></span><span class="sxs-lookup"><span data-stu-id="a0abe-114"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="a0abe-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a0abe-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a0abe-116">一意</span><span class="sxs-lookup"><span data-stu-id="a0abe-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="a0abe-117">エンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="a0abe-117">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0abe-118"><strong>OS</strong></span><span class="sxs-lookup"><span data-stu-id="a0abe-118"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="a0abe-119">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="a0abe-119">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a0abe-120">エンドポイントのオペレーティングシステム (OS)。</span><span class="sxs-lookup"><span data-stu-id="a0abe-120">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0abe-121"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="a0abe-121"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="a0abe-122">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="a0abe-122">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a0abe-123">エンドポイントの CPU 名。</span><span class="sxs-lookup"><span data-stu-id="a0abe-123">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0abe-124"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="a0abe-124"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="a0abe-125">smallint</span><span class="sxs-lookup"><span data-stu-id="a0abe-125">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a0abe-126">エンドポイントの CPU コアの数。</span><span class="sxs-lookup"><span data-stu-id="a0abe-126">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0abe-127"><strong>プロセッサーの速度</strong></span><span class="sxs-lookup"><span data-stu-id="a0abe-127"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="a0abe-128">int</span><span class="sxs-lookup"><span data-stu-id="a0abe-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a0abe-129">エンドポイントの CPU プロセッサの速度。</span><span class="sxs-lookup"><span data-stu-id="a0abe-129">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0abe-130"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="a0abe-130"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="a0abe-131">tinyint</span><span class="sxs-lookup"><span data-stu-id="a0abe-131">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a0abe-132">システムが仮想環境で実行されているかどうかを示すビットフラグ。</span><span class="sxs-lookup"><span data-stu-id="a0abe-132">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="a0abe-133">0x0000 –なし</span><span class="sxs-lookup"><span data-stu-id="a0abe-133">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="a0abe-134">0x0001 – HyperV</span><span class="sxs-lookup"><span data-stu-id="a0abe-134">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="a0abe-135">0x0002 –ヴイエムウェア</span><span class="sxs-lookup"><span data-stu-id="a0abe-135">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="a0abe-136">0x0004 –仮想 PC</span><span class="sxs-lookup"><span data-stu-id="a0abe-136">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="a0abe-137">0x0008 – Xen PC</span><span class="sxs-lookup"><span data-stu-id="a0abe-137">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

