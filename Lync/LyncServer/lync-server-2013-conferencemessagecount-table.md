---
title: 'Lync Server 2013: ConferenceMessageCount テーブル'
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
ms.openlocfilehash: 426ae4abca9f91fcabaedfb5a363703523d6aa94
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="7d6fb-102">Lync Server 2013 の ConferenceMessageCount テーブル</span><span class="sxs-lookup"><span data-stu-id="7d6fb-102">ConferenceMessageCount table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d6fb-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="7d6fb-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="7d6fb-104">このテーブル内の各レコードは、1人の IM 会議で1人のユーザーを表し、そのユーザーから送信されたメッセージの数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7d6fb-104">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="7d6fb-105">各会議は、この表の複数のレコードで表されます。ユーザーごとに1つのレコード。</span><span class="sxs-lookup"><span data-stu-id="7d6fb-105">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d6fb-106">列</span><span class="sxs-lookup"><span data-stu-id="7d6fb-106">Column</span></span></th>
<th><span data-ttu-id="7d6fb-107">データ型</span><span class="sxs-lookup"><span data-stu-id="7d6fb-107">Data Type</span></span></th>
<th><span data-ttu-id="7d6fb-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="7d6fb-108">Key/Index</span></span></th>
<th><span data-ttu-id="7d6fb-109">詳細</span><span class="sxs-lookup"><span data-stu-id="7d6fb-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d6fb-110"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="7d6fb-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7d6fb-111">datetime</span><span class="sxs-lookup"><span data-stu-id="7d6fb-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="7d6fb-112">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="7d6fb-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7d6fb-113">会議インスタンスの時刻。</span><span class="sxs-lookup"><span data-stu-id="7d6fb-113">Time of conference instance.</span></span> <span data-ttu-id="7d6fb-114">電話会議インスタンスを一意に識別するために<strong>Sessionidseq</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="7d6fb-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="7d6fb-115">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 での会議の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d6fb-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d6fb-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7d6fb-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7d6fb-117">int</span><span class="sxs-lookup"><span data-stu-id="7d6fb-117">int</span></span></p></td>
<td><p><span data-ttu-id="7d6fb-118">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="7d6fb-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7d6fb-119">会議インスタンスを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="7d6fb-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="7d6fb-120">電話会議インスタンスを一意に識別するために<strong>Sessionidtime</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="7d6fb-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="7d6fb-121">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 での会議の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d6fb-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d6fb-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="7d6fb-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="7d6fb-123">int</span><span class="sxs-lookup"><span data-stu-id="7d6fb-123">int</span></span></p></td>
<td><p><span data-ttu-id="7d6fb-124">外部</span><span class="sxs-lookup"><span data-stu-id="7d6fb-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7d6fb-125">このユーザーを識別する一意の番号です。 <a href="lync-server-2013-users-table.md">Lync Server 2013 の [ユーザー] テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="7d6fb-125">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d6fb-126"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="7d6fb-126"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="7d6fb-127">smallint</span><span class="sxs-lookup"><span data-stu-id="7d6fb-127">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7d6fb-128">この会議中にこのユーザーによって送信されたメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="7d6fb-128">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

