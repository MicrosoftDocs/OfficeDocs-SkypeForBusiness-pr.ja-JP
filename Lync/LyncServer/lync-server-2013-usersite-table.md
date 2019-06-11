---
title: 'Lync Server 2013: UserSite テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserSite table
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398256(v=OCS.15)
ms:contentKeyID: 48183552
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dfb3e3d99775405ce4a09df706bec8eea59f6f9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="usersite-table-in-lync-server-2013"></a><span data-ttu-id="623bd-102">Lync Server 2013 の UserSite テーブル</span><span class="sxs-lookup"><span data-stu-id="623bd-102">UserSite table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="623bd-103">_**最終更新日:** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="623bd-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="623bd-104">UserSite テーブルは、サポートされているテーブルです。</span><span class="sxs-lookup"><span data-stu-id="623bd-104">The UserSite table is a supporting table.</span></span> <span data-ttu-id="623bd-105">各レコードは、[ネットワーク構成] の設定で定義された1つのユーザーサイトを表します。</span><span class="sxs-lookup"><span data-stu-id="623bd-105">Each record represents one user site defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="623bd-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="623bd-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="623bd-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="623bd-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="623bd-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="623bd-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="623bd-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="623bd-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="623bd-110"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="623bd-110"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="623bd-111">int</span><span class="sxs-lookup"><span data-stu-id="623bd-111">int</span></span></p></td>
<td><p><span data-ttu-id="623bd-112">Primary</span><span class="sxs-lookup"><span data-stu-id="623bd-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="623bd-113">ユーザーサイトを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="623bd-113">Unique number identifying the user site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="623bd-114"><strong>UserSiteName</strong></span><span class="sxs-lookup"><span data-stu-id="623bd-114"><strong>UserSiteName</strong></span></span></p></td>
<td><p><span data-ttu-id="623bd-115">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="623bd-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="623bd-116">一意</span><span class="sxs-lookup"><span data-stu-id="623bd-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="623bd-117">ユーザーサイトの名前。</span><span class="sxs-lookup"><span data-stu-id="623bd-117">User site’s name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="623bd-118"><strong>RegionKey</strong></span><span class="sxs-lookup"><span data-stu-id="623bd-118"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="623bd-119">int</span><span class="sxs-lookup"><span data-stu-id="623bd-119">int</span></span></p></td>
<td><p><span data-ttu-id="623bd-120">外部</span><span class="sxs-lookup"><span data-stu-id="623bd-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="623bd-121"><a href="lync-server-2013-region-table.md">Lync Server 2013 の地域テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="623bd-121">Referenced from <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

