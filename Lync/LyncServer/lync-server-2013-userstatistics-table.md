---
title: 'Lync Server 2013: UserStatistics テーブル'
description: 'Lync Server 2013: UserStatistics テーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserStatistics table
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49733827
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75b34fa3c34af4cc9cf2cacc6ae7feb4d217114c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548533"
---
# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="79a4c-103">Lync Server 2013 の UserStatistics テーブル</span><span class="sxs-lookup"><span data-stu-id="79a4c-103">UserStatistics table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79a4c-104">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="79a4c-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="79a4c-105">UserStatistics テーブルはサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="79a4c-105">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="79a4c-106">このテーブル内の各レコードは、システムの個々のユーザーの使用状況についての情報を格納しています。</span><span class="sxs-lookup"><span data-stu-id="79a4c-106">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="79a4c-107">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="79a4c-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79a4c-108">Column</span><span class="sxs-lookup"><span data-stu-id="79a4c-108">Column</span></span></th>
<th><span data-ttu-id="79a4c-109">データ型</span><span class="sxs-lookup"><span data-stu-id="79a4c-109">Data Type</span></span></th>
<th><span data-ttu-id="79a4c-110">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="79a4c-110">Key/Index</span></span></th>
<th><span data-ttu-id="79a4c-111">詳細</span><span class="sxs-lookup"><span data-stu-id="79a4c-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79a4c-112"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="79a4c-112"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="79a4c-113">int</span><span class="sxs-lookup"><span data-stu-id="79a4c-113">int</span></span></p></td>
<td><p><span data-ttu-id="79a4c-114">Primary</span><span class="sxs-lookup"><span data-stu-id="79a4c-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="79a4c-115">このユーザーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="79a4c-115">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79a4c-116"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="79a4c-116"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="79a4c-117">日付型</span><span class="sxs-lookup"><span data-stu-id="79a4c-117">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="79a4c-118">ユーザーが最後にログインした時刻。</span><span class="sxs-lookup"><span data-stu-id="79a4c-118">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79a4c-119"><strong>Lastconforガント Izedtime</strong></span><span class="sxs-lookup"><span data-stu-id="79a4c-119"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="79a4c-120">日付型</span><span class="sxs-lookup"><span data-stu-id="79a4c-120">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="79a4c-121">ユーザーが最後に会議を開催した時刻。</span><span class="sxs-lookup"><span data-stu-id="79a4c-121">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79a4c-122"><strong>Lastcallオーガナイザー Ercallfailuretime</strong></span><span class="sxs-lookup"><span data-stu-id="79a4c-122"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="79a4c-123">日付型</span><span class="sxs-lookup"><span data-stu-id="79a4c-123">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="79a4c-124">ユーザーが最後に通話に失敗した時刻。</span><span class="sxs-lookup"><span data-stu-id="79a4c-124">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79a4c-125"><strong>Lastconforガント Izercallfailuretime</strong></span><span class="sxs-lookup"><span data-stu-id="79a4c-125"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="79a4c-126">日付型</span><span class="sxs-lookup"><span data-stu-id="79a4c-126">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="79a4c-127">ユーザーが会議開催者として最後に通話に失敗した時刻。</span><span class="sxs-lookup"><span data-stu-id="79a4c-127">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

