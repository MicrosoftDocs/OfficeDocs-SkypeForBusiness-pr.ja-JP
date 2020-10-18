---
title: 'Lync Server 2013: サーバーテーブル'
description: 'Lync Server 2013: サーバーテーブル。'
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
ms.openlocfilehash: 00990a91aec64063480d96a16380171990913ad4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576523"
---
# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="3608e-103">Lync Server 2013 のサーバーテーブル</span><span class="sxs-lookup"><span data-stu-id="3608e-103">Server table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3608e-104">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="3608e-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="3608e-p101">サーバー テーブルは補助的なテーブルです。個々のレコードが 1 つのサーバーを表します。</span><span class="sxs-lookup"><span data-stu-id="3608e-p101">The Server table is a supporting table. Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3608e-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="3608e-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="3608e-108"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="3608e-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="3608e-109"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="3608e-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="3608e-110"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="3608e-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3608e-111"><strong>ServerKey</strong></span><span class="sxs-lookup"><span data-stu-id="3608e-111"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="3608e-112">int</span><span class="sxs-lookup"><span data-stu-id="3608e-112">int</span></span></p></td>
<td><p><span data-ttu-id="3608e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="3608e-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="3608e-114">サーバーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="3608e-114">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3608e-115"><strong>一の Dnorip</strong></span><span class="sxs-lookup"><span data-stu-id="3608e-115"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="3608e-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3608e-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3608e-117">index</span><span class="sxs-lookup"><span data-stu-id="3608e-117">index</span></span></p></td>
<td><p><span data-ttu-id="3608e-118">MAC アドレス文字列。</span><span class="sxs-lookup"><span data-stu-id="3608e-118">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3608e-119"><strong>ServerType</strong></span><span class="sxs-lookup"><span data-stu-id="3608e-119"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="3608e-120">int</span><span class="sxs-lookup"><span data-stu-id="3608e-120">int</span></span></p></td>
<td><p><span data-ttu-id="3608e-121">外部</span><span class="sxs-lookup"><span data-stu-id="3608e-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3608e-122">1: 仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="3608e-122">1: Mediation Server</span></span></p>
<p><span data-ttu-id="3608e-123">2: 音声ビデオ会議サーバー16394: 音声ビデオ エッジ サービス 32769: ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="3608e-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3608e-124"><strong>PoolName</strong></span><span class="sxs-lookup"><span data-stu-id="3608e-124"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="3608e-125">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="3608e-125">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3608e-p102">サーバーが所属するプール。音声ビデオ会議サーバーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="3608e-p102">Pool the server belongs to. Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3608e-128"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="3608e-128"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="3608e-129">日付型</span><span class="sxs-lookup"><span data-stu-id="3608e-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3608e-130">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="3608e-130">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

