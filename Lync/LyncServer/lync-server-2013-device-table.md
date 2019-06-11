---
title: 'Lync Server 2013: Device テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device table
ms:assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398930(v=OCS.15)
ms:contentKeyID: 48185544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 974898f6c3fa96dd9356a0a9eed1e3fab09d288b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-table-in-lync-server-2013"></a><span data-ttu-id="ed35a-102">Lync Server 2013 の Device テーブル</span><span class="sxs-lookup"><span data-stu-id="ed35a-102">Device table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed35a-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ed35a-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ed35a-104">Device テーブルは、さまざまなキャプチャデバイスやレンダリングデバイスに関する情報を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="ed35a-104">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="ed35a-105">テーブル内の各レコードは、1つのデバイスを表します。</span><span class="sxs-lookup"><span data-stu-id="ed35a-105">Each record in the table represents one device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed35a-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="ed35a-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ed35a-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="ed35a-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ed35a-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="ed35a-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ed35a-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="ed35a-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed35a-110"><strong>DeviceKey</strong></span><span class="sxs-lookup"><span data-stu-id="ed35a-110"><strong>DeviceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ed35a-111">int</span><span class="sxs-lookup"><span data-stu-id="ed35a-111">int</span></span></p></td>
<td><p><span data-ttu-id="ed35a-112">Primary</span><span class="sxs-lookup"><span data-stu-id="ed35a-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ed35a-113">このデバイスを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="ed35a-113">Unique number identifying this device.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed35a-114"><strong>DeviceName</strong></span><span class="sxs-lookup"><span data-stu-id="ed35a-114"><strong>DeviceName</strong></span></span></p></td>
<td><p><span data-ttu-id="ed35a-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ed35a-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ed35a-116">DeviceName + DeviceType の固有のキー</span><span class="sxs-lookup"><span data-stu-id="ed35a-116">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="ed35a-117">デバイス名。</span><span class="sxs-lookup"><span data-stu-id="ed35a-117">Device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed35a-118"><strong>DeviceType</strong></span><span class="sxs-lookup"><span data-stu-id="ed35a-118"><strong>DeviceType</strong></span></span></p></td>
<td><p><span data-ttu-id="ed35a-119">bit</span><span class="sxs-lookup"><span data-stu-id="ed35a-119">bit</span></span></p></td>
<td><p><span data-ttu-id="ed35a-120">DeviceName + DeviceType の固有のキー</span><span class="sxs-lookup"><span data-stu-id="ed35a-120">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="ed35a-121">デバイスの種類。</span><span class="sxs-lookup"><span data-stu-id="ed35a-121">Device type.</span></span> <span data-ttu-id="ed35a-122">1はキャプチャデバイス、0はレンダーデバイスです。</span><span class="sxs-lookup"><span data-stu-id="ed35a-122">1 is a capture device, 0 is a render device.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

