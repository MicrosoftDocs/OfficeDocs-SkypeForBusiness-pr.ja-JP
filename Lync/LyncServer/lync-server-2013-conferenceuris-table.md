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
ms.openlocfilehash: e9142be1b2d46a7d7634394970d07dfa450a22e1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529174"
---
# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="05b9d-102">Lync Server 2013 の ConferenceUris テーブル</span><span class="sxs-lookup"><span data-stu-id="05b9d-102">ConferenceUris table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05b9d-103">_**トピックの最終更新日:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="05b9d-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="05b9d-p101">ConfereneUris テーブルは、データベースに記録されている会議セッションに参加したさまざまな会議 URI の一覧を格納する補助的なテーブルです。このテーブルの個々のレコードが、1 つの会議 URI を表します。</span><span class="sxs-lookup"><span data-stu-id="05b9d-p101">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database. Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05b9d-106">Column</span><span class="sxs-lookup"><span data-stu-id="05b9d-106">Column</span></span></th>
<th><span data-ttu-id="05b9d-107">データ型</span><span class="sxs-lookup"><span data-stu-id="05b9d-107">Data Type</span></span></th>
<th><span data-ttu-id="05b9d-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="05b9d-108">Key/Index</span></span></th>
<th><span data-ttu-id="05b9d-109">詳細</span><span class="sxs-lookup"><span data-stu-id="05b9d-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05b9d-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="05b9d-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="05b9d-111">日付型</span><span class="sxs-lookup"><span data-stu-id="05b9d-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="05b9d-112">Primary</span><span class="sxs-lookup"><span data-stu-id="05b9d-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="05b9d-113">タイム スタンプ (社内使用向け)。</span><span class="sxs-lookup"><span data-stu-id="05b9d-113">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05b9d-114"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="05b9d-114"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="05b9d-115">int</span><span class="sxs-lookup"><span data-stu-id="05b9d-115">int</span></span></p></td>
<td><p><span data-ttu-id="05b9d-116">Primary</span><span class="sxs-lookup"><span data-stu-id="05b9d-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="05b9d-117">この会議 URI を識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="05b9d-117">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05b9d-118"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="05b9d-118"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="05b9d-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="05b9d-119">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05b9d-120">会議 URI。</span><span class="sxs-lookup"><span data-stu-id="05b9d-120">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05b9d-121"><strong>チェックサム</strong></span><span class="sxs-lookup"><span data-stu-id="05b9d-121"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="05b9d-122">int</span><span class="sxs-lookup"><span data-stu-id="05b9d-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05b9d-p102">ConferenceUri のチェックサム。データベース検索の速度を速めるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="05b9d-p102">Checksum of ConferenceUri. Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05b9d-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="05b9d-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="05b9d-126">int</span><span class="sxs-lookup"><span data-stu-id="05b9d-126">int</span></span></p></td>
<td><p><span data-ttu-id="05b9d-127">外部</span><span class="sxs-lookup"><span data-stu-id="05b9d-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="05b9d-128">URI の種類。たとえば、「conf: IM 会議用チャット」または「conf: 音声ビデオ会議用の音声ビデオ」など。</span><span class="sxs-lookup"><span data-stu-id="05b9d-128">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="05b9d-129">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013</a> の表の UriTypes」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05b9d-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

