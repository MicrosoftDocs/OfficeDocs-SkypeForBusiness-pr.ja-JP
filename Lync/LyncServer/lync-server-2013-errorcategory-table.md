---
title: 'Lync Server 2013: ErrorCategory テーブル'
description: 'Lync Server 2013: ErrorCategory テーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorCategory table
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204675(v=OCS.15)
ms:contentKeyID: 48183425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8154c73f33b5dad62a338335a960553cfc06ec13
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546433"
---
# <a name="errorcategory-table-in-lync-server-2013"></a><span data-ttu-id="52659-103">Lync Server 2013 の ErrorCategory テーブル</span><span class="sxs-lookup"><span data-stu-id="52659-103">ErrorCategory table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52659-104">_**トピックの最終更新日:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="52659-104">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="52659-105">ErrorCategory テーブルには、Microsoft Lync Server 2013 の診断分類のフレンドリ名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="52659-105">The ErrorCategory table contains the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span> <span data-ttu-id="52659-106">既定では、Lync Server 2013 は次の分類を使用します。</span><span class="sxs-lookup"><span data-stu-id="52659-106">By default, Lync Server 2013 uses the following classifications:</span></span>

  - <span data-ttu-id="52659-107">0 -- 成功</span><span class="sxs-lookup"><span data-stu-id="52659-107">0 -- Success</span></span>

  - <span data-ttu-id="52659-108">1--予期されたエラー</span><span class="sxs-lookup"><span data-stu-id="52659-108">1 -- Expected failure</span></span>

  - <span data-ttu-id="52659-109">2 – 予期しないエラー</span><span class="sxs-lookup"><span data-stu-id="52659-109">2 – Unexpected failure</span></span>

<span data-ttu-id="52659-110">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="52659-110">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52659-111">Column</span><span class="sxs-lookup"><span data-stu-id="52659-111">Column</span></span></th>
<th><span data-ttu-id="52659-112">データ型</span><span class="sxs-lookup"><span data-stu-id="52659-112">Data Type</span></span></th>
<th><span data-ttu-id="52659-113">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="52659-113">Key/Index</span></span></th>
<th><span data-ttu-id="52659-114">詳細</span><span class="sxs-lookup"><span data-stu-id="52659-114">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52659-115"><strong>区分</strong></span><span class="sxs-lookup"><span data-stu-id="52659-115"><strong>CategoryId</strong></span></span></p></td>
<td><p><span data-ttu-id="52659-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="52659-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="52659-117">Primary</span><span class="sxs-lookup"><span data-stu-id="52659-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="52659-118">分類の一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="52659-118">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52659-119"><strong>名前</strong></span><span class="sxs-lookup"><span data-stu-id="52659-119"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="52659-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="52659-120">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52659-p102">分類に割り当てられる値とフレンドリ名。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="52659-p102">Value and friendly name assigned to the classification. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="52659-123">0 -- 成功</span><span class="sxs-lookup"><span data-stu-id="52659-123">0 -- Success</span></span></p></li>
<li><p><span data-ttu-id="52659-124">1--予期されたエラー</span><span class="sxs-lookup"><span data-stu-id="52659-124">1 -- Expected failure</span></span></p></li>
<li><p><span data-ttu-id="52659-125">2 – 予期しないエラー</span><span class="sxs-lookup"><span data-stu-id="52659-125">2 – Unexpected failure</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

