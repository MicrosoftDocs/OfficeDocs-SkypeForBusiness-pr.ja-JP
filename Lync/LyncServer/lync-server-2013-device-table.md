---
title: 'Lync Server 2013: デバイステーブル'
description: 'Lync Server 2013: デバイステーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device table
ms:assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398930(v=OCS.15)
ms:contentKeyID: 48185544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46de64a49eace52d62cbd6384fcae680b5c511b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575643"
---
# <a name="device-table-in-lync-server-2013"></a><span data-ttu-id="4f70d-103">Lync Server 2013 のデバイステーブル</span><span class="sxs-lookup"><span data-stu-id="4f70d-103">Device table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f70d-104">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="4f70d-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="4f70d-105">デバイステーブルは、さまざまなキャプチャまたはレンダーデバイスに関する情報を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="4f70d-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="4f70d-106">テーブル内の各レコードは、1つのデバイスを表します。</span><span class="sxs-lookup"><span data-stu-id="4f70d-106">Each record in the table represents one device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f70d-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="4f70d-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="4f70d-108"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="4f70d-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="4f70d-109"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="4f70d-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="4f70d-110"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="4f70d-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f70d-111"><strong>DeviceKey</strong></span><span class="sxs-lookup"><span data-stu-id="4f70d-111"><strong>DeviceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="4f70d-112">int</span><span class="sxs-lookup"><span data-stu-id="4f70d-112">int</span></span></p></td>
<td><p><span data-ttu-id="4f70d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="4f70d-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="4f70d-114">このデバイスを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="4f70d-114">Unique number identifying this device.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f70d-115"><strong>DeviceName</strong></span><span class="sxs-lookup"><span data-stu-id="4f70d-115"><strong>DeviceName</strong></span></span></p></td>
<td><p><span data-ttu-id="4f70d-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f70d-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f70d-117">DeviceName + DeviceType は一意</span><span class="sxs-lookup"><span data-stu-id="4f70d-117">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="4f70d-118">デバイス名。</span><span class="sxs-lookup"><span data-stu-id="4f70d-118">Device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f70d-119"><strong>DeviceType</strong></span><span class="sxs-lookup"><span data-stu-id="4f70d-119"><strong>DeviceType</strong></span></span></p></td>
<td><p><span data-ttu-id="4f70d-120">若干</span><span class="sxs-lookup"><span data-stu-id="4f70d-120">bit</span></span></p></td>
<td><p><span data-ttu-id="4f70d-121">DeviceName + DeviceType は一意</span><span class="sxs-lookup"><span data-stu-id="4f70d-121">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="4f70d-122">デバイスの種類。</span><span class="sxs-lookup"><span data-stu-id="4f70d-122">Device type.</span></span> <span data-ttu-id="4f70d-123">1はキャプチャデバイス、0はレンダーデバイスです。</span><span class="sxs-lookup"><span data-stu-id="4f70d-123">1 is a capture device, 0 is a render device.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

