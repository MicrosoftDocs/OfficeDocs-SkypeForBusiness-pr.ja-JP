---
title: 'Lync Server 2013: ConferenceSessionDetails テーブル'
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
ms.openlocfilehash: 57d8e3cb0a79c8ce6a6c1c51891fbad265f045de
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529204"
---
# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="69e0d-102">Lync Server 2013 の ConferenceSessionDetails テーブル</span><span class="sxs-lookup"><span data-stu-id="69e0d-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69e0d-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="69e0d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="69e0d-104">各レコードは1つの電話会議セッションを表し、フォーカスがあるセッション、または特定の会議サーバーとのセッションのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="69e0d-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69e0d-105">Column</span><span class="sxs-lookup"><span data-stu-id="69e0d-105">Column</span></span></th>
<th><span data-ttu-id="69e0d-106">データ型</span><span class="sxs-lookup"><span data-stu-id="69e0d-106">Data Type</span></span></th>
<th><span data-ttu-id="69e0d-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="69e0d-107">Key/Index</span></span></th>
<th><span data-ttu-id="69e0d-108">詳細</span><span class="sxs-lookup"><span data-stu-id="69e0d-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69e0d-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-110">Datetime</span><span class="sxs-lookup"><span data-stu-id="69e0d-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="69e0d-111">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="69e0d-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="69e0d-112">セッション要求の時刻。 <strong>Sessionidseq</strong> と組み合わせて、電話会議セッションを一意に識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="69e0d-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="69e0d-113">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69e0d-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69e0d-114"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-115">int</span><span class="sxs-lookup"><span data-stu-id="69e0d-115">int</span></span></p></td>
<td><p><span data-ttu-id="69e0d-116">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="69e0d-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="69e0d-117">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="69e0d-117">ID number to identify the session.</span></span> <span data-ttu-id="69e0d-118"><strong>Sessionidtime</strong>と組み合わせて、電話会議セッションを一意に識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="69e0d-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="69e0d-119">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69e0d-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69e0d-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-121">int</span><span class="sxs-lookup"><span data-stu-id="69e0d-121">int</span></span></p></td>
<td><p><span data-ttu-id="69e0d-122">外部</span><span class="sxs-lookup"><span data-stu-id="69e0d-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69e0d-123">このセッションに関連する会議 URI にフォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="69e0d-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="69e0d-124">詳細については、「 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69e0d-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="69e0d-125">この URI は、フォーカスベースの会議 URI です。</span><span class="sxs-lookup"><span data-stu-id="69e0d-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69e0d-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-127">識別子</span><span class="sxs-lookup"><span data-stu-id="69e0d-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69e0d-128">定期的な電話会議のインスタンスを区別する識別子。</span><span class="sxs-lookup"><span data-stu-id="69e0d-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="69e0d-129">定期的な電話会議の各インスタンスは、ConferenceURI は同じですが、ConfInstance 値が異なります。</span><span class="sxs-lookup"><span data-stu-id="69e0d-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="69e0d-130">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="69e0d-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69e0d-131"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-132">int</span><span class="sxs-lookup"><span data-stu-id="69e0d-132">int</span></span></p></td>
<td><p><span data-ttu-id="69e0d-133">外部</span><span class="sxs-lookup"><span data-stu-id="69e0d-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69e0d-134">このセッションに関連する会議サーバーの会議 URI。</span><span class="sxs-lookup"><span data-stu-id="69e0d-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="69e0d-135">詳細については、「 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69e0d-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="69e0d-136">この URI は、会議サーバーベースの会議 URI です。</span><span class="sxs-lookup"><span data-stu-id="69e0d-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="69e0d-137">フォーカス会議セッションの場合、この列は null になります。</span><span class="sxs-lookup"><span data-stu-id="69e0d-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69e0d-138"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-139">int</span><span class="sxs-lookup"><span data-stu-id="69e0d-139">int</span></span></p></td>
<td><p><span data-ttu-id="69e0d-140">外部</span><span class="sxs-lookup"><span data-stu-id="69e0d-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69e0d-141">電話会議セッションの1人のユーザーの ID。</span><span class="sxs-lookup"><span data-stu-id="69e0d-141">ID of one user in the conference session.</span></span> <span data-ttu-id="69e0d-142">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69e0d-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69e0d-143"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-144">識別子</span><span class="sxs-lookup"><span data-stu-id="69e0d-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69e0d-145">エンドポイントのインスタンスを識別する GUID。</span><span class="sxs-lookup"><span data-stu-id="69e0d-145">A GUID to identify the instance of endpoint.</span></span> <span data-ttu-id="69e0d-146">たとえば、あるユーザーが同じアカウントを持つ別のコンピューターにログオンした場合、各マシンには異なるエンドポイント ID が設定されます。</span><span class="sxs-lookup"><span data-stu-id="69e0d-146">For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69e0d-147"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-148">int</span><span class="sxs-lookup"><span data-stu-id="69e0d-148">int</span></span></p></td>
<td><p><span data-ttu-id="69e0d-149">外部</span><span class="sxs-lookup"><span data-stu-id="69e0d-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69e0d-150">発信者が代理を務めているユーザーの ID を示します。</span><span class="sxs-lookup"><span data-stu-id="69e0d-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="69e0d-151">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69e0d-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69e0d-152"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-153">int</span><span class="sxs-lookup"><span data-stu-id="69e0d-153">int</span></span></p></td>
<td><p><span data-ttu-id="69e0d-154">外部</span><span class="sxs-lookup"><span data-stu-id="69e0d-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69e0d-155">通話の参照元であるユーザーの ID。</span><span class="sxs-lookup"><span data-stu-id="69e0d-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="69e0d-156">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69e0d-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69e0d-157"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-158">int</span><span class="sxs-lookup"><span data-stu-id="69e0d-158">int</span></span></p></td>
<td><p><span data-ttu-id="69e0d-159">外部</span><span class="sxs-lookup"><span data-stu-id="69e0d-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69e0d-160">電話会議ユーザーが使用するクライアントバージョン。</span><span class="sxs-lookup"><span data-stu-id="69e0d-160">Client version used by the conference user.</span></span> <span data-ttu-id="69e0d-161">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69e0d-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69e0d-162"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-163">int</span><span class="sxs-lookup"><span data-stu-id="69e0d-163">int</span></span></p></td>
<td><p><span data-ttu-id="69e0d-164">外部</span><span class="sxs-lookup"><span data-stu-id="69e0d-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69e0d-165">電話会議サーバーが使用するクライアントバージョン。</span><span class="sxs-lookup"><span data-stu-id="69e0d-165">Client version used by the conference server.</span></span> <span data-ttu-id="69e0d-166">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69e0d-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69e0d-167"><strong>Edialogidtime を置換する</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-168">日付型</span><span class="sxs-lookup"><span data-stu-id="69e0d-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="69e0d-169">外部</span><span class="sxs-lookup"><span data-stu-id="69e0d-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69e0d-170">現在のセッションで置き換えられたダイアログを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="69e0d-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="69e0d-171">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69e0d-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69e0d-172"><strong>Edialogidseq を置換する</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-173">int</span><span class="sxs-lookup"><span data-stu-id="69e0d-173">int</span></span></p></td>
<td><p><span data-ttu-id="69e0d-174">外部</span><span class="sxs-lookup"><span data-stu-id="69e0d-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69e0d-175">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="69e0d-175">ID number to identify the session.</span></span> <span data-ttu-id="69e0d-176">このセッションで置き換えられたセッションを一意に識別するために <strong>ReplacesDialogIdTime</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="69e0d-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="69e0d-177">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69e0d-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69e0d-178"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-179">若干</span><span class="sxs-lookup"><span data-stu-id="69e0d-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69e0d-180">会議サーバーによってセッションが開始されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="69e0d-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69e0d-181"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-182">若干</span><span class="sxs-lookup"><span data-stu-id="69e0d-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69e0d-183">セッションが会議サーバーによって終了したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="69e0d-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69e0d-184"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-185">若干</span><span class="sxs-lookup"><span data-stu-id="69e0d-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69e0d-186">ユーザーが内部からログオンしているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="69e0d-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69e0d-187"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-188">int</span><span class="sxs-lookup"><span data-stu-id="69e0d-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69e0d-189">セッションの招待に対するセッション開始プロトコル (SIP) 応答コード。</span><span class="sxs-lookup"><span data-stu-id="69e0d-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="69e0d-190">このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。</span><span class="sxs-lookup"><span data-stu-id="69e0d-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="69e0d-191">INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="69e0d-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69e0d-192"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-193">int</span><span class="sxs-lookup"><span data-stu-id="69e0d-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69e0d-194">SIP ヘッダーから取得された診断 ID。</span><span class="sxs-lookup"><span data-stu-id="69e0d-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69e0d-195"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-196">int</span><span class="sxs-lookup"><span data-stu-id="69e0d-196">int</span></span></p></td>
<td><p><span data-ttu-id="69e0d-197">外部</span><span class="sxs-lookup"><span data-stu-id="69e0d-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69e0d-198">このセッションで使用されるフロントエンド サーバーの ID。</span><span class="sxs-lookup"><span data-stu-id="69e0d-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="69e0d-199">詳細については、「 <a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69e0d-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69e0d-200"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-201">int</span><span class="sxs-lookup"><span data-stu-id="69e0d-201">int</span></span></p></td>
<td><p><span data-ttu-id="69e0d-202">外部</span><span class="sxs-lookup"><span data-stu-id="69e0d-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69e0d-203">セッションが取得されたプールの ID。</span><span class="sxs-lookup"><span data-stu-id="69e0d-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="69e0d-204">詳細については、「 <a href="lync-server-2013-pools-table.md">Lync Server 2013 のプール</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69e0d-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69e0d-205"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-206">int</span><span class="sxs-lookup"><span data-stu-id="69e0d-206">int</span></span></p></td>
<td><p><span data-ttu-id="69e0d-207">外部</span><span class="sxs-lookup"><span data-stu-id="69e0d-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69e0d-208">呼び出しが使用している仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="69e0d-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="69e0d-209">詳細については、「 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 の Mediationservers</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69e0d-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69e0d-210"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-211">int</span><span class="sxs-lookup"><span data-stu-id="69e0d-211">int</span></span></p></td>
<td><p><span data-ttu-id="69e0d-212">外部</span><span class="sxs-lookup"><span data-stu-id="69e0d-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69e0d-213">通話が使用しているゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="69e0d-213">The gateway the call is using.</span></span> <span data-ttu-id="69e0d-214">詳細については、「 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 のゲートウェイ表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69e0d-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69e0d-215"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-216">int</span><span class="sxs-lookup"><span data-stu-id="69e0d-216">int</span></span></p></td>
<td><p><span data-ttu-id="69e0d-217">外部</span><span class="sxs-lookup"><span data-stu-id="69e0d-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69e0d-218">呼び出しが使用しているエッジサーバー。</span><span class="sxs-lookup"><span data-stu-id="69e0d-218">The Edge Server the call is using.</span></span> <span data-ttu-id="69e0d-219">詳細については、「 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69e0d-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69e0d-220"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-221">int</span><span class="sxs-lookup"><span data-stu-id="69e0d-221">int</span></span></p></td>
<td><p><span data-ttu-id="69e0d-222">外部</span><span class="sxs-lookup"><span data-stu-id="69e0d-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69e0d-223">セッションで使用されるコンテンツの種類。</span><span class="sxs-lookup"><span data-stu-id="69e0d-223">Content type used in the session.</span></span> <span data-ttu-id="69e0d-224">詳細については、「 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 の ContentTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69e0d-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69e0d-225"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-226">日付型</span><span class="sxs-lookup"><span data-stu-id="69e0d-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69e0d-227">最初の INVITE 要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="69e0d-227">The time of the first INVITE request.</span></span> <span data-ttu-id="69e0d-228">このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。</span><span class="sxs-lookup"><span data-stu-id="69e0d-228">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="69e0d-229">INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="69e0d-229">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69e0d-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-231">日付型</span><span class="sxs-lookup"><span data-stu-id="69e0d-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69e0d-232">最初の SIP 応答の時間。</span><span class="sxs-lookup"><span data-stu-id="69e0d-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="69e0d-233">このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。</span><span class="sxs-lookup"><span data-stu-id="69e0d-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="69e0d-234">INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="69e0d-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69e0d-235"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-236">日付型</span><span class="sxs-lookup"><span data-stu-id="69e0d-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69e0d-237">セッションが終了した時刻。</span><span class="sxs-lookup"><span data-stu-id="69e0d-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69e0d-238"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-239">tinyint</span><span class="sxs-lookup"><span data-stu-id="69e0d-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="69e0d-240">外部</span><span class="sxs-lookup"><span data-stu-id="69e0d-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69e0d-241"><a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>からの MCU URI の種類の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="69e0d-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="69e0d-242">このフィールドは、クエリのパフォーマンスを向上させるために使用します。</span><span class="sxs-lookup"><span data-stu-id="69e0d-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="69e0d-243">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="69e0d-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69e0d-244"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-245">smallint</span><span class="sxs-lookup"><span data-stu-id="69e0d-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69e0d-246">ユーザー属性を示すビットセット。</span><span class="sxs-lookup"><span data-stu-id="69e0d-246">A bit set that indicates the user attributes.</span></span> <span data-ttu-id="69e0d-247">以下の属性が定義されています。</span><span class="sxs-lookup"><span data-stu-id="69e0d-247">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="69e0d-248">デスクトップ電話と統合-1</span><span class="sxs-lookup"><span data-stu-id="69e0d-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69e0d-249"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="69e0d-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="69e0d-250">smallint</span><span class="sxs-lookup"><span data-stu-id="69e0d-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69e0d-p125">通話の属性を示すビット セット。以下の属性が定義されています。</span><span class="sxs-lookup"><span data-stu-id="69e0d-p125">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="69e0d-253">セッション-1 の再試行</span><span class="sxs-lookup"><span data-stu-id="69e0d-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="69e0d-254">\* ほとんどのセッションでは、SessionIdSeq の値は1になります。</span><span class="sxs-lookup"><span data-stu-id="69e0d-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="69e0d-255">まったく同時に複数のセッションが開始した場合、あるセッションの SessionIdSeq は 1、別のセッションは 2、などとなります。</span><span class="sxs-lookup"><span data-stu-id="69e0d-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

