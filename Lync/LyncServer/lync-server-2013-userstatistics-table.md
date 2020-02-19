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
ms.openlocfilehash: 2758b52b44a58095203deb7e70387934f723ee97
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="000a0-102">Lync Server 2013 の UserStatistics テーブル</span><span class="sxs-lookup"><span data-stu-id="000a0-102">UserStatistics table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="000a0-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="000a0-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="000a0-104">UserStatistics テーブルはサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="000a0-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="000a0-105">このテーブル内の各レコードは、システムの個々のユーザーの使用状況についての情報を格納しています。</span><span class="sxs-lookup"><span data-stu-id="000a0-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="000a0-106">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="000a0-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="000a0-107">列</span><span class="sxs-lookup"><span data-stu-id="000a0-107">Column</span></span></th>
<th><span data-ttu-id="000a0-108">データ型</span><span class="sxs-lookup"><span data-stu-id="000a0-108">Data Type</span></span></th>
<th><span data-ttu-id="000a0-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="000a0-109">Key/Index</span></span></th>
<th><span data-ttu-id="000a0-110">詳細</span><span class="sxs-lookup"><span data-stu-id="000a0-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="000a0-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="000a0-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="000a0-112">int</span><span class="sxs-lookup"><span data-stu-id="000a0-112">int</span></span></p></td>
<td><p><span data-ttu-id="000a0-113">Primary</span><span class="sxs-lookup"><span data-stu-id="000a0-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="000a0-114">このユーザーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="000a0-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="000a0-115"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="000a0-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="000a0-116">日付型</span><span class="sxs-lookup"><span data-stu-id="000a0-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="000a0-117">ユーザーが最後にログインした時刻。</span><span class="sxs-lookup"><span data-stu-id="000a0-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="000a0-118"><strong>Lastconforガント Izedtime</strong></span><span class="sxs-lookup"><span data-stu-id="000a0-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="000a0-119">日付型</span><span class="sxs-lookup"><span data-stu-id="000a0-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="000a0-120">ユーザーが最後に会議を開催した時刻。</span><span class="sxs-lookup"><span data-stu-id="000a0-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="000a0-121"><strong>Lastcallオーガナイザー Ercallfailuretime</strong></span><span class="sxs-lookup"><span data-stu-id="000a0-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="000a0-122">日付型</span><span class="sxs-lookup"><span data-stu-id="000a0-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="000a0-123">ユーザーが最後に通話に失敗した時刻。</span><span class="sxs-lookup"><span data-stu-id="000a0-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="000a0-124"><strong>Lastconforガント Izercallfailuretime</strong></span><span class="sxs-lookup"><span data-stu-id="000a0-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="000a0-125">日付型</span><span class="sxs-lookup"><span data-stu-id="000a0-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="000a0-126">ユーザーが会議開催者として最後に通話に失敗した時刻。</span><span class="sxs-lookup"><span data-stu-id="000a0-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

