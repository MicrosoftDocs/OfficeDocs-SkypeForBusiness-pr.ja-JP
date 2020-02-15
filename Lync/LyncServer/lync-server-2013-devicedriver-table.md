---
title: 'Lync Server 2013: DeviceDriver テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeviceDriver table
ms:assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398844(v=OCS.15)
ms:contentKeyID: 48185449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7431be7ceb964aead28b3c9fa76593c9dda891a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044859"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="devicedriver-table-in-lync-server-2013"></a><span data-ttu-id="7bab8-102">Lync Server 2013 の DeviceDriver テーブル</span><span class="sxs-lookup"><span data-stu-id="7bab8-102">DeviceDriver table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bab8-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7bab8-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7bab8-p101">DeviceDriver テーブルは、サポート テーブルです。各レコードは、キャプチャ デバイスまたはレンダー デバイスが使用するドライバーを表します。</span><span class="sxs-lookup"><span data-stu-id="7bab8-p101">The DeviceDriver table is a supporting table. Each record represents a driver used by either a capture device or render device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7bab8-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="7bab8-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7bab8-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="7bab8-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7bab8-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="7bab8-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7bab8-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="7bab8-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7bab8-110"><strong>DeviceDriverKey</strong></span><span class="sxs-lookup"><span data-stu-id="7bab8-110"><strong>DeviceDriverKey</strong></span></span></p></td>
<td><p><span data-ttu-id="7bab8-111">int</span><span class="sxs-lookup"><span data-stu-id="7bab8-111">int</span></span></p></td>
<td><p><span data-ttu-id="7bab8-112">Primary</span><span class="sxs-lookup"><span data-stu-id="7bab8-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="7bab8-113">このデバイス ドライバー レコードを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="7bab8-113">Unique number identifying this device driver record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bab8-114"><strong>DeviceDriver</strong></span><span class="sxs-lookup"><span data-stu-id="7bab8-114"><strong>DeviceDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="7bab8-115">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="7bab8-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7bab8-116">unique</span><span class="sxs-lookup"><span data-stu-id="7bab8-116">unique</span></span></p></td>
<td><p><span data-ttu-id="7bab8-117">デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="7bab8-117">Device driver name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

