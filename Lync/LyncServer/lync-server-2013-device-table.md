---
title: 'Lync Server 2013: デバイステーブル'
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
ms.openlocfilehash: 1040642874d2963292744eb2543c9ee265440fd2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="device-table-in-lync-server-2013"></a><span data-ttu-id="a238b-102">Lync Server 2013 のデバイステーブル</span><span class="sxs-lookup"><span data-stu-id="a238b-102">Device table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a238b-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a238b-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a238b-104">デバイステーブルは、さまざまなキャプチャまたはレンダーデバイスに関する情報を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="a238b-104">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="a238b-105">テーブル内の各レコードは、1つのデバイスを表します。</span><span class="sxs-lookup"><span data-stu-id="a238b-105">Each record in the table represents one device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a238b-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="a238b-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a238b-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="a238b-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a238b-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="a238b-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a238b-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="a238b-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a238b-110"><strong>DeviceKey</strong></span><span class="sxs-lookup"><span data-stu-id="a238b-110"><strong>DeviceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="a238b-111">int</span><span class="sxs-lookup"><span data-stu-id="a238b-111">int</span></span></p></td>
<td><p><span data-ttu-id="a238b-112">Primary</span><span class="sxs-lookup"><span data-stu-id="a238b-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="a238b-113">このデバイスを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="a238b-113">Unique number identifying this device.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a238b-114"><strong>DeviceName</strong></span><span class="sxs-lookup"><span data-stu-id="a238b-114"><strong>DeviceName</strong></span></span></p></td>
<td><p><span data-ttu-id="a238b-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a238b-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a238b-116">DeviceName + DeviceType は一意</span><span class="sxs-lookup"><span data-stu-id="a238b-116">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="a238b-117">デバイス名。</span><span class="sxs-lookup"><span data-stu-id="a238b-117">Device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a238b-118"><strong>DeviceType</strong></span><span class="sxs-lookup"><span data-stu-id="a238b-118"><strong>DeviceType</strong></span></span></p></td>
<td><p><span data-ttu-id="a238b-119">若干</span><span class="sxs-lookup"><span data-stu-id="a238b-119">bit</span></span></p></td>
<td><p><span data-ttu-id="a238b-120">DeviceName + DeviceType は一意</span><span class="sxs-lookup"><span data-stu-id="a238b-120">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="a238b-121">デバイスの種類。</span><span class="sxs-lookup"><span data-stu-id="a238b-121">Device type.</span></span> <span data-ttu-id="a238b-122">1はキャプチャデバイス、0はレンダーデバイスです。</span><span class="sxs-lookup"><span data-stu-id="a238b-122">1 is a capture device, 0 is a render device.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

