---
title: 'Lync Server 2013: CallPriorities 度テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CallPriorities table
ms:assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398093(v=OCS.15)
ms:contentKeyID: 48183275
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2be19538e065a1f9a25dd58da93b2752a27333e9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="callpriorities-table-in-lync-server-2013"></a><span data-ttu-id="23cda-102">Lync Server 2013 の CallPriorities テーブル</span><span class="sxs-lookup"><span data-stu-id="23cda-102">CallPriorities table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23cda-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="23cda-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="23cda-104">CallPriorities テーブルは、使用できる通話の優先度 ("緊急"、"至急"、"通常" など) の一覧を格納する静的テーブルです。</span><span class="sxs-lookup"><span data-stu-id="23cda-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as ‘emergency’, ‘urgent’, or ‘normal’.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23cda-105">列</span><span class="sxs-lookup"><span data-stu-id="23cda-105">Column</span></span></th>
<th><span data-ttu-id="23cda-106">データ型</span><span class="sxs-lookup"><span data-stu-id="23cda-106">Data Type</span></span></th>
<th><span data-ttu-id="23cda-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="23cda-107">Key/Index</span></span></th>
<th><span data-ttu-id="23cda-108">詳細</span><span class="sxs-lookup"><span data-stu-id="23cda-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23cda-109"><strong>優先順位 Id</strong></span><span class="sxs-lookup"><span data-stu-id="23cda-109"><strong>PriorityId</strong></span></span></p></td>
<td><p><span data-ttu-id="23cda-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="23cda-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="23cda-111">Primary</span><span class="sxs-lookup"><span data-stu-id="23cda-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23cda-112"><strong>[優先度]</strong></span><span class="sxs-lookup"><span data-stu-id="23cda-112"><strong>Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="23cda-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="23cda-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="23cda-114">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="23cda-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="23cda-115">0 -- 不明</span><span class="sxs-lookup"><span data-stu-id="23cda-115">0 - Unknown</span></span></p></li>
<li><p><span data-ttu-id="23cda-116">1 -- 非緊急</span><span class="sxs-lookup"><span data-stu-id="23cda-116">1 – Non-Urgent</span></span></p></li>
<li><p><span data-ttu-id="23cda-117">2 -- 通常</span><span class="sxs-lookup"><span data-stu-id="23cda-117">2 - Normal</span></span></p></li>
<li><p><span data-ttu-id="23cda-118">3 -- 至急</span><span class="sxs-lookup"><span data-stu-id="23cda-118">3 - Urgent</span></span></p></li>
<li><p><span data-ttu-id="23cda-119">4 -- 緊急</span><span class="sxs-lookup"><span data-stu-id="23cda-119">4 - Emergency</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

