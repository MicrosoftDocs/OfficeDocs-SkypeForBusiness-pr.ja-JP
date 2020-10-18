---
title: 'Lync Server 2013: FocusJoinsAndLeaves テーブル'
description: 'Lync Server 2013: FocusJoinsAndLeaves テーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves table
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399026(v=OCS.15)
ms:contentKeyID: 48185690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5796de16ed204ce4f33935d937cbaa425d63a67f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577443"
---
# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="eb97a-103">Lync Server 2013 の FocusJoinsAndLeaves テーブル</span><span class="sxs-lookup"><span data-stu-id="eb97a-103">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb97a-104">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="eb97a-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="eb97a-105">この表の各レコードには、1つの会議に関する1人のユーザーの参加および退出情報に関する CDR 情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="eb97a-105">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="eb97a-106">各会議は、ユーザーが会議に参加および退室するたびに1つずつ、このテーブルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb97a-106">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb97a-107">Column</span><span class="sxs-lookup"><span data-stu-id="eb97a-107">Column</span></span></th>
<th><span data-ttu-id="eb97a-108">データ型</span><span class="sxs-lookup"><span data-stu-id="eb97a-108">Data Type</span></span></th>
<th><span data-ttu-id="eb97a-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="eb97a-109">Key/Index</span></span></th>
<th><span data-ttu-id="eb97a-110">詳細</span><span class="sxs-lookup"><span data-stu-id="eb97a-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb97a-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="eb97a-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="eb97a-112">日付型</span><span class="sxs-lookup"><span data-stu-id="eb97a-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="eb97a-113">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="eb97a-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb97a-114">会議インスタンスの時間。</span><span class="sxs-lookup"><span data-stu-id="eb97a-114">Time of conference instance.</span></span> <span data-ttu-id="eb97a-115"><strong>Sessionidseq</strong>と組み合わせて、電話会議のインスタンスを一意に識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="eb97a-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="eb97a-116">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a> の電話会議の表」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb97a-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb97a-117"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="eb97a-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="eb97a-118">int</span><span class="sxs-lookup"><span data-stu-id="eb97a-118">int</span></span></p></td>
<td><p><span data-ttu-id="eb97a-119">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="eb97a-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb97a-120">会議インスタンスを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="eb97a-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="eb97a-121"><strong>Sessionidtime</strong>と組み合わせて、電話会議のインスタンスを一意に識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="eb97a-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="eb97a-122">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a> の電話会議の表」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb97a-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb97a-123"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="eb97a-123"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="eb97a-124">日付型</span><span class="sxs-lookup"><span data-stu-id="eb97a-124">datetime</span></span></p></td>
<td><p><span data-ttu-id="eb97a-125">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="eb97a-125">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb97a-126">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="eb97a-126">Time of session request.</span></span> <span data-ttu-id="eb97a-127">セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="eb97a-127">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="eb97a-128">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb97a-128">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb97a-129"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="eb97a-129"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="eb97a-130">int</span><span class="sxs-lookup"><span data-stu-id="eb97a-130">int</span></span></p></td>
<td><p><span data-ttu-id="eb97a-131">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="eb97a-131">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb97a-132">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="eb97a-132">ID number to identify the session.</span></span> <span data-ttu-id="eb97a-133">セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="eb97a-133">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="eb97a-134">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb97a-134">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb97a-135"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="eb97a-135"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="eb97a-136">int</span><span class="sxs-lookup"><span data-stu-id="eb97a-136">int</span></span></p></td>
<td><p><span data-ttu-id="eb97a-137">外部</span><span class="sxs-lookup"><span data-stu-id="eb97a-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb97a-138">このユーザーを示す一意の番号。 <a href="lync-server-2013-users-table.md">Lync Server 2013 の [ユーザー] テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="eb97a-138">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb97a-139"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="eb97a-139"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="eb97a-140">int</span><span class="sxs-lookup"><span data-stu-id="eb97a-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eb97a-141">ユーザーが複数のコンピューターまたはデバイスで同時にログオンしている場合、 <strong>UserInstance</strong> を使用して、ユーザーとデバイスの組み合わせを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="eb97a-141">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb97a-142"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="eb97a-142"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="eb97a-143">若干</span><span class="sxs-lookup"><span data-stu-id="eb97a-143">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eb97a-144">ユーザーが内部からログオンしたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="eb97a-144">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb97a-145"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="eb97a-145"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="eb97a-146">int</span><span class="sxs-lookup"><span data-stu-id="eb97a-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eb97a-147">会議でのこのユーザーの役割 (発表者や参加者など)。</span><span class="sxs-lookup"><span data-stu-id="eb97a-147">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb97a-148"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="eb97a-148"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="eb97a-149">日付型</span><span class="sxs-lookup"><span data-stu-id="eb97a-149">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eb97a-150">このユーザーが会議に参加した時刻。</span><span class="sxs-lookup"><span data-stu-id="eb97a-150">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb97a-151"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="eb97a-151"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="eb97a-152">日付型</span><span class="sxs-lookup"><span data-stu-id="eb97a-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eb97a-153">このユーザーが会議から退席した時刻。</span><span class="sxs-lookup"><span data-stu-id="eb97a-153">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb97a-154"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="eb97a-154"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="eb97a-155">int</span><span class="sxs-lookup"><span data-stu-id="eb97a-155">int</span></span></p></td>
<td><p><span data-ttu-id="eb97a-156">外部</span><span class="sxs-lookup"><span data-stu-id="eb97a-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb97a-157">ユーザーのクライアントソフトウェアのバージョン。 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions テーブル</a>に参照されます。</span><span class="sxs-lookup"><span data-stu-id="eb97a-157">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb97a-158"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="eb97a-158"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="eb97a-159">識別子</span><span class="sxs-lookup"><span data-stu-id="eb97a-159">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eb97a-160">電話会議で使用されるエンドポイントのグローバル一意識別子 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="eb97a-160">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="eb97a-161">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="eb97a-161">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

