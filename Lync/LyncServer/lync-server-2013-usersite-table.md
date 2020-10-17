---
title: 'Lync Server 2013: UserSite テーブル'
description: 'Lync Server 2013: UserSite table。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserSite table
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398256(v=OCS.15)
ms:contentKeyID: 48183552
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e0fb3149b9378bbfd3f14da8176eed226e4f57f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548623"
---
# <a name="usersite-table-in-lync-server-2013"></a><span data-ttu-id="f9bd1-103">Lync Server 2013 の UserSite テーブル</span><span class="sxs-lookup"><span data-stu-id="f9bd1-103">UserSite table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9bd1-104">_**トピックの最終更新日:** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="f9bd1-104">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="f9bd1-p101">UserSite テーブルはサポート テーブルです。各レコードは、ネットワーク構成の設定で定義されている 1 つのユーザー サイトを表します。</span><span class="sxs-lookup"><span data-stu-id="f9bd1-p101">The UserSite table is a supporting table. Each record represents one user site defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9bd1-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="f9bd1-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f9bd1-108"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="f9bd1-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f9bd1-109"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="f9bd1-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f9bd1-110"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="f9bd1-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9bd1-111"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="f9bd1-111"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f9bd1-112">int</span><span class="sxs-lookup"><span data-stu-id="f9bd1-112">int</span></span></p></td>
<td><p><span data-ttu-id="f9bd1-113">Primary</span><span class="sxs-lookup"><span data-stu-id="f9bd1-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="f9bd1-114">ユーザー サイトを示す一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="f9bd1-114">Unique number identifying the user site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9bd1-115"><strong>UserSiteName</strong></span><span class="sxs-lookup"><span data-stu-id="f9bd1-115"><strong>UserSiteName</strong></span></span></p></td>
<td><p><span data-ttu-id="f9bd1-116">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="f9bd1-116">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f9bd1-117">一意</span><span class="sxs-lookup"><span data-stu-id="f9bd1-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="f9bd1-118">ユーザー サイトの名前です。</span><span class="sxs-lookup"><span data-stu-id="f9bd1-118">User site’s name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9bd1-119"><strong>RegionKey</strong></span><span class="sxs-lookup"><span data-stu-id="f9bd1-119"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f9bd1-120">int</span><span class="sxs-lookup"><span data-stu-id="f9bd1-120">int</span></span></p></td>
<td><p><span data-ttu-id="f9bd1-121">外部</span><span class="sxs-lookup"><span data-stu-id="f9bd1-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f9bd1-122"><a href="lync-server-2013-region-table.md">Lync Server 2013 の Region テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="f9bd1-122">Referenced from <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

