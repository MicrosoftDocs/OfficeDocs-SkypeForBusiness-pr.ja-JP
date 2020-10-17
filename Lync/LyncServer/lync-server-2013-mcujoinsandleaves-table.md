---
title: 'Lync Server 2013: McuJoinsAndLeaves テーブル'
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
ms.openlocfilehash: f4aa5fb14ff16d13b1cdff72f15c648f9e353922
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524734"
---
# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="939c0-102">Lync Server 2013 の McuJoinsAndLeaves テーブル</span><span class="sxs-lookup"><span data-stu-id="939c0-102">McuJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="939c0-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="939c0-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="939c0-104">この表の各レコードには、ユーザー参加または電話会議サーバーの1つの組み合わせに関する通話の詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="939c0-104">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="939c0-105">たとえば、web 会議と音声ビデオの要素を含む会議にユーザーが参加すると、そのユーザーの web 会議への参加に対して1つのレコードが作成され、そのユーザーの音声/ビデオ会議の参加に対して別のレコードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="939c0-105">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="939c0-106">Column</span><span class="sxs-lookup"><span data-stu-id="939c0-106">Column</span></span></th>
<th><span data-ttu-id="939c0-107">データ型</span><span class="sxs-lookup"><span data-stu-id="939c0-107">Data Type</span></span></th>
<th><span data-ttu-id="939c0-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="939c0-108">Key/Index</span></span></th>
<th><span data-ttu-id="939c0-109">詳細</span><span class="sxs-lookup"><span data-stu-id="939c0-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="939c0-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="939c0-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="939c0-111">日付型</span><span class="sxs-lookup"><span data-stu-id="939c0-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="939c0-112">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="939c0-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="939c0-113">会議インスタンスの時間。</span><span class="sxs-lookup"><span data-stu-id="939c0-113">Time of conference instance.</span></span> <span data-ttu-id="939c0-114"><strong>Sessionidseq</strong>と組み合わせて、電話会議のインスタンスを一意に識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="939c0-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="939c0-115">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a> の電話会議の表」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939c0-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="939c0-116"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="939c0-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="939c0-117">int</span><span class="sxs-lookup"><span data-stu-id="939c0-117">int</span></span></p></td>
<td><p><span data-ttu-id="939c0-118">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="939c0-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="939c0-119">会議インスタンスを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="939c0-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="939c0-120"><strong>Sessionidtime</strong>と組み合わせて、電話会議のインスタンスを一意に識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="939c0-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="939c0-121">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a> の電話会議の表」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939c0-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="939c0-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="939c0-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="939c0-123">int</span><span class="sxs-lookup"><span data-stu-id="939c0-123">int</span></span></p></td>
<td><p><span data-ttu-id="939c0-124">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="939c0-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="939c0-125">このユーザーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="939c0-125">Unique number identifying this user.</span></span> <span data-ttu-id="939c0-126">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939c0-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="939c0-127"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="939c0-127"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="939c0-128">int</span><span class="sxs-lookup"><span data-stu-id="939c0-128">int</span></span></p></td>
<td><p><span data-ttu-id="939c0-129">Primary</span><span class="sxs-lookup"><span data-stu-id="939c0-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="939c0-130">ユーザーが複数のコンピューターまたはデバイスで同時にログオンしている場合、McuUserInstance はユーザーとデバイスの組み合わせを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="939c0-130">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="939c0-131"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="939c0-131"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="939c0-132">若干</span><span class="sxs-lookup"><span data-stu-id="939c0-132">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="939c0-133">ユーザーが PSTN から参加しているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="939c0-133">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="939c0-134"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="939c0-134"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="939c0-135">int</span><span class="sxs-lookup"><span data-stu-id="939c0-135">int</span></span></p></td>
<td><p><span data-ttu-id="939c0-136">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="939c0-136">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="939c0-137">この会議サーバーを示す一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="939c0-137">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="939c0-138">詳細については、「 <a href="lync-server-2013-mcus-table.md">Lync Server 2013 の mcu テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939c0-138">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="939c0-139"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="939c0-139"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="939c0-140">日付型</span><span class="sxs-lookup"><span data-stu-id="939c0-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="939c0-141">外部</span><span class="sxs-lookup"><span data-stu-id="939c0-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="939c0-142">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="939c0-142">Time of session request.</span></span> <span data-ttu-id="939c0-143">セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="939c0-143">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="939c0-144">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939c0-144">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="939c0-145"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="939c0-145"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="939c0-146">int</span><span class="sxs-lookup"><span data-stu-id="939c0-146">int</span></span></p></td>
<td><p><span data-ttu-id="939c0-147">外部</span><span class="sxs-lookup"><span data-stu-id="939c0-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="939c0-148">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="939c0-148">ID number to identify the session.</span></span> <span data-ttu-id="939c0-149">セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="939c0-149">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="939c0-150">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939c0-150">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="939c0-151"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="939c0-151"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="939c0-152">日付型</span><span class="sxs-lookup"><span data-stu-id="939c0-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="939c0-153">このユーザーがこの会議サーバーに参加した時刻。</span><span class="sxs-lookup"><span data-stu-id="939c0-153">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="939c0-154"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="939c0-154"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="939c0-155">日付型</span><span class="sxs-lookup"><span data-stu-id="939c0-155">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="939c0-156">このユーザーがこの会議サーバーから退室した時刻。</span><span class="sxs-lookup"><span data-stu-id="939c0-156">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="939c0-157"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="939c0-157"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="939c0-158">int</span><span class="sxs-lookup"><span data-stu-id="939c0-158">int</span></span></p></td>
<td><p><span data-ttu-id="939c0-159">外部</span><span class="sxs-lookup"><span data-stu-id="939c0-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="939c0-160">電話会議で使用するクライアントソフトウェアのバージョン番号を指定する識別子。</span><span class="sxs-lookup"><span data-stu-id="939c0-160">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="939c0-161">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939c0-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="939c0-162">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="939c0-162">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

