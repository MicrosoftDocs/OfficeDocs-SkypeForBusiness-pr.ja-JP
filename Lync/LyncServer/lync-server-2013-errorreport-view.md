---
title: 'Lync Server 2013: ErrorReport view'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b50a2615fe83ed481d9642ac6895120f20b9fd0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="1fb89-102">Lync Server 2013 での ErrorReport の表示</span><span class="sxs-lookup"><span data-stu-id="1fb89-102">ErrorReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fb89-103">_**最終更新日:** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="1fb89-103">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="1fb89-104">ErrorReport ビューには、報告されたエラーに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="1fb89-104">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="1fb89-105">各レコードはエラー発生の1つです。</span><span class="sxs-lookup"><span data-stu-id="1fb89-105">Each record is one error occurrence.</span></span> <span data-ttu-id="1fb89-106">このエラーは、フロントエンドサーバーで実行されている CDR エージェントまたはクライアントから送信された cd-r エージェントによってキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="1fb89-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="1fb89-107">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="1fb89-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1fb89-108">列</span><span class="sxs-lookup"><span data-stu-id="1fb89-108">Column</span></span></th>
<th><span data-ttu-id="1fb89-109">データ型</span><span class="sxs-lookup"><span data-stu-id="1fb89-109">Data Type</span></span></th>
<th><span data-ttu-id="1fb89-110">詳細</span><span class="sxs-lookup"><span data-stu-id="1fb89-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1fb89-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-112">datetime</span><span class="sxs-lookup"><span data-stu-id="1fb89-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="1fb89-113">エラーが発生した時刻。</span><span class="sxs-lookup"><span data-stu-id="1fb89-113">Time of error occurred.</span></span> <span data-ttu-id="1fb89-114">エラーを一意に識別するには、ErrorReportSeq と組み合わせて使います。</span><span class="sxs-lookup"><span data-stu-id="1fb89-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb89-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-116">int</span><span class="sxs-lookup"><span data-stu-id="1fb89-116">int</span></span></p></td>
<td><p><span data-ttu-id="1fb89-117">エラーを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="1fb89-117">ID number to identify the error.</span></span> <span data-ttu-id="1fb89-118">エラーを一意に識別するための ErrorTime と共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1fb89-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fb89-119"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-119"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-120">int</span><span class="sxs-lookup"><span data-stu-id="1fb89-120">int</span></span></p></td>
<td><p><span data-ttu-id="1fb89-121">エラーレポートの診断 ID。</span><span class="sxs-lookup"><span data-stu-id="1fb89-121">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb89-122"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-122"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1fb89-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1fb89-124">エラーを発生させたユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="1fb89-124">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fb89-125"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-125"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1fb89-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1fb89-127">エラーを発生させたユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="1fb89-127">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="1fb89-128">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fb89-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb89-129"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-129"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1fb89-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1fb89-131">エラーを発生させたユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="1fb89-131">Tenant of the user who originated the error.</span></span> <span data-ttu-id="1fb89-132">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fb89-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fb89-133"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-133"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-134">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1fb89-134">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1fb89-135">エラーレポートのターゲットであるユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="1fb89-135">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb89-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1fb89-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1fb89-138">エラーレポートの対象となるユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="1fb89-138">Type of URI of the user who target of the error report.</span></span> <span data-ttu-id="1fb89-139">詳細については、UriTypes の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fb89-139">See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fb89-140"><strong>すべての Ant</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-140"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-141">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1fb89-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1fb89-142">エラーレポートの対象ユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="1fb89-142">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="1fb89-143">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fb89-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb89-144"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-144"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1fb89-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1fb89-146">エラーレポートのターゲットとなった会議の URI。</span><span class="sxs-lookup"><span data-stu-id="1fb89-146">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fb89-147"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-147"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1fb89-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1fb89-149">エラーレポートのターゲットとなった会議の URI の種類。</span><span class="sxs-lookup"><span data-stu-id="1fb89-149">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="1fb89-150">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fb89-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb89-151"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-151"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-152">datetime</span><span class="sxs-lookup"><span data-stu-id="1fb89-152">datetime</span></span></p></td>
<td><p><span data-ttu-id="1fb89-153">エラーレポートを生成したセッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="1fb89-153">Time of session request that originated the error report.</span></span> <span data-ttu-id="1fb89-154">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="1fb89-154">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="1fb89-155">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fb89-155">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fb89-156"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-156"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-157">int</span><span class="sxs-lookup"><span data-stu-id="1fb89-157">int</span></span></p></td>
<td><p><span data-ttu-id="1fb89-158">エラーレポートを生成したセッション要求を識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="1fb89-158">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="1fb89-159">セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="1fb89-159">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="1fb89-160">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fb89-160">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb89-161"><strong>この Id</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-161"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-162">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="1fb89-162">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="1fb89-163">エラーを発生させたセッションの SIP ダイアログ ID。</span><span class="sxs-lookup"><span data-stu-id="1fb89-163">SIP dialog ID of session that originated the error.</span></span> <span data-ttu-id="1fb89-164">形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1fb89-164">The format is:</span></span></p>
<p><span data-ttu-id="1fb89-165">ダイアログ; 開始タグからタグへ</span><span class="sxs-lookup"><span data-stu-id="1fb89-165">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="1fb89-166">このデータは、次の構文を使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="1fb89-166">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="1fb89-167">キャスト (cast (ExternalId as varbinary (max)) (varchar (max)))</span><span class="sxs-lookup"><span data-stu-id="1fb89-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fb89-168"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-168"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-169">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1fb89-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1fb89-170">エラーの発生元のユーザーによって使用されたクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="1fb89-170">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb89-171"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-171"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-172">int</span><span class="sxs-lookup"><span data-stu-id="1fb89-172">int</span></span></p></td>
<td><p><span data-ttu-id="1fb89-173">エラーの発生元のユーザーによって使用されたクライアント。</span><span class="sxs-lookup"><span data-stu-id="1fb89-173">Client used by the user who originated the error.</span></span> <span data-ttu-id="1fb89-174">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fb89-174">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fb89-175"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-175"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-176">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="1fb89-176">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="1fb89-177">エラーの発生元のユーザーによって使用されたクライアントのカテゴリの名前です。</span><span class="sxs-lookup"><span data-stu-id="1fb89-177">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb89-178"><strong>ソース</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-178"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-179">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1fb89-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1fb89-180">エラーが発生したサーバーの名前 (サーバーコンポーネントからレポートが送信された場合)。</span><span class="sxs-lookup"><span data-stu-id="1fb89-180">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fb89-181"><strong>Application</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-181"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-182">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1fb89-182">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1fb89-183">エラーの発生元のアプリケーションの名前 (サーバーコンポーネントからレポートが送信された場合)。</span><span class="sxs-lookup"><span data-stu-id="1fb89-183">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb89-184"><strong>返信</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-184"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-185">int</span><span class="sxs-lookup"><span data-stu-id="1fb89-185">int</span></span></p></td>
<td><p><span data-ttu-id="1fb89-186">エラーレポートが含まれる SIP メッセージのセッションへの SIP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="1fb89-186">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fb89-187"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-187"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-188">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="1fb89-188">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="1fb89-189">失敗した要求の種類。</span><span class="sxs-lookup"><span data-stu-id="1fb89-189">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb89-190"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-190"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-191">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="1fb89-191">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="1fb89-192">失敗した要求のコンテンツタイプ。</span><span class="sxs-lookup"><span data-stu-id="1fb89-192">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fb89-193"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-193"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1fb89-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1fb89-195">セッションの種類。</span><span class="sxs-lookup"><span data-stu-id="1fb89-195">Type of session.</span></span> <span data-ttu-id="1fb89-196">詳細については、「 <a href="lync-server-2013-calltype-table.md">Lync Server 2013 の CallType テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fb89-196">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb89-197"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-197"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-198">長さ</span><span class="sxs-lookup"><span data-stu-id="1fb89-198">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="1fb89-199">電話会議に参加しているさまざまなコンポーネントについての、固有の識別子による結合時間情報の関連付け。</span><span class="sxs-lookup"><span data-stu-id="1fb89-199">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fb89-200"><strong>SetupTime 時間</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-200"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-201">int</span><span class="sxs-lookup"><span data-stu-id="1fb89-201">int</span></span></p></td>
<td><p><span data-ttu-id="1fb89-202">特定のコンポーネントが会議に参加するために必要な時間 (ミリ秒単位) です。</span><span class="sxs-lookup"><span data-stu-id="1fb89-202">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb89-203"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-203"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-204">bit</span><span class="sxs-lookup"><span data-stu-id="1fb89-204">bit</span></span></p></td>
<td><p><span data-ttu-id="1fb89-205">エラーレポートが、フロントエンドサーバーで実行されている CDR エージェントまたはクライアントによってキャプチャされたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="1fb89-205">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fb89-206"><strong>フラッグ</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-206"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-207">smallint</span><span class="sxs-lookup"><span data-stu-id="1fb89-207">smallint</span></span></p></td>
<td><p><span data-ttu-id="1fb89-208">今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="1fb89-208">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb89-209"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-209"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-210">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="1fb89-210">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="1fb89-211">エラーに関する追加情報。</span><span class="sxs-lookup"><span data-stu-id="1fb89-211">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fb89-212"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-212"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-213">nvarchar</span><span class="sxs-lookup"><span data-stu-id="1fb89-213">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="1fb89-214">レポートを提出したフロントエンドサーバーの完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="1fb89-214">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb89-215"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="1fb89-215"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb89-216">nvarchar</span><span class="sxs-lookup"><span data-stu-id="1fb89-216">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="1fb89-217">レポートを提出したフロントエンドサーバーを含むプールの完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="1fb89-217">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

