---
title: 'Lync Server 2013: UserStatistics テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserStatistics table
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49733827
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0f684850625f61ca72bbcc9c4bc53b56fcc6b38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="3e64c-102">Lync Server 2013 の UserStatistics テーブル</span><span class="sxs-lookup"><span data-stu-id="3e64c-102">UserStatistics table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e64c-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3e64c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3e64c-104">UserStatistics テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="3e64c-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="3e64c-105">テーブルの各レコードには、個々のユーザーによるシステムの使用状況に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="3e64c-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="3e64c-106">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3e64c-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e64c-107">列</span><span class="sxs-lookup"><span data-stu-id="3e64c-107">Column</span></span></th>
<th><span data-ttu-id="3e64c-108">データ型</span><span class="sxs-lookup"><span data-stu-id="3e64c-108">Data Type</span></span></th>
<th><span data-ttu-id="3e64c-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="3e64c-109">Key/Index</span></span></th>
<th><span data-ttu-id="3e64c-110">詳細</span><span class="sxs-lookup"><span data-stu-id="3e64c-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e64c-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="3e64c-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="3e64c-112">int</span><span class="sxs-lookup"><span data-stu-id="3e64c-112">int</span></span></p></td>
<td><p><span data-ttu-id="3e64c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="3e64c-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="3e64c-114">このユーザーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="3e64c-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e64c-115"><strong>最終ログイン時間</strong></span><span class="sxs-lookup"><span data-stu-id="3e64c-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3e64c-116">datetime</span><span class="sxs-lookup"><span data-stu-id="3e64c-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e64c-117">前回ユーザーがログインした日時。</span><span class="sxs-lookup"><span data-stu-id="3e64c-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e64c-118"><strong>Lastconforizedtime</strong></span><span class="sxs-lookup"><span data-stu-id="3e64c-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3e64c-119">datetime</span><span class="sxs-lookup"><span data-stu-id="3e64c-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e64c-120">ユーザーが最後に会議を開催した日時。</span><span class="sxs-lookup"><span data-stu-id="3e64c-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e64c-121"><strong>Lastcallオーガナイザー Ercallfailuretime</strong></span><span class="sxs-lookup"><span data-stu-id="3e64c-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3e64c-122">datetime</span><span class="sxs-lookup"><span data-stu-id="3e64c-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e64c-123">前回ユーザーが通話の失敗を経験した日時。</span><span class="sxs-lookup"><span data-stu-id="3e64c-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e64c-124"><strong>Lastconforガント Izercallfailuretime</strong></span><span class="sxs-lookup"><span data-stu-id="3e64c-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3e64c-125">datetime</span><span class="sxs-lookup"><span data-stu-id="3e64c-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e64c-126">前回ユーザーが会議開催者として通話の失敗を経験した時刻。</span><span class="sxs-lookup"><span data-stu-id="3e64c-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

