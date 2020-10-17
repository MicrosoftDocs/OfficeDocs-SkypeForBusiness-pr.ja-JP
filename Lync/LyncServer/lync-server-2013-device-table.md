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
ms.openlocfilehash: 8bd5b62059329d9a2277e28f1a2ae08c25384bde
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522434"
---
# <a name="device-table-in-lync-server-2013"></a><span data-ttu-id="70575-102">Lync Server 2013 のデバイステーブル</span><span class="sxs-lookup"><span data-stu-id="70575-102">Device table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70575-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="70575-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="70575-104">デバイステーブルは、さまざまなキャプチャまたはレンダーデバイスに関する情報を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="70575-104">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="70575-105">テーブル内の各レコードは、1つのデバイスを表します。</span><span class="sxs-lookup"><span data-stu-id="70575-105">Each record in the table represents one device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70575-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="70575-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="70575-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="70575-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="70575-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="70575-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="70575-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="70575-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70575-110"><strong>DeviceKey</strong></span><span class="sxs-lookup"><span data-stu-id="70575-110"><strong>DeviceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="70575-111">int</span><span class="sxs-lookup"><span data-stu-id="70575-111">int</span></span></p></td>
<td><p><span data-ttu-id="70575-112">Primary</span><span class="sxs-lookup"><span data-stu-id="70575-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="70575-113">このデバイスを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="70575-113">Unique number identifying this device.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70575-114"><strong>DeviceName</strong></span><span class="sxs-lookup"><span data-stu-id="70575-114"><strong>DeviceName</strong></span></span></p></td>
<td><p><span data-ttu-id="70575-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="70575-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="70575-116">DeviceName + DeviceType は一意</span><span class="sxs-lookup"><span data-stu-id="70575-116">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="70575-117">デバイス名。</span><span class="sxs-lookup"><span data-stu-id="70575-117">Device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70575-118"><strong>DeviceType</strong></span><span class="sxs-lookup"><span data-stu-id="70575-118"><strong>DeviceType</strong></span></span></p></td>
<td><p><span data-ttu-id="70575-119">若干</span><span class="sxs-lookup"><span data-stu-id="70575-119">bit</span></span></p></td>
<td><p><span data-ttu-id="70575-120">DeviceName + DeviceType は一意</span><span class="sxs-lookup"><span data-stu-id="70575-120">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="70575-121">デバイスの種類。</span><span class="sxs-lookup"><span data-stu-id="70575-121">Device type.</span></span> <span data-ttu-id="70575-122">1はキャプチャデバイス、0はレンダーデバイスです。</span><span class="sxs-lookup"><span data-stu-id="70575-122">1 is a capture device, 0 is a render device.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

