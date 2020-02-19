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
ms.openlocfilehash: f7f0907b6c92d3ca5ed1adf7f1a991242d6ddeb1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="96c00-102">Lync Server 2013 の ConferenceSessionDetails テーブル</span><span class="sxs-lookup"><span data-stu-id="96c00-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96c00-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="96c00-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="96c00-104">各レコードは1つの電話会議セッションを表し、フォーカスがあるセッション、または特定の会議サーバーとのセッションのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="96c00-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="96c00-105">列</span><span class="sxs-lookup"><span data-stu-id="96c00-105">Column</span></span></th>
<th><span data-ttu-id="96c00-106">データ型</span><span class="sxs-lookup"><span data-stu-id="96c00-106">Data Type</span></span></th>
<th><span data-ttu-id="96c00-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="96c00-107">Key/Index</span></span></th>
<th><span data-ttu-id="96c00-108">詳細</span><span class="sxs-lookup"><span data-stu-id="96c00-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96c00-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-110">Datetime</span><span class="sxs-lookup"><span data-stu-id="96c00-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="96c00-111">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="96c00-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="96c00-112">セッション要求の時刻。<strong>Sessionidseq</strong>と組み合わせて、電話会議セッションを一意に識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="96c00-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="96c00-113">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c00-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96c00-114"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-115">int</span><span class="sxs-lookup"><span data-stu-id="96c00-115">int</span></span></p></td>
<td><p><span data-ttu-id="96c00-116">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="96c00-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="96c00-117">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="96c00-117">ID number to identify the session.</span></span> <span data-ttu-id="96c00-118"><strong>Sessionidtime</strong>と組み合わせて、電話会議セッションを一意に識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="96c00-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="96c00-119">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c00-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96c00-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-121">int</span><span class="sxs-lookup"><span data-stu-id="96c00-121">int</span></span></p></td>
<td><p><span data-ttu-id="96c00-122">外部</span><span class="sxs-lookup"><span data-stu-id="96c00-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="96c00-123">このセッションに関連する会議 URI にフォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="96c00-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="96c00-124">詳細については、「 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c00-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="96c00-125">この URI は、フォーカスベースの会議 URI です。</span><span class="sxs-lookup"><span data-stu-id="96c00-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96c00-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-127">識別子</span><span class="sxs-lookup"><span data-stu-id="96c00-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96c00-128">定期的な電話会議のインスタンスを区別する識別子。</span><span class="sxs-lookup"><span data-stu-id="96c00-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="96c00-129">定期的な電話会議の各インスタンスは、ConferenceURI は同じですが、ConfInstance 値が異なります。</span><span class="sxs-lookup"><span data-stu-id="96c00-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="96c00-130">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="96c00-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96c00-131"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-132">int</span><span class="sxs-lookup"><span data-stu-id="96c00-132">int</span></span></p></td>
<td><p><span data-ttu-id="96c00-133">外部</span><span class="sxs-lookup"><span data-stu-id="96c00-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="96c00-134">このセッションに関連する会議サーバーの会議 URI。</span><span class="sxs-lookup"><span data-stu-id="96c00-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="96c00-135">詳細については、「 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c00-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="96c00-136">この URI は、会議サーバーベースの会議 URI です。</span><span class="sxs-lookup"><span data-stu-id="96c00-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="96c00-137">フォーカス会議セッションの場合、この列は null になります。</span><span class="sxs-lookup"><span data-stu-id="96c00-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96c00-138"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-139">int</span><span class="sxs-lookup"><span data-stu-id="96c00-139">int</span></span></p></td>
<td><p><span data-ttu-id="96c00-140">外部</span><span class="sxs-lookup"><span data-stu-id="96c00-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="96c00-141">電話会議セッションの1人のユーザーの ID。</span><span class="sxs-lookup"><span data-stu-id="96c00-141">ID of one user in the conference session.</span></span> <span data-ttu-id="96c00-142">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c00-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96c00-143"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-144">識別子</span><span class="sxs-lookup"><span data-stu-id="96c00-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96c00-145">エンドポイントのインスタンスを識別する GUID。</span><span class="sxs-lookup"><span data-stu-id="96c00-145">A GUID to identify the instance of endpoint.</span></span> <span data-ttu-id="96c00-146">たとえば、あるユーザーが同じアカウントを持つ別のコンピューターにログオンした場合、各マシンには異なるエンドポイント ID が設定されます。</span><span class="sxs-lookup"><span data-stu-id="96c00-146">For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96c00-147"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-148">int</span><span class="sxs-lookup"><span data-stu-id="96c00-148">int</span></span></p></td>
<td><p><span data-ttu-id="96c00-149">外部</span><span class="sxs-lookup"><span data-stu-id="96c00-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="96c00-150">発信者が代理を務めているユーザーの ID を示します。</span><span class="sxs-lookup"><span data-stu-id="96c00-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="96c00-151">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c00-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96c00-152"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-153">int</span><span class="sxs-lookup"><span data-stu-id="96c00-153">int</span></span></p></td>
<td><p><span data-ttu-id="96c00-154">外部</span><span class="sxs-lookup"><span data-stu-id="96c00-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="96c00-155">通話の参照元であるユーザーの ID。</span><span class="sxs-lookup"><span data-stu-id="96c00-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="96c00-156">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c00-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96c00-157"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-158">int</span><span class="sxs-lookup"><span data-stu-id="96c00-158">int</span></span></p></td>
<td><p><span data-ttu-id="96c00-159">外部</span><span class="sxs-lookup"><span data-stu-id="96c00-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="96c00-160">電話会議ユーザーが使用するクライアントバージョン。</span><span class="sxs-lookup"><span data-stu-id="96c00-160">Client version used by the conference user.</span></span> <span data-ttu-id="96c00-161">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c00-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96c00-162"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-163">int</span><span class="sxs-lookup"><span data-stu-id="96c00-163">int</span></span></p></td>
<td><p><span data-ttu-id="96c00-164">外部</span><span class="sxs-lookup"><span data-stu-id="96c00-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="96c00-165">電話会議サーバーが使用するクライアントバージョン。</span><span class="sxs-lookup"><span data-stu-id="96c00-165">Client version used by the conference server.</span></span> <span data-ttu-id="96c00-166">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c00-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96c00-167"><strong>Edialogidtime を置換する</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-168">日付型</span><span class="sxs-lookup"><span data-stu-id="96c00-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="96c00-169">外部</span><span class="sxs-lookup"><span data-stu-id="96c00-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="96c00-170">現在のセッションで置き換えられたダイアログを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="96c00-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="96c00-171">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c00-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96c00-172"><strong>Edialogidseq を置換する</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-173">int</span><span class="sxs-lookup"><span data-stu-id="96c00-173">int</span></span></p></td>
<td><p><span data-ttu-id="96c00-174">外部</span><span class="sxs-lookup"><span data-stu-id="96c00-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="96c00-175">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="96c00-175">ID number to identify the session.</span></span> <span data-ttu-id="96c00-176">このセッションで置き換えられたセッションを一意に識別するために <strong>ReplacesDialogIdTime</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="96c00-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="96c00-177">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c00-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96c00-178"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-179">若干</span><span class="sxs-lookup"><span data-stu-id="96c00-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96c00-180">会議サーバーによってセッションが開始されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="96c00-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96c00-181"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-182">若干</span><span class="sxs-lookup"><span data-stu-id="96c00-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96c00-183">セッションが会議サーバーによって終了したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="96c00-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96c00-184"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-185">若干</span><span class="sxs-lookup"><span data-stu-id="96c00-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96c00-186">ユーザーが内部からログオンしているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="96c00-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96c00-187"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-188">int</span><span class="sxs-lookup"><span data-stu-id="96c00-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96c00-189">セッションの招待に対するセッション開始プロトコル (SIP) 応答コード。</span><span class="sxs-lookup"><span data-stu-id="96c00-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="96c00-190">このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。</span><span class="sxs-lookup"><span data-stu-id="96c00-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="96c00-191">INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="96c00-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96c00-192"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-193">int</span><span class="sxs-lookup"><span data-stu-id="96c00-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96c00-194">SIP ヘッダーから取得された診断 ID。</span><span class="sxs-lookup"><span data-stu-id="96c00-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96c00-195"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-196">int</span><span class="sxs-lookup"><span data-stu-id="96c00-196">int</span></span></p></td>
<td><p><span data-ttu-id="96c00-197">外部</span><span class="sxs-lookup"><span data-stu-id="96c00-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="96c00-198">このセッションで使用されるフロントエンド サーバーの ID。</span><span class="sxs-lookup"><span data-stu-id="96c00-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="96c00-199">詳細については、「 <a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c00-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96c00-200"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-201">int</span><span class="sxs-lookup"><span data-stu-id="96c00-201">int</span></span></p></td>
<td><p><span data-ttu-id="96c00-202">外部</span><span class="sxs-lookup"><span data-stu-id="96c00-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="96c00-203">セッションが取得されたプールの ID。</span><span class="sxs-lookup"><span data-stu-id="96c00-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="96c00-204">詳細については、「 <a href="lync-server-2013-pools-table.md">Lync Server 2013 のプール</a>」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c00-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96c00-205"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-206">int</span><span class="sxs-lookup"><span data-stu-id="96c00-206">int</span></span></p></td>
<td><p><span data-ttu-id="96c00-207">外部</span><span class="sxs-lookup"><span data-stu-id="96c00-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="96c00-208">呼び出しが使用している仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="96c00-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="96c00-209">詳細については、「 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 の Mediationservers</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c00-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96c00-210"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-211">int</span><span class="sxs-lookup"><span data-stu-id="96c00-211">int</span></span></p></td>
<td><p><span data-ttu-id="96c00-212">外部</span><span class="sxs-lookup"><span data-stu-id="96c00-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="96c00-213">通話が使用しているゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="96c00-213">The gateway the call is using.</span></span> <span data-ttu-id="96c00-214">詳細については、「 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 のゲートウェイ表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c00-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96c00-215"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-216">int</span><span class="sxs-lookup"><span data-stu-id="96c00-216">int</span></span></p></td>
<td><p><span data-ttu-id="96c00-217">外部</span><span class="sxs-lookup"><span data-stu-id="96c00-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="96c00-218">呼び出しが使用しているエッジサーバー。</span><span class="sxs-lookup"><span data-stu-id="96c00-218">The Edge Server the call is using.</span></span> <span data-ttu-id="96c00-219">詳細については、「 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c00-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96c00-220"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-221">int</span><span class="sxs-lookup"><span data-stu-id="96c00-221">int</span></span></p></td>
<td><p><span data-ttu-id="96c00-222">外部</span><span class="sxs-lookup"><span data-stu-id="96c00-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="96c00-223">セッションで使用されるコンテンツの種類。</span><span class="sxs-lookup"><span data-stu-id="96c00-223">Content type used in the session.</span></span> <span data-ttu-id="96c00-224">詳細については、「 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 の ContentTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c00-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96c00-225"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-226">日付型</span><span class="sxs-lookup"><span data-stu-id="96c00-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96c00-227">最初の INVITE 要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="96c00-227">The time of the first INVITE request.</span></span> <span data-ttu-id="96c00-228">このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。</span><span class="sxs-lookup"><span data-stu-id="96c00-228">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="96c00-229">INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="96c00-229">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96c00-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-231">日付型</span><span class="sxs-lookup"><span data-stu-id="96c00-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96c00-232">最初の SIP 応答の時間。</span><span class="sxs-lookup"><span data-stu-id="96c00-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="96c00-233">このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。</span><span class="sxs-lookup"><span data-stu-id="96c00-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="96c00-234">INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="96c00-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96c00-235"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-236">日付型</span><span class="sxs-lookup"><span data-stu-id="96c00-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96c00-237">セッションが終了した時刻。</span><span class="sxs-lookup"><span data-stu-id="96c00-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96c00-238"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-239">tinyint</span><span class="sxs-lookup"><span data-stu-id="96c00-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="96c00-240">外部</span><span class="sxs-lookup"><span data-stu-id="96c00-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="96c00-241"><a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>からの MCU URI の種類の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="96c00-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="96c00-242">このフィールドは、クエリのパフォーマンスを向上させるために使用します。</span><span class="sxs-lookup"><span data-stu-id="96c00-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="96c00-243">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="96c00-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96c00-244"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-245">smallint</span><span class="sxs-lookup"><span data-stu-id="96c00-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96c00-246">ユーザー属性を示すビットセット。</span><span class="sxs-lookup"><span data-stu-id="96c00-246">A bit set that indicates the user attributes.</span></span> <span data-ttu-id="96c00-247">以下の属性が定義されています。</span><span class="sxs-lookup"><span data-stu-id="96c00-247">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="96c00-248">デスクトップ電話と統合-1</span><span class="sxs-lookup"><span data-stu-id="96c00-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96c00-249"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="96c00-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="96c00-250">smallint</span><span class="sxs-lookup"><span data-stu-id="96c00-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96c00-p125">通話の属性を示すビット セット。以下の属性が定義されています。</span><span class="sxs-lookup"><span data-stu-id="96c00-p125">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="96c00-253">セッション-1 の再試行</span><span class="sxs-lookup"><span data-stu-id="96c00-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="96c00-254">\*ほとんどのセッションでは、SessionIdSeq の値は1になります。</span><span class="sxs-lookup"><span data-stu-id="96c00-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="96c00-255">まったく同時に複数のセッションが開始した場合、あるセッションの SessionIdSeq は 1、別のセッションは 2、などとなります。</span><span class="sxs-lookup"><span data-stu-id="96c00-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

