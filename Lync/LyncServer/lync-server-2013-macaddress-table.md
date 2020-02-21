---
title: 'Lync Server 2013: MacAddress テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MacAddress table
ms:assetid: a32e68c5-3f95-4217-aff4-cb3d1cc70505
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412761(v=OCS.15)
ms:contentKeyID: 48184963
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85f9e49dd2d4272cea5f3a36326612992aba2ddb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="macaddress-table-in-lync-server-2013"></a><span data-ttu-id="e5a43-102">Lync Server 2013 の MacAddress テーブル</span><span class="sxs-lookup"><span data-stu-id="e5a43-102">MacAddress table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5a43-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e5a43-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e5a43-p101">MacAddress テーブルは補助的なテーブルです。個々のレコードが 1 つのソースを表します。</span><span class="sxs-lookup"><span data-stu-id="e5a43-p101">The MacAddress table is a supporting table. Each record represents one source.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5a43-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="e5a43-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e5a43-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="e5a43-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e5a43-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="e5a43-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e5a43-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="e5a43-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5a43-110"><strong>MacAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="e5a43-110"><strong>MacAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e5a43-111">int</span><span class="sxs-lookup"><span data-stu-id="e5a43-111">int</span></span></p></td>
<td><p><span data-ttu-id="e5a43-112">Primary</span><span class="sxs-lookup"><span data-stu-id="e5a43-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e5a43-113">MAC アドレスを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="e5a43-113">Unique number identifying the Mac address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5a43-114"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="e5a43-114"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="e5a43-115">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e5a43-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5a43-116">一意</span><span class="sxs-lookup"><span data-stu-id="e5a43-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="e5a43-117">MAC アドレス文字列。</span><span class="sxs-lookup"><span data-stu-id="e5a43-117">Mac address string.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

