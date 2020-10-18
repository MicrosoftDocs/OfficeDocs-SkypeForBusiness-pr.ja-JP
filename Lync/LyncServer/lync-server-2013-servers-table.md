---
title: 'Lync Server 2013: Servers テーブル'
description: 'Lync Server 2013: Servers テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Servers table
ms:assetid: 1535e676-a647-4606-bc56-e8bfde5ca823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398223(v=OCS.15)
ms:contentKeyID: 48183487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7ff7bd94aa6a999169d35cc3a8cd057c92188c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576513"
---
# <a name="servers-table-in-lync-server-2013"></a><span data-ttu-id="d870d-103">Lync Server 2013 のサーバーテーブル</span><span class="sxs-lookup"><span data-stu-id="d870d-103">Servers table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d870d-104">_**トピックの最終更新日:** 2010-11-05_</span><span class="sxs-lookup"><span data-stu-id="d870d-104">_**Topic Last Modified:** 2010-11-05_</span></span>

<span data-ttu-id="d870d-105">Servers テーブルは、さまざまなサーバーに関する情報を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="d870d-105">The Servers table is a supporting table that stores information about the various servers.</span></span> <span data-ttu-id="d870d-106">テーブル内の各レコードは、1つのサーバーを表します。</span><span class="sxs-lookup"><span data-stu-id="d870d-106">Each record in the table represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d870d-107">Column</span><span class="sxs-lookup"><span data-stu-id="d870d-107">Column</span></span></th>
<th><span data-ttu-id="d870d-108">データ型</span><span class="sxs-lookup"><span data-stu-id="d870d-108">Data Type</span></span></th>
<th><span data-ttu-id="d870d-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="d870d-109">Key/Index</span></span></th>
<th><span data-ttu-id="d870d-110">詳細</span><span class="sxs-lookup"><span data-stu-id="d870d-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d870d-111"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="d870d-111"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="d870d-112">int</span><span class="sxs-lookup"><span data-stu-id="d870d-112">int</span></span></p></td>
<td><p><span data-ttu-id="d870d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d870d-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="d870d-114">このサーバーを示す一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="d870d-114">Unique number identifying this server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d870d-115"><strong>ServerFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="d870d-115"><strong>ServerFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="d870d-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d870d-116">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d870d-117">サーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="d870d-117">Server FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

