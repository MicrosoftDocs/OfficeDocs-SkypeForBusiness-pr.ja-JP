---
title: 'Lync Server 2013: セッションの詳細ビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fabf7ae963240f6a2b14ac8c3db272e0cb06091c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="ee243-102">Lync Server 2013 のセッション詳細表示</span><span class="sxs-lookup"><span data-stu-id="ee243-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee243-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ee243-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ee243-104">セッション詳細ビューには、VoIP 電話、2パーティの IM セッション、その他の種類のセッションなど、ピアツーピアセッションに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="ee243-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="ee243-105">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ee243-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ee243-106">列</span><span class="sxs-lookup"><span data-stu-id="ee243-106">Column</span></span></th>
<th><span data-ttu-id="ee243-107">データ型</span><span class="sxs-lookup"><span data-stu-id="ee243-107">Data Type</span></span></th>
<th><span data-ttu-id="ee243-108">詳細</span><span class="sxs-lookup"><span data-stu-id="ee243-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee243-109"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-110">datetime</span><span class="sxs-lookup"><span data-stu-id="ee243-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="ee243-111">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="ee243-111">Time of session request.</span></span> <span data-ttu-id="ee243-112">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="ee243-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="ee243-113">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 テーブルのダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee243-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee243-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-115">int</span><span class="sxs-lookup"><span data-stu-id="ee243-115">int</span></span></p></td>
<td><p><span data-ttu-id="ee243-116">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="ee243-116">ID number to identify the session.</span></span> <span data-ttu-id="ee243-117">セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="ee243-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="ee243-118">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee243-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee243-119"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-120">datetime</span><span class="sxs-lookup"><span data-stu-id="ee243-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="ee243-121">最初の招待要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="ee243-121">Time of the first INVITE request.</span></span> <span data-ttu-id="ee243-122">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="ee243-122">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="ee243-123">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="ee243-123">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="ee243-124">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="ee243-124">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="ee243-125">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="ee243-125">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee243-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ee243-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ee243-128">セッションを開始したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="ee243-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee243-129"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ee243-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ee243-131">セッションに参加したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="ee243-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee243-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-133">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ee243-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee243-134">セッションを開始したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="ee243-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="ee243-135">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee243-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee243-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ee243-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee243-138">セッションに参加したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="ee243-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="ee243-139">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee243-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee243-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ee243-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ee243-142">セッションを開始したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="ee243-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="ee243-143">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee243-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee243-144"><strong>すべての Ant</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-145">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ee243-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee243-146">セッションに参加したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="ee243-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="ee243-147">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee243-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee243-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-149">長さ</span><span class="sxs-lookup"><span data-stu-id="ee243-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="ee243-150">セッションを開始したユーザーのエンドポイントを表す一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="ee243-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee243-151"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-152">長さ</span><span class="sxs-lookup"><span data-stu-id="ee243-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="ee243-153">セッションに参加したユーザーのエンドポイントを表す一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="ee243-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee243-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-155">datetime</span><span class="sxs-lookup"><span data-stu-id="ee243-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="ee243-156">セッションの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="ee243-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee243-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-158">int</span><span class="sxs-lookup"><span data-stu-id="ee243-158">int</span></span></p></td>
<td><p><span data-ttu-id="ee243-159">セッションを開始したユーザーによって送信されたメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="ee243-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee243-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-161">int</span><span class="sxs-lookup"><span data-stu-id="ee243-161">int</span></span></p></td>
<td><p><span data-ttu-id="ee243-162">セッションに参加したユーザーによって送信されたメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="ee243-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee243-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-164">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ee243-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee243-165">セッションを開始したユーザーによって使用されたクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="ee243-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee243-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-167">int</span><span class="sxs-lookup"><span data-stu-id="ee243-167">int</span></span></p></td>
<td><p><span data-ttu-id="ee243-168">セッションを開始したユーザーによって使用されたクライアント。</span><span class="sxs-lookup"><span data-stu-id="ee243-168">Client used by the user who started the session.</span></span> <span data-ttu-id="ee243-169">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee243-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee243-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="ee243-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ee243-172">セッションを開始したユーザーによって使用されたクライアントのカテゴリの名前です。</span><span class="sxs-lookup"><span data-stu-id="ee243-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee243-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-174">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ee243-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee243-175">セッションに参加したユーザーによって使用されたクライアントのバージョン</span><span class="sxs-lookup"><span data-stu-id="ee243-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee243-176"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-177">int</span><span class="sxs-lookup"><span data-stu-id="ee243-177">int</span></span></p></td>
<td><p><span data-ttu-id="ee243-178">セッションに参加したユーザーによって使用されたクライアント。</span><span class="sxs-lookup"><span data-stu-id="ee243-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="ee243-179">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee243-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee243-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="ee243-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ee243-182">セッションに参加したユーザーによって使用されたクライアントのカテゴリの名前です。</span><span class="sxs-lookup"><span data-stu-id="ee243-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee243-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ee243-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ee243-185">セッションのターゲットユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="ee243-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee243-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ee243-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ee243-188">セッションのターゲットユーザーの URI の種類です。</span><span class="sxs-lookup"><span data-stu-id="ee243-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="ee243-189">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee243-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee243-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ee243-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ee243-192">セッションが開始されたユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="ee243-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee243-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ee243-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee243-195">セッションが開始されたユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="ee243-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="ee243-196">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee243-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee243-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-198">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ee243-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee243-199">セッションを開始したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="ee243-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="ee243-200">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee243-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee243-201"><strong>△この Uri</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ee243-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ee243-203">セッションを参照したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="ee243-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee243-204"><strong>ベンチャー Redbyuritん</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-205">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ee243-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee243-206">セッションを参照したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="ee243-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="ee243-207">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee243-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee243-208"><strong>このテナント</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-209">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ee243-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee243-210">セッションを参照したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="ee243-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="ee243-211">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee243-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee243-212"><strong>この Id</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-213">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="ee243-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="ee243-214">SIP ダイアログ ID。</span><span class="sxs-lookup"><span data-stu-id="ee243-214">SIP dialog ID.</span></span> <span data-ttu-id="ee243-215">形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ee243-215">The format is:</span></span></p>
<p><span data-ttu-id="ee243-216">ダイアログ; 開始タグからタグへ</span><span class="sxs-lookup"><span data-stu-id="ee243-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee243-217"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-218">長さ</span><span class="sxs-lookup"><span data-stu-id="ee243-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="ee243-219">複数のセッションの関連付けに使用する GUID。</span><span class="sxs-lookup"><span data-stu-id="ee243-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee243-220"><strong>Edialogidtime の置き換え</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-221">datetime</span><span class="sxs-lookup"><span data-stu-id="ee243-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="ee243-222">セッションによって置き換えられたダイアログの時間です。</span><span class="sxs-lookup"><span data-stu-id="ee243-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="ee243-223">セッションによって置き換えられるダイアログを一意に識別するには、置換 Edialogidseq と組み合わせて使います。</span><span class="sxs-lookup"><span data-stu-id="ee243-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="ee243-224">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee243-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee243-225"><strong>Edialogidseq の置き換え</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-226">int</span><span class="sxs-lookup"><span data-stu-id="ee243-226">int</span></span></p></td>
<td><p><span data-ttu-id="ee243-227">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="ee243-227">ID number to identify the session.</span></span> <span data-ttu-id="ee243-228">セッションによって置き換えられるダイアログを一意に識別するために、交換 Edialogidtime と組み合わせて使います。</span><span class="sxs-lookup"><span data-stu-id="ee243-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="ee243-229">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee243-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee243-230"><strong>置換の方法 Id</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-231">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="ee243-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="ee243-232">SIP ダイアログ ID によってセッションが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="ee243-232">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="ee243-233">形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ee243-233">The format is:</span></span></p>
<p><span data-ttu-id="ee243-234">ダイアログ; 開始タグからタグへ</span><span class="sxs-lookup"><span data-stu-id="ee243-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee243-235"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-236">datetime</span><span class="sxs-lookup"><span data-stu-id="ee243-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="ee243-237">最初の招待メッセージに対する返信の時刻。</span><span class="sxs-lookup"><span data-stu-id="ee243-237">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="ee243-238">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="ee243-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="ee243-239">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="ee243-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee243-240"><strong>返信</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-241">int</span><span class="sxs-lookup"><span data-stu-id="ee243-241">int</span></span></p></td>
<td><p><span data-ttu-id="ee243-242">セッション招待状への SIP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="ee243-242">SIP response code to the session invitation.</span></span> <span data-ttu-id="ee243-243">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="ee243-243">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="ee243-244">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="ee243-244">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee243-245"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-246">int</span><span class="sxs-lookup"><span data-stu-id="ee243-246">int</span></span></p></td>
<td><p><span data-ttu-id="ee243-247">SIP ヘッダーからキャプチャされた診断 ID。</span><span class="sxs-lookup"><span data-stu-id="ee243-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee243-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-249">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ee243-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee243-250">セッションのコンテンツの種類です。</span><span class="sxs-lookup"><span data-stu-id="ee243-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee243-251"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-252">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ee243-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee243-253">セッションのデータをキャプチャしたフロントエンドサーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="ee243-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee243-254"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-255">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ee243-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee243-256">セッションのデータをキャプチャしたプールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="ee243-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee243-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-258">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ee243-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee243-259">セッションを開始したユーザーによって使用されたエッジサーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="ee243-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee243-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-261">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ee243-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee243-262">セッションを開始したユーザーによって使用されたエッジサーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="ee243-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee243-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-264">bit</span><span class="sxs-lookup"><span data-stu-id="ee243-264">bit</span></span></p></td>
<td><p><span data-ttu-id="ee243-265">セッションを開始したユーザーが内部ネットワークからログオンしているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ee243-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee243-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-267">bit</span><span class="sxs-lookup"><span data-stu-id="ee243-267">bit</span></span></p></td>
<td><p><span data-ttu-id="ee243-268">セッションに参加したユーザーが内部ネットワークからログオンしているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ee243-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee243-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-270">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ee243-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee243-271">セッションの通話優先度。</span><span class="sxs-lookup"><span data-stu-id="ee243-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee243-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-273">smallint</span><span class="sxs-lookup"><span data-stu-id="ee243-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="ee243-274">セッションを開始したユーザーの属性を示します。</span><span class="sxs-lookup"><span data-stu-id="ee243-274">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="ee243-275">次の属性定義を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ee243-275">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="ee243-276">0x01-デスクトップ電話と統合</span><span class="sxs-lookup"><span data-stu-id="ee243-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee243-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-278">smallint</span><span class="sxs-lookup"><span data-stu-id="ee243-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="ee243-279">セッションを開始したユーザーの属性を示します。</span><span class="sxs-lookup"><span data-stu-id="ee243-279">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="ee243-280">次の属性定義を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ee243-280">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="ee243-281">0x01-デスクトップ電話と統合</span><span class="sxs-lookup"><span data-stu-id="ee243-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee243-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-283">smallint</span><span class="sxs-lookup"><span data-stu-id="ee243-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="ee243-284">呼び出しの属性を示します。</span><span class="sxs-lookup"><span data-stu-id="ee243-284">Indicates the call attributes.</span></span> <span data-ttu-id="ee243-285">次の属性定義を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ee243-285">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="ee243-286">0x01-再試行セッション</span><span class="sxs-lookup"><span data-stu-id="ee243-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="ee243-287">0x02-応答グループの代理としてエージェントによって発信された通話</span><span class="sxs-lookup"><span data-stu-id="ee243-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee243-288"><strong>場所</strong></span><span class="sxs-lookup"><span data-stu-id="ee243-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="ee243-289">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="ee243-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="ee243-290">緊急通話の場所。</span><span class="sxs-lookup"><span data-stu-id="ee243-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

