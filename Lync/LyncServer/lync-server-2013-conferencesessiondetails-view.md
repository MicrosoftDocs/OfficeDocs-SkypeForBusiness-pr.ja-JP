---
title: 'Lync Server 2013: ConferenceSessionDetails view'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceSessionDetails view
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49733660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0432606a49766f7ea6755f5f234343ac70ca6c0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="a497b-102">Lync Server 2013 での ConferenceSessionDetails の表示</span><span class="sxs-lookup"><span data-stu-id="a497b-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a497b-103">_**最終更新日:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="a497b-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="a497b-104">ConferenceSessionDetails ビューには、マルチパーティセッションに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="a497b-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="a497b-105">各レコードは1つの会議セッションを表します。これは、フォーカスのあるセッションまたは特定の会議サーバーのセッションのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="a497b-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="a497b-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a497b-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a497b-107">列</span><span class="sxs-lookup"><span data-stu-id="a497b-107">Column</span></span></th>
<th><span data-ttu-id="a497b-108">データ型</span><span class="sxs-lookup"><span data-stu-id="a497b-108">Data Type</span></span></th>
<th><span data-ttu-id="a497b-109">詳細</span><span class="sxs-lookup"><span data-stu-id="a497b-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a497b-110"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-111">datetime</span><span class="sxs-lookup"><span data-stu-id="a497b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="a497b-112">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="a497b-112">Time of session request.</span></span> <span data-ttu-id="a497b-113">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="a497b-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="a497b-114">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a497b-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a497b-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-116">int</span><span class="sxs-lookup"><span data-stu-id="a497b-116">int</span></span></p></td>
<td><p><span data-ttu-id="a497b-117">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="a497b-117">ID number to identify the session.</span></span> <span data-ttu-id="a497b-118">セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="a497b-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="a497b-119">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a497b-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a497b-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-121">datetime</span><span class="sxs-lookup"><span data-stu-id="a497b-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="a497b-122">最初の招待要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="a497b-122">Time of the first INVITE request.</span></span> <span data-ttu-id="a497b-123">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="a497b-123">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="a497b-124">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="a497b-124">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a497b-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a497b-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a497b-127">会議の URI。</span><span class="sxs-lookup"><span data-stu-id="a497b-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a497b-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a497b-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a497b-130">電話会議 URI の種類。</span><span class="sxs-lookup"><span data-stu-id="a497b-130">Type of conference URI.</span></span> <span data-ttu-id="a497b-131">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a497b-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a497b-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-133">長さ</span><span class="sxs-lookup"><span data-stu-id="a497b-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="a497b-134">定期的な会議のインスタンスを区別する識別子。</span><span class="sxs-lookup"><span data-stu-id="a497b-134">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="a497b-135">各定期的な会議インスタンスの ConferenceURI は同じですが、異なる ConfInstance 値があります。</span><span class="sxs-lookup"><span data-stu-id="a497b-135">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a497b-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a497b-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a497b-138">会議サーバーの URI。</span><span class="sxs-lookup"><span data-stu-id="a497b-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a497b-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a497b-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a497b-141">会議サーバーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="a497b-141">Type of conferencing server URI.</span></span> <span data-ttu-id="a497b-142">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a497b-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a497b-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a497b-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a497b-145">セッションに関連するユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="a497b-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a497b-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-147">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a497b-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a497b-148">セッションの一部だったユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="a497b-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="a497b-149">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a497b-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a497b-150"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a497b-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a497b-152">セッションの一部だったユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="a497b-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="a497b-153">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a497b-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a497b-154"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-155">長さ</span><span class="sxs-lookup"><span data-stu-id="a497b-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="a497b-156">セッションの一部だったユーザーの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="a497b-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a497b-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-158">datetime</span><span class="sxs-lookup"><span data-stu-id="a497b-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="a497b-159">セッションの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="a497b-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a497b-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-161">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a497b-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a497b-162">会議サーバーのバージョン。</span><span class="sxs-lookup"><span data-stu-id="a497b-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a497b-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-164">int</span><span class="sxs-lookup"><span data-stu-id="a497b-164">int</span></span></p></td>
<td><p><span data-ttu-id="a497b-165">会議サーバーの種類。</span><span class="sxs-lookup"><span data-stu-id="a497b-165">Type of conference server.</span></span> <span data-ttu-id="a497b-166">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a497b-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a497b-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="a497b-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="a497b-169">会議サーバーのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="a497b-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a497b-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-171">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a497b-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a497b-172">セッションに参加したユーザーによって使用されたクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="a497b-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a497b-173"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-174">int</span><span class="sxs-lookup"><span data-stu-id="a497b-174">int</span></span></p></td>
<td><p><span data-ttu-id="a497b-175">セッションに参加したユーザーによって使用されたクライアント。</span><span class="sxs-lookup"><span data-stu-id="a497b-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="a497b-176">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a497b-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a497b-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="a497b-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="a497b-179">セッションの一部だったユーザーによって使用されたクライアントのカテゴリの名前です。</span><span class="sxs-lookup"><span data-stu-id="a497b-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a497b-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a497b-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a497b-182">セッションが開始されたユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="a497b-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a497b-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-184">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a497b-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a497b-185">セッションが開始されたユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="a497b-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="a497b-186">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a497b-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a497b-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-188">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a497b-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a497b-189">セッションを開始したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="a497b-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="a497b-190">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a497b-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a497b-191"><strong>△この Uri</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a497b-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a497b-193">セッションを参照したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="a497b-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a497b-194"><strong>ベンチャー Redbyuritん</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-195">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a497b-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a497b-196">セッションを参照したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="a497b-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="a497b-197">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a497b-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a497b-198"><strong>、Uritbyuritenant</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-199">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a497b-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a497b-200">セッションを参照したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="a497b-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="a497b-201">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a497b-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a497b-202"><strong>この Id</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-203">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="a497b-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="a497b-204">SIP ダイアログ ID。</span><span class="sxs-lookup"><span data-stu-id="a497b-204">SIP dialog ID.</span></span> <span data-ttu-id="a497b-205">書式は</span><span class="sxs-lookup"><span data-stu-id="a497b-205">The format is</span></span></p>
<p><span data-ttu-id="a497b-206">:d ialog; from タグ; to タグ</span><span class="sxs-lookup"><span data-stu-id="a497b-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a497b-207"><strong>Edialogidtime の置き換え</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-208">datetime</span><span class="sxs-lookup"><span data-stu-id="a497b-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="a497b-209">現在のセッションによって置き換えられたダイアログを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="a497b-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="a497b-210">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a497b-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a497b-211"><strong>Edialogidseq の置き換え</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-212">int</span><span class="sxs-lookup"><span data-stu-id="a497b-212">int</span></span></p></td>
<td><p><span data-ttu-id="a497b-213">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="a497b-213">ID number to identify the session.</span></span> <span data-ttu-id="a497b-214">このセッションによって置き換えられるセッションを一意に識別するには、置換 Edialogidtime と組み合わせて使います。</span><span class="sxs-lookup"><span data-stu-id="a497b-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="a497b-215">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a497b-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a497b-216"><strong>置換の方法 Id</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-217">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="a497b-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="a497b-218">SIP ダイアログ ID によってセッションが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="a497b-218">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="a497b-219">の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a497b-219">The format of the is:</span></span></p>
<p><span data-ttu-id="a497b-220">ダイアログ; 開始タグからタグへ</span><span class="sxs-lookup"><span data-stu-id="a497b-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a497b-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-222">bit</span><span class="sxs-lookup"><span data-stu-id="a497b-222">bit</span></span></p></td>
<td><p><span data-ttu-id="a497b-223">セッションが会議サーバーによって開始されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a497b-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a497b-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-225">bit</span><span class="sxs-lookup"><span data-stu-id="a497b-225">bit</span></span></p></td>
<td><p><span data-ttu-id="a497b-226">会議サーバーによってセッションが終了したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a497b-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a497b-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-228">bit</span><span class="sxs-lookup"><span data-stu-id="a497b-228">bit</span></span></p></td>
<td><p><span data-ttu-id="a497b-229">ユーザーが内部ネットワークからログオンしているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a497b-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a497b-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-231">datetime</span><span class="sxs-lookup"><span data-stu-id="a497b-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="a497b-232">最初の招待メッセージに対する返信の時刻。</span><span class="sxs-lookup"><span data-stu-id="a497b-232">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="a497b-233">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="a497b-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="a497b-234">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="a497b-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a497b-235"><strong>返信</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-236">int</span><span class="sxs-lookup"><span data-stu-id="a497b-236">int</span></span></p></td>
<td><p><span data-ttu-id="a497b-237">セッション招待状への SIP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="a497b-237">SIP response code to the session invitation.</span></span> <span data-ttu-id="a497b-238">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="a497b-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="a497b-239">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="a497b-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a497b-240"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-241">int</span><span class="sxs-lookup"><span data-stu-id="a497b-241">int</span></span></p></td>
<td><p><span data-ttu-id="a497b-242">セッション SIP ヘッダーからキャプチャされた診断 ID。</span><span class="sxs-lookup"><span data-stu-id="a497b-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a497b-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-244">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a497b-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a497b-245">セッションのコンテンツタイプ。</span><span class="sxs-lookup"><span data-stu-id="a497b-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a497b-246"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-247">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a497b-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a497b-248">セッションのデータをキャプチャしたフロントエンドサーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="a497b-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a497b-249"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-250">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a497b-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a497b-251">セッションのデータをキャプチャしたプールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="a497b-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a497b-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-253">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a497b-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a497b-254">セッションに参加したユーザーによって使用される仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="a497b-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a497b-255"><strong>ゲートウェイ</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-256">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a497b-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a497b-257">セッションに参加したユーザーが使用したゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="a497b-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a497b-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-259">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a497b-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a497b-260">セッションに参加したユーザーによって使用されたエッジサーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="a497b-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a497b-261"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-262">smallint</span><span class="sxs-lookup"><span data-stu-id="a497b-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="a497b-263">セッションに参加したユーザーの属性を示します。</span><span class="sxs-lookup"><span data-stu-id="a497b-263">Indicates the attributes of the user who participated in the session.</span></span> <span data-ttu-id="a497b-264">次の属性定義を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a497b-264">The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="a497b-265">0x01-デスクトップ電話と統合</span><span class="sxs-lookup"><span data-stu-id="a497b-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a497b-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="a497b-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="a497b-267">smallint</span><span class="sxs-lookup"><span data-stu-id="a497b-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="a497b-268">呼び出しの属性を示します。</span><span class="sxs-lookup"><span data-stu-id="a497b-268">Indicates the call attributes.</span></span> <span data-ttu-id="a497b-269">次の属性定義を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a497b-269">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="a497b-270">0x01-再試行 Session0</span><span class="sxs-lookup"><span data-stu-id="a497b-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="a497b-271">x02-応答グループの代理としてエージェントによって発信された通話</span><span class="sxs-lookup"><span data-stu-id="a497b-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

