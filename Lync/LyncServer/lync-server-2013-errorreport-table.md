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
ms.openlocfilehash: 8de4163f94d5848808c5b01c34b1676d3a0bbcff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="0ab79-102">Lync Server 2013 の ErrorReport テーブル</span><span class="sxs-lookup"><span data-stu-id="0ab79-102">ErrorReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ab79-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="0ab79-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="0ab79-104">ErrorReport テーブルには、発生したエラーに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="0ab79-104">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="0ab79-105">各レコードはエラー発生の1つです。</span><span class="sxs-lookup"><span data-stu-id="0ab79-105">Each record is one error occurrence.</span></span> <span data-ttu-id="0ab79-106">このエラーは、フロントエンドサーバーで実行されている CDR エージェントまたはクライアントから送信された cd-r エージェントによってキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="0ab79-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ab79-107">列</span><span class="sxs-lookup"><span data-stu-id="0ab79-107">Column</span></span></th>
<th><span data-ttu-id="0ab79-108">データ型</span><span class="sxs-lookup"><span data-stu-id="0ab79-108">Data Type</span></span></th>
<th><span data-ttu-id="0ab79-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="0ab79-109">Key/Index</span></span></th>
<th><span data-ttu-id="0ab79-110">詳細</span><span class="sxs-lookup"><span data-stu-id="0ab79-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ab79-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="0ab79-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0ab79-112">datetime</span><span class="sxs-lookup"><span data-stu-id="0ab79-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="0ab79-113">Primary</span><span class="sxs-lookup"><span data-stu-id="0ab79-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="0ab79-114">エラーが発生した日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="0ab79-114">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ab79-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0ab79-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0ab79-116">int</span><span class="sxs-lookup"><span data-stu-id="0ab79-116">int</span></span></p></td>
<td><p><span data-ttu-id="0ab79-117">Primary</span><span class="sxs-lookup"><span data-stu-id="0ab79-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="0ab79-118">エラーレポートを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="0ab79-118">ID number to identify the error report.</span></span> <span data-ttu-id="0ab79-119">エラーレポートを一意に識別するための<strong>Errortime</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ab79-119">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ab79-120"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="0ab79-120"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="0ab79-121">int</span><span class="sxs-lookup"><span data-stu-id="0ab79-121">int</span></span></p></td>
<td><p><span data-ttu-id="0ab79-122">外部</span><span class="sxs-lookup"><span data-stu-id="0ab79-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0ab79-123">エラーの種類の一意の ID です。</span><span class="sxs-lookup"><span data-stu-id="0ab79-123">Unique ID of the error type.</span></span> <span data-ttu-id="0ab79-124">詳細については、「 <a href="lync-server-2013-errordef-table.md">Lync Server 2013 の Errordef テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ab79-124">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ab79-125"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="0ab79-125"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="0ab79-126">int</span><span class="sxs-lookup"><span data-stu-id="0ab79-126">int</span></span></p></td>
<td><p><span data-ttu-id="0ab79-127">外部</span><span class="sxs-lookup"><span data-stu-id="0ab79-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0ab79-128">エラーの原因となった要求を生成したユーザー。</span><span class="sxs-lookup"><span data-stu-id="0ab79-128">User who originated the request that caused the error.</span></span> <span data-ttu-id="0ab79-129">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ab79-129">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ab79-130"><strong>ToUserId</strong></span><span class="sxs-lookup"><span data-stu-id="0ab79-130"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="0ab79-131">int</span><span class="sxs-lookup"><span data-stu-id="0ab79-131">int</span></span></p></td>
<td><p><span data-ttu-id="0ab79-132">外部</span><span class="sxs-lookup"><span data-stu-id="0ab79-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0ab79-133">エラーの原因となった要求の送信先ユーザー。</span><span class="sxs-lookup"><span data-stu-id="0ab79-133">Destination user for the request that caused the error.</span></span> <span data-ttu-id="0ab79-134">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ab79-134">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ab79-135"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="0ab79-135"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="0ab79-136">int</span><span class="sxs-lookup"><span data-stu-id="0ab79-136">int</span></span></p></td>
<td><p><span data-ttu-id="0ab79-137">外部</span><span class="sxs-lookup"><span data-stu-id="0ab79-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0ab79-138">エラーに関連する会議の URI。</span><span class="sxs-lookup"><span data-stu-id="0ab79-138">Conference URI related to the error.</span></span> <span data-ttu-id="0ab79-139">詳細については、「 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ab79-139">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="0ab79-140">通常、ConferenceUriId が null でない場合は、FromUserId または ToUserId は null になります。</span><span class="sxs-lookup"><span data-stu-id="0ab79-140">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ab79-141"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="0ab79-141"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0ab79-142">datetime</span><span class="sxs-lookup"><span data-stu-id="0ab79-142">datetime</span></span></p></td>
<td><p><span data-ttu-id="0ab79-143">外部</span><span class="sxs-lookup"><span data-stu-id="0ab79-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0ab79-144">セッションを一意に識別するために<strong>Sessionidseq</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ab79-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="0ab79-145">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ab79-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ab79-146"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0ab79-146"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0ab79-147">int</span><span class="sxs-lookup"><span data-stu-id="0ab79-147">int</span></span></p></td>
<td><p><span data-ttu-id="0ab79-148">外部</span><span class="sxs-lookup"><span data-stu-id="0ab79-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0ab79-149">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="0ab79-149">ID number to identify the session.</span></span> <span data-ttu-id="0ab79-150">セッションを一意に識別するために<strong>Sessionidtime</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ab79-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="0ab79-151">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ab79-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ab79-152"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="0ab79-152"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="0ab79-153">int</span><span class="sxs-lookup"><span data-stu-id="0ab79-153">int</span></span></p></td>
<td><p><span data-ttu-id="0ab79-154">外部</span><span class="sxs-lookup"><span data-stu-id="0ab79-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0ab79-155">エラーレポートを送信したサーバー (レポートがサーバーコンポーネントから送信されている場合)。</span><span class="sxs-lookup"><span data-stu-id="0ab79-155">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="0ab79-156">詳細については、「 <a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ab79-156">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="0ab79-157">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0ab79-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ab79-158"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="0ab79-158"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="0ab79-159">int</span><span class="sxs-lookup"><span data-stu-id="0ab79-159">int</span></span></p></td>
<td><p><span data-ttu-id="0ab79-160">外部</span><span class="sxs-lookup"><span data-stu-id="0ab79-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0ab79-161">エラーレポートを送信したサーバー (レポートがサーバーコンポーネントから送信されている場合)。</span><span class="sxs-lookup"><span data-stu-id="0ab79-161">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="0ab79-162">詳細については、「 <a href="lync-server-2013-application-table.md">Lync Server 2013 のアプリケーションテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ab79-162">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="0ab79-163">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0ab79-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ab79-164"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="0ab79-164"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="0ab79-165">画像</span><span class="sxs-lookup"><span data-stu-id="0ab79-165">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0ab79-166">エラーに関する詳細情報。</span><span class="sxs-lookup"><span data-stu-id="0ab79-166">More information about the error.</span></span></p>
<p><span data-ttu-id="0ab79-167">このデータは、次の構文を使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="0ab79-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ab79-168"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="0ab79-168"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="0ab79-169">int</span><span class="sxs-lookup"><span data-stu-id="0ab79-169">int</span></span></p></td>
<td><p><span data-ttu-id="0ab79-170">外部</span><span class="sxs-lookup"><span data-stu-id="0ab79-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0ab79-171">エラーレポートを送信するエンドポイントのクライアントバージョン。</span><span class="sxs-lookup"><span data-stu-id="0ab79-171">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="0ab79-172">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ab79-172">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ab79-173"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="0ab79-173"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="0ab79-174">bit</span><span class="sxs-lookup"><span data-stu-id="0ab79-174">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0ab79-175">エラーレポートは、フロントエンドサーバーで実行されている CDR エージェントまたはクライアントによってキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="0ab79-175">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ab79-176"><strong>フラッグ</strong></span><span class="sxs-lookup"><span data-stu-id="0ab79-176"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="0ab79-177">smallint</span><span class="sxs-lookup"><span data-stu-id="0ab79-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0ab79-178">今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="0ab79-178">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ab79-179"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="0ab79-179"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="0ab79-180">長さ</span><span class="sxs-lookup"><span data-stu-id="0ab79-180">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0ab79-181">電話会議に参加しているさまざまなコンポーネントについての、固有の識別子による結合時間情報の関連付け。</span><span class="sxs-lookup"><span data-stu-id="0ab79-181">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="0ab79-182">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0ab79-182">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ab79-183"><strong>SessionSetupTime 時間</strong></span><span class="sxs-lookup"><span data-stu-id="0ab79-183"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0ab79-184">int</span><span class="sxs-lookup"><span data-stu-id="0ab79-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0ab79-185">特定のコンポーネントが会議に参加するために必要な時間 (ミリ秒単位) です。</span><span class="sxs-lookup"><span data-stu-id="0ab79-185">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="0ab79-186">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0ab79-186">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ab79-187"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="0ab79-187"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="0ab79-188">int</span><span class="sxs-lookup"><span data-stu-id="0ab79-188">int</span></span></p></td>
<td><p><span data-ttu-id="0ab79-189">外部</span><span class="sxs-lookup"><span data-stu-id="0ab79-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0ab79-190">エラーレポートを生成したサーバーの完全修飾ドメイン名を表します。</span><span class="sxs-lookup"><span data-stu-id="0ab79-190">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ab79-191"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="0ab79-191"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="0ab79-192">int</span><span class="sxs-lookup"><span data-stu-id="0ab79-192">int</span></span></p></td>
<td><p><span data-ttu-id="0ab79-193">外部</span><span class="sxs-lookup"><span data-stu-id="0ab79-193">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0ab79-194">エラーレポートが生成されたプールの完全修飾ドメイン名を表します。</span><span class="sxs-lookup"><span data-stu-id="0ab79-194">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

