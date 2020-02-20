---
title: 'Lync Server 2013: 電話会議テーブル'
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
ms.openlocfilehash: 27984e3f39821dd68f18f980550a2c571d27b9b1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145155"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="cb007-102">Lync Server 2013 の会議テーブル</span><span class="sxs-lookup"><span data-stu-id="cb007-102">Conference table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb007-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="cb007-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="cb007-104">会議テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="cb007-104">The Conference table is a supporting table.</span></span> <span data-ttu-id="cb007-105">各レコードは、1つの会議またはピアツーピアセッションを表します。</span><span class="sxs-lookup"><span data-stu-id="cb007-105">Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb007-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="cb007-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="cb007-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="cb007-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="cb007-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="cb007-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="cb007-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="cb007-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb007-110"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="cb007-110"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="cb007-111">int</span><span class="sxs-lookup"><span data-stu-id="cb007-111">int</span></span></p></td>
<td><p><span data-ttu-id="cb007-112">Primary</span><span class="sxs-lookup"><span data-stu-id="cb007-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="cb007-113">この会議レコードを示す一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="cb007-113">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb007-114"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="cb007-114"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="cb007-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cb007-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="cb007-116">unique</span><span class="sxs-lookup"><span data-stu-id="cb007-116">unique</span></span></p></td>
<td><p><span data-ttu-id="cb007-117">これが会議の場合は会議 URI、ピアツーピア セッションの場合は DialogID です。</span><span class="sxs-lookup"><span data-stu-id="cb007-117">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb007-118"><strong>チェックサム</strong></span><span class="sxs-lookup"><span data-stu-id="cb007-118"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="cb007-119">int</span><span class="sxs-lookup"><span data-stu-id="cb007-119">int</span></span></p></td>
<td><p><span data-ttu-id="cb007-120">index</span><span class="sxs-lookup"><span data-stu-id="cb007-120">index</span></span></p></td>
<td><p><span data-ttu-id="cb007-121">会議 URI のチェックサム。</span><span class="sxs-lookup"><span data-stu-id="cb007-121">Checksum of the conference URI.</span></span> <span data-ttu-id="cb007-122">これは内部で使用されます。</span><span class="sxs-lookup"><span data-stu-id="cb007-122">This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb007-123"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="cb007-123"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="cb007-124">日付型</span><span class="sxs-lookup"><span data-stu-id="cb007-124">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cb007-125">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="cb007-125">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

