---
title: 'Lync Server 2013: ConferenceSessionDetails テーブル'
description: 'Lync Server 2013: ConferenceSessionDetails テーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d101eb1607e366ab814e60acaeee80820fe87c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566783"
---
# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="4c5ff-103">Lync Server 2013 の ConferenceSessionDetails テーブル</span><span class="sxs-lookup"><span data-stu-id="4c5ff-103">ConferenceSessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c5ff-104">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="4c5ff-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4c5ff-105">各レコードは1つの電話会議セッションを表し、フォーカスがあるセッション、または特定の会議サーバーとのセッションのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c5ff-106">Column</span><span class="sxs-lookup"><span data-stu-id="4c5ff-106">Column</span></span></th>
<th><span data-ttu-id="4c5ff-107">データ型</span><span class="sxs-lookup"><span data-stu-id="4c5ff-107">Data Type</span></span></th>
<th><span data-ttu-id="4c5ff-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="4c5ff-108">Key/Index</span></span></th>
<th><span data-ttu-id="4c5ff-109">詳細</span><span class="sxs-lookup"><span data-stu-id="4c5ff-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c5ff-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-111">Datetime</span><span class="sxs-lookup"><span data-stu-id="4c5ff-111">Datetime</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-112">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="4c5ff-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-113">セッション要求の時刻。 <strong>Sessionidseq</strong> と組み合わせて、電話会議セッションを一意に識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-113">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="4c5ff-114">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c5ff-115"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-116">int</span><span class="sxs-lookup"><span data-stu-id="4c5ff-116">int</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-117">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="4c5ff-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-118">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-118">ID number to identify the session.</span></span> <span data-ttu-id="4c5ff-119"><strong>Sessionidtime</strong>と組み合わせて、電話会議セッションを一意に識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="4c5ff-120">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c5ff-121"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-121"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-122">int</span><span class="sxs-lookup"><span data-stu-id="4c5ff-122">int</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-123">外部</span><span class="sxs-lookup"><span data-stu-id="4c5ff-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-124">このセッションに関連する会議 URI にフォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-124">Focus conference URI related to this session.</span></span> <span data-ttu-id="4c5ff-125">詳細については、「 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-125">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="4c5ff-126">この URI は、フォーカスベースの会議 URI です。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-126">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c5ff-127"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-127"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-128">識別子</span><span class="sxs-lookup"><span data-stu-id="4c5ff-128">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c5ff-129">定期的な電話会議のインスタンスを区別する識別子。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-129">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="4c5ff-130">定期的な電話会議の各インスタンスは、ConferenceURI は同じですが、ConfInstance 値が異なります。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-130">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="4c5ff-131">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-131">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c5ff-132"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-132"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-133">int</span><span class="sxs-lookup"><span data-stu-id="4c5ff-133">int</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-134">外部</span><span class="sxs-lookup"><span data-stu-id="4c5ff-134">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-135">このセッションに関連する会議サーバーの会議 URI。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-135">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="4c5ff-136">詳細については、「 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-136">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="4c5ff-137">この URI は、会議サーバーベースの会議 URI です。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-137">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="4c5ff-138">フォーカス会議セッションの場合、この列は null になります。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-138">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c5ff-139"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-139"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-140">int</span><span class="sxs-lookup"><span data-stu-id="4c5ff-140">int</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-141">外部</span><span class="sxs-lookup"><span data-stu-id="4c5ff-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-142">電話会議セッションの1人のユーザーの ID。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-142">ID of one user in the conference session.</span></span> <span data-ttu-id="4c5ff-143">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-143">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c5ff-144"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-144"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-145">識別子</span><span class="sxs-lookup"><span data-stu-id="4c5ff-145">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c5ff-146">エンドポイントのインスタンスを識別する GUID。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-146">A GUID to identify the instance of endpoint.</span></span> <span data-ttu-id="4c5ff-147">たとえば、あるユーザーが同じアカウントを持つ別のコンピューターにログオンした場合、各マシンには異なるエンドポイント ID が設定されます。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-147">For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c5ff-148"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-148"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-149">int</span><span class="sxs-lookup"><span data-stu-id="4c5ff-149">int</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-150">外部</span><span class="sxs-lookup"><span data-stu-id="4c5ff-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-151">発信者が代理を務めているユーザーの ID を示します。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-151">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="4c5ff-152">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-152">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c5ff-153"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-153"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-154">int</span><span class="sxs-lookup"><span data-stu-id="4c5ff-154">int</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-155">外部</span><span class="sxs-lookup"><span data-stu-id="4c5ff-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-156">通話の参照元であるユーザーの ID。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-156">ID of the user by who the call is referred.</span></span> <span data-ttu-id="4c5ff-157">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c5ff-158"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-158"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-159">int</span><span class="sxs-lookup"><span data-stu-id="4c5ff-159">int</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-160">外部</span><span class="sxs-lookup"><span data-stu-id="4c5ff-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-161">電話会議ユーザーが使用するクライアントバージョン。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-161">Client version used by the conference user.</span></span> <span data-ttu-id="4c5ff-162">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-162">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c5ff-163"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-163"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-164">int</span><span class="sxs-lookup"><span data-stu-id="4c5ff-164">int</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-165">外部</span><span class="sxs-lookup"><span data-stu-id="4c5ff-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-166">電話会議サーバーが使用するクライアントバージョン。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-166">Client version used by the conference server.</span></span> <span data-ttu-id="4c5ff-167">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-167">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c5ff-168"><strong>Edialogidtime を置換する</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-168"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-169">日付型</span><span class="sxs-lookup"><span data-stu-id="4c5ff-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-170">外部</span><span class="sxs-lookup"><span data-stu-id="4c5ff-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-171">現在のセッションで置き換えられたダイアログを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-171">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="4c5ff-172">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-172">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c5ff-173"><strong>Edialogidseq を置換する</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-173"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-174">int</span><span class="sxs-lookup"><span data-stu-id="4c5ff-174">int</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-175">外部</span><span class="sxs-lookup"><span data-stu-id="4c5ff-175">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-176">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-176">ID number to identify the session.</span></span> <span data-ttu-id="4c5ff-177">このセッションで置き換えられたセッションを一意に識別するために <strong>ReplacesDialogIdTime</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-177">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="4c5ff-178">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-178">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c5ff-179"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-179"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-180">若干</span><span class="sxs-lookup"><span data-stu-id="4c5ff-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c5ff-181">会議サーバーによってセッションが開始されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-181">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c5ff-182"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-182"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-183">若干</span><span class="sxs-lookup"><span data-stu-id="4c5ff-183">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c5ff-184">セッションが会議サーバーによって終了したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-184">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c5ff-185"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-185"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-186">若干</span><span class="sxs-lookup"><span data-stu-id="4c5ff-186">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c5ff-187">ユーザーが内部からログオンしているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-187">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c5ff-188"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-188"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-189">int</span><span class="sxs-lookup"><span data-stu-id="4c5ff-189">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c5ff-190">セッションの招待に対するセッション開始プロトコル (SIP) 応答コード。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-190">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="4c5ff-191">このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-191">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="4c5ff-192">INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-192">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c5ff-193"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-193"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-194">int</span><span class="sxs-lookup"><span data-stu-id="4c5ff-194">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c5ff-195">SIP ヘッダーから取得された診断 ID。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-195">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c5ff-196"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-196"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-197">int</span><span class="sxs-lookup"><span data-stu-id="4c5ff-197">int</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-198">外部</span><span class="sxs-lookup"><span data-stu-id="4c5ff-198">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-199">このセッションで使用されるフロントエンド サーバーの ID。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-199">ID of the front-end server used for this session.</span></span> <span data-ttu-id="4c5ff-200">詳細については、「 <a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-200">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c5ff-201"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-201"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-202">int</span><span class="sxs-lookup"><span data-stu-id="4c5ff-202">int</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-203">外部</span><span class="sxs-lookup"><span data-stu-id="4c5ff-203">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-204">セッションが取得されたプールの ID。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-204">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="4c5ff-205">詳細については、「 <a href="lync-server-2013-pools-table.md">Lync Server 2013 のプール</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-205">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c5ff-206"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-206"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-207">int</span><span class="sxs-lookup"><span data-stu-id="4c5ff-207">int</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-208">外部</span><span class="sxs-lookup"><span data-stu-id="4c5ff-208">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-209">呼び出しが使用している仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-209">The Mediation Server the call is using.</span></span> <span data-ttu-id="4c5ff-210">詳細については、「 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 の Mediationservers</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-210">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c5ff-211"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-211"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-212">int</span><span class="sxs-lookup"><span data-stu-id="4c5ff-212">int</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-213">外部</span><span class="sxs-lookup"><span data-stu-id="4c5ff-213">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-214">通話が使用しているゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-214">The gateway the call is using.</span></span> <span data-ttu-id="4c5ff-215">詳細については、「 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 のゲートウェイ表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-215">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c5ff-216"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-216"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-217">int</span><span class="sxs-lookup"><span data-stu-id="4c5ff-217">int</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-218">外部</span><span class="sxs-lookup"><span data-stu-id="4c5ff-218">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-219">呼び出しが使用しているエッジサーバー。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-219">The Edge Server the call is using.</span></span> <span data-ttu-id="4c5ff-220">詳細については、「 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-220">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c5ff-221"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-221"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-222">int</span><span class="sxs-lookup"><span data-stu-id="4c5ff-222">int</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-223">外部</span><span class="sxs-lookup"><span data-stu-id="4c5ff-223">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-224">セッションで使用されるコンテンツの種類。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-224">Content type used in the session.</span></span> <span data-ttu-id="4c5ff-225">詳細については、「 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 の ContentTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-225">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c5ff-226"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-226"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-227">日付型</span><span class="sxs-lookup"><span data-stu-id="4c5ff-227">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c5ff-228">最初の INVITE 要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-228">The time of the first INVITE request.</span></span> <span data-ttu-id="4c5ff-229">このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-229">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="4c5ff-230">INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-230">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c5ff-231"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-231"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-232">日付型</span><span class="sxs-lookup"><span data-stu-id="4c5ff-232">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c5ff-233">最初の SIP 応答の時間。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-233">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="4c5ff-234">このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-234">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="4c5ff-235">INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-235">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c5ff-236"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-236"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-237">日付型</span><span class="sxs-lookup"><span data-stu-id="4c5ff-237">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c5ff-238">セッションが終了した時刻。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-238">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c5ff-239"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-239"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-240">tinyint</span><span class="sxs-lookup"><span data-stu-id="4c5ff-240">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-241">外部</span><span class="sxs-lookup"><span data-stu-id="4c5ff-241">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c5ff-242"><a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>からの MCU URI の種類の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-242">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="4c5ff-243">このフィールドは、クエリのパフォーマンスを向上させるために使用します。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-243">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="4c5ff-244">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-244">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c5ff-245"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-245"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-246">smallint</span><span class="sxs-lookup"><span data-stu-id="4c5ff-246">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c5ff-247">ユーザー属性を示すビットセット。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-247">A bit set that indicates the user attributes.</span></span> <span data-ttu-id="4c5ff-248">以下の属性が定義されています。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-248">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="4c5ff-249">デスクトップ電話と統合-1</span><span class="sxs-lookup"><span data-stu-id="4c5ff-249">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c5ff-250"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="4c5ff-250"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5ff-251">smallint</span><span class="sxs-lookup"><span data-stu-id="4c5ff-251">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c5ff-p125">通話の属性を示すビット セット。以下の属性が定義されています。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-p125">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="4c5ff-254">セッション-1 の再試行</span><span class="sxs-lookup"><span data-stu-id="4c5ff-254">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4c5ff-255">\* ほとんどのセッションでは、SessionIdSeq の値は1になります。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-255">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="4c5ff-256">まったく同時に複数のセッションが開始した場合、あるセッションの SessionIdSeq は 1、別のセッションは 2、などとなります。</span><span class="sxs-lookup"><span data-stu-id="4c5ff-256">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

