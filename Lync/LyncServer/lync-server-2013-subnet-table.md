---
title: 'Lync Server 2013: Subnet テーブル'
description: 'Lync Server 2013: Subnet table。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Subnet table
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398582(v=OCS.15)
ms:contentKeyID: 48184544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d30c04ddf897e0a62551709b30211ba724a75cbf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546313"
---
# <a name="subnet-table-in-lync-server-2013"></a><span data-ttu-id="3d4fc-103">Lync Server 2013 のサブネットテーブル</span><span class="sxs-lookup"><span data-stu-id="3d4fc-103">Subnet table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d4fc-104">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="3d4fc-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="3d4fc-p101">Subnet テーブルは、サポート テーブルです。それぞれのレコードは、ネットワーク構成の設定で定義された 1 つのサブネットを表します。</span><span class="sxs-lookup"><span data-stu-id="3d4fc-p101">The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3d4fc-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="3d4fc-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="3d4fc-108"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="3d4fc-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="3d4fc-109"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="3d4fc-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="3d4fc-110"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="3d4fc-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d4fc-111"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="3d4fc-111"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="3d4fc-112">int</span><span class="sxs-lookup"><span data-stu-id="3d4fc-112">int</span></span></p></td>
<td><p><span data-ttu-id="3d4fc-113">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="3d4fc-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="3d4fc-114">サブネット IP の整数表現。</span><span class="sxs-lookup"><span data-stu-id="3d4fc-114">Integer representation for the subnet IP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d4fc-115"><strong>マスク</strong></span><span class="sxs-lookup"><span data-stu-id="3d4fc-115"><strong>SubnetMask</strong></span></span></p></td>
<td><p><span data-ttu-id="3d4fc-116">int</span><span class="sxs-lookup"><span data-stu-id="3d4fc-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3d4fc-117">サブネット マスク。</span><span class="sxs-lookup"><span data-stu-id="3d4fc-117">Subnet mask.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d4fc-118"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="3d4fc-118"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="3d4fc-119">int</span><span class="sxs-lookup"><span data-stu-id="3d4fc-119">int</span></span></p></td>
<td><p><span data-ttu-id="3d4fc-120">外部</span><span class="sxs-lookup"><span data-stu-id="3d4fc-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3d4fc-121"><a href="lync-server-2013-usersite-table.md">Lync Server 2013 の Usersite テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="3d4fc-121">Referenced from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d4fc-122"><strong>サブネットの説明</strong></span><span class="sxs-lookup"><span data-stu-id="3d4fc-122"><strong>SubnetDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="3d4fc-123">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="3d4fc-123">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3d4fc-124">サブネットの説明。</span><span class="sxs-lookup"><span data-stu-id="3d4fc-124">The description for the subnet.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

