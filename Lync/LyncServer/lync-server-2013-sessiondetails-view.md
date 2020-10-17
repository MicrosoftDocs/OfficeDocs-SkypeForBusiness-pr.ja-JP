---
title: 'Lync Server 2013: SessionDetails ビュー'
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
ms.openlocfilehash: 8baf67ce72103ef0dda64a9b0b43a8f6dd6402f4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510064"
---
# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="250cd-102">Lync Server 2013 の SessionDetails ビュー</span><span class="sxs-lookup"><span data-stu-id="250cd-102">SessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="250cd-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="250cd-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="250cd-104">SessionDetails ビューには、ピアツーピアセッションに関する情報が格納されます。これは VoIP-VoIP 電話、2者間の IM セッション、またはその他の種類のセッションである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="250cd-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="250cd-105">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="250cd-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="250cd-106">Column</span><span class="sxs-lookup"><span data-stu-id="250cd-106">Column</span></span></th>
<th><span data-ttu-id="250cd-107">データ型</span><span class="sxs-lookup"><span data-stu-id="250cd-107">Data Type</span></span></th>
<th><span data-ttu-id="250cd-108">詳細</span><span class="sxs-lookup"><span data-stu-id="250cd-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="250cd-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-110">日付型</span><span class="sxs-lookup"><span data-stu-id="250cd-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="250cd-111">セッション要求の時間。</span><span class="sxs-lookup"><span data-stu-id="250cd-111">Time of session request.</span></span> <span data-ttu-id="250cd-112">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="250cd-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="250cd-113">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013</a> の表」の「Dialogs table」テーブルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="250cd-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250cd-114"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-115">int</span><span class="sxs-lookup"><span data-stu-id="250cd-115">int</span></span></p></td>
<td><p><span data-ttu-id="250cd-116">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="250cd-116">ID number to identify the session.</span></span> <span data-ttu-id="250cd-117">セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="250cd-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="250cd-118">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="250cd-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250cd-119"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-120">日付型</span><span class="sxs-lookup"><span data-stu-id="250cd-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="250cd-p104">最初の INVITE 要求の時刻。通常は、セッションの最初の INVITE メッセージから生成されたデータが設定されます。INVITE メッセージがない場合は、関連する最初の SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。このフィールドには通常、セッションの最初の INVITE メッセージから生成されたデータが設定されます。INVITE メッセージがない場合、このフィールドには関連する最初の SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="250cd-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO). This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250cd-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="250cd-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="250cd-128">セッションを開始したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="250cd-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250cd-129"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="250cd-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="250cd-131">セッションに参加したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="250cd-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250cd-132"><strong>Fromuritoff</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-133">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="250cd-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="250cd-134">セッションを開始したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="250cd-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="250cd-135">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="250cd-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250cd-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="250cd-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="250cd-138">セッションに参加したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="250cd-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="250cd-139">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="250cd-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250cd-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="250cd-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="250cd-142">セッションを開始したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="250cd-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="250cd-143">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="250cd-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250cd-144"><strong>すべての Ant</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-145">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="250cd-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="250cd-146">セッションに参加したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="250cd-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="250cd-147">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="250cd-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250cd-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-149">識別子</span><span class="sxs-lookup"><span data-stu-id="250cd-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="250cd-150">セッションを開始したユーザーのエンドポイントの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="250cd-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250cd-151"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-152">識別子</span><span class="sxs-lookup"><span data-stu-id="250cd-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="250cd-153">セッションに参加したユーザーのエンドポイントの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="250cd-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250cd-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-155">日付型</span><span class="sxs-lookup"><span data-stu-id="250cd-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="250cd-156">セッションの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="250cd-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250cd-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-158">int</span><span class="sxs-lookup"><span data-stu-id="250cd-158">int</span></span></p></td>
<td><p><span data-ttu-id="250cd-159">セッションを開始したユーザーが送信したメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="250cd-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250cd-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-161">int</span><span class="sxs-lookup"><span data-stu-id="250cd-161">int</span></span></p></td>
<td><p><span data-ttu-id="250cd-162">セッションに参加したユーザーが送信したメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="250cd-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250cd-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-164">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="250cd-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="250cd-165">セッションを開始したユーザーが使用しているクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="250cd-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250cd-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-167">int</span><span class="sxs-lookup"><span data-stu-id="250cd-167">int</span></span></p></td>
<td><p><span data-ttu-id="250cd-168">セッションを開始したユーザーが使用しているクライアント。</span><span class="sxs-lookup"><span data-stu-id="250cd-168">Client used by the user who started the session.</span></span> <span data-ttu-id="250cd-169">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="250cd-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250cd-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="250cd-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="250cd-172">セッションを開始したユーザーが使用しているクライアントのカテゴリ名。</span><span class="sxs-lookup"><span data-stu-id="250cd-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250cd-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="250cd-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="250cd-175">セッションに参加したユーザーが使用しているクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="250cd-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250cd-176"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-177">int</span><span class="sxs-lookup"><span data-stu-id="250cd-177">int</span></span></p></td>
<td><p><span data-ttu-id="250cd-178">セッションに参加したユーザーが使用しているクライアント。</span><span class="sxs-lookup"><span data-stu-id="250cd-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="250cd-179">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="250cd-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250cd-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="250cd-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="250cd-182">セッションに参加したユーザーが使用しているクライアントのカテゴリ名。</span><span class="sxs-lookup"><span data-stu-id="250cd-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250cd-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="250cd-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="250cd-185">セッションのターゲット ユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="250cd-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250cd-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="250cd-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="250cd-188">セッションのターゲット ユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="250cd-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="250cd-189">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="250cd-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250cd-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="250cd-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="250cd-192">代表してセッションを開始したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="250cd-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250cd-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="250cd-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="250cd-195">代表してセッションを開始したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="250cd-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="250cd-196">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="250cd-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250cd-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-198">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="250cd-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="250cd-199">代表してセッションを開始したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="250cd-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="250cd-200">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="250cd-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250cd-201"><strong>があります。</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="250cd-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="250cd-203">セッションを委譲したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="250cd-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250cd-204"><strong>ベンチャー Redbyuritん</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-205">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="250cd-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="250cd-206">セッションを委譲したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="250cd-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="250cd-207">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="250cd-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250cd-208"><strong>このテナント</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-209">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="250cd-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="250cd-210">セッションを委譲したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="250cd-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="250cd-211">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="250cd-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250cd-212"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-213">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="250cd-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="250cd-p116">SIP ダイアログ ID。形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="250cd-p116">SIP dialog ID. The format is:</span></span></p>
<p><span data-ttu-id="250cd-216">dialog、from タグ、およびタグ</span><span class="sxs-lookup"><span data-stu-id="250cd-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250cd-217"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-218">識別子</span><span class="sxs-lookup"><span data-stu-id="250cd-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="250cd-219">複数のセッションを相互に関連付けるために使用する GUID。</span><span class="sxs-lookup"><span data-stu-id="250cd-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250cd-220"><strong>Edialogidtime を置換する</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-221">日付型</span><span class="sxs-lookup"><span data-stu-id="250cd-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="250cd-222">セッションに置き換えられたダイアログの時刻。</span><span class="sxs-lookup"><span data-stu-id="250cd-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="250cd-223">セッションに置き換えられるダイアログを一意に識別するために ReplaceDialogIdSeq と併用されます。</span><span class="sxs-lookup"><span data-stu-id="250cd-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="250cd-224">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="250cd-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250cd-225"><strong>Edialogidseq を置換する</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-226">int</span><span class="sxs-lookup"><span data-stu-id="250cd-226">int</span></span></p></td>
<td><p><span data-ttu-id="250cd-227">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="250cd-227">ID number to identify the session.</span></span> <span data-ttu-id="250cd-228">セッションに置き換えられるダイアログを一意に識別するために ReplacesDialogIdTime と併用されます。</span><span class="sxs-lookup"><span data-stu-id="250cd-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="250cd-229">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="250cd-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250cd-230"><strong>置換 Es/交換 Id</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-231">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="250cd-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="250cd-p119">セッションに置き換えられる SIP ダイアログ ID。形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="250cd-p119">SIP dialog ID the session replaces. The format is:</span></span></p>
<p><span data-ttu-id="250cd-234">dialog、from タグ、およびタグ</span><span class="sxs-lookup"><span data-stu-id="250cd-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250cd-235"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-236">日付型</span><span class="sxs-lookup"><span data-stu-id="250cd-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="250cd-p120">最初の INVITE メッセージに対する応答の時刻。通常は、セッションの最初の INVITE メッセージから生成されたデータが設定されます。INVITE メッセージがない場合は、関連する最初の SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="250cd-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250cd-240"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-241">int</span><span class="sxs-lookup"><span data-stu-id="250cd-241">int</span></span></p></td>
<td><p><span data-ttu-id="250cd-p121">セッションへの招待に対する SIP 応答コード。このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="250cd-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250cd-245"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-246">int</span><span class="sxs-lookup"><span data-stu-id="250cd-246">int</span></span></p></td>
<td><p><span data-ttu-id="250cd-247">SIP ヘッダーから取得された診断 ID。</span><span class="sxs-lookup"><span data-stu-id="250cd-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250cd-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-249">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="250cd-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="250cd-250">セッションのコンテンツの種類。</span><span class="sxs-lookup"><span data-stu-id="250cd-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250cd-251"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-252">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="250cd-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="250cd-253">セッションのデータをキャプチャしたフロントエンド サーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="250cd-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250cd-254"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-255">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="250cd-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="250cd-256">セッションのデータをキャプチャしたプールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="250cd-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250cd-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-258">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="250cd-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="250cd-259">セッションを開始したユーザーが使用しているエッジ サーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="250cd-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250cd-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-261">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="250cd-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="250cd-262">セッションを開始したユーザーが使用しているエッジ サーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="250cd-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250cd-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-264">若干</span><span class="sxs-lookup"><span data-stu-id="250cd-264">bit</span></span></p></td>
<td><p><span data-ttu-id="250cd-265">セッションを開始したユーザーが内部ネットワークからログオンしていたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="250cd-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250cd-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-267">若干</span><span class="sxs-lookup"><span data-stu-id="250cd-267">bit</span></span></p></td>
<td><p><span data-ttu-id="250cd-268">セッションに参加したユーザーが内部ネットワークからログオンしていたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="250cd-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250cd-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-270">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="250cd-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="250cd-271">セッションの通話の優先順位。</span><span class="sxs-lookup"><span data-stu-id="250cd-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250cd-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-273">smallint</span><span class="sxs-lookup"><span data-stu-id="250cd-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="250cd-p122">セッションを開始したユーザーの属性を示します。次の属性定義ができます。</span><span class="sxs-lookup"><span data-stu-id="250cd-p122">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="250cd-276">0x01 - デスクトップ電話と統合</span><span class="sxs-lookup"><span data-stu-id="250cd-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250cd-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-278">smallint</span><span class="sxs-lookup"><span data-stu-id="250cd-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="250cd-p123">セッションを開始したユーザーの属性を示します。次の属性定義ができます。</span><span class="sxs-lookup"><span data-stu-id="250cd-p123">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="250cd-281">0x01 - デスクトップ電話と統合</span><span class="sxs-lookup"><span data-stu-id="250cd-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250cd-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-283">smallint</span><span class="sxs-lookup"><span data-stu-id="250cd-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="250cd-p124">通話の属性を示します。次の属性定義ができます。</span><span class="sxs-lookup"><span data-stu-id="250cd-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="250cd-286">0x01 - 再試行されたセッション</span><span class="sxs-lookup"><span data-stu-id="250cd-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="250cd-287">0x02 - 応答グループの代理を務めるエージェントによって行われた通話</span><span class="sxs-lookup"><span data-stu-id="250cd-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250cd-288"><strong>Location</strong></span><span class="sxs-lookup"><span data-stu-id="250cd-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="250cd-289">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="250cd-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="250cd-290">緊急通話の場所。</span><span class="sxs-lookup"><span data-stu-id="250cd-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

