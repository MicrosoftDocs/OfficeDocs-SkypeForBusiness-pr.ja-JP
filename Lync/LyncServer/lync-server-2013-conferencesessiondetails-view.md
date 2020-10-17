---
title: 'Lync Server 2013: ConferenceSessionDetails ビュー'
description: 'Lync Server 2013: ConferenceSessionDetails ビュー。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails view
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49733660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1c62f020413efecdbc0f909618256ccc7308d4f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566773"
---
# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="2b43d-103">Lync Server 2013 の ConferenceSessionDetails ビュー</span><span class="sxs-lookup"><span data-stu-id="2b43d-103">ConferenceSessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b43d-104">_**トピックの最終更新日:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="2b43d-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="2b43d-105">ConferenceSessionDetails ビューは、マルチパーティセッションに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="2b43d-105">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="2b43d-106">各レコードは1つの電話会議セッションを表し、フォーカスがあるセッション、または特定の会議サーバーとのセッションのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="2b43d-106">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="2b43d-107">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2b43d-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b43d-108">Column</span><span class="sxs-lookup"><span data-stu-id="2b43d-108">Column</span></span></th>
<th><span data-ttu-id="2b43d-109">データ型</span><span class="sxs-lookup"><span data-stu-id="2b43d-109">Data Type</span></span></th>
<th><span data-ttu-id="2b43d-110">詳細</span><span class="sxs-lookup"><span data-stu-id="2b43d-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b43d-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-112">日付型</span><span class="sxs-lookup"><span data-stu-id="2b43d-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="2b43d-113">セッション要求の時間。</span><span class="sxs-lookup"><span data-stu-id="2b43d-113">Time of session request.</span></span> <span data-ttu-id="2b43d-114">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="2b43d-114">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="2b43d-115">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b43d-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b43d-116"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-117">int</span><span class="sxs-lookup"><span data-stu-id="2b43d-117">int</span></span></p></td>
<td><p><span data-ttu-id="2b43d-118">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="2b43d-118">ID number to identify the session.</span></span> <span data-ttu-id="2b43d-119">セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="2b43d-119">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="2b43d-120">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b43d-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b43d-121"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-121"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-122">日付型</span><span class="sxs-lookup"><span data-stu-id="2b43d-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="2b43d-p104">最初の INVITE 要求の時刻。通常、このフィールドには、セッションでの最初の INVITE メッセージから生成されたデータが設定されます。INVITE メッセージがない場合は、関連する最初の SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日付と時刻が設定されます。</span><span class="sxs-lookup"><span data-stu-id="2b43d-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b43d-126"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-126"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2b43d-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b43d-128">電話会議の URI。</span><span class="sxs-lookup"><span data-stu-id="2b43d-128">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b43d-129"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-129"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b43d-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b43d-131">電話会議の URI の種類。</span><span class="sxs-lookup"><span data-stu-id="2b43d-131">Type of conference URI.</span></span> <span data-ttu-id="2b43d-132">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b43d-132">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b43d-133"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-133"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-134">識別子</span><span class="sxs-lookup"><span data-stu-id="2b43d-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="2b43d-p106">定期的な電話会議のインスタンスを区別する識別子。定期的な電話会議の各インスタンスは、ConferenceURI は同じですが、ConfInstance 値が異なります。</span><span class="sxs-lookup"><span data-stu-id="2b43d-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b43d-137"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-137"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-138">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2b43d-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b43d-139">電話会議サーバーの URI。</span><span class="sxs-lookup"><span data-stu-id="2b43d-139">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b43d-140"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-140"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b43d-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b43d-142">電話会議サーバーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="2b43d-142">Type of conferencing server URI.</span></span> <span data-ttu-id="2b43d-143">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b43d-143">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b43d-144"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-144"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2b43d-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b43d-146">セッションに参加したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="2b43d-146">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b43d-147"><strong>Useruritoff</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-147"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b43d-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b43d-149">セッションに参加したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="2b43d-149">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="2b43d-150">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b43d-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b43d-151"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-151"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-152">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b43d-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b43d-153">セッションに参加したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="2b43d-153">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="2b43d-154">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b43d-154">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b43d-155"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-155"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-156">識別子</span><span class="sxs-lookup"><span data-stu-id="2b43d-156">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="2b43d-157">セッションに参加したユーザーの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="2b43d-157">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b43d-158"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-158"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-159">日付型</span><span class="sxs-lookup"><span data-stu-id="2b43d-159">datetime</span></span></p></td>
<td><p><span data-ttu-id="2b43d-160">セッションの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="2b43d-160">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b43d-161"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-161"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-162">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b43d-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b43d-163">電話会議サーバーのバージョン。</span><span class="sxs-lookup"><span data-stu-id="2b43d-163">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b43d-164"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-164"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-165">int</span><span class="sxs-lookup"><span data-stu-id="2b43d-165">int</span></span></p></td>
<td><p><span data-ttu-id="2b43d-166">電話会議サーバーの種類。</span><span class="sxs-lookup"><span data-stu-id="2b43d-166">Type of conference server.</span></span> <span data-ttu-id="2b43d-167">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b43d-167">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b43d-168"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-168"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="2b43d-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="2b43d-170">電話会議サーバーのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="2b43d-170">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b43d-171"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-171"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-172">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b43d-172">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b43d-173">セッションに参加したユーザーが使用するクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="2b43d-173">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b43d-174"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-174"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-175">int</span><span class="sxs-lookup"><span data-stu-id="2b43d-175">int</span></span></p></td>
<td><p><span data-ttu-id="2b43d-176">セッションに参加したユーザーが使用するクライアント。</span><span class="sxs-lookup"><span data-stu-id="2b43d-176">Client used by the user who participated in the session.</span></span> <span data-ttu-id="2b43d-177">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b43d-177">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b43d-178"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-178"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-179">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="2b43d-179">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="2b43d-180">セッションに参加したユーザーが使用するクライアントのカテゴリの名前。</span><span class="sxs-lookup"><span data-stu-id="2b43d-180">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b43d-181"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-181"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-182">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2b43d-182">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b43d-183">セッションが開始されたユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="2b43d-183">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b43d-184"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-184"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-185">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b43d-185">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b43d-186">代表してセッションを開始したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="2b43d-186">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="2b43d-187">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b43d-187">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b43d-188"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-188"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-189">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b43d-189">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b43d-190">代表してセッションを開始したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="2b43d-190">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="2b43d-191">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b43d-191">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b43d-192"><strong>があります。</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-192"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-193">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2b43d-193">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b43d-194">セッションを委譲したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="2b43d-194">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b43d-195"><strong>ベンチャー Redbyuritん</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-195"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-196">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b43d-196">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b43d-197">セッションを委譲したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="2b43d-197">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="2b43d-198">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b43d-198">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b43d-199"><strong>ベンチャー Redbyuritenant</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-199"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-200">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b43d-200">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b43d-201">セッションを委譲したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="2b43d-201">Tenant of the user who referred the session.</span></span> <span data-ttu-id="2b43d-202">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b43d-202">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b43d-203"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-203"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-204">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="2b43d-204">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="2b43d-p116">SIP ダイアログ ID。形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2b43d-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="2b43d-207">:d ialog; からタグを開始します。</span><span class="sxs-lookup"><span data-stu-id="2b43d-207">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b43d-208"><strong>Edialogidtime を置換する</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-208"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-209">日付型</span><span class="sxs-lookup"><span data-stu-id="2b43d-209">datetime</span></span></p></td>
<td><p><span data-ttu-id="2b43d-210">現在のセッションで置き換えられる前のダイアログを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="2b43d-210">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="2b43d-211">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b43d-211">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b43d-212"><strong>Edialogidseq を置換する</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-212"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-213">int</span><span class="sxs-lookup"><span data-stu-id="2b43d-213">int</span></span></p></td>
<td><p><span data-ttu-id="2b43d-214">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="2b43d-214">ID number to identify the session.</span></span> <span data-ttu-id="2b43d-215">このセッションで置き換えられるセッションを一意に識別するために ReplaceDialogIdTime と併用されます。</span><span class="sxs-lookup"><span data-stu-id="2b43d-215">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="2b43d-216">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b43d-216">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b43d-217"><strong>置換 Es/交換 Id</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-217"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-218">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="2b43d-218">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="2b43d-p119">セッションによって置き換えられる SIP ダイアログ ID。形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2b43d-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="2b43d-221">dialog、from タグ、およびタグ</span><span class="sxs-lookup"><span data-stu-id="2b43d-221">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b43d-222"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-222"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-223">若干</span><span class="sxs-lookup"><span data-stu-id="2b43d-223">bit</span></span></p></td>
<td><p><span data-ttu-id="2b43d-224">セッションが電話会議サーバーによって開始されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2b43d-224">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b43d-225"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-225"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-226">若干</span><span class="sxs-lookup"><span data-stu-id="2b43d-226">bit</span></span></p></td>
<td><p><span data-ttu-id="2b43d-227">セッションが電話会議サーバーによって終了されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2b43d-227">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b43d-228"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-228"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-229">若干</span><span class="sxs-lookup"><span data-stu-id="2b43d-229">bit</span></span></p></td>
<td><p><span data-ttu-id="2b43d-230">ユーザーが内部ネットワークからログオンしたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2b43d-230">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b43d-231"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-231"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-232">日付型</span><span class="sxs-lookup"><span data-stu-id="2b43d-232">datetime</span></span></p></td>
<td><p><span data-ttu-id="2b43d-p120">最初の INVITE メッセージに対する応答の時刻。通常は、セッションの最初の INVITE メッセージから生成されたデータが設定されます。INVITE メッセージがない場合は、関連する最初の SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="2b43d-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b43d-236"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-236"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-237">int</span><span class="sxs-lookup"><span data-stu-id="2b43d-237">int</span></span></p></td>
<td><p><span data-ttu-id="2b43d-p121">セッションへの招待に対する SIP 応答コード。このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="2b43d-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b43d-241"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-241"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-242">int</span><span class="sxs-lookup"><span data-stu-id="2b43d-242">int</span></span></p></td>
<td><p><span data-ttu-id="2b43d-243">セッションの SIP ヘッダーから取得された診断 ID。</span><span class="sxs-lookup"><span data-stu-id="2b43d-243">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b43d-244"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-244"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-245">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b43d-245">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b43d-246">セッションのコンテンツの種類。</span><span class="sxs-lookup"><span data-stu-id="2b43d-246">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b43d-247"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-247"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-248">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b43d-248">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b43d-249">セッションのデータをキャプチャしたフロントエンド サーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="2b43d-249">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b43d-250"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-250"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-251">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b43d-251">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b43d-252">セッションのデータを取得したプールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="2b43d-252">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b43d-253"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-253"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-254">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b43d-254">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b43d-255">セッションに参加したユーザーが使用した仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="2b43d-255">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b43d-256"><strong>ゲートウェイ</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-256"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-257">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b43d-257">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b43d-258">セッションに参加したユーザーが使用したゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="2b43d-258">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b43d-259"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-259"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-260">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b43d-260">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b43d-261">セッションに参加したユーザーが使用したエッジ サーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="2b43d-261">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b43d-262"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-262"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-263">smallint</span><span class="sxs-lookup"><span data-stu-id="2b43d-263">smallint</span></span></p></td>
<td><p><span data-ttu-id="2b43d-p122">セッションに参加したユーザーの属性を示します。次の属性定義を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b43d-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="2b43d-266">0x01 - デスクトップ電話と統合</span><span class="sxs-lookup"><span data-stu-id="2b43d-266">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b43d-267"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="2b43d-267"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="2b43d-268">smallint</span><span class="sxs-lookup"><span data-stu-id="2b43d-268">smallint</span></span></p></td>
<td><p><span data-ttu-id="2b43d-p123">通話の属性を示します。次の属性定義を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b43d-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="2b43d-271">0x01 - 再試行セッション0</span><span class="sxs-lookup"><span data-stu-id="2b43d-271">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="2b43d-272">x02 - 応答グループの代理を務めるエージェントによって行われた通話</span><span class="sxs-lookup"><span data-stu-id="2b43d-272">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

