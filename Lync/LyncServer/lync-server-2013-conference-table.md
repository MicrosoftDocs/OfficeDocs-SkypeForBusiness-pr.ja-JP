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
ms.openlocfilehash: a6f51e05c9721ca789724dcd015c62c2a71d8731
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520642"
---
# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="145b1-102">Lync Server 2013 の会議テーブル</span><span class="sxs-lookup"><span data-stu-id="145b1-102">Conference table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="145b1-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="145b1-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="145b1-104">会議テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="145b1-104">The Conference table is a supporting table.</span></span> <span data-ttu-id="145b1-105">各レコードは、1つの会議またはピアツーピアセッションを表します。</span><span class="sxs-lookup"><span data-stu-id="145b1-105">Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="145b1-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="145b1-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="145b1-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="145b1-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="145b1-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="145b1-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="145b1-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="145b1-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="145b1-110"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="145b1-110"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="145b1-111">int</span><span class="sxs-lookup"><span data-stu-id="145b1-111">int</span></span></p></td>
<td><p><span data-ttu-id="145b1-112">Primary</span><span class="sxs-lookup"><span data-stu-id="145b1-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="145b1-113">この会議レコードを示す一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="145b1-113">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="145b1-114"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="145b1-114"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="145b1-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="145b1-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="145b1-116">unique</span><span class="sxs-lookup"><span data-stu-id="145b1-116">unique</span></span></p></td>
<td><p><span data-ttu-id="145b1-117">これが会議の場合は会議 URI、ピアツーピア セッションの場合は DialogID です。</span><span class="sxs-lookup"><span data-stu-id="145b1-117">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="145b1-118"><strong>チェックサム</strong></span><span class="sxs-lookup"><span data-stu-id="145b1-118"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="145b1-119">int</span><span class="sxs-lookup"><span data-stu-id="145b1-119">int</span></span></p></td>
<td><p><span data-ttu-id="145b1-120">index</span><span class="sxs-lookup"><span data-stu-id="145b1-120">index</span></span></p></td>
<td><p><span data-ttu-id="145b1-121">会議 URI のチェックサム。</span><span class="sxs-lookup"><span data-stu-id="145b1-121">Checksum of the conference URI.</span></span> <span data-ttu-id="145b1-122">これは内部で使用されます。</span><span class="sxs-lookup"><span data-stu-id="145b1-122">This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="145b1-123"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="145b1-123"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="145b1-124">日付型</span><span class="sxs-lookup"><span data-stu-id="145b1-124">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="145b1-125">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="145b1-125">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

