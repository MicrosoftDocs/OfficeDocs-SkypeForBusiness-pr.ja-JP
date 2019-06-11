---
title: 'Lync Server 2013: Devices テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Devices table
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398351(v=OCS.15)
ms:contentKeyID: 48184169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f78e0b4ba3bb5271a2de43e423dfa4b3baf17cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="c659b-102">Lync Server 2013 の Devices テーブル</span><span class="sxs-lookup"><span data-stu-id="c659b-102">Devices table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c659b-103">_**最終更新日:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="c659b-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="c659b-104">Devices テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="c659b-104">The Devices table is a supporting table.</span></span> <span data-ttu-id="c659b-105">各レコードには、1つのデバイス (卓上電話) に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="c659b-105">Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c659b-106">列</span><span class="sxs-lookup"><span data-stu-id="c659b-106">Column</span></span></th>
<th><span data-ttu-id="c659b-107">データ型</span><span class="sxs-lookup"><span data-stu-id="c659b-107">Data Type</span></span></th>
<th><span data-ttu-id="c659b-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="c659b-108">Key/Index</span></span></th>
<th><span data-ttu-id="c659b-109">詳細</span><span class="sxs-lookup"><span data-stu-id="c659b-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c659b-110"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="c659b-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="c659b-111">int</span><span class="sxs-lookup"><span data-stu-id="c659b-111">int</span></span></p></td>
<td><p><span data-ttu-id="c659b-112">Primary</span><span class="sxs-lookup"><span data-stu-id="c659b-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="c659b-113">このハードウェアバージョンを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="c659b-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c659b-114"><strong>Manufacturerid]</strong></span><span class="sxs-lookup"><span data-stu-id="c659b-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="c659b-115">int</span><span class="sxs-lookup"><span data-stu-id="c659b-115">int</span></span></p></td>
<td><p><span data-ttu-id="c659b-116">外部</span><span class="sxs-lookup"><span data-stu-id="c659b-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c659b-117">このデバイスの製造元。</span><span class="sxs-lookup"><span data-stu-id="c659b-117">Manufacturer of this device.</span></span> <span data-ttu-id="c659b-118">詳細については、「 <a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 の製造元の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c659b-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c659b-119"><strong>ハードウェアの Versionid</strong></span><span class="sxs-lookup"><span data-stu-id="c659b-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="c659b-120">int</span><span class="sxs-lookup"><span data-stu-id="c659b-120">int</span></span></p></td>
<td><p><span data-ttu-id="c659b-121">外部</span><span class="sxs-lookup"><span data-stu-id="c659b-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c659b-122">このデバイスのハードウェアバージョン。</span><span class="sxs-lookup"><span data-stu-id="c659b-122">Hardware version of this device.</span></span> <span data-ttu-id="c659b-123">詳細については、「 <a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 のハードウェアバージョンの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c659b-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c659b-124"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="c659b-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="c659b-125">bigint</span><span class="sxs-lookup"><span data-stu-id="c659b-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c659b-126">MAC アドレス</span><span class="sxs-lookup"><span data-stu-id="c659b-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

