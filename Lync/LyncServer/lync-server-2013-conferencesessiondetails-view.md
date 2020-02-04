---
title: 'Lync Server 2013: ConferenceSessionDetails view'
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
ms.openlocfilehash: 46356099c3eee20794a4198720597dc4395b563f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="63b8c-102">Lync Server 2013 での ConferenceSessionDetails の表示</span><span class="sxs-lookup"><span data-stu-id="63b8c-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63b8c-103">_**最終更新日:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="63b8c-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="63b8c-104">ConferenceSessionDetails ビューには、マルチパーティセッションに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="63b8c-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="63b8c-105">各レコードは1つの会議セッションを表します。これは、フォーカスのあるセッションまたは特定の会議サーバーのセッションのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="63b8c-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="63b8c-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="63b8c-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63b8c-107">列</span><span class="sxs-lookup"><span data-stu-id="63b8c-107">Column</span></span></th>
<th><span data-ttu-id="63b8c-108">データ型</span><span class="sxs-lookup"><span data-stu-id="63b8c-108">Data Type</span></span></th>
<th><span data-ttu-id="63b8c-109">詳細</span><span class="sxs-lookup"><span data-stu-id="63b8c-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63b8c-110"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-111">datetime</span><span class="sxs-lookup"><span data-stu-id="63b8c-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="63b8c-112">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="63b8c-112">Time of session request.</span></span> <span data-ttu-id="63b8c-113">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="63b8c-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="63b8c-114">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b8c-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b8c-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-116">int</span><span class="sxs-lookup"><span data-stu-id="63b8c-116">int</span></span></p></td>
<td><p><span data-ttu-id="63b8c-117">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="63b8c-117">ID number to identify the session.</span></span> <span data-ttu-id="63b8c-118">セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="63b8c-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="63b8c-119">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b8c-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b8c-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-121">datetime</span><span class="sxs-lookup"><span data-stu-id="63b8c-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="63b8c-122">最初の招待要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="63b8c-122">Time of the first INVITE request.</span></span> <span data-ttu-id="63b8c-123">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="63b8c-123">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="63b8c-124">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="63b8c-124">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b8c-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="63b8c-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="63b8c-127">会議の URI。</span><span class="sxs-lookup"><span data-stu-id="63b8c-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b8c-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63b8c-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63b8c-130">電話会議 URI の種類。</span><span class="sxs-lookup"><span data-stu-id="63b8c-130">Type of conference URI.</span></span> <span data-ttu-id="63b8c-131">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b8c-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b8c-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-133">長さ</span><span class="sxs-lookup"><span data-stu-id="63b8c-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="63b8c-134">定期的な会議のインスタンスを区別する識別子。</span><span class="sxs-lookup"><span data-stu-id="63b8c-134">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="63b8c-135">各定期的な会議インスタンスの ConferenceURI は同じですが、異なる ConfInstance 値があります。</span><span class="sxs-lookup"><span data-stu-id="63b8c-135">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b8c-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="63b8c-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="63b8c-138">会議サーバーの URI。</span><span class="sxs-lookup"><span data-stu-id="63b8c-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b8c-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63b8c-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63b8c-141">会議サーバーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="63b8c-141">Type of conferencing server URI.</span></span> <span data-ttu-id="63b8c-142">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b8c-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b8c-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="63b8c-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="63b8c-145">セッションに関連するユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="63b8c-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b8c-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-147">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63b8c-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63b8c-148">セッションの一部だったユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="63b8c-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="63b8c-149">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b8c-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b8c-150"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63b8c-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63b8c-152">セッションの一部だったユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="63b8c-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="63b8c-153">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b8c-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b8c-154"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-155">長さ</span><span class="sxs-lookup"><span data-stu-id="63b8c-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="63b8c-156">セッションの一部だったユーザーの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="63b8c-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b8c-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-158">datetime</span><span class="sxs-lookup"><span data-stu-id="63b8c-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="63b8c-159">セッションの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="63b8c-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b8c-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-161">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63b8c-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63b8c-162">会議サーバーのバージョン。</span><span class="sxs-lookup"><span data-stu-id="63b8c-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b8c-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-164">int</span><span class="sxs-lookup"><span data-stu-id="63b8c-164">int</span></span></p></td>
<td><p><span data-ttu-id="63b8c-165">会議サーバーの種類。</span><span class="sxs-lookup"><span data-stu-id="63b8c-165">Type of conference server.</span></span> <span data-ttu-id="63b8c-166">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b8c-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b8c-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="63b8c-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="63b8c-169">会議サーバーのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="63b8c-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b8c-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-171">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63b8c-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63b8c-172">セッションに参加したユーザーによって使用されたクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="63b8c-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b8c-173"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-174">int</span><span class="sxs-lookup"><span data-stu-id="63b8c-174">int</span></span></p></td>
<td><p><span data-ttu-id="63b8c-175">セッションに参加したユーザーによって使用されたクライアント。</span><span class="sxs-lookup"><span data-stu-id="63b8c-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="63b8c-176">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b8c-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b8c-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="63b8c-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="63b8c-179">セッションの一部だったユーザーによって使用されたクライアントのカテゴリの名前です。</span><span class="sxs-lookup"><span data-stu-id="63b8c-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b8c-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="63b8c-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="63b8c-182">セッションが開始されたユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="63b8c-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b8c-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-184">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63b8c-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63b8c-185">セッションが開始されたユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="63b8c-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="63b8c-186">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b8c-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b8c-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-188">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63b8c-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63b8c-189">セッションを開始したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="63b8c-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="63b8c-190">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b8c-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b8c-191"><strong>△この Uri</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="63b8c-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="63b8c-193">セッションを参照したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="63b8c-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b8c-194"><strong>ベンチャー Redbyuritん</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-195">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63b8c-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63b8c-196">セッションを参照したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="63b8c-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="63b8c-197">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b8c-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b8c-198"><strong>、Uritbyuritenant</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-199">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63b8c-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63b8c-200">セッションを参照したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="63b8c-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="63b8c-201">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b8c-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b8c-202"><strong>この Id</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-203">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="63b8c-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="63b8c-204">SIP ダイアログ ID。</span><span class="sxs-lookup"><span data-stu-id="63b8c-204">SIP dialog ID.</span></span> <span data-ttu-id="63b8c-205">書式は</span><span class="sxs-lookup"><span data-stu-id="63b8c-205">The format is</span></span></p>
<p><span data-ttu-id="63b8c-206">:d ialog; from タグ; to タグ</span><span class="sxs-lookup"><span data-stu-id="63b8c-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b8c-207"><strong>Edialogidtime の置き換え</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-208">datetime</span><span class="sxs-lookup"><span data-stu-id="63b8c-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="63b8c-209">現在のセッションによって置き換えられたダイアログを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="63b8c-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="63b8c-210">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b8c-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b8c-211"><strong>Edialogidseq の置き換え</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-212">int</span><span class="sxs-lookup"><span data-stu-id="63b8c-212">int</span></span></p></td>
<td><p><span data-ttu-id="63b8c-213">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="63b8c-213">ID number to identify the session.</span></span> <span data-ttu-id="63b8c-214">このセッションによって置き換えられるセッションを一意に識別するには、置換 Edialogidtime と組み合わせて使います。</span><span class="sxs-lookup"><span data-stu-id="63b8c-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="63b8c-215">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b8c-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b8c-216"><strong>置換の方法 Id</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-217">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="63b8c-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="63b8c-218">SIP ダイアログ ID によってセッションが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="63b8c-218">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="63b8c-219">の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="63b8c-219">The format of the is:</span></span></p>
<p><span data-ttu-id="63b8c-220">ダイアログ; 開始タグからタグへ</span><span class="sxs-lookup"><span data-stu-id="63b8c-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b8c-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-222">bit</span><span class="sxs-lookup"><span data-stu-id="63b8c-222">bit</span></span></p></td>
<td><p><span data-ttu-id="63b8c-223">セッションが会議サーバーによって開始されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="63b8c-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b8c-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-225">bit</span><span class="sxs-lookup"><span data-stu-id="63b8c-225">bit</span></span></p></td>
<td><p><span data-ttu-id="63b8c-226">会議サーバーによってセッションが終了したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="63b8c-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b8c-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-228">bit</span><span class="sxs-lookup"><span data-stu-id="63b8c-228">bit</span></span></p></td>
<td><p><span data-ttu-id="63b8c-229">ユーザーが内部ネットワークからログオンしているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="63b8c-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b8c-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-231">datetime</span><span class="sxs-lookup"><span data-stu-id="63b8c-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="63b8c-232">最初の招待メッセージに対する返信の時刻。</span><span class="sxs-lookup"><span data-stu-id="63b8c-232">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="63b8c-233">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="63b8c-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="63b8c-234">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="63b8c-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b8c-235"><strong>返信</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-236">int</span><span class="sxs-lookup"><span data-stu-id="63b8c-236">int</span></span></p></td>
<td><p><span data-ttu-id="63b8c-237">セッション招待状への SIP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="63b8c-237">SIP response code to the session invitation.</span></span> <span data-ttu-id="63b8c-238">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="63b8c-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="63b8c-239">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="63b8c-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b8c-240"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-241">int</span><span class="sxs-lookup"><span data-stu-id="63b8c-241">int</span></span></p></td>
<td><p><span data-ttu-id="63b8c-242">セッション SIP ヘッダーからキャプチャされた診断 ID。</span><span class="sxs-lookup"><span data-stu-id="63b8c-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b8c-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-244">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63b8c-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63b8c-245">セッションのコンテンツタイプ。</span><span class="sxs-lookup"><span data-stu-id="63b8c-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b8c-246"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-247">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63b8c-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63b8c-248">セッションのデータをキャプチャしたフロントエンドサーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="63b8c-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b8c-249"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-250">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63b8c-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63b8c-251">セッションのデータをキャプチャしたプールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="63b8c-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b8c-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-253">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63b8c-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63b8c-254">セッションに参加したユーザーによって使用される仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="63b8c-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b8c-255"><strong>ゲートウェイ</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-256">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63b8c-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63b8c-257">セッションに参加したユーザーが使用したゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="63b8c-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b8c-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-259">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63b8c-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63b8c-260">セッションに参加したユーザーによって使用されたエッジサーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="63b8c-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b8c-261"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-262">smallint</span><span class="sxs-lookup"><span data-stu-id="63b8c-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="63b8c-263">セッションに参加したユーザーの属性を示します。</span><span class="sxs-lookup"><span data-stu-id="63b8c-263">Indicates the attributes of the user who participated in the session.</span></span> <span data-ttu-id="63b8c-264">次の属性定義を使用できます。</span><span class="sxs-lookup"><span data-stu-id="63b8c-264">The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="63b8c-265">0x01-デスクトップ電話と統合</span><span class="sxs-lookup"><span data-stu-id="63b8c-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b8c-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="63b8c-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="63b8c-267">smallint</span><span class="sxs-lookup"><span data-stu-id="63b8c-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="63b8c-268">呼び出しの属性を示します。</span><span class="sxs-lookup"><span data-stu-id="63b8c-268">Indicates the call attributes.</span></span> <span data-ttu-id="63b8c-269">次の属性定義を使用できます。</span><span class="sxs-lookup"><span data-stu-id="63b8c-269">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="63b8c-270">0x01-再試行 Session0</span><span class="sxs-lookup"><span data-stu-id="63b8c-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="63b8c-271">x02-応答グループの代理としてエージェントによって発信された通話</span><span class="sxs-lookup"><span data-stu-id="63b8c-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

