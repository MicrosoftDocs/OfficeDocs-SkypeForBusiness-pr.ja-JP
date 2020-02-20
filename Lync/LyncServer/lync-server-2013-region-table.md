---
title: 'Lync Server 2013: Region テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Region table
ms:assetid: 1751a6aa-a6e8-4f16-8eb7-ae731c2e3ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398235(v=OCS.15)
ms:contentKeyID: 48183518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc53c7479d2ddaf3f3f2af6c987a7eb159340775
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="region-table-in-lync-server-2013"></a><span data-ttu-id="07e08-102">Lync Server 2013 の Region テーブル</span><span class="sxs-lookup"><span data-stu-id="07e08-102">Region table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07e08-103">_**トピックの最終更新日:** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="07e08-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="07e08-p101">Region テーブルはサポート テーブルです。各レコードは、ネットワーク構成設定で定義されている 1 つの国/地域を表します。</span><span class="sxs-lookup"><span data-stu-id="07e08-p101">The Region table is a supporting table. Each record represents one country/region defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07e08-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="07e08-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="07e08-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="07e08-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="07e08-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="07e08-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="07e08-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="07e08-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07e08-110"><strong>RegionKey</strong></span><span class="sxs-lookup"><span data-stu-id="07e08-110"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="07e08-111">int</span><span class="sxs-lookup"><span data-stu-id="07e08-111">int</span></span></p></td>
<td><p><span data-ttu-id="07e08-112">Primary</span><span class="sxs-lookup"><span data-stu-id="07e08-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="07e08-113">国/地域を示す一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="07e08-113">Unique number identifying the country/region.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e08-114"><strong>RegionName</strong></span><span class="sxs-lookup"><span data-stu-id="07e08-114"><strong>RegionName</strong></span></span></p></td>
<td><p><span data-ttu-id="07e08-115">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="07e08-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="07e08-116">一意</span><span class="sxs-lookup"><span data-stu-id="07e08-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="07e08-117">国/地域の名前です。</span><span class="sxs-lookup"><span data-stu-id="07e08-117">The name of the country/region.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

