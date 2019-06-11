---
title: 'Lync Server 2013: McuJoinsAndLeaves テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: McuJoinsAndLeaves table
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398316(v=OCS.15)
ms:contentKeyID: 48184115
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a936b6d6d9b371238873909646a146b94f659c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="75cd7-102">Lync Server 2013 の McuJoinsAndLeaves テーブル</span><span class="sxs-lookup"><span data-stu-id="75cd7-102">McuJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75cd7-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="75cd7-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="75cd7-104">この表の各レコードには、ユーザーの参加または退出と会議サーバーの1つの組み合わせについての通話の詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="75cd7-104">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="75cd7-105">たとえば、web 会議や音声/ビデオの要素を含む会議にユーザーが参加した場合、そのユーザーの web 会議参加用に1つのレコードが作成され、ユーザーの音声/ビデオ会議の参加用に別のレコードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="75cd7-105">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75cd7-106">列</span><span class="sxs-lookup"><span data-stu-id="75cd7-106">Column</span></span></th>
<th><span data-ttu-id="75cd7-107">データ型</span><span class="sxs-lookup"><span data-stu-id="75cd7-107">Data Type</span></span></th>
<th><span data-ttu-id="75cd7-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="75cd7-108">Key/Index</span></span></th>
<th><span data-ttu-id="75cd7-109">詳細</span><span class="sxs-lookup"><span data-stu-id="75cd7-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75cd7-110"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="75cd7-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="75cd7-111">datetime</span><span class="sxs-lookup"><span data-stu-id="75cd7-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="75cd7-112">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="75cd7-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="75cd7-113">会議インスタンスの時刻。</span><span class="sxs-lookup"><span data-stu-id="75cd7-113">Time of conference instance.</span></span> <span data-ttu-id="75cd7-114">電話会議インスタンスを一意に識別するために<strong>Sessionidseq</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="75cd7-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="75cd7-115">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 での会議の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75cd7-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75cd7-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="75cd7-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="75cd7-117">int</span><span class="sxs-lookup"><span data-stu-id="75cd7-117">int</span></span></p></td>
<td><p><span data-ttu-id="75cd7-118">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="75cd7-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="75cd7-119">会議インスタンスを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="75cd7-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="75cd7-120">電話会議インスタンスを一意に識別するために<strong>Sessionidtime</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="75cd7-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="75cd7-121">詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 での会議の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75cd7-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75cd7-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="75cd7-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="75cd7-123">int</span><span class="sxs-lookup"><span data-stu-id="75cd7-123">int</span></span></p></td>
<td><p><span data-ttu-id="75cd7-124">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="75cd7-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="75cd7-125">このユーザーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="75cd7-125">Unique number identifying this user.</span></span> <span data-ttu-id="75cd7-126">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75cd7-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75cd7-127"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="75cd7-127"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="75cd7-128">int</span><span class="sxs-lookup"><span data-stu-id="75cd7-128">int</span></span></p></td>
<td><p><span data-ttu-id="75cd7-129">Primary</span><span class="sxs-lookup"><span data-stu-id="75cd7-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="75cd7-130">ユーザーが複数のコンピューターまたはデバイスに一度にログオンしている場合、McuUserInstance はユーザーとデバイスの組み合わせを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="75cd7-130">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75cd7-131"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="75cd7-131"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="75cd7-132">bit</span><span class="sxs-lookup"><span data-stu-id="75cd7-132">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="75cd7-133">ユーザーが PSTN から参加しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="75cd7-133">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75cd7-134"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="75cd7-134"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="75cd7-135">int</span><span class="sxs-lookup"><span data-stu-id="75cd7-135">int</span></span></p></td>
<td><p><span data-ttu-id="75cd7-136">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="75cd7-136">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="75cd7-137">この会議サーバーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="75cd7-137">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="75cd7-138">詳細については、「 <a href="lync-server-2013-mcus-table.md">Lync Server 2013 での mcu の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75cd7-138">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75cd7-139"><strong>/セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="75cd7-139"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="75cd7-140">datetime</span><span class="sxs-lookup"><span data-stu-id="75cd7-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="75cd7-141">外部</span><span class="sxs-lookup"><span data-stu-id="75cd7-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="75cd7-142">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="75cd7-142">Time of session request.</span></span> <span data-ttu-id="75cd7-143">セッションを一意に識別するために<strong>Sessionidseq</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="75cd7-143">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="75cd7-144">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75cd7-144">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75cd7-145"><strong>"/セッション Id"</strong></span><span class="sxs-lookup"><span data-stu-id="75cd7-145"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="75cd7-146">int</span><span class="sxs-lookup"><span data-stu-id="75cd7-146">int</span></span></p></td>
<td><p><span data-ttu-id="75cd7-147">外部</span><span class="sxs-lookup"><span data-stu-id="75cd7-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="75cd7-148">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="75cd7-148">ID number to identify the session.</span></span> <span data-ttu-id="75cd7-149">セッションを一意に識別するために<strong>Sessionidtime</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="75cd7-149">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="75cd7-150">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75cd7-150">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75cd7-151"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="75cd7-151"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="75cd7-152">datetime</span><span class="sxs-lookup"><span data-stu-id="75cd7-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="75cd7-153">このユーザーがこの会議サーバーに参加する時刻です。</span><span class="sxs-lookup"><span data-stu-id="75cd7-153">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75cd7-154"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="75cd7-154"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="75cd7-155">datetime</span><span class="sxs-lookup"><span data-stu-id="75cd7-155">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="75cd7-156">このユーザーがこの会議サーバーから退席した時刻。</span><span class="sxs-lookup"><span data-stu-id="75cd7-156">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75cd7-157"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="75cd7-157"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="75cd7-158">int</span><span class="sxs-lookup"><span data-stu-id="75cd7-158">int</span></span></p></td>
<td><p><span data-ttu-id="75cd7-159">外部</span><span class="sxs-lookup"><span data-stu-id="75cd7-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="75cd7-160">電話会議で使用するクライアントソフトウェアのバージョン番号を指定する識別子。</span><span class="sxs-lookup"><span data-stu-id="75cd7-160">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="75cd7-161">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75cd7-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="75cd7-162">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="75cd7-162">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

