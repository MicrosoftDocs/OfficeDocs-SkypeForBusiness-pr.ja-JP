---
title: 'Lync Server 2013: プールテーブル'
description: 'Lync Server 2013: プールテーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Pools table
ms:assetid: e0632b8d-e23a-4365-8a7a-6ca0957a46a9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398991(v=OCS.15)
ms:contentKeyID: 48185680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a587eba6798121f39fe64ff8bd720b62e9311ec0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543193"
---
# <a name="pools-table-in-lync-server-2013"></a><span data-ttu-id="7fd76-103">Lync Server 2013 のプールテーブル</span><span class="sxs-lookup"><span data-stu-id="7fd76-103">Pools table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fd76-104">_**トピックの最終更新日:** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="7fd76-104">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="7fd76-105">プールテーブルは、さまざまなプールに関する情報を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="7fd76-105">The Pools table is a supporting table that stores information about the various pool.</span></span> <span data-ttu-id="7fd76-106">このテーブル内の各レコードは、1 つのプールを表しています。</span><span class="sxs-lookup"><span data-stu-id="7fd76-106">Each record in the table represents one pool.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7fd76-107">Column</span><span class="sxs-lookup"><span data-stu-id="7fd76-107">Column</span></span></th>
<th><span data-ttu-id="7fd76-108">データ型</span><span class="sxs-lookup"><span data-stu-id="7fd76-108">Data Type</span></span></th>
<th><span data-ttu-id="7fd76-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="7fd76-109">Key/Index</span></span></th>
<th><span data-ttu-id="7fd76-110">詳細</span><span class="sxs-lookup"><span data-stu-id="7fd76-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7fd76-111"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="7fd76-111"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="7fd76-112">int</span><span class="sxs-lookup"><span data-stu-id="7fd76-112">int</span></span></p></td>
<td><p><span data-ttu-id="7fd76-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7fd76-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="7fd76-114">このプールを示す一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="7fd76-114">Unique number identifying this pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fd76-115"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="7fd76-115"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="7fd76-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7fd76-116">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7fd76-117">プールの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="7fd76-117">Pool FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

