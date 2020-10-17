---
title: 'Lync Server 2013: ConferenceUris テーブル'
description: 'Lync Server 2013: ConferenceUris テーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a142aa9ad1fe4d3ae92aa3e21aa9eee505457cbe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566743"
---
# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="ec28a-103">Lync Server 2013 の ConferenceUris テーブル</span><span class="sxs-lookup"><span data-stu-id="ec28a-103">ConferenceUris table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec28a-104">_**トピックの最終更新日:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="ec28a-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="ec28a-p101">ConfereneUris テーブルは、データベースに記録されている会議セッションに参加したさまざまな会議 URI の一覧を格納する補助的なテーブルです。このテーブルの個々のレコードが、1 つの会議 URI を表します。</span><span class="sxs-lookup"><span data-stu-id="ec28a-p101">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database. Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ec28a-107">Column</span><span class="sxs-lookup"><span data-stu-id="ec28a-107">Column</span></span></th>
<th><span data-ttu-id="ec28a-108">データ型</span><span class="sxs-lookup"><span data-stu-id="ec28a-108">Data Type</span></span></th>
<th><span data-ttu-id="ec28a-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="ec28a-109">Key/Index</span></span></th>
<th><span data-ttu-id="ec28a-110">詳細</span><span class="sxs-lookup"><span data-stu-id="ec28a-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec28a-111"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="ec28a-111"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="ec28a-112">日付型</span><span class="sxs-lookup"><span data-stu-id="ec28a-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="ec28a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ec28a-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="ec28a-114">タイム スタンプ (社内使用向け)。</span><span class="sxs-lookup"><span data-stu-id="ec28a-114">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec28a-115"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="ec28a-115"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="ec28a-116">int</span><span class="sxs-lookup"><span data-stu-id="ec28a-116">int</span></span></p></td>
<td><p><span data-ttu-id="ec28a-117">Primary</span><span class="sxs-lookup"><span data-stu-id="ec28a-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="ec28a-118">この会議 URI を識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="ec28a-118">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec28a-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="ec28a-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ec28a-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ec28a-120">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec28a-121">会議 URI。</span><span class="sxs-lookup"><span data-stu-id="ec28a-121">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec28a-122"><strong>チェックサム</strong></span><span class="sxs-lookup"><span data-stu-id="ec28a-122"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="ec28a-123">int</span><span class="sxs-lookup"><span data-stu-id="ec28a-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec28a-p102">ConferenceUri のチェックサム。データベース検索の速度を速めるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ec28a-p102">Checksum of ConferenceUri. Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec28a-126"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="ec28a-126"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="ec28a-127">int</span><span class="sxs-lookup"><span data-stu-id="ec28a-127">int</span></span></p></td>
<td><p><span data-ttu-id="ec28a-128">外部</span><span class="sxs-lookup"><span data-stu-id="ec28a-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ec28a-129">URI の種類。たとえば、「conf: IM 会議用チャット」または「conf: 音声ビデオ会議用の音声ビデオ」など。</span><span class="sxs-lookup"><span data-stu-id="ec28a-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="ec28a-130">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013</a> の表の UriTypes」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec28a-130">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

