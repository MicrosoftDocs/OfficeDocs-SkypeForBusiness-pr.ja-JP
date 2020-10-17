---
title: 'Lync Server 2013: Phone テーブル'
description: 'Lync Server 2013: Phone テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Phones table
ms:assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425923(v=OCS.15)
ms:contentKeyID: 48183996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c62fffecd2442b79aefde77eb037dca4bffc9d4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554813"
---
# <a name="phones-table-in-lync-server-2013"></a><span data-ttu-id="b33d1-103">Lync Server 2013 の電話表</span><span class="sxs-lookup"><span data-stu-id="b33d1-103">Phones table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b33d1-104">_**トピックの最終更新日:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="b33d1-104">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="b33d1-105">Phone テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="b33d1-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="b33d1-106">テーブル内の各レコードには、データベース内のレコードを持つ VoIP 呼び出しに関係する1つの電話番号に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="b33d1-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b33d1-107">Column</span><span class="sxs-lookup"><span data-stu-id="b33d1-107">Column</span></span></th>
<th><span data-ttu-id="b33d1-108">データ型</span><span class="sxs-lookup"><span data-stu-id="b33d1-108">Data Type</span></span></th>
<th><span data-ttu-id="b33d1-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="b33d1-109">Key/Index</span></span></th>
<th><span data-ttu-id="b33d1-110">詳細</span><span class="sxs-lookup"><span data-stu-id="b33d1-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b33d1-111"><strong>PhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="b33d1-111"><strong>PhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="b33d1-112">int</span><span class="sxs-lookup"><span data-stu-id="b33d1-112">int</span></span></p></td>
<td><p><span data-ttu-id="b33d1-113">Primary</span><span class="sxs-lookup"><span data-stu-id="b33d1-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="b33d1-114">この電話を示す一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="b33d1-114">Unique number identifying this phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b33d1-115"><strong>電話の Uri</strong></span><span class="sxs-lookup"><span data-stu-id="b33d1-115"><strong>PhoneUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b33d1-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b33d1-116">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b33d1-117">電話番号。</span><span class="sxs-lookup"><span data-stu-id="b33d1-117">Phone number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b33d1-118"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="b33d1-118"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="b33d1-119">dateTime</span><span class="sxs-lookup"><span data-stu-id="b33d1-119">dateTime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b33d1-120">タイムスタンプ (内部使用のみ)。</span><span class="sxs-lookup"><span data-stu-id="b33d1-120">Time stamp (for internal use only).</span></span></p>
<p><span data-ttu-id="b33d1-121">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b33d1-121">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

