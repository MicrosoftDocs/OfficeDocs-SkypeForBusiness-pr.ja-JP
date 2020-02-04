---
title: 'Lync Server 2013: CallPriorities テーブル'
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
ms.openlocfilehash: 31ddf598fcf33b4f4841f9e3a9e857fd57ea608c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="callpriorities-table-in-lync-server-2013"></a><span data-ttu-id="44b22-102">Lync Server 2013 の CallPriorities テーブル</span><span class="sxs-lookup"><span data-stu-id="44b22-102">CallPriorities table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44b22-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="44b22-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="44b22-104">CallPriorities 度テーブルは、"緊急"、"緊急"、"標準" などの、可能な呼び出しの優先順位の一覧を保存する静的テーブルです。</span><span class="sxs-lookup"><span data-stu-id="44b22-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as ‘emergency’, ‘urgent’, or ‘normal’.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44b22-105">列</span><span class="sxs-lookup"><span data-stu-id="44b22-105">Column</span></span></th>
<th><span data-ttu-id="44b22-106">データ型</span><span class="sxs-lookup"><span data-stu-id="44b22-106">Data Type</span></span></th>
<th><span data-ttu-id="44b22-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="44b22-107">Key/Index</span></span></th>
<th><span data-ttu-id="44b22-108">詳細</span><span class="sxs-lookup"><span data-stu-id="44b22-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44b22-109"><strong>優先順位 Id</strong></span><span class="sxs-lookup"><span data-stu-id="44b22-109"><strong>PriorityId</strong></span></span></p></td>
<td><p><span data-ttu-id="44b22-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="44b22-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="44b22-111">Primary</span><span class="sxs-lookup"><span data-stu-id="44b22-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44b22-112"><strong>[Priority]</strong></span><span class="sxs-lookup"><span data-stu-id="44b22-112"><strong>Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="44b22-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="44b22-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44b22-114">許可される値:</span><span class="sxs-lookup"><span data-stu-id="44b22-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="44b22-115">0-不明</span><span class="sxs-lookup"><span data-stu-id="44b22-115">0 - Unknown</span></span></p></li>
<li><p><span data-ttu-id="44b22-116">1–緊急以外</span><span class="sxs-lookup"><span data-stu-id="44b22-116">1 – Non-Urgent</span></span></p></li>
<li><p><span data-ttu-id="44b22-117">2-標準</span><span class="sxs-lookup"><span data-stu-id="44b22-117">2 - Normal</span></span></p></li>
<li><p><span data-ttu-id="44b22-118">3-緊急</span><span class="sxs-lookup"><span data-stu-id="44b22-118">3 - Urgent</span></span></p></li>
<li><p><span data-ttu-id="44b22-119">4-緊急</span><span class="sxs-lookup"><span data-stu-id="44b22-119">4 - Emergency</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

