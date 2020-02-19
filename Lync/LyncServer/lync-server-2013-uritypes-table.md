---
title: 'Lync Server 2013: UriTypes テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UriTypes table
ms:assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398587(v=OCS.15)
ms:contentKeyID: 48184553
ms.date: 06/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10b123caa837fbdc9bbea9fc8a524b47c4950822
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140880"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="uritypes-table-in-lync-server-2013"></a><span data-ttu-id="45470-102">Lync Server 2013 の UriTypes テーブル</span><span class="sxs-lookup"><span data-stu-id="45470-102">UriTypes table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45470-103">_**トピックの最終更新日:** 2015-06-16_</span><span class="sxs-lookup"><span data-stu-id="45470-103">_**Topic Last Modified:** 2015-06-16_</span></span>

<span data-ttu-id="45470-104">UriTypes テーブルには、Microsoft Lync Server 2013 で監視されたさまざまな URI (Uniform resource identifier) の種類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="45470-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45470-105">列</span><span class="sxs-lookup"><span data-stu-id="45470-105">Column</span></span></th>
<th><span data-ttu-id="45470-106">データ型</span><span class="sxs-lookup"><span data-stu-id="45470-106">Data Type</span></span></th>
<th><span data-ttu-id="45470-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="45470-107">Key/Index</span></span></th>
<th><span data-ttu-id="45470-108">詳細</span><span class="sxs-lookup"><span data-stu-id="45470-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45470-109"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="45470-109"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="45470-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="45470-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="45470-111">Primary</span><span class="sxs-lookup"><span data-stu-id="45470-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="45470-112">URI の種類に割り当てられている一意の ID です。</span><span class="sxs-lookup"><span data-stu-id="45470-112">Unique identifier assigned to a URI type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45470-113"><strong>UriType</strong></span><span class="sxs-lookup"><span data-stu-id="45470-113"><strong>UriType</strong></span></span></p></td>
<td><p><span data-ttu-id="45470-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="45470-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="45470-p101">URI の種類の説明です。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="45470-p101">Descriptions of the different URI types. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="45470-117">1–電話の Uri</span><span class="sxs-lookup"><span data-stu-id="45470-117">1 – Phone Uri</span></span></p></li>
<li><p><span data-ttu-id="45470-118">0–ユーザー Uri</span><span class="sxs-lookup"><span data-stu-id="45470-118">0 – User Uri</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

