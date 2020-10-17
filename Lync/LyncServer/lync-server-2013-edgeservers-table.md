---
title: 'Lync Server 2013: EdgeServers テーブル'
description: 'Lync Server 2013: EdgeServers テーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: EdgeServers table
ms:assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412833(v=OCS.15)
ms:contentKeyID: 48185081
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e4097ca58b75f873dcc12b84e5d971e9e378d07
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551653"
---
# <a name="edgeservers-table-in-lync-server-2013"></a><span data-ttu-id="42d4e-103">Lync Server 2013 の EdgeServers テーブル</span><span class="sxs-lookup"><span data-stu-id="42d4e-103">EdgeServers table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42d4e-104">_**トピックの最終更新日:** 2010-11-06_</span><span class="sxs-lookup"><span data-stu-id="42d4e-104">_**Topic Last Modified:** 2010-11-06_</span></span>

<span data-ttu-id="42d4e-105">EdgeServers テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="42d4e-105">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="42d4e-106">各レコードには、データベース内のレコードを持つ呼び出しに関係する1つのエッジサーバーに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="42d4e-106">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42d4e-107">Column</span><span class="sxs-lookup"><span data-stu-id="42d4e-107">Column</span></span></th>
<th><span data-ttu-id="42d4e-108">データ型</span><span class="sxs-lookup"><span data-stu-id="42d4e-108">Data Type</span></span></th>
<th><span data-ttu-id="42d4e-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="42d4e-109">Key/Index</span></span></th>
<th><span data-ttu-id="42d4e-110">詳細</span><span class="sxs-lookup"><span data-stu-id="42d4e-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42d4e-111"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="42d4e-111"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="42d4e-112">int</span><span class="sxs-lookup"><span data-stu-id="42d4e-112">int</span></span></p></td>
<td><p><span data-ttu-id="42d4e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="42d4e-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="42d4e-114">このエッジサーバーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="42d4e-114">Unique number identifying this Edge Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42d4e-115"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="42d4e-115"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="42d4e-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="42d4e-116">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="42d4e-117">エッジサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="42d4e-117">Edge Server name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

