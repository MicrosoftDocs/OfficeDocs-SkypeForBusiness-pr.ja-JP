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
ms.openlocfilehash: b6f1de8d9ae54a71a04e90a914edbd779aa3e41d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744647"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="uritypes-table-in-lync-server-2013"></a><span data-ttu-id="e6c6e-102">Lync Server 2013 の UriTypes テーブル</span><span class="sxs-lookup"><span data-stu-id="e6c6e-102">UriTypes table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6c6e-103">_**最終更新日:** 2015-06-16_</span><span class="sxs-lookup"><span data-stu-id="e6c6e-103">_**Topic Last Modified:** 2015-06-16_</span></span>

<span data-ttu-id="e6c6e-104">UriTypes テーブルには、Microsoft Lync Server 2013 で監視されるさまざまな URI (Uniform resource identifier) の種類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e6c6e-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e6c6e-105">列</span><span class="sxs-lookup"><span data-stu-id="e6c6e-105">Column</span></span></th>
<th><span data-ttu-id="e6c6e-106">データ型</span><span class="sxs-lookup"><span data-stu-id="e6c6e-106">Data Type</span></span></th>
<th><span data-ttu-id="e6c6e-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="e6c6e-107">Key/Index</span></span></th>
<th><span data-ttu-id="e6c6e-108">詳細</span><span class="sxs-lookup"><span data-stu-id="e6c6e-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e6c6e-109"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="e6c6e-109"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="e6c6e-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="e6c6e-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e6c6e-111">Primary</span><span class="sxs-lookup"><span data-stu-id="e6c6e-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="e6c6e-112">URI 型に割り当てられている一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="e6c6e-112">Unique identifier assigned to a URI type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6c6e-113"><strong>UriType</strong></span><span class="sxs-lookup"><span data-stu-id="e6c6e-113"><strong>UriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e6c6e-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e6c6e-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e6c6e-115">各種の URI の種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="e6c6e-115">Descriptions of the different URI types.</span></span> <span data-ttu-id="e6c6e-116">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e6c6e-116">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="e6c6e-117">1–電話の Uri</span><span class="sxs-lookup"><span data-stu-id="e6c6e-117">1 – Phone Uri</span></span></p></li>
<li><p><span data-ttu-id="e6c6e-118">0–ユーザー Uri</span><span class="sxs-lookup"><span data-stu-id="e6c6e-118">0 – User Uri</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

