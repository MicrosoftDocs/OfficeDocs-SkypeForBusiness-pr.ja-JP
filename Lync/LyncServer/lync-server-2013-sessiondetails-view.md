---
title: 'Lync Server 2013: セッションの詳細ビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bd3902fd35679366e905c04e99ff1e72b2ece86
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="faf52-102">Lync Server 2013 のセッション詳細表示</span><span class="sxs-lookup"><span data-stu-id="faf52-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="faf52-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="faf52-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="faf52-104">セッション詳細ビューには、VoIP 電話、2パーティの IM セッション、その他の種類のセッションなど、ピアツーピアセッションに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="faf52-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="faf52-105">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="faf52-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="faf52-106">列</span><span class="sxs-lookup"><span data-stu-id="faf52-106">Column</span></span></th>
<th><span data-ttu-id="faf52-107">データ型</span><span class="sxs-lookup"><span data-stu-id="faf52-107">Data Type</span></span></th>
<th><span data-ttu-id="faf52-108">詳細</span><span class="sxs-lookup"><span data-stu-id="faf52-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="faf52-109"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-110">datetime</span><span class="sxs-lookup"><span data-stu-id="faf52-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="faf52-111">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="faf52-111">Time of session request.</span></span> <span data-ttu-id="faf52-112">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="faf52-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="faf52-113">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 テーブルのダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="faf52-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf52-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-115">int</span><span class="sxs-lookup"><span data-stu-id="faf52-115">int</span></span></p></td>
<td><p><span data-ttu-id="faf52-116">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="faf52-116">ID number to identify the session.</span></span> <span data-ttu-id="faf52-117">セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="faf52-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="faf52-118">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="faf52-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf52-119"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-120">datetime</span><span class="sxs-lookup"><span data-stu-id="faf52-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="faf52-121">最初の招待要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="faf52-121">Time of the first INVITE request.</span></span> <span data-ttu-id="faf52-122">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="faf52-122">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="faf52-123">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="faf52-123">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="faf52-124">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="faf52-124">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="faf52-125">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="faf52-125">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf52-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="faf52-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="faf52-128">セッションを開始したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="faf52-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf52-129"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="faf52-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="faf52-131">セッションに参加したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="faf52-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf52-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-133">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="faf52-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="faf52-134">セッションを開始したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="faf52-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="faf52-135">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="faf52-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf52-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="faf52-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="faf52-138">セッションに参加したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="faf52-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="faf52-139">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="faf52-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf52-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="faf52-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="faf52-142">セッションを開始したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="faf52-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="faf52-143">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="faf52-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf52-144"><strong>すべての Ant</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-145">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="faf52-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="faf52-146">セッションに参加したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="faf52-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="faf52-147">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="faf52-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf52-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-149">長さ</span><span class="sxs-lookup"><span data-stu-id="faf52-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="faf52-150">セッションを開始したユーザーのエンドポイントを表す一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="faf52-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf52-151"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-152">長さ</span><span class="sxs-lookup"><span data-stu-id="faf52-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="faf52-153">セッションに参加したユーザーのエンドポイントを表す一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="faf52-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf52-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-155">datetime</span><span class="sxs-lookup"><span data-stu-id="faf52-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="faf52-156">セッションの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="faf52-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf52-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-158">int</span><span class="sxs-lookup"><span data-stu-id="faf52-158">int</span></span></p></td>
<td><p><span data-ttu-id="faf52-159">セッションを開始したユーザーによって送信されたメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="faf52-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf52-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-161">int</span><span class="sxs-lookup"><span data-stu-id="faf52-161">int</span></span></p></td>
<td><p><span data-ttu-id="faf52-162">セッションに参加したユーザーによって送信されたメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="faf52-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf52-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-164">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="faf52-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="faf52-165">セッションを開始したユーザーによって使用されたクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="faf52-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf52-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-167">int</span><span class="sxs-lookup"><span data-stu-id="faf52-167">int</span></span></p></td>
<td><p><span data-ttu-id="faf52-168">セッションを開始したユーザーによって使用されたクライアント。</span><span class="sxs-lookup"><span data-stu-id="faf52-168">Client used by the user who started the session.</span></span> <span data-ttu-id="faf52-169">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="faf52-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf52-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="faf52-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="faf52-172">セッションを開始したユーザーによって使用されたクライアントのカテゴリの名前です。</span><span class="sxs-lookup"><span data-stu-id="faf52-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf52-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-174">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="faf52-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="faf52-175">セッションに参加したユーザーによって使用されたクライアントのバージョン</span><span class="sxs-lookup"><span data-stu-id="faf52-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf52-176"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-177">int</span><span class="sxs-lookup"><span data-stu-id="faf52-177">int</span></span></p></td>
<td><p><span data-ttu-id="faf52-178">セッションに参加したユーザーによって使用されたクライアント。</span><span class="sxs-lookup"><span data-stu-id="faf52-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="faf52-179">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="faf52-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf52-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="faf52-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="faf52-182">セッションに参加したユーザーによって使用されたクライアントのカテゴリの名前です。</span><span class="sxs-lookup"><span data-stu-id="faf52-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf52-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="faf52-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="faf52-185">セッションのターゲットユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="faf52-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf52-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="faf52-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="faf52-188">セッションのターゲットユーザーの URI の種類です。</span><span class="sxs-lookup"><span data-stu-id="faf52-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="faf52-189">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="faf52-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf52-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="faf52-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="faf52-192">セッションが開始されたユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="faf52-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf52-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="faf52-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="faf52-195">セッションが開始されたユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="faf52-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="faf52-196">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="faf52-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf52-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-198">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="faf52-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="faf52-199">セッションを開始したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="faf52-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="faf52-200">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="faf52-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf52-201"><strong>△この Uri</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="faf52-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="faf52-203">セッションを参照したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="faf52-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf52-204"><strong>ベンチャー Redbyuritん</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-205">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="faf52-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="faf52-206">セッションを参照したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="faf52-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="faf52-207">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="faf52-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf52-208"><strong>このテナント</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-209">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="faf52-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="faf52-210">セッションを参照したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="faf52-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="faf52-211">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="faf52-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf52-212"><strong>この Id</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-213">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="faf52-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="faf52-214">SIP ダイアログ ID。</span><span class="sxs-lookup"><span data-stu-id="faf52-214">SIP dialog ID.</span></span> <span data-ttu-id="faf52-215">形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="faf52-215">The format is:</span></span></p>
<p><span data-ttu-id="faf52-216">ダイアログ; 開始タグからタグへ</span><span class="sxs-lookup"><span data-stu-id="faf52-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf52-217"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-218">長さ</span><span class="sxs-lookup"><span data-stu-id="faf52-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="faf52-219">複数のセッションの関連付けに使用する GUID。</span><span class="sxs-lookup"><span data-stu-id="faf52-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf52-220"><strong>Edialogidtime の置き換え</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-221">datetime</span><span class="sxs-lookup"><span data-stu-id="faf52-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="faf52-222">セッションによって置き換えられたダイアログの時間です。</span><span class="sxs-lookup"><span data-stu-id="faf52-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="faf52-223">セッションによって置き換えられるダイアログを一意に識別するには、置換 Edialogidseq と組み合わせて使います。</span><span class="sxs-lookup"><span data-stu-id="faf52-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="faf52-224">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="faf52-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf52-225"><strong>Edialogidseq の置き換え</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-226">int</span><span class="sxs-lookup"><span data-stu-id="faf52-226">int</span></span></p></td>
<td><p><span data-ttu-id="faf52-227">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="faf52-227">ID number to identify the session.</span></span> <span data-ttu-id="faf52-228">セッションによって置き換えられるダイアログを一意に識別するために、交換 Edialogidtime と組み合わせて使います。</span><span class="sxs-lookup"><span data-stu-id="faf52-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="faf52-229">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="faf52-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf52-230"><strong>置換の方法 Id</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-231">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="faf52-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="faf52-232">SIP ダイアログ ID によってセッションが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="faf52-232">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="faf52-233">形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="faf52-233">The format is:</span></span></p>
<p><span data-ttu-id="faf52-234">ダイアログ; 開始タグからタグへ</span><span class="sxs-lookup"><span data-stu-id="faf52-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf52-235"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-236">datetime</span><span class="sxs-lookup"><span data-stu-id="faf52-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="faf52-237">最初の招待メッセージに対する返信の時刻。</span><span class="sxs-lookup"><span data-stu-id="faf52-237">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="faf52-238">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="faf52-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="faf52-239">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="faf52-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf52-240"><strong>返信</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-241">int</span><span class="sxs-lookup"><span data-stu-id="faf52-241">int</span></span></p></td>
<td><p><span data-ttu-id="faf52-242">セッション招待状への SIP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="faf52-242">SIP response code to the session invitation.</span></span> <span data-ttu-id="faf52-243">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="faf52-243">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="faf52-244">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="faf52-244">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf52-245"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-246">int</span><span class="sxs-lookup"><span data-stu-id="faf52-246">int</span></span></p></td>
<td><p><span data-ttu-id="faf52-247">SIP ヘッダーからキャプチャされた診断 ID。</span><span class="sxs-lookup"><span data-stu-id="faf52-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf52-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-249">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="faf52-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="faf52-250">セッションのコンテンツの種類です。</span><span class="sxs-lookup"><span data-stu-id="faf52-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf52-251"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-252">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="faf52-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="faf52-253">セッションのデータをキャプチャしたフロントエンドサーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="faf52-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf52-254"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-255">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="faf52-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="faf52-256">セッションのデータをキャプチャしたプールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="faf52-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf52-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-258">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="faf52-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="faf52-259">セッションを開始したユーザーによって使用されたエッジサーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="faf52-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf52-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-261">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="faf52-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="faf52-262">セッションを開始したユーザーによって使用されたエッジサーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="faf52-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf52-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-264">bit</span><span class="sxs-lookup"><span data-stu-id="faf52-264">bit</span></span></p></td>
<td><p><span data-ttu-id="faf52-265">セッションを開始したユーザーが内部ネットワークからログオンしているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="faf52-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf52-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-267">bit</span><span class="sxs-lookup"><span data-stu-id="faf52-267">bit</span></span></p></td>
<td><p><span data-ttu-id="faf52-268">セッションに参加したユーザーが内部ネットワークからログオンしているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="faf52-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf52-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-270">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="faf52-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="faf52-271">セッションの通話優先度。</span><span class="sxs-lookup"><span data-stu-id="faf52-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf52-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-273">smallint</span><span class="sxs-lookup"><span data-stu-id="faf52-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="faf52-274">セッションを開始したユーザーの属性を示します。</span><span class="sxs-lookup"><span data-stu-id="faf52-274">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="faf52-275">次の属性定義を使用できます。</span><span class="sxs-lookup"><span data-stu-id="faf52-275">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="faf52-276">0x01-デスクトップ電話と統合</span><span class="sxs-lookup"><span data-stu-id="faf52-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf52-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-278">smallint</span><span class="sxs-lookup"><span data-stu-id="faf52-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="faf52-279">セッションを開始したユーザーの属性を示します。</span><span class="sxs-lookup"><span data-stu-id="faf52-279">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="faf52-280">次の属性定義を使用できます。</span><span class="sxs-lookup"><span data-stu-id="faf52-280">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="faf52-281">0x01-デスクトップ電話と統合</span><span class="sxs-lookup"><span data-stu-id="faf52-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf52-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-283">smallint</span><span class="sxs-lookup"><span data-stu-id="faf52-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="faf52-284">呼び出しの属性を示します。</span><span class="sxs-lookup"><span data-stu-id="faf52-284">Indicates the call attributes.</span></span> <span data-ttu-id="faf52-285">次の属性定義を使用できます。</span><span class="sxs-lookup"><span data-stu-id="faf52-285">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="faf52-286">0x01-再試行セッション</span><span class="sxs-lookup"><span data-stu-id="faf52-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="faf52-287">0x02-応答グループの代理としてエージェントによって発信された通話</span><span class="sxs-lookup"><span data-stu-id="faf52-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf52-288"><strong>場所</strong></span><span class="sxs-lookup"><span data-stu-id="faf52-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="faf52-289">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="faf52-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="faf52-290">緊急通話の場所。</span><span class="sxs-lookup"><span data-stu-id="faf52-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

