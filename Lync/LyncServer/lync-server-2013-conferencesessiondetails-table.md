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
ms.openlocfilehash: 61da586f3ecaf215b3bb636a80141ba8aaa19f18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="bb324-102">Lync Server 2013 の ConferenceSessionDetails テーブル</span><span class="sxs-lookup"><span data-stu-id="bb324-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb324-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="bb324-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="bb324-104">各レコードは1つの会議セッションを表します。これは、フォーカスのあるセッションまたは特定の会議サーバーのセッションのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="bb324-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb324-105">列</span><span class="sxs-lookup"><span data-stu-id="bb324-105">Column</span></span></th>
<th><span data-ttu-id="bb324-106">データ型</span><span class="sxs-lookup"><span data-stu-id="bb324-106">Data Type</span></span></th>
<th><span data-ttu-id="bb324-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="bb324-107">Key/Index</span></span></th>
<th><span data-ttu-id="bb324-108">詳細</span><span class="sxs-lookup"><span data-stu-id="bb324-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb324-109"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-110">Datetime</span><span class="sxs-lookup"><span data-stu-id="bb324-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="bb324-111">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="bb324-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="bb324-112">セッション要求の時刻。電話会議セッションを一意に識別するために<strong>Sessionidseq</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb324-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="bb324-113">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb324-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb324-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-115">int</span><span class="sxs-lookup"><span data-stu-id="bb324-115">int</span></span></p></td>
<td><p><span data-ttu-id="bb324-116">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="bb324-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="bb324-117">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="bb324-117">ID number to identify the session.</span></span> <span data-ttu-id="bb324-118">電話会議セッションを一意に識別するために<strong>Sessionidtime</strong>と組み合わせて使われます。</span><span class="sxs-lookup"><span data-stu-id="bb324-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="bb324-119">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb324-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb324-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-121">int</span><span class="sxs-lookup"><span data-stu-id="bb324-121">int</span></span></p></td>
<td><p><span data-ttu-id="bb324-122">外部</span><span class="sxs-lookup"><span data-stu-id="bb324-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bb324-123">このセッションに関連する会議の URI にフォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="bb324-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="bb324-124">詳細については、「 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb324-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="bb324-125">この URI は、フォーカスベースの会議 URI です。</span><span class="sxs-lookup"><span data-stu-id="bb324-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb324-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-127">長さ</span><span class="sxs-lookup"><span data-stu-id="bb324-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb324-128">定期的な会議のインスタンスを区別する識別子。</span><span class="sxs-lookup"><span data-stu-id="bb324-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="bb324-129">各定期的な会議インスタンスの ConferenceURI は同じですが、異なる ConfInstance 値があります。</span><span class="sxs-lookup"><span data-stu-id="bb324-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="bb324-130">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="bb324-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb324-131"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-132">int</span><span class="sxs-lookup"><span data-stu-id="bb324-132">int</span></span></p></td>
<td><p><span data-ttu-id="bb324-133">外部</span><span class="sxs-lookup"><span data-stu-id="bb324-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bb324-134">このセッションに関連する会議サーバーの会議 URI。</span><span class="sxs-lookup"><span data-stu-id="bb324-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="bb324-135">詳細については、「 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb324-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="bb324-136">この URI は、会議サーバーベースの会議 URI です。</span><span class="sxs-lookup"><span data-stu-id="bb324-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="bb324-137">フォーカス会議セッションの場合、この列は null になります。</span><span class="sxs-lookup"><span data-stu-id="bb324-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb324-138"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-139">int</span><span class="sxs-lookup"><span data-stu-id="bb324-139">int</span></span></p></td>
<td><p><span data-ttu-id="bb324-140">外部</span><span class="sxs-lookup"><span data-stu-id="bb324-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bb324-141">会議セッションの1人のユーザーの ID です。</span><span class="sxs-lookup"><span data-stu-id="bb324-141">ID of one user in the conference session.</span></span> <span data-ttu-id="bb324-142">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb324-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb324-143"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-144">長さ</span><span class="sxs-lookup"><span data-stu-id="bb324-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb324-145">エンドポイントのインスタンスを識別するための GUID。</span><span class="sxs-lookup"><span data-stu-id="bb324-145">A GUID to identify the instance of endpoint.</span></span> <span data-ttu-id="bb324-146">たとえば、あるユーザーが同じアカウントで異なるコンピューターにログオンしている場合、各コンピューターには別のエンドポイント ID があります。</span><span class="sxs-lookup"><span data-stu-id="bb324-146">For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb324-147"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-148">int</span><span class="sxs-lookup"><span data-stu-id="bb324-148">int</span></span></p></td>
<td><p><span data-ttu-id="bb324-149">外部</span><span class="sxs-lookup"><span data-stu-id="bb324-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bb324-150">発信者が代理としているユーザーの ID を示します。</span><span class="sxs-lookup"><span data-stu-id="bb324-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="bb324-151">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb324-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb324-152"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-153">int</span><span class="sxs-lookup"><span data-stu-id="bb324-153">int</span></span></p></td>
<td><p><span data-ttu-id="bb324-154">外部</span><span class="sxs-lookup"><span data-stu-id="bb324-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bb324-155">通話を参照するユーザーの ID です。</span><span class="sxs-lookup"><span data-stu-id="bb324-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="bb324-156">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb324-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb324-157"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-158">int</span><span class="sxs-lookup"><span data-stu-id="bb324-158">int</span></span></p></td>
<td><p><span data-ttu-id="bb324-159">外部</span><span class="sxs-lookup"><span data-stu-id="bb324-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bb324-160">電話会議ユーザーが使用したクライアントバージョン。</span><span class="sxs-lookup"><span data-stu-id="bb324-160">Client version used by the conference user.</span></span> <span data-ttu-id="bb324-161">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb324-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb324-162"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-163">int</span><span class="sxs-lookup"><span data-stu-id="bb324-163">int</span></span></p></td>
<td><p><span data-ttu-id="bb324-164">外部</span><span class="sxs-lookup"><span data-stu-id="bb324-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bb324-165">会議サーバーで使用されるクライアントのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="bb324-165">Client version used by the conference server.</span></span> <span data-ttu-id="bb324-166">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb324-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb324-167"><strong>Edialogidtime の置き換え</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-168">datetime</span><span class="sxs-lookup"><span data-stu-id="bb324-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="bb324-169">外部</span><span class="sxs-lookup"><span data-stu-id="bb324-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bb324-170">現在のセッションによって置き換えられたダイアログを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="bb324-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="bb324-171">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb324-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb324-172"><strong>Edialogidseq の置き換え</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-173">int</span><span class="sxs-lookup"><span data-stu-id="bb324-173">int</span></span></p></td>
<td><p><span data-ttu-id="bb324-174">外部</span><span class="sxs-lookup"><span data-stu-id="bb324-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bb324-175">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="bb324-175">ID number to identify the session.</span></span> <span data-ttu-id="bb324-176">このセッションによって置き換えられるセッションを一意に識別するために、<strong>代替の操作と組み合わせ</strong>て使います。</span><span class="sxs-lookup"><span data-stu-id="bb324-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="bb324-177">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb324-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb324-178"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-179">bit</span><span class="sxs-lookup"><span data-stu-id="bb324-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb324-180">セッションが会議サーバーによって開始されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="bb324-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb324-181"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-182">bit</span><span class="sxs-lookup"><span data-stu-id="bb324-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb324-183">会議サーバーによってセッションが終了したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="bb324-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb324-184"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-185">bit</span><span class="sxs-lookup"><span data-stu-id="bb324-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb324-186">ユーザーが内部からログオンしているかどうか。</span><span class="sxs-lookup"><span data-stu-id="bb324-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb324-187"><strong>返信</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-188">int</span><span class="sxs-lookup"><span data-stu-id="bb324-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb324-189">セッションの招待状へのセッション開始プロトコル (SIP) 応答コード。</span><span class="sxs-lookup"><span data-stu-id="bb324-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="bb324-190">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="bb324-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="bb324-191">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="bb324-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb324-192"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-193">int</span><span class="sxs-lookup"><span data-stu-id="bb324-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb324-194">SIP ヘッダーからキャプチャされた診断 ID。</span><span class="sxs-lookup"><span data-stu-id="bb324-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb324-195"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-196">int</span><span class="sxs-lookup"><span data-stu-id="bb324-196">int</span></span></p></td>
<td><p><span data-ttu-id="bb324-197">外部</span><span class="sxs-lookup"><span data-stu-id="bb324-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bb324-198">このセッションで使用するフロントエンドサーバーの ID です。</span><span class="sxs-lookup"><span data-stu-id="bb324-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="bb324-199">詳細については、「 <a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb324-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb324-200"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-201">int</span><span class="sxs-lookup"><span data-stu-id="bb324-201">int</span></span></p></td>
<td><p><span data-ttu-id="bb324-202">外部</span><span class="sxs-lookup"><span data-stu-id="bb324-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bb324-203">セッションがキャプチャされたプールの ID です。</span><span class="sxs-lookup"><span data-stu-id="bb324-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="bb324-204">詳細については、「 <a href="lync-server-2013-pools-table.md">Lync Server 2013 のプールテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb324-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb324-205"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-206">int</span><span class="sxs-lookup"><span data-stu-id="bb324-206">int</span></span></p></td>
<td><p><span data-ttu-id="bb324-207">外部</span><span class="sxs-lookup"><span data-stu-id="bb324-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bb324-208">通話が使用している仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="bb324-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="bb324-209">詳細については、「 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 の Mediationservers の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb324-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb324-210"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-211">int</span><span class="sxs-lookup"><span data-stu-id="bb324-211">int</span></span></p></td>
<td><p><span data-ttu-id="bb324-212">外部</span><span class="sxs-lookup"><span data-stu-id="bb324-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bb324-213">通話が使用しているゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="bb324-213">The gateway the call is using.</span></span> <span data-ttu-id="bb324-214">詳細については、「 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 のゲートウェイテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb324-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb324-215"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-216">int</span><span class="sxs-lookup"><span data-stu-id="bb324-216">int</span></span></p></td>
<td><p><span data-ttu-id="bb324-217">外部</span><span class="sxs-lookup"><span data-stu-id="bb324-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bb324-218">通話が使用しているエッジサーバー。</span><span class="sxs-lookup"><span data-stu-id="bb324-218">The Edge Server the call is using.</span></span> <span data-ttu-id="bb324-219">詳細については、「 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb324-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb324-220"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-221">int</span><span class="sxs-lookup"><span data-stu-id="bb324-221">int</span></span></p></td>
<td><p><span data-ttu-id="bb324-222">外部</span><span class="sxs-lookup"><span data-stu-id="bb324-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bb324-223">セッションで使用されるコンテンツタイプ。</span><span class="sxs-lookup"><span data-stu-id="bb324-223">Content type used in the session.</span></span> <span data-ttu-id="bb324-224">詳細については、「 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 の ContentTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb324-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb324-225"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-226">datetime</span><span class="sxs-lookup"><span data-stu-id="bb324-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb324-227">最初の招待要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="bb324-227">The time of the first INVITE request.</span></span> <span data-ttu-id="bb324-228">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="bb324-228">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="bb324-229">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="bb324-229">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb324-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-231">datetime</span><span class="sxs-lookup"><span data-stu-id="bb324-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb324-232">最初の SIP 応答の時刻。</span><span class="sxs-lookup"><span data-stu-id="bb324-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="bb324-233">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="bb324-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="bb324-234">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="bb324-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb324-235"><strong>セッション終了時刻</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-236">datetime</span><span class="sxs-lookup"><span data-stu-id="bb324-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb324-237">セッションが終了した時刻。</span><span class="sxs-lookup"><span data-stu-id="bb324-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb324-238"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-239">tinyint</span><span class="sxs-lookup"><span data-stu-id="bb324-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bb324-240">外部</span><span class="sxs-lookup"><span data-stu-id="bb324-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bb324-241"><a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>の MCU URI の種類の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bb324-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="bb324-242">このフィールドは、クエリのパフォーマンスを向上させるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb324-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="bb324-243">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="bb324-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb324-244"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-245">smallint</span><span class="sxs-lookup"><span data-stu-id="bb324-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb324-246">ユーザー属性を示すビットセット。</span><span class="sxs-lookup"><span data-stu-id="bb324-246">A bit set that indicates the user attributes.</span></span> <span data-ttu-id="bb324-247">次の属性定義が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb324-247">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="bb324-248">デスクトップ電話と統合-1</span><span class="sxs-lookup"><span data-stu-id="bb324-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb324-249"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="bb324-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="bb324-250">smallint</span><span class="sxs-lookup"><span data-stu-id="bb324-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb324-251">呼び出し属性を示すビットセット。</span><span class="sxs-lookup"><span data-stu-id="bb324-251">A bit set that indicates the call attributes.</span></span> <span data-ttu-id="bb324-252">次の属性定義が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb324-252">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="bb324-253">セッションを再試行しました-1</span><span class="sxs-lookup"><span data-stu-id="bb324-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bb324-254">\*ほとんどのセッションでは、SessionIdSeq の値は1になります。</span><span class="sxs-lookup"><span data-stu-id="bb324-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="bb324-255">複数のセッションが同時に開始された場合は、1つのセッションの SessionIdSeq は1、それ以外の場合は2となります。</span><span class="sxs-lookup"><span data-stu-id="bb324-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

