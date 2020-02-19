---
title: 'Lync Server 2013: ConferenceSessionDetails ビュー'
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
ms.openlocfilehash: ef6d8baf95cc99c342e18200f9a17e5ab03a7f4f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="c5fbc-102">Lync Server 2013 の ConferenceSessionDetails ビュー</span><span class="sxs-lookup"><span data-stu-id="c5fbc-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5fbc-103">_**トピックの最終更新日:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="c5fbc-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="c5fbc-104">ConferenceSessionDetails ビューは、マルチパーティセッションに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="c5fbc-105">各レコードは1つの電話会議セッションを表し、フォーカスがあるセッション、または特定の会議サーバーとのセッションのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="c5fbc-106">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5fbc-107">列</span><span class="sxs-lookup"><span data-stu-id="c5fbc-107">Column</span></span></th>
<th><span data-ttu-id="c5fbc-108">データ型</span><span class="sxs-lookup"><span data-stu-id="c5fbc-108">Data Type</span></span></th>
<th><span data-ttu-id="c5fbc-109">詳細</span><span class="sxs-lookup"><span data-stu-id="c5fbc-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5fbc-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-111">日付型</span><span class="sxs-lookup"><span data-stu-id="c5fbc-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-112">セッション要求の時間。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-112">Time of session request.</span></span> <span data-ttu-id="c5fbc-113">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="c5fbc-114">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5fbc-115"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-116">int</span><span class="sxs-lookup"><span data-stu-id="c5fbc-116">int</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-117">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-117">ID number to identify the session.</span></span> <span data-ttu-id="c5fbc-118">セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="c5fbc-119">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5fbc-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-121">日付型</span><span class="sxs-lookup"><span data-stu-id="c5fbc-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-p104">最初の INVITE 要求の時刻。通常、このフィールドには、セッションでの最初の INVITE メッセージから生成されたデータが設定されます。INVITE メッセージがない場合は、関連する最初の SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日付と時刻が設定されます。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5fbc-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c5fbc-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-127">電話会議の URI。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5fbc-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-129">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c5fbc-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-130">電話会議の URI の種類。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-130">Type of conference URI.</span></span> <span data-ttu-id="c5fbc-131">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5fbc-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-133">識別子</span><span class="sxs-lookup"><span data-stu-id="c5fbc-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-p106">定期的な電話会議のインスタンスを区別する識別子。定期的な電話会議の各インスタンスは、ConferenceURI は同じですが、ConfInstance 値が異なります。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5fbc-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c5fbc-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-138">電話会議サーバーの URI。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5fbc-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c5fbc-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-141">電話会議サーバーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-141">Type of conferencing server URI.</span></span> <span data-ttu-id="c5fbc-142">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5fbc-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c5fbc-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-145">セッションに参加したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5fbc-146"><strong>Useruritoff</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-147">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c5fbc-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-148">セッションに参加したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="c5fbc-149">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5fbc-150"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c5fbc-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-152">セッションに参加したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="c5fbc-153">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5fbc-154"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-155">識別子</span><span class="sxs-lookup"><span data-stu-id="c5fbc-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-156">セッションに参加したユーザーの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5fbc-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-158">日付型</span><span class="sxs-lookup"><span data-stu-id="c5fbc-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-159">セッションの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5fbc-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-161">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c5fbc-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-162">電話会議サーバーのバージョン。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5fbc-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-164">int</span><span class="sxs-lookup"><span data-stu-id="c5fbc-164">int</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-165">電話会議サーバーの種類。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-165">Type of conference server.</span></span> <span data-ttu-id="c5fbc-166">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5fbc-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="c5fbc-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-169">電話会議サーバーのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5fbc-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-171">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c5fbc-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-172">セッションに参加したユーザーが使用するクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5fbc-173"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-174">int</span><span class="sxs-lookup"><span data-stu-id="c5fbc-174">int</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-175">セッションに参加したユーザーが使用するクライアント。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="c5fbc-176">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5fbc-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="c5fbc-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-179">セッションに参加したユーザーが使用するクライアントのカテゴリの名前。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5fbc-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c5fbc-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-182">セッションが開始されたユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5fbc-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-184">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c5fbc-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-185">代表してセッションを開始したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="c5fbc-186">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5fbc-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-188">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c5fbc-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-189">代表してセッションを開始したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="c5fbc-190">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5fbc-191"><strong>があります。</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c5fbc-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-193">セッションを委譲したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5fbc-194"><strong>ベンチャー Redbyuritん</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c5fbc-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-196">セッションを委譲したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="c5fbc-197">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5fbc-198"><strong>ベンチャー Redbyuritenant</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c5fbc-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-200">セッションを委譲したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="c5fbc-201">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5fbc-202"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-203">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="c5fbc-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-p116">SIP ダイアログ ID。形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="c5fbc-206">:d ialog; からタグを開始します。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5fbc-207"><strong>Edialogidtime を置換する</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-208">日付型</span><span class="sxs-lookup"><span data-stu-id="c5fbc-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-209">現在のセッションで置き換えられる前のダイアログを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="c5fbc-210">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5fbc-211"><strong>Edialogidseq を置換する</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-212">int</span><span class="sxs-lookup"><span data-stu-id="c5fbc-212">int</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-213">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-213">ID number to identify the session.</span></span> <span data-ttu-id="c5fbc-214">このセッションで置き換えられるセッションを一意に識別するために ReplaceDialogIdTime と併用されます。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="c5fbc-215">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5fbc-216"><strong>置換 Es/交換 Id</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-217">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="c5fbc-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-p119">セッションによって置き換えられる SIP ダイアログ ID。形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="c5fbc-220">dialog、from タグ、およびタグ</span><span class="sxs-lookup"><span data-stu-id="c5fbc-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5fbc-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-222">若干</span><span class="sxs-lookup"><span data-stu-id="c5fbc-222">bit</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-223">セッションが電話会議サーバーによって開始されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5fbc-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-225">若干</span><span class="sxs-lookup"><span data-stu-id="c5fbc-225">bit</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-226">セッションが電話会議サーバーによって終了されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5fbc-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-228">若干</span><span class="sxs-lookup"><span data-stu-id="c5fbc-228">bit</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-229">ユーザーが内部ネットワークからログオンしたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5fbc-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-231">日付型</span><span class="sxs-lookup"><span data-stu-id="c5fbc-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-p120">最初の INVITE メッセージに対する応答の時刻。通常は、セッションの最初の INVITE メッセージから生成されたデータが設定されます。INVITE メッセージがない場合は、関連する最初の SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5fbc-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-236">int</span><span class="sxs-lookup"><span data-stu-id="c5fbc-236">int</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-p121">セッションへの招待に対する SIP 応答コード。このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5fbc-240"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-241">int</span><span class="sxs-lookup"><span data-stu-id="c5fbc-241">int</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-242">セッションの SIP ヘッダーから取得された診断 ID。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5fbc-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-244">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c5fbc-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-245">セッションのコンテンツの種類。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5fbc-246"><strong>Fea-frontend-server-role</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-247">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c5fbc-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-248">セッションのデータをキャプチャしたフロントエンド サーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5fbc-249"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-250">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c5fbc-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-251">セッションのデータを取得したプールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5fbc-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-253">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c5fbc-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-254">セッションに参加したユーザーが使用した仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5fbc-255"><strong>ゲートウェイ</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-256">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c5fbc-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-257">セッションに参加したユーザーが使用したゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5fbc-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-259">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c5fbc-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-260">セッションに参加したユーザーが使用したエッジ サーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5fbc-261"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-262">smallint</span><span class="sxs-lookup"><span data-stu-id="c5fbc-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-p122">セッションに参加したユーザーの属性を示します。次の属性定義を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="c5fbc-265">0x01 - デスクトップ電話と統合</span><span class="sxs-lookup"><span data-stu-id="c5fbc-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5fbc-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="c5fbc-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fbc-267">smallint</span><span class="sxs-lookup"><span data-stu-id="c5fbc-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="c5fbc-p123">通話の属性を示します。次の属性定義を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c5fbc-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="c5fbc-270">0x01 - 再試行セッション0</span><span class="sxs-lookup"><span data-stu-id="c5fbc-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="c5fbc-271">x02 - 応答グループの代理を務めるエージェントによって行われた通話</span><span class="sxs-lookup"><span data-stu-id="c5fbc-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

