---
title: 'Lync Server 2013: UserAgent テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent table
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48185582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 041db946d80226f626b7248f604f1b3fa00a7ffc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="useragent-table-in-lync-server-2013"></a><span data-ttu-id="382c5-102">Lync Server 2013 の UserAgent テーブル</span><span class="sxs-lookup"><span data-stu-id="382c5-102">UserAgent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="382c5-103">_**トピックの最終更新日:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="382c5-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="382c5-104">UserAgent テーブルは、データベースに記録されたセッションに参加しているさまざまなユーザーエージェントのリストを格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="382c5-104">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="382c5-105">テーブル内の各レコードは、1つのユーザーエージェントを表します。</span><span class="sxs-lookup"><span data-stu-id="382c5-105">Each record in the table represents one user agent</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="382c5-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="382c5-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="382c5-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="382c5-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="382c5-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="382c5-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="382c5-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="382c5-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="382c5-110"><strong>UserAgentKey</strong></span><span class="sxs-lookup"><span data-stu-id="382c5-110"><strong>UserAgentKey</strong></span></span></p></td>
<td><p><span data-ttu-id="382c5-111">int</span><span class="sxs-lookup"><span data-stu-id="382c5-111">int</span></span></p></td>
<td><p><span data-ttu-id="382c5-112">Primary</span><span class="sxs-lookup"><span data-stu-id="382c5-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="382c5-113">このユーザーエージェントを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="382c5-113">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="382c5-114"><strong>UserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="382c5-114"><strong>UserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="382c5-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="382c5-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="382c5-116">一意</span><span class="sxs-lookup"><span data-stu-id="382c5-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="382c5-117">ユーザーエージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="382c5-117">User Agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="382c5-118"><strong>UAType</strong></span><span class="sxs-lookup"><span data-stu-id="382c5-118"><strong>UAType</strong></span></span></p></td>
<td><p><span data-ttu-id="382c5-119">smallint</span><span class="sxs-lookup"><span data-stu-id="382c5-119">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="382c5-120">1は仲介サーバーです。</span><span class="sxs-lookup"><span data-stu-id="382c5-120">1 is Mediation Server.</span></span></p>
<p><span data-ttu-id="382c5-121">2は音声ビデオ会議サーバーです。</span><span class="sxs-lookup"><span data-stu-id="382c5-121">2 is A/V Conferencing Server.</span></span></p>
<p><span data-ttu-id="382c5-122">4は Lync です。</span><span class="sxs-lookup"><span data-stu-id="382c5-122">4 is Lync.</span></span></p>
<p><span data-ttu-id="382c5-123">8は IP 電話です。</span><span class="sxs-lookup"><span data-stu-id="382c5-123">8 is IP Phone.</span></span></p>
<p><span data-ttu-id="382c5-124">16は Live Meeting コンソールです。</span><span class="sxs-lookup"><span data-stu-id="382c5-124">16 is Live Meeting Console.</span></span></p>
<p><span data-ttu-id="382c5-125">32は展開検証ツール (DVT) です。</span><span class="sxs-lookup"><span data-stu-id="382c5-125">32 is Deployment Validation Tool (DVT).</span></span></p>
<p><span data-ttu-id="382c5-126">64は、Macintosh コンピューターの Lync です。</span><span class="sxs-lookup"><span data-stu-id="382c5-126">64 is Lync on Macintosh computers.</span></span></p>
<p><span data-ttu-id="382c5-127">128は、Office Communications Server 2007 R2 アテンダントです。</span><span class="sxs-lookup"><span data-stu-id="382c5-127">128 is Office Communications Server 2007 R2 Attendant.</span></span></p>
<p><span data-ttu-id="382c5-128">256は会議アナウンスサービスです。</span><span class="sxs-lookup"><span data-stu-id="382c5-128">256 is Conferencing Announcement service.</span></span></p>
<p><span data-ttu-id="382c5-129">512は、会議自動応答です。</span><span class="sxs-lookup"><span data-stu-id="382c5-129">512 is Conferencing Auto Attendant.</span></span></p>
<p><span data-ttu-id="382c5-130">1024は応答グループアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="382c5-130">1024 is Response Group application.</span></span></p>
<p><span data-ttu-id="382c5-131">2048は外部音声コントロールです。</span><span class="sxs-lookup"><span data-stu-id="382c5-131">2048 is Outside Voice Control.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

