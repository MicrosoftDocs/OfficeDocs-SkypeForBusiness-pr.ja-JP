---
title: 'Lync Server 2013: ErrorReport ビュー'
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
ms.openlocfilehash: a1fe360726c94062391a4559f73a375d68b5f384
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="e5aa8-102">Lync Server 2013 の ErrorReport ビュー</span><span class="sxs-lookup"><span data-stu-id="e5aa8-102">ErrorReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5aa8-103">_**トピックの最終更新日:** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="e5aa8-103">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="e5aa8-104">ErrorReport ビューは、報告されたエラーに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-104">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="e5aa8-105">各レコードは、エラー発生の1つです。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-105">Each record is one error occurrence.</span></span> <span data-ttu-id="e5aa8-106">エラーは、フロントエンドサーバーで実行されている CDR エージェント、またはクライアントから送信されます。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="e5aa8-107">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5aa8-108">列</span><span class="sxs-lookup"><span data-stu-id="e5aa8-108">Column</span></span></th>
<th><span data-ttu-id="e5aa8-109">データ型</span><span class="sxs-lookup"><span data-stu-id="e5aa8-109">Data Type</span></span></th>
<th><span data-ttu-id="e5aa8-110">詳細</span><span class="sxs-lookup"><span data-stu-id="e5aa8-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5aa8-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-112">日付型</span><span class="sxs-lookup"><span data-stu-id="e5aa8-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-p102">エラーが発生した時刻。エラー を一意に識別するために ErrorReportSeq と併用されます。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5aa8-115"><strong>Errorreportseq、</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-116">int</span><span class="sxs-lookup"><span data-stu-id="e5aa8-116">int</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-p103">エラーを識別する ID 番号。エラーを一意に識別するために ErrorTime と併用されます。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5aa8-119"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-119"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-120">int</span><span class="sxs-lookup"><span data-stu-id="e5aa8-120">int</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-121">エラー レポートの診断 ID。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-121">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5aa8-122"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-122"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e5aa8-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-124">エラーを発生させたユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-124">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5aa8-125"><strong>Fromuritoff</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-125"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e5aa8-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-127">エラーを発生させたユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-127">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="e5aa8-128">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5aa8-129"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-129"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e5aa8-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-131">エラーを発生させたユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-131">Tenant of the user who originated the error.</span></span> <span data-ttu-id="e5aa8-132">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5aa8-133"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-133"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-134">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e5aa8-134">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-135">エラーレポートのターゲットであったユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-135">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5aa8-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e5aa8-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-138">エラーレポートの対象となるユーザーの URI の種類です。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-138">Type of URI of the user who target of the error report.</span></span> <span data-ttu-id="e5aa8-139">詳細については、「UriTypes Table」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-139">See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5aa8-140"><strong>すべての Ant</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-140"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e5aa8-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-142">エラーレポートを対象とするユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-142">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="e5aa8-143">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5aa8-144"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-144"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e5aa8-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-146">エラーレポートのターゲットであった会議の URI。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-146">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5aa8-147"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-147"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e5aa8-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-149">エラーレポートのターゲットであった会議の URI の種類。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-149">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="e5aa8-150">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5aa8-151"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-151"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-152">日付型</span><span class="sxs-lookup"><span data-stu-id="e5aa8-152">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-153">エラーレポートを生成したセッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-153">Time of session request that originated the error report.</span></span> <span data-ttu-id="e5aa8-154">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-154">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="e5aa8-155">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-155">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5aa8-156"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-156"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-157">int</span><span class="sxs-lookup"><span data-stu-id="e5aa8-157">int</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-158">エラーレポートを生成したセッション要求を識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-158">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="e5aa8-159">セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-159">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="e5aa8-160">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-160">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5aa8-161"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-161"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-162">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="e5aa8-162">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-163">エラーを発生させたセッションの SIP ダイアログ ID。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-163">SIP dialog ID of session that originated the error.</span></span> <span data-ttu-id="e5aa8-164">形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-164">The format is:</span></span></p>
<p><span data-ttu-id="e5aa8-165">dialog、from タグ、およびタグ</span><span class="sxs-lookup"><span data-stu-id="e5aa8-165">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="e5aa8-166">このデータは、次の構文を使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-166">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="e5aa8-167">cast (varbinary (varbinary (max) としての ExternalId) as varchar (max))</span><span class="sxs-lookup"><span data-stu-id="e5aa8-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5aa8-168"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-168"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-169">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e5aa8-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-170">エラーを発生させたユーザーが使用しているクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-170">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5aa8-171"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-171"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-172">int</span><span class="sxs-lookup"><span data-stu-id="e5aa8-172">int</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-173">エラーを発生させたユーザーが使用しているクライアント。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-173">Client used by the user who originated the error.</span></span> <span data-ttu-id="e5aa8-174">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-174">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5aa8-175"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-175"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-176">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e5aa8-176">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-177">エラーを発生させたユーザーが使用しているクライアントのカテゴリの名前。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-177">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5aa8-178"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-178"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-179">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e5aa8-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-180">エラーを発生させたサーバーの名前 (サーバー コンポーネントからレポートが送信された場合)。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-180">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5aa8-181"><strong>Application</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-181"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-182">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e5aa8-182">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-183">エラーを発生させたアプリケーションの名前 (サーバー コンポーネントからレポートが送信された場合)。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-183">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5aa8-184"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-184"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-185">int</span><span class="sxs-lookup"><span data-stu-id="e5aa8-185">int</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-186">エラーレポートを含む SIP メッセージのセッションに対する SIP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-186">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5aa8-187"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-187"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-188">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="e5aa8-188">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-189">失敗した要求の種類。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-189">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5aa8-190"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-190"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-191">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="e5aa8-191">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-192">失敗した要求のコンテンツの種類。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-192">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5aa8-193"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-193"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e5aa8-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-195">セッションの種類。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-195">Type of session.</span></span> <span data-ttu-id="e5aa8-196">詳細については、「 <a href="lync-server-2013-calltype-table.md">Lync Server 2013 の CallType テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-196">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5aa8-197"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-197"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-198">識別子</span><span class="sxs-lookup"><span data-stu-id="e5aa8-198">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-199">会議に関するさまざまなコンポーネントの参加時間情報に関係する一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-199">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5aa8-200"><strong>SetupTime タイム</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-200"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-201">int</span><span class="sxs-lookup"><span data-stu-id="e5aa8-201">int</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-202">特定のコンポーネントが会議に参加するのに必要な時間 (ミリ秒)。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-202">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5aa8-203"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-203"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-204">若干</span><span class="sxs-lookup"><span data-stu-id="e5aa8-204">bit</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-205">エラー報告がフロントエンドサーバーで実行されている CDR エージェントによってキャプチャされたか、クライアントによって送信されたかを示します。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-205">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5aa8-206"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-206"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-207">smallint</span><span class="sxs-lookup"><span data-stu-id="e5aa8-207">smallint</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-208">将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-208">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5aa8-209"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-209"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-210">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="e5aa8-210">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-211">エラーに関する追加情報。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-211">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5aa8-212"><strong>Fea-frontend-server-role</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-212"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-213">nvarchar</span><span class="sxs-lookup"><span data-stu-id="e5aa8-213">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-214">レポートを送信したフロントエンドサーバーの完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-214">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5aa8-215"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="e5aa8-215"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e5aa8-216">nvarchar</span><span class="sxs-lookup"><span data-stu-id="e5aa8-216">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="e5aa8-217">レポートを送信したフロントエンドサーバーが含まれているプールの完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="e5aa8-217">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

