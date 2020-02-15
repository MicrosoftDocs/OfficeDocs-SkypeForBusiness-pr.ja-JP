---
title: 'Lync Server 2013: ErrorReport テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f9377b70923c1dc2c7213e9ac72486daffcda99
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="a2e77-102">Lync Server 2013 の ErrorReport テーブル</span><span class="sxs-lookup"><span data-stu-id="a2e77-102">ErrorReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2e77-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a2e77-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a2e77-104">ErrorReport テーブルには、発生したエラーに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="a2e77-104">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="a2e77-105">各レコードは、エラー発生の1つです。</span><span class="sxs-lookup"><span data-stu-id="a2e77-105">Each record is one error occurrence.</span></span> <span data-ttu-id="a2e77-106">エラーは、フロントエンドサーバーで実行されている CDR エージェント、またはクライアントから送信されます。</span><span class="sxs-lookup"><span data-stu-id="a2e77-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2e77-107">列</span><span class="sxs-lookup"><span data-stu-id="a2e77-107">Column</span></span></th>
<th><span data-ttu-id="a2e77-108">データ型</span><span class="sxs-lookup"><span data-stu-id="a2e77-108">Data Type</span></span></th>
<th><span data-ttu-id="a2e77-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="a2e77-109">Key/Index</span></span></th>
<th><span data-ttu-id="a2e77-110">詳細</span><span class="sxs-lookup"><span data-stu-id="a2e77-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2e77-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="a2e77-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a2e77-112">日付型</span><span class="sxs-lookup"><span data-stu-id="a2e77-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="a2e77-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a2e77-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="a2e77-114">エラーが発生した日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="a2e77-114">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2e77-115"><strong>Errorreportseq、</strong></span><span class="sxs-lookup"><span data-stu-id="a2e77-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a2e77-116">int</span><span class="sxs-lookup"><span data-stu-id="a2e77-116">int</span></span></p></td>
<td><p><span data-ttu-id="a2e77-117">Primary</span><span class="sxs-lookup"><span data-stu-id="a2e77-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="a2e77-118">エラーレポートを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="a2e77-118">ID number to identify the error report.</span></span> <span data-ttu-id="a2e77-119">エラーレポートを一意に識別するために<strong>Errortime</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="a2e77-119">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2e77-120"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="a2e77-120"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2e77-121">int</span><span class="sxs-lookup"><span data-stu-id="a2e77-121">int</span></span></p></td>
<td><p><span data-ttu-id="a2e77-122">外部</span><span class="sxs-lookup"><span data-stu-id="a2e77-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a2e77-123">エラーの種類の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="a2e77-123">Unique ID of the error type.</span></span> <span data-ttu-id="a2e77-124">詳細については、「 <a href="lync-server-2013-errordef-table.md">Lync Server 2013 の Errordef table</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2e77-124">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2e77-125"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="a2e77-125"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2e77-126">int</span><span class="sxs-lookup"><span data-stu-id="a2e77-126">int</span></span></p></td>
<td><p><span data-ttu-id="a2e77-127">外部</span><span class="sxs-lookup"><span data-stu-id="a2e77-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a2e77-128">エラーの原因となった要求を発信したユーザー。</span><span class="sxs-lookup"><span data-stu-id="a2e77-128">User who originated the request that caused the error.</span></span> <span data-ttu-id="a2e77-129">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2e77-129">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2e77-130"><strong>ToUserId</strong></span><span class="sxs-lookup"><span data-stu-id="a2e77-130"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2e77-131">int</span><span class="sxs-lookup"><span data-stu-id="a2e77-131">int</span></span></p></td>
<td><p><span data-ttu-id="a2e77-132">外部</span><span class="sxs-lookup"><span data-stu-id="a2e77-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a2e77-133">エラーの原因となった要求の送信先ユーザー。</span><span class="sxs-lookup"><span data-stu-id="a2e77-133">Destination user for the request that caused the error.</span></span> <span data-ttu-id="a2e77-134">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2e77-134">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2e77-135"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="a2e77-135"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2e77-136">int</span><span class="sxs-lookup"><span data-stu-id="a2e77-136">int</span></span></p></td>
<td><p><span data-ttu-id="a2e77-137">外部</span><span class="sxs-lookup"><span data-stu-id="a2e77-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a2e77-138">エラーに関連する会議 URI。</span><span class="sxs-lookup"><span data-stu-id="a2e77-138">Conference URI related to the error.</span></span> <span data-ttu-id="a2e77-139">詳細については、「 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2e77-139">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="a2e77-140">通常、ConferenceUriId が null でない場合、FromUserId または ToUserId のいずれかが null になります。</span><span class="sxs-lookup"><span data-stu-id="a2e77-140">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2e77-141"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a2e77-141"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a2e77-142">日付型</span><span class="sxs-lookup"><span data-stu-id="a2e77-142">datetime</span></span></p></td>
<td><p><span data-ttu-id="a2e77-143">外部</span><span class="sxs-lookup"><span data-stu-id="a2e77-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a2e77-144">セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="a2e77-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="a2e77-145">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2e77-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2e77-146"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="a2e77-146"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a2e77-147">int</span><span class="sxs-lookup"><span data-stu-id="a2e77-147">int</span></span></p></td>
<td><p><span data-ttu-id="a2e77-148">外部</span><span class="sxs-lookup"><span data-stu-id="a2e77-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a2e77-149">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="a2e77-149">ID number to identify the session.</span></span> <span data-ttu-id="a2e77-150">セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="a2e77-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="a2e77-151">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2e77-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2e77-152"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="a2e77-152"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2e77-153">int</span><span class="sxs-lookup"><span data-stu-id="a2e77-153">int</span></span></p></td>
<td><p><span data-ttu-id="a2e77-154">外部</span><span class="sxs-lookup"><span data-stu-id="a2e77-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a2e77-155">エラーレポートを送信したサーバー (レポートがサーバーコンポーネントから送信されている場合)。</span><span class="sxs-lookup"><span data-stu-id="a2e77-155">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="a2e77-156">詳細については、「 <a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2e77-156">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="a2e77-157">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a2e77-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2e77-158"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="a2e77-158"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2e77-159">int</span><span class="sxs-lookup"><span data-stu-id="a2e77-159">int</span></span></p></td>
<td><p><span data-ttu-id="a2e77-160">外部</span><span class="sxs-lookup"><span data-stu-id="a2e77-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a2e77-161">エラーレポートを送信したサーバー (レポートがサーバーコンポーネントから送信されている場合)。</span><span class="sxs-lookup"><span data-stu-id="a2e77-161">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="a2e77-162">詳細については、「 <a href="lync-server-2013-application-table.md">Lync Server 2013 のアプリケーションテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2e77-162">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="a2e77-163">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a2e77-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2e77-164"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="a2e77-164"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="a2e77-165">image</span><span class="sxs-lookup"><span data-stu-id="a2e77-165">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a2e77-166">エラーに関する詳細情報。</span><span class="sxs-lookup"><span data-stu-id="a2e77-166">More information about the error.</span></span></p>
<p><span data-ttu-id="a2e77-167">このデータは、次の構文を使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="a2e77-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2e77-168"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="a2e77-168"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2e77-169">int</span><span class="sxs-lookup"><span data-stu-id="a2e77-169">int</span></span></p></td>
<td><p><span data-ttu-id="a2e77-170">外部</span><span class="sxs-lookup"><span data-stu-id="a2e77-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a2e77-171">エラーレポートを送信するエンドポイントのクライアントバージョン。</span><span class="sxs-lookup"><span data-stu-id="a2e77-171">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="a2e77-172">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2e77-172">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2e77-173"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="a2e77-173"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="a2e77-174">若干</span><span class="sxs-lookup"><span data-stu-id="a2e77-174">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a2e77-175">は、フロントエンドサーバーで実行されている CDR エージェントまたはクライアントによって送信されたエラーレポートです。</span><span class="sxs-lookup"><span data-stu-id="a2e77-175">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2e77-176"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="a2e77-176"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="a2e77-177">smallint</span><span class="sxs-lookup"><span data-stu-id="a2e77-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a2e77-178">将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="a2e77-178">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2e77-179"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="a2e77-179"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2e77-180">識別子</span><span class="sxs-lookup"><span data-stu-id="a2e77-180">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a2e77-181">会議に関するさまざまなコンポーネントの参加時間情報に関係する一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="a2e77-181">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="a2e77-182">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a2e77-182">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2e77-183"><strong>SessionSetupTime 時間</strong></span><span class="sxs-lookup"><span data-stu-id="a2e77-183"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a2e77-184">int</span><span class="sxs-lookup"><span data-stu-id="a2e77-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a2e77-185">特定のコンポーネントが会議に参加するのに必要な時間 (ミリ秒)。</span><span class="sxs-lookup"><span data-stu-id="a2e77-185">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="a2e77-186">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a2e77-186">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2e77-187"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="a2e77-187"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2e77-188">int</span><span class="sxs-lookup"><span data-stu-id="a2e77-188">int</span></span></p></td>
<td><p><span data-ttu-id="a2e77-189">外部</span><span class="sxs-lookup"><span data-stu-id="a2e77-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a2e77-190">エラーレポートを生成したサーバーの完全修飾ドメイン名を表します。</span><span class="sxs-lookup"><span data-stu-id="a2e77-190">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2e77-191"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="a2e77-191"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2e77-192">int</span><span class="sxs-lookup"><span data-stu-id="a2e77-192">int</span></span></p></td>
<td><p><span data-ttu-id="a2e77-193">外部</span><span class="sxs-lookup"><span data-stu-id="a2e77-193">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a2e77-194">エラー報告が生成されたプールの完全修飾ドメイン名を表します。</span><span class="sxs-lookup"><span data-stu-id="a2e77-194">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

