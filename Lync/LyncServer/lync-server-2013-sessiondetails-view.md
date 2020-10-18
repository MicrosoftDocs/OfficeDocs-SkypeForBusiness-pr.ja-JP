---
title: 'Lync Server 2013: SessionDetails ビュー'
description: 'Lync Server 2013: SessionDetails ビュー。'
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
ms.openlocfilehash: 4c9f657257e54389defb805919be61adbdecad74
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573243"
---
# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="b92f8-103">Lync Server 2013 の SessionDetails ビュー</span><span class="sxs-lookup"><span data-stu-id="b92f8-103">SessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b92f8-104">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="b92f8-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="b92f8-105">SessionDetails ビューには、ピアツーピアセッションに関する情報が格納されます。これは VoIP-VoIP 電話、2者間の IM セッション、またはその他の種類のセッションである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b92f8-105">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="b92f8-106">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b92f8-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b92f8-107">Column</span><span class="sxs-lookup"><span data-stu-id="b92f8-107">Column</span></span></th>
<th><span data-ttu-id="b92f8-108">データ型</span><span class="sxs-lookup"><span data-stu-id="b92f8-108">Data Type</span></span></th>
<th><span data-ttu-id="b92f8-109">詳細</span><span class="sxs-lookup"><span data-stu-id="b92f8-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-111">日付型</span><span class="sxs-lookup"><span data-stu-id="b92f8-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="b92f8-112">セッション要求の時間。</span><span class="sxs-lookup"><span data-stu-id="b92f8-112">Time of session request.</span></span> <span data-ttu-id="b92f8-113">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="b92f8-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="b92f8-114">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013</a> の表」の「Dialogs table」テーブルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92f8-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-115"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-116">int</span><span class="sxs-lookup"><span data-stu-id="b92f8-116">int</span></span></p></td>
<td><p><span data-ttu-id="b92f8-117">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="b92f8-117">ID number to identify the session.</span></span> <span data-ttu-id="b92f8-118">セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="b92f8-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="b92f8-119">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92f8-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-121">日付型</span><span class="sxs-lookup"><span data-stu-id="b92f8-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="b92f8-p104">最初の INVITE 要求の時刻。通常は、セッションの最初の INVITE メッセージから生成されたデータが設定されます。INVITE メッセージがない場合は、関連する最初の SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。このフィールドには通常、セッションの最初の INVITE メッセージから生成されたデータが設定されます。INVITE メッセージがない場合、このフィールドには関連する最初の SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="b92f8-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO). This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-127"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-127"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b92f8-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-129">セッションを開始したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="b92f8-129">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-130"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-130"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-131">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b92f8-131">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-132">セッションに参加したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="b92f8-132">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-133"><strong>Fromuritoff</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-133"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b92f8-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-135">セッションを開始したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="b92f8-135">Type of URI of the user who started the session.</span></span> <span data-ttu-id="b92f8-136">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92f8-136">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-137"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-137"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-138">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b92f8-138">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-139">セッションに参加したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="b92f8-139">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="b92f8-140">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92f8-140">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-141"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-141"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b92f8-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-143">セッションを開始したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="b92f8-143">Tenant of the user who started the session.</span></span> <span data-ttu-id="b92f8-144">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92f8-144">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-145"><strong>すべての Ant</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-145"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-146">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b92f8-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-147">セッションに参加したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="b92f8-147">The tenant of the user who joined the session.</span></span> <span data-ttu-id="b92f8-148">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92f8-148">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-149"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-149"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-150">識別子</span><span class="sxs-lookup"><span data-stu-id="b92f8-150">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="b92f8-151">セッションを開始したユーザーのエンドポイントの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="b92f8-151">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-152"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-152"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-153">識別子</span><span class="sxs-lookup"><span data-stu-id="b92f8-153">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="b92f8-154">セッションに参加したユーザーのエンドポイントの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="b92f8-154">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-155"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-155"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-156">日付型</span><span class="sxs-lookup"><span data-stu-id="b92f8-156">datetime</span></span></p></td>
<td><p><span data-ttu-id="b92f8-157">セッションの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="b92f8-157">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-158"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-158"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-159">int</span><span class="sxs-lookup"><span data-stu-id="b92f8-159">int</span></span></p></td>
<td><p><span data-ttu-id="b92f8-160">セッションを開始したユーザーが送信したメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="b92f8-160">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-161"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-161"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-162">int</span><span class="sxs-lookup"><span data-stu-id="b92f8-162">int</span></span></p></td>
<td><p><span data-ttu-id="b92f8-163">セッションに参加したユーザーが送信したメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="b92f8-163">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-164"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-164"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b92f8-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-166">セッションを開始したユーザーが使用しているクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="b92f8-166">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-167"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-167"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-168">int</span><span class="sxs-lookup"><span data-stu-id="b92f8-168">int</span></span></p></td>
<td><p><span data-ttu-id="b92f8-169">セッションを開始したユーザーが使用しているクライアント。</span><span class="sxs-lookup"><span data-stu-id="b92f8-169">Client used by the user who started the session.</span></span> <span data-ttu-id="b92f8-170">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92f8-170">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-171"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-171"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b92f8-172">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-173">セッションを開始したユーザーが使用しているクライアントのカテゴリ名。</span><span class="sxs-lookup"><span data-stu-id="b92f8-173">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-174"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-174"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-175">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b92f8-175">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-176">セッションに参加したユーザーが使用しているクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="b92f8-176">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-177"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-177"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-178">int</span><span class="sxs-lookup"><span data-stu-id="b92f8-178">int</span></span></p></td>
<td><p><span data-ttu-id="b92f8-179">セッションに参加したユーザーが使用しているクライアント。</span><span class="sxs-lookup"><span data-stu-id="b92f8-179">Client used by the user who joined the session.</span></span> <span data-ttu-id="b92f8-180">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92f8-180">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-181"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-181"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-182">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b92f8-182">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-183">セッションに参加したユーザーが使用しているクライアントのカテゴリ名。</span><span class="sxs-lookup"><span data-stu-id="b92f8-183">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-184"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-184"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-185">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b92f8-185">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-186">セッションのターゲット ユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="b92f8-186">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-187"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-187"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-188">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b92f8-188">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-189">セッションのターゲット ユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="b92f8-189">Type of URI of the target user for the session.</span></span> <span data-ttu-id="b92f8-190">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92f8-190">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-191"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-191"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b92f8-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-193">代表してセッションを開始したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="b92f8-193">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-194"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-194"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b92f8-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-196">代表してセッションを開始したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="b92f8-196">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="b92f8-197">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92f8-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-198"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-198"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b92f8-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-200">代表してセッションを開始したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="b92f8-200">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="b92f8-201">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92f8-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-202"><strong>があります。</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-202"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-203">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b92f8-203">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-204">セッションを委譲したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="b92f8-204">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-205"><strong>ベンチャー Redbyuritん</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-205"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-206">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b92f8-206">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-207">セッションを委譲したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="b92f8-207">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="b92f8-208">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92f8-208">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-209"><strong>このテナント</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-209"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-210">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b92f8-210">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-211">セッションを委譲したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="b92f8-211">Tenant of the user who referred the session.</span></span> <span data-ttu-id="b92f8-212">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92f8-212">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-213"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-213"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-214">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="b92f8-214">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-p116">SIP ダイアログ ID。形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b92f8-p116">SIP dialog ID. The format is:</span></span></p>
<p><span data-ttu-id="b92f8-217">dialog、from タグ、およびタグ</span><span class="sxs-lookup"><span data-stu-id="b92f8-217">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-218"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-218"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-219">識別子</span><span class="sxs-lookup"><span data-stu-id="b92f8-219">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="b92f8-220">複数のセッションを相互に関連付けるために使用する GUID。</span><span class="sxs-lookup"><span data-stu-id="b92f8-220">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-221"><strong>Edialogidtime を置換する</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-221"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-222">日付型</span><span class="sxs-lookup"><span data-stu-id="b92f8-222">datetime</span></span></p></td>
<td><p><span data-ttu-id="b92f8-223">セッションに置き換えられたダイアログの時刻。</span><span class="sxs-lookup"><span data-stu-id="b92f8-223">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="b92f8-224">セッションに置き換えられるダイアログを一意に識別するために ReplaceDialogIdSeq と併用されます。</span><span class="sxs-lookup"><span data-stu-id="b92f8-224">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="b92f8-225">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92f8-225">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-226"><strong>Edialogidseq を置換する</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-226"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-227">int</span><span class="sxs-lookup"><span data-stu-id="b92f8-227">int</span></span></p></td>
<td><p><span data-ttu-id="b92f8-228">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="b92f8-228">ID number to identify the session.</span></span> <span data-ttu-id="b92f8-229">セッションに置き換えられるダイアログを一意に識別するために ReplacesDialogIdTime と併用されます。</span><span class="sxs-lookup"><span data-stu-id="b92f8-229">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="b92f8-230">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92f8-230">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-231"><strong>置換 Es/交換 Id</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-231"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-232">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="b92f8-232">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-p119">セッションに置き換えられる SIP ダイアログ ID。形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b92f8-p119">SIP dialog ID the session replaces. The format is:</span></span></p>
<p><span data-ttu-id="b92f8-235">dialog、from タグ、およびタグ</span><span class="sxs-lookup"><span data-stu-id="b92f8-235">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-236"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-236"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-237">日付型</span><span class="sxs-lookup"><span data-stu-id="b92f8-237">datetime</span></span></p></td>
<td><p><span data-ttu-id="b92f8-p120">最初の INVITE メッセージに対する応答の時刻。通常は、セッションの最初の INVITE メッセージから生成されたデータが設定されます。INVITE メッセージがない場合は、関連する最初の SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="b92f8-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-241"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-241"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-242">int</span><span class="sxs-lookup"><span data-stu-id="b92f8-242">int</span></span></p></td>
<td><p><span data-ttu-id="b92f8-p121">セッションへの招待に対する SIP 応答コード。このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="b92f8-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-246"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-246"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-247">int</span><span class="sxs-lookup"><span data-stu-id="b92f8-247">int</span></span></p></td>
<td><p><span data-ttu-id="b92f8-248">SIP ヘッダーから取得された診断 ID。</span><span class="sxs-lookup"><span data-stu-id="b92f8-248">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-249"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-249"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-250">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b92f8-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-251">セッションのコンテンツの種類。</span><span class="sxs-lookup"><span data-stu-id="b92f8-251">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-252"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-252"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-253">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b92f8-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-254">セッションのデータをキャプチャしたフロントエンド サーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="b92f8-254">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-255"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-255"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-256">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b92f8-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-257">セッションのデータをキャプチャしたプールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="b92f8-257">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-258"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-258"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-259">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b92f8-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-260">セッションを開始したユーザーが使用しているエッジ サーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="b92f8-260">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-261"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-261"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-262">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b92f8-262">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-263">セッションを開始したユーザーが使用しているエッジ サーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="b92f8-263">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-264"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-264"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-265">若干</span><span class="sxs-lookup"><span data-stu-id="b92f8-265">bit</span></span></p></td>
<td><p><span data-ttu-id="b92f8-266">セッションを開始したユーザーが内部ネットワークからログオンしていたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b92f8-266">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-267"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-267"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-268">若干</span><span class="sxs-lookup"><span data-stu-id="b92f8-268">bit</span></span></p></td>
<td><p><span data-ttu-id="b92f8-269">セッションに参加したユーザーが内部ネットワークからログオンしていたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b92f8-269">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-270"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-270"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-271">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b92f8-271">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-272">セッションの通話の優先順位。</span><span class="sxs-lookup"><span data-stu-id="b92f8-272">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-273"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-273"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-274">smallint</span><span class="sxs-lookup"><span data-stu-id="b92f8-274">smallint</span></span></p></td>
<td><p><span data-ttu-id="b92f8-p122">セッションを開始したユーザーの属性を示します。次の属性定義ができます。</span><span class="sxs-lookup"><span data-stu-id="b92f8-p122">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="b92f8-277">0x01 - デスクトップ電話と統合</span><span class="sxs-lookup"><span data-stu-id="b92f8-277">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-278"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-278"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-279">smallint</span><span class="sxs-lookup"><span data-stu-id="b92f8-279">smallint</span></span></p></td>
<td><p><span data-ttu-id="b92f8-p123">セッションを開始したユーザーの属性を示します。次の属性定義ができます。</span><span class="sxs-lookup"><span data-stu-id="b92f8-p123">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="b92f8-282">0x01 - デスクトップ電話と統合</span><span class="sxs-lookup"><span data-stu-id="b92f8-282">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-283"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-283"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-284">smallint</span><span class="sxs-lookup"><span data-stu-id="b92f8-284">smallint</span></span></p></td>
<td><p><span data-ttu-id="b92f8-p124">通話の属性を示します。次の属性定義ができます。</span><span class="sxs-lookup"><span data-stu-id="b92f8-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="b92f8-287">0x01 - 再試行されたセッション</span><span class="sxs-lookup"><span data-stu-id="b92f8-287">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="b92f8-288">0x02 - 応答グループの代理を務めるエージェントによって行われた通話</span><span class="sxs-lookup"><span data-stu-id="b92f8-288">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-289"><strong>Location</strong></span><span class="sxs-lookup"><span data-stu-id="b92f8-289"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="b92f8-290">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="b92f8-290">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="b92f8-291">緊急通話の場所。</span><span class="sxs-lookup"><span data-stu-id="b92f8-291">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

