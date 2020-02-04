---
title: 'Lync Server 2013: Conference テーブル'
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
ms.openlocfilehash: 4941dc3ef59630cd77cfb0f8a51407d15ca628f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="a9122-102">Lync Server 2013 の Conference テーブル</span><span class="sxs-lookup"><span data-stu-id="a9122-102">Conference table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9122-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a9122-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a9122-104">会議の表は、サポートされているテーブルです。</span><span class="sxs-lookup"><span data-stu-id="a9122-104">The Conference table is a supporting table.</span></span> <span data-ttu-id="a9122-105">各レコードは、1つの会議またはピアツーピアセッションを表します。</span><span class="sxs-lookup"><span data-stu-id="a9122-105">Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9122-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="a9122-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a9122-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="a9122-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a9122-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="a9122-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a9122-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="a9122-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9122-110"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="a9122-110"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="a9122-111">int</span><span class="sxs-lookup"><span data-stu-id="a9122-111">int</span></span></p></td>
<td><p><span data-ttu-id="a9122-112">Primary</span><span class="sxs-lookup"><span data-stu-id="a9122-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="a9122-113">この会議レコードを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="a9122-113">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9122-114"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="a9122-114"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="a9122-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a9122-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a9122-116">一意</span><span class="sxs-lookup"><span data-stu-id="a9122-116">unique</span></span></p></td>
<td><p><span data-ttu-id="a9122-117">会議の URI (会議の場合) または [この Id がピアツーピアセッションの場合] です。</span><span class="sxs-lookup"><span data-stu-id="a9122-117">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9122-118"><strong>サム</strong></span><span class="sxs-lookup"><span data-stu-id="a9122-118"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="a9122-119">int</span><span class="sxs-lookup"><span data-stu-id="a9122-119">int</span></span></p></td>
<td><p><span data-ttu-id="a9122-120">位置</span><span class="sxs-lookup"><span data-stu-id="a9122-120">index</span></span></p></td>
<td><p><span data-ttu-id="a9122-121">会議 URI のチェックサム。</span><span class="sxs-lookup"><span data-stu-id="a9122-121">Checksum of the conference URI.</span></span> <span data-ttu-id="a9122-122">これは内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a9122-122">This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9122-123"><strong>Nextupdatupdat</strong></span><span class="sxs-lookup"><span data-stu-id="a9122-123"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="a9122-124">datetime</span><span class="sxs-lookup"><span data-stu-id="a9122-124">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a9122-125">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="a9122-125">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

