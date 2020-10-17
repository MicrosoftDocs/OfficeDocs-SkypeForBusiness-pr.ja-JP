---
title: 'Lync Server 2013: ErrorReport テーブル'
description: 'Lync Server 2013: ErrorReport テーブル。'
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
ms.openlocfilehash: 9c1cc65c396c16dc137255438f7ef7c32b2d0b78
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572013"
---
# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="71537-103">Lync Server 2013 の ErrorReport テーブル</span><span class="sxs-lookup"><span data-stu-id="71537-103">ErrorReport table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71537-104">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="71537-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="71537-105">ErrorReport テーブルには、発生したエラーに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="71537-105">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="71537-106">各レコードは、エラー発生の1つです。</span><span class="sxs-lookup"><span data-stu-id="71537-106">Each record is one error occurrence.</span></span> <span data-ttu-id="71537-107">エラーは、フロントエンドサーバーで実行されている CDR エージェント、またはクライアントから送信されます。</span><span class="sxs-lookup"><span data-stu-id="71537-107">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71537-108">Column</span><span class="sxs-lookup"><span data-stu-id="71537-108">Column</span></span></th>
<th><span data-ttu-id="71537-109">データ型</span><span class="sxs-lookup"><span data-stu-id="71537-109">Data Type</span></span></th>
<th><span data-ttu-id="71537-110">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="71537-110">Key/Index</span></span></th>
<th><span data-ttu-id="71537-111">詳細</span><span class="sxs-lookup"><span data-stu-id="71537-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71537-112"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="71537-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="71537-113">日付型</span><span class="sxs-lookup"><span data-stu-id="71537-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="71537-114">Primary</span><span class="sxs-lookup"><span data-stu-id="71537-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="71537-115">エラーが発生した日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="71537-115">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71537-116"><strong>Errorreportseq、</strong></span><span class="sxs-lookup"><span data-stu-id="71537-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="71537-117">int</span><span class="sxs-lookup"><span data-stu-id="71537-117">int</span></span></p></td>
<td><p><span data-ttu-id="71537-118">Primary</span><span class="sxs-lookup"><span data-stu-id="71537-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="71537-119">エラーレポートを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="71537-119">ID number to identify the error report.</span></span> <span data-ttu-id="71537-120">エラーレポートを一意に識別するために <strong>Errortime</strong> と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="71537-120">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71537-121"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="71537-121"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="71537-122">int</span><span class="sxs-lookup"><span data-stu-id="71537-122">int</span></span></p></td>
<td><p><span data-ttu-id="71537-123">外部</span><span class="sxs-lookup"><span data-stu-id="71537-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71537-124">エラーの種類の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="71537-124">Unique ID of the error type.</span></span> <span data-ttu-id="71537-125">詳細については、「 <a href="lync-server-2013-errordef-table.md">Lync Server 2013 の Errordef table</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71537-125">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71537-126"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="71537-126"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="71537-127">int</span><span class="sxs-lookup"><span data-stu-id="71537-127">int</span></span></p></td>
<td><p><span data-ttu-id="71537-128">外部</span><span class="sxs-lookup"><span data-stu-id="71537-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71537-129">エラーの原因となった要求を発信したユーザー。</span><span class="sxs-lookup"><span data-stu-id="71537-129">User who originated the request that caused the error.</span></span> <span data-ttu-id="71537-130">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71537-130">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71537-131"><strong>ToUserId</strong></span><span class="sxs-lookup"><span data-stu-id="71537-131"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="71537-132">int</span><span class="sxs-lookup"><span data-stu-id="71537-132">int</span></span></p></td>
<td><p><span data-ttu-id="71537-133">外部</span><span class="sxs-lookup"><span data-stu-id="71537-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71537-134">エラーの原因となった要求の送信先ユーザー。</span><span class="sxs-lookup"><span data-stu-id="71537-134">Destination user for the request that caused the error.</span></span> <span data-ttu-id="71537-135">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71537-135">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71537-136"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="71537-136"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="71537-137">int</span><span class="sxs-lookup"><span data-stu-id="71537-137">int</span></span></p></td>
<td><p><span data-ttu-id="71537-138">外部</span><span class="sxs-lookup"><span data-stu-id="71537-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71537-139">エラーに関連する会議 URI。</span><span class="sxs-lookup"><span data-stu-id="71537-139">Conference URI related to the error.</span></span> <span data-ttu-id="71537-140">詳細については、「 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71537-140">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="71537-141">通常、ConferenceUriId が null でない場合、FromUserId または ToUserId のいずれかが null になります。</span><span class="sxs-lookup"><span data-stu-id="71537-141">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71537-142"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="71537-142"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="71537-143">日付型</span><span class="sxs-lookup"><span data-stu-id="71537-143">datetime</span></span></p></td>
<td><p><span data-ttu-id="71537-144">外部</span><span class="sxs-lookup"><span data-stu-id="71537-144">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71537-145">セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="71537-145">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="71537-146">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71537-146">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71537-147"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="71537-147"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="71537-148">int</span><span class="sxs-lookup"><span data-stu-id="71537-148">int</span></span></p></td>
<td><p><span data-ttu-id="71537-149">外部</span><span class="sxs-lookup"><span data-stu-id="71537-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71537-150">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="71537-150">ID number to identify the session.</span></span> <span data-ttu-id="71537-151">セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="71537-151">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="71537-152">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71537-152">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71537-153"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="71537-153"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="71537-154">int</span><span class="sxs-lookup"><span data-stu-id="71537-154">int</span></span></p></td>
<td><p><span data-ttu-id="71537-155">外部</span><span class="sxs-lookup"><span data-stu-id="71537-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71537-156">エラーレポートを送信したサーバー (レポートがサーバーコンポーネントから送信されている場合)。</span><span class="sxs-lookup"><span data-stu-id="71537-156">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="71537-157">詳細については、「 <a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71537-157">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="71537-158">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="71537-158">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71537-159"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="71537-159"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="71537-160">int</span><span class="sxs-lookup"><span data-stu-id="71537-160">int</span></span></p></td>
<td><p><span data-ttu-id="71537-161">外部</span><span class="sxs-lookup"><span data-stu-id="71537-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71537-162">エラーレポートを送信したサーバー (レポートがサーバーコンポーネントから送信されている場合)。</span><span class="sxs-lookup"><span data-stu-id="71537-162">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="71537-163">詳細については、「 <a href="lync-server-2013-application-table.md">Lync Server 2013 のアプリケーションテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71537-163">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="71537-164">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="71537-164">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71537-165"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="71537-165"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="71537-166">image</span><span class="sxs-lookup"><span data-stu-id="71537-166">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71537-167">エラーに関する詳細情報。</span><span class="sxs-lookup"><span data-stu-id="71537-167">More information about the error.</span></span></p>
<p><span data-ttu-id="71537-168">このデータは、次の構文を使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="71537-168">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71537-169"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="71537-169"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="71537-170">int</span><span class="sxs-lookup"><span data-stu-id="71537-170">int</span></span></p></td>
<td><p><span data-ttu-id="71537-171">外部</span><span class="sxs-lookup"><span data-stu-id="71537-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71537-172">エラーレポートを送信するエンドポイントのクライアントバージョン。</span><span class="sxs-lookup"><span data-stu-id="71537-172">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="71537-173">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71537-173">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71537-174"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="71537-174"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="71537-175">若干</span><span class="sxs-lookup"><span data-stu-id="71537-175">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71537-176">は、フロントエンドサーバーで実行されている CDR エージェントまたはクライアントによって送信されたエラーレポートです。</span><span class="sxs-lookup"><span data-stu-id="71537-176">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71537-177"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="71537-177"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="71537-178">smallint</span><span class="sxs-lookup"><span data-stu-id="71537-178">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71537-179">将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="71537-179">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71537-180"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="71537-180"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="71537-181">識別子</span><span class="sxs-lookup"><span data-stu-id="71537-181">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71537-182">会議に関するさまざまなコンポーネントの参加時間情報に関係する一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="71537-182">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="71537-183">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="71537-183">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71537-184"><strong>SessionSetupTime 時間</strong></span><span class="sxs-lookup"><span data-stu-id="71537-184"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="71537-185">int</span><span class="sxs-lookup"><span data-stu-id="71537-185">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71537-186">特定のコンポーネントが会議に参加するのに必要な時間 (ミリ秒)。</span><span class="sxs-lookup"><span data-stu-id="71537-186">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="71537-187">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="71537-187">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71537-188"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="71537-188"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="71537-189">int</span><span class="sxs-lookup"><span data-stu-id="71537-189">int</span></span></p></td>
<td><p><span data-ttu-id="71537-190">外部</span><span class="sxs-lookup"><span data-stu-id="71537-190">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71537-191">エラーレポートを生成したサーバーの完全修飾ドメイン名を表します。</span><span class="sxs-lookup"><span data-stu-id="71537-191">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71537-192"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="71537-192"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="71537-193">int</span><span class="sxs-lookup"><span data-stu-id="71537-193">int</span></span></p></td>
<td><p><span data-ttu-id="71537-194">外部</span><span class="sxs-lookup"><span data-stu-id="71537-194">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71537-195">エラー報告が生成されたプールの完全修飾ドメイン名を表します。</span><span class="sxs-lookup"><span data-stu-id="71537-195">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

