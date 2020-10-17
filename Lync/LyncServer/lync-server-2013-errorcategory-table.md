---
title: 'Lync Server 2013: ErrorCategory テーブル'
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
ms.openlocfilehash: 7f21535c1806223e7687ceb24ee94a93fe15238d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533154"
---
# <a name="errorcategory-table-in-lync-server-2013"></a><span data-ttu-id="a9228-102">Lync Server 2013 の ErrorCategory テーブル</span><span class="sxs-lookup"><span data-stu-id="a9228-102">ErrorCategory table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9228-103">_**トピックの最終更新日:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="a9228-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="a9228-104">ErrorCategory テーブルには、Microsoft Lync Server 2013 の診断分類のフレンドリ名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a9228-104">The ErrorCategory table contains the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span> <span data-ttu-id="a9228-105">既定では、Lync Server 2013 は次の分類を使用します。</span><span class="sxs-lookup"><span data-stu-id="a9228-105">By default, Lync Server 2013 uses the following classifications:</span></span>

  - <span data-ttu-id="a9228-106">0 -- 成功</span><span class="sxs-lookup"><span data-stu-id="a9228-106">0 -- Success</span></span>

  - <span data-ttu-id="a9228-107">1--予期されたエラー</span><span class="sxs-lookup"><span data-stu-id="a9228-107">1 -- Expected failure</span></span>

  - <span data-ttu-id="a9228-108">2 – 予期しないエラー</span><span class="sxs-lookup"><span data-stu-id="a9228-108">2 – Unexpected failure</span></span>

<span data-ttu-id="a9228-109">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a9228-109">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9228-110">Column</span><span class="sxs-lookup"><span data-stu-id="a9228-110">Column</span></span></th>
<th><span data-ttu-id="a9228-111">データ型</span><span class="sxs-lookup"><span data-stu-id="a9228-111">Data Type</span></span></th>
<th><span data-ttu-id="a9228-112">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="a9228-112">Key/Index</span></span></th>
<th><span data-ttu-id="a9228-113">詳細</span><span class="sxs-lookup"><span data-stu-id="a9228-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9228-114"><strong>区分</strong></span><span class="sxs-lookup"><span data-stu-id="a9228-114"><strong>CategoryId</strong></span></span></p></td>
<td><p><span data-ttu-id="a9228-115">tinyint</span><span class="sxs-lookup"><span data-stu-id="a9228-115">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a9228-116">Primary</span><span class="sxs-lookup"><span data-stu-id="a9228-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="a9228-117">分類の一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="a9228-117">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9228-118"><strong>名前</strong></span><span class="sxs-lookup"><span data-stu-id="a9228-118"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="a9228-119">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a9228-119">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a9228-p102">分類に割り当てられる値とフレンドリ名。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a9228-p102">Value and friendly name assigned to the classification. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="a9228-122">0 -- 成功</span><span class="sxs-lookup"><span data-stu-id="a9228-122">0 -- Success</span></span></p></li>
<li><p><span data-ttu-id="a9228-123">1--予期されたエラー</span><span class="sxs-lookup"><span data-stu-id="a9228-123">1 -- Expected failure</span></span></p></li>
<li><p><span data-ttu-id="a9228-124">2 – 予期しないエラー</span><span class="sxs-lookup"><span data-stu-id="a9228-124">2 – Unexpected failure</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

