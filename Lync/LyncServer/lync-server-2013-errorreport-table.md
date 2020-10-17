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
ms.openlocfilehash: 321a975e9461e39de882d9620cdded9d2554e8ed
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533144"
---
# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="ac6fd-102">Lync Server 2013 の ErrorReport テーブル</span><span class="sxs-lookup"><span data-stu-id="ac6fd-102">ErrorReport table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac6fd-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ac6fd-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ac6fd-104">ErrorReport テーブルには、発生したエラーに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-104">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="ac6fd-105">各レコードは、エラー発生の1つです。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-105">Each record is one error occurrence.</span></span> <span data-ttu-id="ac6fd-106">エラーは、フロントエンドサーバーで実行されている CDR エージェント、またはクライアントから送信されます。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac6fd-107">Column</span><span class="sxs-lookup"><span data-stu-id="ac6fd-107">Column</span></span></th>
<th><span data-ttu-id="ac6fd-108">データ型</span><span class="sxs-lookup"><span data-stu-id="ac6fd-108">Data Type</span></span></th>
<th><span data-ttu-id="ac6fd-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="ac6fd-109">Key/Index</span></span></th>
<th><span data-ttu-id="ac6fd-110">詳細</span><span class="sxs-lookup"><span data-stu-id="ac6fd-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac6fd-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="ac6fd-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ac6fd-112">日付型</span><span class="sxs-lookup"><span data-stu-id="ac6fd-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ac6fd-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-114">エラーが発生した日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-114">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac6fd-115"><strong>Errorreportseq、</strong></span><span class="sxs-lookup"><span data-stu-id="ac6fd-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ac6fd-116">int</span><span class="sxs-lookup"><span data-stu-id="ac6fd-116">int</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-117">Primary</span><span class="sxs-lookup"><span data-stu-id="ac6fd-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-118">エラーレポートを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-118">ID number to identify the error report.</span></span> <span data-ttu-id="ac6fd-119">エラーレポートを一意に識別するために <strong>Errortime</strong> と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-119">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac6fd-120"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="ac6fd-120"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="ac6fd-121">int</span><span class="sxs-lookup"><span data-stu-id="ac6fd-121">int</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-122">外部</span><span class="sxs-lookup"><span data-stu-id="ac6fd-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-123">エラーの種類の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-123">Unique ID of the error type.</span></span> <span data-ttu-id="ac6fd-124">詳細については、「 <a href="lync-server-2013-errordef-table.md">Lync Server 2013 の Errordef table</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-124">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac6fd-125"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="ac6fd-125"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="ac6fd-126">int</span><span class="sxs-lookup"><span data-stu-id="ac6fd-126">int</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-127">外部</span><span class="sxs-lookup"><span data-stu-id="ac6fd-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-128">エラーの原因となった要求を発信したユーザー。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-128">User who originated the request that caused the error.</span></span> <span data-ttu-id="ac6fd-129">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-129">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac6fd-130"><strong>ToUserId</strong></span><span class="sxs-lookup"><span data-stu-id="ac6fd-130"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="ac6fd-131">int</span><span class="sxs-lookup"><span data-stu-id="ac6fd-131">int</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-132">外部</span><span class="sxs-lookup"><span data-stu-id="ac6fd-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-133">エラーの原因となった要求の送信先ユーザー。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-133">Destination user for the request that caused the error.</span></span> <span data-ttu-id="ac6fd-134">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-134">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac6fd-135"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="ac6fd-135"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="ac6fd-136">int</span><span class="sxs-lookup"><span data-stu-id="ac6fd-136">int</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-137">外部</span><span class="sxs-lookup"><span data-stu-id="ac6fd-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-138">エラーに関連する会議 URI。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-138">Conference URI related to the error.</span></span> <span data-ttu-id="ac6fd-139">詳細については、「 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-139">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="ac6fd-140">通常、ConferenceUriId が null でない場合、FromUserId または ToUserId のいずれかが null になります。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-140">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac6fd-141"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ac6fd-141"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ac6fd-142">日付型</span><span class="sxs-lookup"><span data-stu-id="ac6fd-142">datetime</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-143">外部</span><span class="sxs-lookup"><span data-stu-id="ac6fd-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-144">セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ac6fd-145">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac6fd-146"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="ac6fd-146"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ac6fd-147">int</span><span class="sxs-lookup"><span data-stu-id="ac6fd-147">int</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-148">外部</span><span class="sxs-lookup"><span data-stu-id="ac6fd-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-149">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-149">ID number to identify the session.</span></span> <span data-ttu-id="ac6fd-150">セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ac6fd-151">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac6fd-152"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="ac6fd-152"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="ac6fd-153">int</span><span class="sxs-lookup"><span data-stu-id="ac6fd-153">int</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-154">外部</span><span class="sxs-lookup"><span data-stu-id="ac6fd-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-155">エラーレポートを送信したサーバー (レポートがサーバーコンポーネントから送信されている場合)。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-155">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="ac6fd-156">詳細については、「 <a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-156">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="ac6fd-157">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac6fd-158"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="ac6fd-158"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="ac6fd-159">int</span><span class="sxs-lookup"><span data-stu-id="ac6fd-159">int</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-160">外部</span><span class="sxs-lookup"><span data-stu-id="ac6fd-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-161">エラーレポートを送信したサーバー (レポートがサーバーコンポーネントから送信されている場合)。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-161">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="ac6fd-162">詳細については、「 <a href="lync-server-2013-application-table.md">Lync Server 2013 のアプリケーションテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-162">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="ac6fd-163">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac6fd-164"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="ac6fd-164"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="ac6fd-165">image</span><span class="sxs-lookup"><span data-stu-id="ac6fd-165">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ac6fd-166">エラーに関する詳細情報。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-166">More information about the error.</span></span></p>
<p><span data-ttu-id="ac6fd-167">このデータは、次の構文を使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac6fd-168"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="ac6fd-168"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="ac6fd-169">int</span><span class="sxs-lookup"><span data-stu-id="ac6fd-169">int</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-170">外部</span><span class="sxs-lookup"><span data-stu-id="ac6fd-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-171">エラーレポートを送信するエンドポイントのクライアントバージョン。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-171">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="ac6fd-172">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-172">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac6fd-173"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="ac6fd-173"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="ac6fd-174">若干</span><span class="sxs-lookup"><span data-stu-id="ac6fd-174">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ac6fd-175">は、フロントエンドサーバーで実行されている CDR エージェントまたはクライアントによって送信されたエラーレポートです。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-175">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac6fd-176"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="ac6fd-176"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="ac6fd-177">smallint</span><span class="sxs-lookup"><span data-stu-id="ac6fd-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ac6fd-178">将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-178">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac6fd-179"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="ac6fd-179"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="ac6fd-180">識別子</span><span class="sxs-lookup"><span data-stu-id="ac6fd-180">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ac6fd-181">会議に関するさまざまなコンポーネントの参加時間情報に関係する一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-181">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="ac6fd-182">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-182">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac6fd-183"><strong>SessionSetupTime 時間</strong></span><span class="sxs-lookup"><span data-stu-id="ac6fd-183"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ac6fd-184">int</span><span class="sxs-lookup"><span data-stu-id="ac6fd-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ac6fd-185">特定のコンポーネントが会議に参加するのに必要な時間 (ミリ秒)。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-185">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="ac6fd-186">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-186">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac6fd-187"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="ac6fd-187"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ac6fd-188">int</span><span class="sxs-lookup"><span data-stu-id="ac6fd-188">int</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-189">外部</span><span class="sxs-lookup"><span data-stu-id="ac6fd-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-190">エラーレポートを生成したサーバーの完全修飾ドメイン名を表します。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-190">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac6fd-191"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="ac6fd-191"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="ac6fd-192">int</span><span class="sxs-lookup"><span data-stu-id="ac6fd-192">int</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-193">外部</span><span class="sxs-lookup"><span data-stu-id="ac6fd-193">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ac6fd-194">エラー報告が生成されたプールの完全修飾ドメイン名を表します。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-194">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

