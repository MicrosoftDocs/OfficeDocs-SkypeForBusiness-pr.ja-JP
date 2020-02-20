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
ms.openlocfilehash: 138fe5f989fb11986c3db6e134fa7f975a95c96e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="2c781-102">Lync Server 2013 の McuJoinsAndLeaves テーブル</span><span class="sxs-lookup"><span data-stu-id="2c781-102">McuJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c781-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="2c781-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2c781-104">この表の各レコードには、ユーザー参加または電話会議サーバーの1つの組み合わせに関する通話の詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2c781-104">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="2c781-105">たとえば、web 会議と音声ビデオの要素を含む会議にユーザーが参加すると、そのユーザーの web 会議への参加に対して1つのレコードが作成され、そのユーザーの音声/ビデオ会議の参加に対して別のレコードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2c781-105">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c781-106">列</span><span class="sxs-lookup"><span data-stu-id="2c781-106">Column</span></span></th>
<th><span data-ttu-id="2c781-107">データ型</span><span class="sxs-lookup"><span data-stu-id="2c781-107">Data Type</span></span></th>
<th><span data-ttu-id="2c781-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="2c781-108">Key/Index</span></span></th>
<th><span data-ttu-id="2c781-109">詳細</span><span class="sxs-lookup"><span data-stu-id="2c781-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c781-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="2c781-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2c781-111">日付型</span><span class="sxs-lookup"><span data-stu-id="2c781-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="2c781-112">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="2c781-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2c781-113">会議インスタンスの時間。</span><span class="sxs-lookup"><span data-stu-id="2c781-113">Time of conference instance.</span></span> <span data-ttu-id="2c781-114"><strong>Sessionidseq</strong>と組み合わせて、電話会議のインスタンスを一意に識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2c781-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="2c781-115">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a>の電話会議の表」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c781-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c781-116"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="2c781-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2c781-117">int</span><span class="sxs-lookup"><span data-stu-id="2c781-117">int</span></span></p></td>
<td><p><span data-ttu-id="2c781-118">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="2c781-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2c781-119">会議インスタンスを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="2c781-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="2c781-120"><strong>Sessionidtime</strong>と組み合わせて、電話会議のインスタンスを一意に識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2c781-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="2c781-121">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a>の電話会議の表」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c781-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c781-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="2c781-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="2c781-123">int</span><span class="sxs-lookup"><span data-stu-id="2c781-123">int</span></span></p></td>
<td><p><span data-ttu-id="2c781-124">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="2c781-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2c781-125">このユーザーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="2c781-125">Unique number identifying this user.</span></span> <span data-ttu-id="2c781-126">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c781-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c781-127"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="2c781-127"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="2c781-128">int</span><span class="sxs-lookup"><span data-stu-id="2c781-128">int</span></span></p></td>
<td><p><span data-ttu-id="2c781-129">Primary</span><span class="sxs-lookup"><span data-stu-id="2c781-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="2c781-130">ユーザーが複数のコンピューターまたはデバイスで同時にログオンしている場合、McuUserInstance はユーザーとデバイスの組み合わせを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="2c781-130">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c781-131"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="2c781-131"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="2c781-132">若干</span><span class="sxs-lookup"><span data-stu-id="2c781-132">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2c781-133">ユーザーが PSTN から参加しているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="2c781-133">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c781-134"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="2c781-134"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="2c781-135">int</span><span class="sxs-lookup"><span data-stu-id="2c781-135">int</span></span></p></td>
<td><p><span data-ttu-id="2c781-136">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="2c781-136">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2c781-137">この会議サーバーを示す一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="2c781-137">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="2c781-138">詳細については、「 <a href="lync-server-2013-mcus-table.md">Lync Server 2013 の mcu テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c781-138">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c781-139"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="2c781-139"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2c781-140">日付型</span><span class="sxs-lookup"><span data-stu-id="2c781-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="2c781-141">外部</span><span class="sxs-lookup"><span data-stu-id="2c781-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2c781-142">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="2c781-142">Time of session request.</span></span> <span data-ttu-id="2c781-143">セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="2c781-143">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="2c781-144">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c781-144">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c781-145"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2c781-145"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2c781-146">int</span><span class="sxs-lookup"><span data-stu-id="2c781-146">int</span></span></p></td>
<td><p><span data-ttu-id="2c781-147">外部</span><span class="sxs-lookup"><span data-stu-id="2c781-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2c781-148">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="2c781-148">ID number to identify the session.</span></span> <span data-ttu-id="2c781-149">セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="2c781-149">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="2c781-150">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c781-150">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c781-151"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="2c781-151"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2c781-152">日付型</span><span class="sxs-lookup"><span data-stu-id="2c781-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2c781-153">このユーザーがこの会議サーバーに参加した時刻。</span><span class="sxs-lookup"><span data-stu-id="2c781-153">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c781-154"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="2c781-154"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2c781-155">日付型</span><span class="sxs-lookup"><span data-stu-id="2c781-155">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2c781-156">このユーザーがこの会議サーバーから退室した時刻。</span><span class="sxs-lookup"><span data-stu-id="2c781-156">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c781-157"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="2c781-157"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="2c781-158">int</span><span class="sxs-lookup"><span data-stu-id="2c781-158">int</span></span></p></td>
<td><p><span data-ttu-id="2c781-159">外部</span><span class="sxs-lookup"><span data-stu-id="2c781-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2c781-160">電話会議で使用するクライアントソフトウェアのバージョン番号を指定する識別子。</span><span class="sxs-lookup"><span data-stu-id="2c781-160">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="2c781-161">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c781-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="2c781-162">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2c781-162">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

