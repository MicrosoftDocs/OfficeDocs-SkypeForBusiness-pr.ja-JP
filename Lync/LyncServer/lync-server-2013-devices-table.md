---
title: 'Lync Server 2013: Devices テーブル'
description: 'Lync Server 2013: Devices テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Devices table
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398351(v=OCS.15)
ms:contentKeyID: 48184169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 763e1788e2874f9f9831c089ffe8fa077621b030
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576243"
---
# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="c0881-103">Lync Server 2013 の Devices テーブル</span><span class="sxs-lookup"><span data-stu-id="c0881-103">Devices table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0881-104">_**トピックの最終更新日:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="c0881-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="c0881-p101">Devices テーブルは、サポート テーブルです。各レコードには、1 つのデバイス (卓上電話) に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="c0881-p101">The Devices table is a supporting table. Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0881-107">Column</span><span class="sxs-lookup"><span data-stu-id="c0881-107">Column</span></span></th>
<th><span data-ttu-id="c0881-108">データ型</span><span class="sxs-lookup"><span data-stu-id="c0881-108">Data Type</span></span></th>
<th><span data-ttu-id="c0881-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="c0881-109">Key/Index</span></span></th>
<th><span data-ttu-id="c0881-110">詳細</span><span class="sxs-lookup"><span data-stu-id="c0881-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0881-111"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="c0881-111"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="c0881-112">int</span><span class="sxs-lookup"><span data-stu-id="c0881-112">int</span></span></p></td>
<td><p><span data-ttu-id="c0881-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c0881-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="c0881-114">このハードウェア バージョンを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="c0881-114">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0881-115"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="c0881-115"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="c0881-116">int</span><span class="sxs-lookup"><span data-stu-id="c0881-116">int</span></span></p></td>
<td><p><span data-ttu-id="c0881-117">外部</span><span class="sxs-lookup"><span data-stu-id="c0881-117">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c0881-118">このデバイスの製造元。</span><span class="sxs-lookup"><span data-stu-id="c0881-118">Manufacturer of this device.</span></span> <span data-ttu-id="c0881-119">詳細については、「 <a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 の製造元</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0881-119">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0881-120"><strong>ハードウェア Versionid</strong></span><span class="sxs-lookup"><span data-stu-id="c0881-120"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="c0881-121">int</span><span class="sxs-lookup"><span data-stu-id="c0881-121">int</span></span></p></td>
<td><p><span data-ttu-id="c0881-122">外部</span><span class="sxs-lookup"><span data-stu-id="c0881-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c0881-123">このデバイスのハードウェア バージョン。</span><span class="sxs-lookup"><span data-stu-id="c0881-123">Hardware version of this device.</span></span> <span data-ttu-id="c0881-124">詳細については、「 <a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 のハードウェアバージョン表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0881-124">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0881-125"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="c0881-125"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="c0881-126">bigint</span><span class="sxs-lookup"><span data-stu-id="c0881-126">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0881-127">MAC アドレス</span><span class="sxs-lookup"><span data-stu-id="c0881-127">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

