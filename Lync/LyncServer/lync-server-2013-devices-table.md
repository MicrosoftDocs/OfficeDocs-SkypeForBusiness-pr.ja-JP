---
title: 'Lync Server 2013: Devices テーブル'
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
ms.openlocfilehash: 9c6e1fb5afda3a657bbeff864f5bba06349f4fb4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="5a739-102">Lync Server 2013 の Devices テーブル</span><span class="sxs-lookup"><span data-stu-id="5a739-102">Devices table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a739-103">_**トピックの最終更新日:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="5a739-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="5a739-p101">Devices テーブルは、サポート テーブルです。各レコードには、1 つのデバイス (卓上電話) に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="5a739-p101">The Devices table is a supporting table. Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5a739-106">列</span><span class="sxs-lookup"><span data-stu-id="5a739-106">Column</span></span></th>
<th><span data-ttu-id="5a739-107">データ型</span><span class="sxs-lookup"><span data-stu-id="5a739-107">Data Type</span></span></th>
<th><span data-ttu-id="5a739-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="5a739-108">Key/Index</span></span></th>
<th><span data-ttu-id="5a739-109">詳細</span><span class="sxs-lookup"><span data-stu-id="5a739-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a739-110"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="5a739-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="5a739-111">int</span><span class="sxs-lookup"><span data-stu-id="5a739-111">int</span></span></p></td>
<td><p><span data-ttu-id="5a739-112">Primary</span><span class="sxs-lookup"><span data-stu-id="5a739-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="5a739-113">このハードウェア バージョンを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="5a739-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a739-114"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="5a739-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="5a739-115">int</span><span class="sxs-lookup"><span data-stu-id="5a739-115">int</span></span></p></td>
<td><p><span data-ttu-id="5a739-116">外部</span><span class="sxs-lookup"><span data-stu-id="5a739-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5a739-117">このデバイスの製造元。</span><span class="sxs-lookup"><span data-stu-id="5a739-117">Manufacturer of this device.</span></span> <span data-ttu-id="5a739-118">詳細については、「 <a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 の製造元</a>」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a739-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a739-119"><strong>ハードウェア Versionid</strong></span><span class="sxs-lookup"><span data-stu-id="5a739-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="5a739-120">int</span><span class="sxs-lookup"><span data-stu-id="5a739-120">int</span></span></p></td>
<td><p><span data-ttu-id="5a739-121">外部</span><span class="sxs-lookup"><span data-stu-id="5a739-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5a739-122">このデバイスのハードウェア バージョン。</span><span class="sxs-lookup"><span data-stu-id="5a739-122">Hardware version of this device.</span></span> <span data-ttu-id="5a739-123">詳細については、「 <a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 のハードウェアバージョン表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a739-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a739-124"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="5a739-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="5a739-125">bigint</span><span class="sxs-lookup"><span data-stu-id="5a739-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5a739-126">MAC アドレス</span><span class="sxs-lookup"><span data-stu-id="5a739-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

