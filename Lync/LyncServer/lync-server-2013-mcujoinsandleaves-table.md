---
title: 'Lync Server 2013: McuJoinsAndLeaves テーブル'
description: 'Lync Server 2013: McuJoinsAndLeaves テーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves table
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398316(v=OCS.15)
ms:contentKeyID: 48184115
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee7d9473892ac357dcefd80b0d52382c5dd7d930
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556503"
---
# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="cdb6a-103">Lync Server 2013 の McuJoinsAndLeaves テーブル</span><span class="sxs-lookup"><span data-stu-id="cdb6a-103">McuJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cdb6a-104">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="cdb6a-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="cdb6a-105">この表の各レコードには、ユーザー参加または電話会議サーバーの1つの組み合わせに関する通話の詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cdb6a-105">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="cdb6a-106">たとえば、web 会議と音声ビデオの要素を含む会議にユーザーが参加すると、そのユーザーの web 会議への参加に対して1つのレコードが作成され、そのユーザーの音声/ビデオ会議の参加に対して別のレコードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cdb6a-106">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cdb6a-107">Column</span><span class="sxs-lookup"><span data-stu-id="cdb6a-107">Column</span></span></th>
<th><span data-ttu-id="cdb6a-108">データ型</span><span class="sxs-lookup"><span data-stu-id="cdb6a-108">Data Type</span></span></th>
<th><span data-ttu-id="cdb6a-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="cdb6a-109">Key/Index</span></span></th>
<th><span data-ttu-id="cdb6a-110">詳細</span><span class="sxs-lookup"><span data-stu-id="cdb6a-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdb6a-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="cdb6a-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cdb6a-112">日付型</span><span class="sxs-lookup"><span data-stu-id="cdb6a-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="cdb6a-113">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="cdb6a-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="cdb6a-114">会議インスタンスの時間。</span><span class="sxs-lookup"><span data-stu-id="cdb6a-114">Time of conference instance.</span></span> <span data-ttu-id="cdb6a-115"><strong>Sessionidseq</strong>と組み合わせて、電話会議のインスタンスを一意に識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="cdb6a-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="cdb6a-116">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a> の電話会議の表」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdb6a-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdb6a-117"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="cdb6a-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="cdb6a-118">int</span><span class="sxs-lookup"><span data-stu-id="cdb6a-118">int</span></span></p></td>
<td><p><span data-ttu-id="cdb6a-119">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="cdb6a-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="cdb6a-120">会議インスタンスを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="cdb6a-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="cdb6a-121"><strong>Sessionidtime</strong>と組み合わせて、電話会議のインスタンスを一意に識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="cdb6a-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="cdb6a-122">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a> の電話会議の表」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdb6a-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdb6a-123"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="cdb6a-123"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="cdb6a-124">int</span><span class="sxs-lookup"><span data-stu-id="cdb6a-124">int</span></span></p></td>
<td><p><span data-ttu-id="cdb6a-125">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="cdb6a-125">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="cdb6a-126">このユーザーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="cdb6a-126">Unique number identifying this user.</span></span> <span data-ttu-id="cdb6a-127">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdb6a-127">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdb6a-128"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="cdb6a-128"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="cdb6a-129">int</span><span class="sxs-lookup"><span data-stu-id="cdb6a-129">int</span></span></p></td>
<td><p><span data-ttu-id="cdb6a-130">Primary</span><span class="sxs-lookup"><span data-stu-id="cdb6a-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="cdb6a-131">ユーザーが複数のコンピューターまたはデバイスで同時にログオンしている場合、McuUserInstance はユーザーとデバイスの組み合わせを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="cdb6a-131">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdb6a-132"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="cdb6a-132"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="cdb6a-133">若干</span><span class="sxs-lookup"><span data-stu-id="cdb6a-133">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cdb6a-134">ユーザーが PSTN から参加しているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="cdb6a-134">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdb6a-135"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="cdb6a-135"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="cdb6a-136">int</span><span class="sxs-lookup"><span data-stu-id="cdb6a-136">int</span></span></p></td>
<td><p><span data-ttu-id="cdb6a-137">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="cdb6a-137">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="cdb6a-138">この会議サーバーを示す一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="cdb6a-138">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="cdb6a-139">詳細については、「 <a href="lync-server-2013-mcus-table.md">Lync Server 2013 の mcu テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdb6a-139">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdb6a-140"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="cdb6a-140"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cdb6a-141">日付型</span><span class="sxs-lookup"><span data-stu-id="cdb6a-141">datetime</span></span></p></td>
<td><p><span data-ttu-id="cdb6a-142">外部</span><span class="sxs-lookup"><span data-stu-id="cdb6a-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cdb6a-143">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="cdb6a-143">Time of session request.</span></span> <span data-ttu-id="cdb6a-144">セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="cdb6a-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="cdb6a-145">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdb6a-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdb6a-146"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="cdb6a-146"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="cdb6a-147">int</span><span class="sxs-lookup"><span data-stu-id="cdb6a-147">int</span></span></p></td>
<td><p><span data-ttu-id="cdb6a-148">外部</span><span class="sxs-lookup"><span data-stu-id="cdb6a-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cdb6a-149">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="cdb6a-149">ID number to identify the session.</span></span> <span data-ttu-id="cdb6a-150">セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="cdb6a-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="cdb6a-151">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdb6a-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdb6a-152"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="cdb6a-152"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cdb6a-153">日付型</span><span class="sxs-lookup"><span data-stu-id="cdb6a-153">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cdb6a-154">このユーザーがこの会議サーバーに参加した時刻。</span><span class="sxs-lookup"><span data-stu-id="cdb6a-154">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdb6a-155"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="cdb6a-155"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cdb6a-156">日付型</span><span class="sxs-lookup"><span data-stu-id="cdb6a-156">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cdb6a-157">このユーザーがこの会議サーバーから退室した時刻。</span><span class="sxs-lookup"><span data-stu-id="cdb6a-157">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdb6a-158"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="cdb6a-158"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="cdb6a-159">int</span><span class="sxs-lookup"><span data-stu-id="cdb6a-159">int</span></span></p></td>
<td><p><span data-ttu-id="cdb6a-160">外部</span><span class="sxs-lookup"><span data-stu-id="cdb6a-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cdb6a-161">電話会議で使用するクライアントソフトウェアのバージョン番号を指定する識別子。</span><span class="sxs-lookup"><span data-stu-id="cdb6a-161">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="cdb6a-162">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdb6a-162">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="cdb6a-163">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cdb6a-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

