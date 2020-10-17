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
ms.openlocfilehash: c5fdc4c3b20bdd60d2c8013b79a15bdfd30b56af
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536934"
---
# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="28200-102">Lync Server 2013 の Devices テーブル</span><span class="sxs-lookup"><span data-stu-id="28200-102">Devices table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28200-103">_**トピックの最終更新日:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="28200-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="28200-p101">Devices テーブルは、サポート テーブルです。各レコードには、1 つのデバイス (卓上電話) に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="28200-p101">The Devices table is a supporting table. Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="28200-106">Column</span><span class="sxs-lookup"><span data-stu-id="28200-106">Column</span></span></th>
<th><span data-ttu-id="28200-107">データ型</span><span class="sxs-lookup"><span data-stu-id="28200-107">Data Type</span></span></th>
<th><span data-ttu-id="28200-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="28200-108">Key/Index</span></span></th>
<th><span data-ttu-id="28200-109">詳細</span><span class="sxs-lookup"><span data-stu-id="28200-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28200-110"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="28200-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="28200-111">int</span><span class="sxs-lookup"><span data-stu-id="28200-111">int</span></span></p></td>
<td><p><span data-ttu-id="28200-112">Primary</span><span class="sxs-lookup"><span data-stu-id="28200-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="28200-113">このハードウェア バージョンを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="28200-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28200-114"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="28200-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="28200-115">int</span><span class="sxs-lookup"><span data-stu-id="28200-115">int</span></span></p></td>
<td><p><span data-ttu-id="28200-116">外部</span><span class="sxs-lookup"><span data-stu-id="28200-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="28200-117">このデバイスの製造元。</span><span class="sxs-lookup"><span data-stu-id="28200-117">Manufacturer of this device.</span></span> <span data-ttu-id="28200-118">詳細については、「 <a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 の製造元</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28200-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28200-119"><strong>ハードウェア Versionid</strong></span><span class="sxs-lookup"><span data-stu-id="28200-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="28200-120">int</span><span class="sxs-lookup"><span data-stu-id="28200-120">int</span></span></p></td>
<td><p><span data-ttu-id="28200-121">外部</span><span class="sxs-lookup"><span data-stu-id="28200-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="28200-122">このデバイスのハードウェア バージョン。</span><span class="sxs-lookup"><span data-stu-id="28200-122">Hardware version of this device.</span></span> <span data-ttu-id="28200-123">詳細については、「 <a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 のハードウェアバージョン表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28200-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28200-124"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="28200-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="28200-125">bigint</span><span class="sxs-lookup"><span data-stu-id="28200-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="28200-126">MAC アドレス</span><span class="sxs-lookup"><span data-stu-id="28200-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

