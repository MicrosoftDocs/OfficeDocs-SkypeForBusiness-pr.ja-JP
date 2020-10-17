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
ms.openlocfilehash: 6902636d8d45949a08b259a1fee1bbab191ce0ff
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534584"
---
# <a name="macaddress-table-in-lync-server-2013"></a><span data-ttu-id="63073-102">Lync Server 2013 の MacAddress テーブル</span><span class="sxs-lookup"><span data-stu-id="63073-102">MacAddress table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63073-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="63073-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="63073-p101">MacAddress テーブルは補助的なテーブルです。個々のレコードが 1 つのソースを表します。</span><span class="sxs-lookup"><span data-stu-id="63073-p101">The MacAddress table is a supporting table. Each record represents one source.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63073-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="63073-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="63073-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="63073-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="63073-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="63073-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="63073-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="63073-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63073-110"><strong>MacAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="63073-110"><strong>MacAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="63073-111">int</span><span class="sxs-lookup"><span data-stu-id="63073-111">int</span></span></p></td>
<td><p><span data-ttu-id="63073-112">Primary</span><span class="sxs-lookup"><span data-stu-id="63073-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="63073-113">MAC アドレスを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="63073-113">Unique number identifying the Mac address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63073-114"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="63073-114"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="63073-115">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="63073-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63073-116">一意</span><span class="sxs-lookup"><span data-stu-id="63073-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="63073-117">MAC アドレス文字列。</span><span class="sxs-lookup"><span data-stu-id="63073-117">Mac address string.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

