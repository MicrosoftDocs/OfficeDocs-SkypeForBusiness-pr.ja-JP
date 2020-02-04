---
title: 'Lync Server 2013: サーバー テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server table
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398801(v=OCS.15)
ms:contentKeyID: 48184890
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1d0cdb5733e6fc6e21d1dcda1fff6214332de6b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="103cd-102">Lync Server 2013 のサーバー テーブル</span><span class="sxs-lookup"><span data-stu-id="103cd-102">Server table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="103cd-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="103cd-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="103cd-104">サーバーテーブルは、サポートされているテーブルです。</span><span class="sxs-lookup"><span data-stu-id="103cd-104">The Server table is a supporting table.</span></span> <span data-ttu-id="103cd-105">各レコードは1つのサーバーを表します。</span><span class="sxs-lookup"><span data-stu-id="103cd-105">Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="103cd-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="103cd-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="103cd-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="103cd-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="103cd-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="103cd-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="103cd-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="103cd-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="103cd-110"><strong>ServerKey</strong></span><span class="sxs-lookup"><span data-stu-id="103cd-110"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="103cd-111">int</span><span class="sxs-lookup"><span data-stu-id="103cd-111">int</span></span></p></td>
<td><p><span data-ttu-id="103cd-112">Primary</span><span class="sxs-lookup"><span data-stu-id="103cd-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="103cd-113">サーバーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="103cd-113">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="103cd-114"><strong>同一の Dnorip</strong></span><span class="sxs-lookup"><span data-stu-id="103cd-114"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="103cd-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="103cd-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="103cd-116">位置</span><span class="sxs-lookup"><span data-stu-id="103cd-116">index</span></span></p></td>
<td><p><span data-ttu-id="103cd-117">MAC アドレス文字列。</span><span class="sxs-lookup"><span data-stu-id="103cd-117">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="103cd-118"><strong>ServerType</strong></span><span class="sxs-lookup"><span data-stu-id="103cd-118"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="103cd-119">int</span><span class="sxs-lookup"><span data-stu-id="103cd-119">int</span></span></p></td>
<td><p><span data-ttu-id="103cd-120">外部</span><span class="sxs-lookup"><span data-stu-id="103cd-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="103cd-121">1: 仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="103cd-121">1: Mediation Server</span></span></p>
<p><span data-ttu-id="103cd-122">2: a/v 会議 Server16394: A/V Edge service32769: ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="103cd-122">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="103cd-123"><strong>PoolName</strong></span><span class="sxs-lookup"><span data-stu-id="103cd-123"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="103cd-124">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="103cd-124">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="103cd-125">サーバーが所属するプール。</span><span class="sxs-lookup"><span data-stu-id="103cd-125">Pool the server belongs to.</span></span> <span data-ttu-id="103cd-126">A/V 会議サーバーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="103cd-126">Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="103cd-127"><strong>Nextupdatupdat</strong></span><span class="sxs-lookup"><span data-stu-id="103cd-127"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="103cd-128">datetime</span><span class="sxs-lookup"><span data-stu-id="103cd-128">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="103cd-129">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="103cd-129">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

