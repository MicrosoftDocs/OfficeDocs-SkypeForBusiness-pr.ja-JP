---
title: 'Lync Server 2013: ConferenceUris テーブル'
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
ms.openlocfilehash: 3cacbaf4e8c7c826ae2e00e9c86b44cc8387f315
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="44975-102">Lync Server 2013 の ConferenceUris テーブル</span><span class="sxs-lookup"><span data-stu-id="44975-102">ConferenceUris table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44975-103">_**最終更新日:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="44975-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="44975-104">ConfereneUris テーブルは、データベースに記録された会議セッションに参加しているさまざまな会議の Uri のリストを格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="44975-104">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="44975-105">テーブル内の各レコードは、1つの会議 URI を表します。</span><span class="sxs-lookup"><span data-stu-id="44975-105">Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44975-106">列</span><span class="sxs-lookup"><span data-stu-id="44975-106">Column</span></span></th>
<th><span data-ttu-id="44975-107">データ型</span><span class="sxs-lookup"><span data-stu-id="44975-107">Data Type</span></span></th>
<th><span data-ttu-id="44975-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="44975-108">Key/Index</span></span></th>
<th><span data-ttu-id="44975-109">詳細</span><span class="sxs-lookup"><span data-stu-id="44975-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44975-110"><strong>Nextupdatupdat</strong></span><span class="sxs-lookup"><span data-stu-id="44975-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="44975-111">datetime</span><span class="sxs-lookup"><span data-stu-id="44975-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="44975-112">Primary</span><span class="sxs-lookup"><span data-stu-id="44975-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="44975-113">タイムスタンプ、内部使用。</span><span class="sxs-lookup"><span data-stu-id="44975-113">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44975-114"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="44975-114"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="44975-115">int</span><span class="sxs-lookup"><span data-stu-id="44975-115">int</span></span></p></td>
<td><p><span data-ttu-id="44975-116">Primary</span><span class="sxs-lookup"><span data-stu-id="44975-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="44975-117">この会議 URI を識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="44975-117">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44975-118"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="44975-118"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="44975-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="44975-119">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44975-120">会議の URI。</span><span class="sxs-lookup"><span data-stu-id="44975-120">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44975-121"><strong>サム</strong></span><span class="sxs-lookup"><span data-stu-id="44975-121"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="44975-122">int</span><span class="sxs-lookup"><span data-stu-id="44975-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44975-123">ConferenceUri のチェックサム。</span><span class="sxs-lookup"><span data-stu-id="44975-123">Checksum of ConferenceUri.</span></span> <span data-ttu-id="44975-124">データベースの検索速度を上げるために使われます。</span><span class="sxs-lookup"><span data-stu-id="44975-124">Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44975-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="44975-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="44975-126">int</span><span class="sxs-lookup"><span data-stu-id="44975-126">int</span></span></p></td>
<td><p><span data-ttu-id="44975-127">外部</span><span class="sxs-lookup"><span data-stu-id="44975-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="44975-128">URI の種類 ("conf: IM 会議用チャット" または "conf: 音声/ビデオ会議用のオーディオビデオ" など)。</span><span class="sxs-lookup"><span data-stu-id="44975-128">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="44975-129">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 テーブルの UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44975-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

