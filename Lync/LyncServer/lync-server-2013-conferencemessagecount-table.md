---
title: 'Lync Server 2013: ConferenceMessageCount テーブル'
description: 'Lync Server 2013: ConferenceMessageCount テーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount table
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398590(v=OCS.15)
ms:contentKeyID: 48184570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 271b654c09ab1aef194eb613e660de208aea1534
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561623"
---
# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="b2651-103">Lync Server 2013 の ConferenceMessageCount テーブル</span><span class="sxs-lookup"><span data-stu-id="b2651-103">ConferenceMessageCount table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2651-104">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b2651-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b2651-105">このテーブルの各レコードは、1つの IM 会議の1人のユーザーを表し、そのユーザーによって送信されたメッセージの数を含みます。</span><span class="sxs-lookup"><span data-stu-id="b2651-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="b2651-106">各会議は、この表の複数のレコードで表されます。ユーザーごとに1つのレコード。</span><span class="sxs-lookup"><span data-stu-id="b2651-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2651-107">Column</span><span class="sxs-lookup"><span data-stu-id="b2651-107">Column</span></span></th>
<th><span data-ttu-id="b2651-108">データ型</span><span class="sxs-lookup"><span data-stu-id="b2651-108">Data Type</span></span></th>
<th><span data-ttu-id="b2651-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="b2651-109">Key/Index</span></span></th>
<th><span data-ttu-id="b2651-110">詳細</span><span class="sxs-lookup"><span data-stu-id="b2651-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2651-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b2651-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b2651-112">日付型</span><span class="sxs-lookup"><span data-stu-id="b2651-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="b2651-113">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="b2651-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b2651-114">会議インスタンスの時間。</span><span class="sxs-lookup"><span data-stu-id="b2651-114">Time of conference instance.</span></span> <span data-ttu-id="b2651-115"><strong>Sessionidseq</strong>と組み合わせて、電話会議のインスタンスを一意に識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b2651-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="b2651-116">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a> の電話会議の表」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2651-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2651-117"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="b2651-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b2651-118">int</span><span class="sxs-lookup"><span data-stu-id="b2651-118">int</span></span></p></td>
<td><p><span data-ttu-id="b2651-119">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="b2651-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b2651-120">会議インスタンスを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="b2651-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="b2651-121"><strong>Sessionidtime</strong>と組み合わせて、電話会議のインスタンスを一意に識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b2651-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="b2651-122">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a> の電話会議の表」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2651-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2651-123"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="b2651-123"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="b2651-124">int</span><span class="sxs-lookup"><span data-stu-id="b2651-124">int</span></span></p></td>
<td><p><span data-ttu-id="b2651-125">外部</span><span class="sxs-lookup"><span data-stu-id="b2651-125">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b2651-126">このユーザーを示す一意の番号。 <a href="lync-server-2013-users-table.md">Lync Server 2013 の [ユーザー] テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="b2651-126">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2651-127"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="b2651-127"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="b2651-128">smallint</span><span class="sxs-lookup"><span data-stu-id="b2651-128">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b2651-129">この会議中にこのユーザーによって送信されたメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="b2651-129">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

