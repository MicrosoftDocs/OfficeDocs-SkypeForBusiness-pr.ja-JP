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
ms.openlocfilehash: 03d4b2af9c0d746c713a2e98019f278ceb3df6e5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="uritypes-table-in-lync-server-2013"></a><span data-ttu-id="1ee8b-102">Lync Server 2013 の UriTypes テーブル</span><span class="sxs-lookup"><span data-stu-id="1ee8b-102">UriTypes table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ee8b-103">_**トピックの最終更新日:** 2015-06-16_</span><span class="sxs-lookup"><span data-stu-id="1ee8b-103">_**Topic Last Modified:** 2015-06-16_</span></span>

<span data-ttu-id="1ee8b-104">UriTypes テーブルには、Microsoft Lync Server 2013 で監視されたさまざまな URI (Uniform resource identifier) の種類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1ee8b-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ee8b-105">列</span><span class="sxs-lookup"><span data-stu-id="1ee8b-105">Column</span></span></th>
<th><span data-ttu-id="1ee8b-106">データ型</span><span class="sxs-lookup"><span data-stu-id="1ee8b-106">Data Type</span></span></th>
<th><span data-ttu-id="1ee8b-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="1ee8b-107">Key/Index</span></span></th>
<th><span data-ttu-id="1ee8b-108">詳細</span><span class="sxs-lookup"><span data-stu-id="1ee8b-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ee8b-109"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="1ee8b-109"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee8b-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="1ee8b-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1ee8b-111">Primary</span><span class="sxs-lookup"><span data-stu-id="1ee8b-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="1ee8b-112">URI の種類に割り当てられている一意の ID です。</span><span class="sxs-lookup"><span data-stu-id="1ee8b-112">Unique identifier assigned to a URI type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee8b-113"><strong>UriType</strong></span><span class="sxs-lookup"><span data-stu-id="1ee8b-113"><strong>UriType</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee8b-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ee8b-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1ee8b-p101">URI の種類の説明です。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1ee8b-p101">Descriptions of the different URI types. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="1ee8b-117">1–電話の Uri</span><span class="sxs-lookup"><span data-stu-id="1ee8b-117">1 – Phone Uri</span></span></p></li>
<li><p><span data-ttu-id="1ee8b-118">0–ユーザー Uri</span><span class="sxs-lookup"><span data-stu-id="1ee8b-118">0 – User Uri</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

