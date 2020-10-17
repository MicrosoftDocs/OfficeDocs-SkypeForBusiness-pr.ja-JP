---
title: 'Lync Server 2013: 電話会議テーブル'
description: 'Lync Server 2013: 電話会議テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference table
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425762(v=OCS.15)
ms:contentKeyID: 48183700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 565725b527399cb3be55c649dfd74d8bcb5f13a2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550663"
---
# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="95ab8-103">Lync Server 2013 の会議テーブル</span><span class="sxs-lookup"><span data-stu-id="95ab8-103">Conference table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95ab8-104">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="95ab8-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="95ab8-105">会議テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="95ab8-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="95ab8-106">各レコードは、1つの会議またはピアツーピアセッションを表します。</span><span class="sxs-lookup"><span data-stu-id="95ab8-106">Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95ab8-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="95ab8-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="95ab8-108"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="95ab8-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="95ab8-109"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="95ab8-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="95ab8-110"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="95ab8-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95ab8-111"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="95ab8-111"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="95ab8-112">int</span><span class="sxs-lookup"><span data-stu-id="95ab8-112">int</span></span></p></td>
<td><p><span data-ttu-id="95ab8-113">Primary</span><span class="sxs-lookup"><span data-stu-id="95ab8-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="95ab8-114">この会議レコードを示す一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="95ab8-114">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95ab8-115"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="95ab8-115"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="95ab8-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="95ab8-116">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="95ab8-117">unique</span><span class="sxs-lookup"><span data-stu-id="95ab8-117">unique</span></span></p></td>
<td><p><span data-ttu-id="95ab8-118">これが会議の場合は会議 URI、ピアツーピア セッションの場合は DialogID です。</span><span class="sxs-lookup"><span data-stu-id="95ab8-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95ab8-119"><strong>チェックサム</strong></span><span class="sxs-lookup"><span data-stu-id="95ab8-119"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="95ab8-120">int</span><span class="sxs-lookup"><span data-stu-id="95ab8-120">int</span></span></p></td>
<td><p><span data-ttu-id="95ab8-121">index</span><span class="sxs-lookup"><span data-stu-id="95ab8-121">index</span></span></p></td>
<td><p><span data-ttu-id="95ab8-122">会議 URI のチェックサム。</span><span class="sxs-lookup"><span data-stu-id="95ab8-122">Checksum of the conference URI.</span></span> <span data-ttu-id="95ab8-123">これは内部で使用されます。</span><span class="sxs-lookup"><span data-stu-id="95ab8-123">This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95ab8-124"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="95ab8-124"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="95ab8-125">日付型</span><span class="sxs-lookup"><span data-stu-id="95ab8-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="95ab8-126">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="95ab8-126">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

