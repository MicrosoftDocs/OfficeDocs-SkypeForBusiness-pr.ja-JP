---
title: 'Lync Server 2013: ErrorReport ビュー'
description: 'Lync Server 2013: ErrorReport ビュー。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50fb0a362c71d8dfb5873157e7b1ed3d3eb680ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572043"
---
# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="9260c-103">Lync Server 2013 の ErrorReport ビュー</span><span class="sxs-lookup"><span data-stu-id="9260c-103">ErrorReport view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9260c-104">_**トピックの最終更新日:** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="9260c-104">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="9260c-105">ErrorReport ビューは、報告されたエラーに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="9260c-105">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="9260c-106">各レコードは、エラー発生の1つです。</span><span class="sxs-lookup"><span data-stu-id="9260c-106">Each record is one error occurrence.</span></span> <span data-ttu-id="9260c-107">エラーは、フロントエンドサーバーで実行されている CDR エージェント、またはクライアントから送信されます。</span><span class="sxs-lookup"><span data-stu-id="9260c-107">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="9260c-108">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="9260c-108">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9260c-109">Column</span><span class="sxs-lookup"><span data-stu-id="9260c-109">Column</span></span></th>
<th><span data-ttu-id="9260c-110">データ型</span><span class="sxs-lookup"><span data-stu-id="9260c-110">Data Type</span></span></th>
<th><span data-ttu-id="9260c-111">詳細</span><span class="sxs-lookup"><span data-stu-id="9260c-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9260c-112"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-113">日付型</span><span class="sxs-lookup"><span data-stu-id="9260c-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="9260c-p102">エラーが発生した時刻。エラー を一意に識別するために ErrorReportSeq と併用されます。</span><span class="sxs-lookup"><span data-stu-id="9260c-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9260c-116"><strong>Errorreportseq、</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-117">int</span><span class="sxs-lookup"><span data-stu-id="9260c-117">int</span></span></p></td>
<td><p><span data-ttu-id="9260c-p103">エラーを識別する ID 番号。エラーを一意に識別するために ErrorTime と併用されます。</span><span class="sxs-lookup"><span data-stu-id="9260c-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9260c-120"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-120"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-121">int</span><span class="sxs-lookup"><span data-stu-id="9260c-121">int</span></span></p></td>
<td><p><span data-ttu-id="9260c-122">エラー レポートの診断 ID。</span><span class="sxs-lookup"><span data-stu-id="9260c-122">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9260c-123"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-123"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-124">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9260c-124">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9260c-125">エラーを発生させたユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="9260c-125">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9260c-126"><strong>Fromuritoff</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-126"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9260c-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9260c-128">エラーを発生させたユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="9260c-128">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="9260c-129">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9260c-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9260c-130"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-130"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9260c-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9260c-132">エラーを発生させたユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="9260c-132">Tenant of the user who originated the error.</span></span> <span data-ttu-id="9260c-133">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9260c-133">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9260c-134"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-134"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-135">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9260c-135">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9260c-136">エラーレポートのターゲットであったユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="9260c-136">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9260c-137"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-137"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-138">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9260c-138">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9260c-139">エラーレポートの対象となるユーザーの URI の種類です。</span><span class="sxs-lookup"><span data-stu-id="9260c-139">Type of URI of the user who target of the error report.</span></span> <span data-ttu-id="9260c-140">詳細については、「UriTypes Table」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9260c-140">See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9260c-141"><strong>すべての Ant</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-141"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9260c-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9260c-143">エラーレポートを対象とするユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="9260c-143">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="9260c-144">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9260c-144">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9260c-145"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-145"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-146">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9260c-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9260c-147">エラーレポートのターゲットであった会議の URI。</span><span class="sxs-lookup"><span data-stu-id="9260c-147">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9260c-148"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-148"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-149">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9260c-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9260c-150">エラーレポートのターゲットであった会議の URI の種類。</span><span class="sxs-lookup"><span data-stu-id="9260c-150">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="9260c-151">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9260c-151">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9260c-152"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-152"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-153">日付型</span><span class="sxs-lookup"><span data-stu-id="9260c-153">datetime</span></span></p></td>
<td><p><span data-ttu-id="9260c-154">エラーレポートを生成したセッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="9260c-154">Time of session request that originated the error report.</span></span> <span data-ttu-id="9260c-155">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="9260c-155">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="9260c-156">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9260c-156">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9260c-157"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-157"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-158">int</span><span class="sxs-lookup"><span data-stu-id="9260c-158">int</span></span></p></td>
<td><p><span data-ttu-id="9260c-159">エラーレポートを生成したセッション要求を識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="9260c-159">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="9260c-160">セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="9260c-160">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="9260c-161">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9260c-161">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9260c-162"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-162"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-163">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="9260c-163">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="9260c-164">エラーを発生させたセッションの SIP ダイアログ ID。</span><span class="sxs-lookup"><span data-stu-id="9260c-164">SIP dialog ID of session that originated the error.</span></span> <span data-ttu-id="9260c-165">形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9260c-165">The format is:</span></span></p>
<p><span data-ttu-id="9260c-166">dialog、from タグ、およびタグ</span><span class="sxs-lookup"><span data-stu-id="9260c-166">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="9260c-167">このデータは、次の構文を使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="9260c-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="9260c-168">cast (varbinary (varbinary (max) としての ExternalId) as varchar (max))</span><span class="sxs-lookup"><span data-stu-id="9260c-168">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9260c-169"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-169"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-170">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9260c-170">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9260c-171">エラーを発生させたユーザーが使用しているクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="9260c-171">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9260c-172"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-172"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-173">int</span><span class="sxs-lookup"><span data-stu-id="9260c-173">int</span></span></p></td>
<td><p><span data-ttu-id="9260c-174">エラーを発生させたユーザーが使用しているクライアント。</span><span class="sxs-lookup"><span data-stu-id="9260c-174">Client used by the user who originated the error.</span></span> <span data-ttu-id="9260c-175">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9260c-175">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9260c-176"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-176"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-177">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="9260c-177">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="9260c-178">エラーを発生させたユーザーが使用しているクライアントのカテゴリの名前。</span><span class="sxs-lookup"><span data-stu-id="9260c-178">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9260c-179"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-179"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-180">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9260c-180">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9260c-181">エラーを発生させたサーバーの名前 (サーバー コンポーネントからレポートが送信された場合)。</span><span class="sxs-lookup"><span data-stu-id="9260c-181">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9260c-182"><strong>Application</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-182"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-183">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9260c-183">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9260c-184">エラーを発生させたアプリケーションの名前 (サーバー コンポーネントからレポートが送信された場合)。</span><span class="sxs-lookup"><span data-stu-id="9260c-184">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9260c-185"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-185"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-186">int</span><span class="sxs-lookup"><span data-stu-id="9260c-186">int</span></span></p></td>
<td><p><span data-ttu-id="9260c-187">エラーレポートを含む SIP メッセージのセッションに対する SIP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="9260c-187">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9260c-188"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-188"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-189">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="9260c-189">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="9260c-190">失敗した要求の種類。</span><span class="sxs-lookup"><span data-stu-id="9260c-190">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9260c-191"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-191"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-192">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="9260c-192">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="9260c-193">失敗した要求のコンテンツの種類。</span><span class="sxs-lookup"><span data-stu-id="9260c-193">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9260c-194"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-194"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9260c-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9260c-196">セッションの種類。</span><span class="sxs-lookup"><span data-stu-id="9260c-196">Type of session.</span></span> <span data-ttu-id="9260c-197">詳細については、「 <a href="lync-server-2013-calltype-table.md">Lync Server 2013 の CallType テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9260c-197">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9260c-198"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-198"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-199">識別子</span><span class="sxs-lookup"><span data-stu-id="9260c-199">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="9260c-200">会議に関するさまざまなコンポーネントの参加時間情報に関係する一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="9260c-200">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9260c-201"><strong>SetupTime タイム</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-201"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-202">int</span><span class="sxs-lookup"><span data-stu-id="9260c-202">int</span></span></p></td>
<td><p><span data-ttu-id="9260c-203">特定のコンポーネントが会議に参加するのに必要な時間 (ミリ秒)。</span><span class="sxs-lookup"><span data-stu-id="9260c-203">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9260c-204"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-204"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-205">若干</span><span class="sxs-lookup"><span data-stu-id="9260c-205">bit</span></span></p></td>
<td><p><span data-ttu-id="9260c-206">エラー報告がフロントエンドサーバーで実行されている CDR エージェントによってキャプチャされたか、クライアントによって送信されたかを示します。</span><span class="sxs-lookup"><span data-stu-id="9260c-206">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9260c-207"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-207"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-208">smallint</span><span class="sxs-lookup"><span data-stu-id="9260c-208">smallint</span></span></p></td>
<td><p><span data-ttu-id="9260c-209">将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="9260c-209">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9260c-210"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-210"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-211">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="9260c-211">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="9260c-212">エラーに関する追加情報。</span><span class="sxs-lookup"><span data-stu-id="9260c-212">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9260c-213"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-213"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-214">nvarchar</span><span class="sxs-lookup"><span data-stu-id="9260c-214">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="9260c-215">レポートを送信したフロントエンドサーバーの完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="9260c-215">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9260c-216"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="9260c-216"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="9260c-217">nvarchar</span><span class="sxs-lookup"><span data-stu-id="9260c-217">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="9260c-218">レポートを送信したフロントエンドサーバーが含まれているプールの完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="9260c-218">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

