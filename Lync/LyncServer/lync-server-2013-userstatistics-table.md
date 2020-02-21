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
ms.openlocfilehash: 876d861e62014738816c02e2a6c2628f5dd46fc0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212883"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="dafad-102">Lync Server 2013 の UserStatistics テーブル</span><span class="sxs-lookup"><span data-stu-id="dafad-102">UserStatistics table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dafad-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="dafad-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="dafad-104">UserStatistics テーブルはサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="dafad-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="dafad-105">このテーブル内の各レコードは、システムの個々のユーザーの使用状況についての情報を格納しています。</span><span class="sxs-lookup"><span data-stu-id="dafad-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="dafad-106">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="dafad-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dafad-107">列</span><span class="sxs-lookup"><span data-stu-id="dafad-107">Column</span></span></th>
<th><span data-ttu-id="dafad-108">データ型</span><span class="sxs-lookup"><span data-stu-id="dafad-108">Data Type</span></span></th>
<th><span data-ttu-id="dafad-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="dafad-109">Key/Index</span></span></th>
<th><span data-ttu-id="dafad-110">詳細</span><span class="sxs-lookup"><span data-stu-id="dafad-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dafad-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="dafad-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="dafad-112">int</span><span class="sxs-lookup"><span data-stu-id="dafad-112">int</span></span></p></td>
<td><p><span data-ttu-id="dafad-113">Primary</span><span class="sxs-lookup"><span data-stu-id="dafad-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="dafad-114">このユーザーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="dafad-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dafad-115"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="dafad-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dafad-116">日付型</span><span class="sxs-lookup"><span data-stu-id="dafad-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dafad-117">ユーザーが最後にログインした時刻。</span><span class="sxs-lookup"><span data-stu-id="dafad-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dafad-118"><strong>Lastconforガント Izedtime</strong></span><span class="sxs-lookup"><span data-stu-id="dafad-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dafad-119">日付型</span><span class="sxs-lookup"><span data-stu-id="dafad-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dafad-120">ユーザーが最後に会議を開催した時刻。</span><span class="sxs-lookup"><span data-stu-id="dafad-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dafad-121"><strong>Lastcallオーガナイザー Ercallfailuretime</strong></span><span class="sxs-lookup"><span data-stu-id="dafad-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dafad-122">日付型</span><span class="sxs-lookup"><span data-stu-id="dafad-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dafad-123">ユーザーが最後に通話に失敗した時刻。</span><span class="sxs-lookup"><span data-stu-id="dafad-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dafad-124"><strong>Lastconforガント Izercallfailuretime</strong></span><span class="sxs-lookup"><span data-stu-id="dafad-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dafad-125">日付型</span><span class="sxs-lookup"><span data-stu-id="dafad-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dafad-126">ユーザーが会議開催者として最後に通話に失敗した時刻。</span><span class="sxs-lookup"><span data-stu-id="dafad-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

