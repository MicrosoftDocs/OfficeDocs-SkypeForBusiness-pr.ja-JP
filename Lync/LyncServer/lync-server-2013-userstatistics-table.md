---
title: 'Lync Server 2013: UserStatistics テーブル'
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
ms.openlocfilehash: 7609747848e1943a08eff2fa77b87f0168710f81
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="3f14b-102">Lync Server 2013 の UserStatistics テーブル</span><span class="sxs-lookup"><span data-stu-id="3f14b-102">UserStatistics table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f14b-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3f14b-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3f14b-104">UserStatistics テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="3f14b-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="3f14b-105">テーブルの各レコードには、個々のユーザーによるシステムの使用状況に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="3f14b-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="3f14b-106">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3f14b-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f14b-107">列</span><span class="sxs-lookup"><span data-stu-id="3f14b-107">Column</span></span></th>
<th><span data-ttu-id="3f14b-108">データ型</span><span class="sxs-lookup"><span data-stu-id="3f14b-108">Data Type</span></span></th>
<th><span data-ttu-id="3f14b-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="3f14b-109">Key/Index</span></span></th>
<th><span data-ttu-id="3f14b-110">詳細</span><span class="sxs-lookup"><span data-stu-id="3f14b-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f14b-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="3f14b-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f14b-112">int</span><span class="sxs-lookup"><span data-stu-id="3f14b-112">int</span></span></p></td>
<td><p><span data-ttu-id="3f14b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="3f14b-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="3f14b-114">このユーザーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="3f14b-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f14b-115"><strong>最終ログイン時間</strong></span><span class="sxs-lookup"><span data-stu-id="3f14b-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3f14b-116">datetime</span><span class="sxs-lookup"><span data-stu-id="3f14b-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f14b-117">前回ユーザーがログインした日時。</span><span class="sxs-lookup"><span data-stu-id="3f14b-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f14b-118"><strong>Lastconforizedtime</strong></span><span class="sxs-lookup"><span data-stu-id="3f14b-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3f14b-119">datetime</span><span class="sxs-lookup"><span data-stu-id="3f14b-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f14b-120">ユーザーが最後に会議を開催した日時。</span><span class="sxs-lookup"><span data-stu-id="3f14b-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f14b-121"><strong>Lastcallオーガナイザー Ercallfailuretime</strong></span><span class="sxs-lookup"><span data-stu-id="3f14b-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3f14b-122">datetime</span><span class="sxs-lookup"><span data-stu-id="3f14b-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f14b-123">前回ユーザーが通話の失敗を経験した日時。</span><span class="sxs-lookup"><span data-stu-id="3f14b-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f14b-124"><strong>Lastconforガント Izercallfailuretime</strong></span><span class="sxs-lookup"><span data-stu-id="3f14b-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3f14b-125">datetime</span><span class="sxs-lookup"><span data-stu-id="3f14b-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f14b-126">前回ユーザーが会議開催者として通話の失敗を経験した時刻。</span><span class="sxs-lookup"><span data-stu-id="3f14b-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

