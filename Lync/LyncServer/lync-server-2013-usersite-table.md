---
title: 'Lync Server 2013: UserSite テーブル'
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
ms.openlocfilehash: 656bf8f692617392db02e186fcccebba25a01b0d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530004"
---
# <a name="usersite-table-in-lync-server-2013"></a><span data-ttu-id="e5d4e-102">Lync Server 2013 の UserSite テーブル</span><span class="sxs-lookup"><span data-stu-id="e5d4e-102">UserSite table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5d4e-103">_**トピックの最終更新日:** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="e5d4e-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="e5d4e-p101">UserSite テーブルはサポート テーブルです。各レコードは、ネットワーク構成の設定で定義されている 1 つのユーザー サイトを表します。</span><span class="sxs-lookup"><span data-stu-id="e5d4e-p101">The UserSite table is a supporting table. Each record represents one user site defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5d4e-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="e5d4e-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e5d4e-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="e5d4e-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e5d4e-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="e5d4e-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e5d4e-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="e5d4e-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5d4e-110"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="e5d4e-110"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e5d4e-111">int</span><span class="sxs-lookup"><span data-stu-id="e5d4e-111">int</span></span></p></td>
<td><p><span data-ttu-id="e5d4e-112">Primary</span><span class="sxs-lookup"><span data-stu-id="e5d4e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e5d4e-113">ユーザー サイトを示す一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="e5d4e-113">Unique number identifying the user site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5d4e-114"><strong>UserSiteName</strong></span><span class="sxs-lookup"><span data-stu-id="e5d4e-114"><strong>UserSiteName</strong></span></span></p></td>
<td><p><span data-ttu-id="e5d4e-115">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e5d4e-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e5d4e-116">一意</span><span class="sxs-lookup"><span data-stu-id="e5d4e-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="e5d4e-117">ユーザー サイトの名前です。</span><span class="sxs-lookup"><span data-stu-id="e5d4e-117">User site’s name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5d4e-118"><strong>RegionKey</strong></span><span class="sxs-lookup"><span data-stu-id="e5d4e-118"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e5d4e-119">int</span><span class="sxs-lookup"><span data-stu-id="e5d4e-119">int</span></span></p></td>
<td><p><span data-ttu-id="e5d4e-120">外部</span><span class="sxs-lookup"><span data-stu-id="e5d4e-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e5d4e-121"><a href="lync-server-2013-region-table.md">Lync Server 2013 の Region テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="e5d4e-121">Referenced from <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

