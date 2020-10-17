---
title: 'Lync Server 2013: Session テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d74d2732d2f8ad293450f4945eef00bccb9a572d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510084"
---
# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="bc595-102">Lync Server 2013 の Session テーブル</span><span class="sxs-lookup"><span data-stu-id="bc595-102">Session table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc595-103">_**トピックの最終更新日:** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="bc595-103">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="bc595-104">各レコードは、音声またはオーディオとビデオを含む1つのセッションを表します。</span><span class="sxs-lookup"><span data-stu-id="bc595-104">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="bc595-105">このファイルには、セッションに関する全体的な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bc595-105">It contains overall information about the session.</span></span> <span data-ttu-id="bc595-106">セッションは、2つのエンドポイント間のオーディオまたはビデオセッション開始プロトコル (SIP) ダイアログとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="bc595-106">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc595-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="bc595-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="bc595-108"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="bc595-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="bc595-109"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="bc595-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="bc595-110"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="bc595-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc595-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="bc595-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bc595-112">日付型</span><span class="sxs-lookup"><span data-stu-id="bc595-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="bc595-113">Primary</span><span class="sxs-lookup"><span data-stu-id="bc595-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="bc595-114"><a href="lync-server-2013-dialog-table.md">Lync Server 2013 のダイアログテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="bc595-114">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc595-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="bc595-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="bc595-116">int</span><span class="sxs-lookup"><span data-stu-id="bc595-116">int</span></span></p></td>
<td><p><span data-ttu-id="bc595-117">Primary</span><span class="sxs-lookup"><span data-stu-id="bc595-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="bc595-118"><a href="lync-server-2013-dialog-table.md">Lync Server 2013 のダイアログテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="bc595-118">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc595-119"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="bc595-119"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="bc595-120">int</span><span class="sxs-lookup"><span data-stu-id="bc595-120">int</span></span></p></td>
<td><p><span data-ttu-id="bc595-121">外部</span><span class="sxs-lookup"><span data-stu-id="bc595-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bc595-122">電話会議キー。</span><span class="sxs-lookup"><span data-stu-id="bc595-122">Conference key.</span></span> <span data-ttu-id="bc595-123"><a href="lync-server-2013-conference-table.md">Lync Server 2013 の会議テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="bc595-123">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc595-124"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="bc595-124"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="bc595-125">int</span><span class="sxs-lookup"><span data-stu-id="bc595-125">int</span></span></p></td>
<td><p><span data-ttu-id="bc595-126">外部</span><span class="sxs-lookup"><span data-stu-id="bc595-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bc595-127">関連付けキー。</span><span class="sxs-lookup"><span data-stu-id="bc595-127">Correlation key.</span></span> <span data-ttu-id="bc595-128"><a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 の Sessioncorrelation テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="bc595-128">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc595-129"><strong>' このカテゴリ</strong></span><span class="sxs-lookup"><span data-stu-id="bc595-129"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="bc595-130">若干</span><span class="sxs-lookup"><span data-stu-id="bc595-130">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bc595-131">ダイアログのカテゴリ。0は Lync Server から仲介サーバーまでです。1は仲介サーバーから PSTN ゲートウェイレグになります。</span><span class="sxs-lookup"><span data-stu-id="bc595-131">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc595-132"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="bc595-132"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="bc595-133">若干</span><span class="sxs-lookup"><span data-stu-id="bc595-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bc595-134">通話がバイパスされたかどうかを示すフラグ。</span><span class="sxs-lookup"><span data-stu-id="bc595-134">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc595-135"><strong>Mediabypasswarnings フラグ</strong></span><span class="sxs-lookup"><span data-stu-id="bc595-135"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="bc595-136">int</span><span class="sxs-lookup"><span data-stu-id="bc595-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bc595-137">このフィールドは、(存在する場合) バイパス ID が一致したのに通話がバイパスされなかった理由を示します。</span><span class="sxs-lookup"><span data-stu-id="bc595-137">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="bc595-138">Lync Server では、1つの値のみが定義されています。</span><span class="sxs-lookup"><span data-stu-id="bc595-138">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="bc595-139">0x0001 - 既定のネットワーク アダプターのバイパス ID が不明です。</span><span class="sxs-lookup"><span data-stu-id="bc595-139">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc595-140"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="bc595-140"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bc595-141">日付型</span><span class="sxs-lookup"><span data-stu-id="bc595-141">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bc595-142">通話の開始時刻。</span><span class="sxs-lookup"><span data-stu-id="bc595-142">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc595-143"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="bc595-143"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bc595-144">日付型</span><span class="sxs-lookup"><span data-stu-id="bc595-144">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bc595-145">通話の終了時刻。</span><span class="sxs-lookup"><span data-stu-id="bc595-145">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc595-146"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="bc595-146"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="bc595-147">int</span><span class="sxs-lookup"><span data-stu-id="bc595-147">int</span></span></p></td>
<td><p><span data-ttu-id="bc595-148">外部</span><span class="sxs-lookup"><span data-stu-id="bc595-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bc595-149">発信者のプール。</span><span class="sxs-lookup"><span data-stu-id="bc595-149">The pool of the caller.</span></span> <span data-ttu-id="bc595-150"><a href="lync-server-2013-pool-table.md">Lync Server 2013 のプールテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="bc595-150">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc595-151"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="bc595-151"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="bc595-152">int</span><span class="sxs-lookup"><span data-stu-id="bc595-152">int</span></span></p></td>
<td><p><span data-ttu-id="bc595-153">外部</span><span class="sxs-lookup"><span data-stu-id="bc595-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bc595-154">通話受信者のプール。</span><span class="sxs-lookup"><span data-stu-id="bc595-154">The pool of the call receiver.</span></span> <span data-ttu-id="bc595-155"><a href="lync-server-2013-pool-table.md">Lync Server 2013 のプールテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="bc595-155">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc595-156"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="bc595-156"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="bc595-157">int</span><span class="sxs-lookup"><span data-stu-id="bc595-157">int</span></span></p></td>
<td><p><span data-ttu-id="bc595-158">外部</span><span class="sxs-lookup"><span data-stu-id="bc595-158">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bc595-159">受信エンドポイントの SIP p アサートされた id (PAI) の SIP URI。</span><span class="sxs-lookup"><span data-stu-id="bc595-159">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="bc595-160"><a href="lync-server-2013-user-table.md">Lync Server 2013 のユーザーテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="bc595-160">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc595-161"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="bc595-161"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="bc595-162">int</span><span class="sxs-lookup"><span data-stu-id="bc595-162">int</span></span></p></td>
<td><p><span data-ttu-id="bc595-163">外部</span><span class="sxs-lookup"><span data-stu-id="bc595-163">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bc595-164">発信者の URI。</span><span class="sxs-lookup"><span data-stu-id="bc595-164">Caller’s URI.</span></span> <span data-ttu-id="bc595-165"><a href="lync-server-2013-user-table.md">Lync Server 2013 のユーザーテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="bc595-165">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc595-166"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="bc595-166"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="bc595-167">int</span><span class="sxs-lookup"><span data-stu-id="bc595-167">int</span></span></p></td>
<td><p><span data-ttu-id="bc595-168">外部</span><span class="sxs-lookup"><span data-stu-id="bc595-168">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bc595-169">発信者のエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="bc595-169">Caller’s endpoint.</span></span> <span data-ttu-id="bc595-170"><a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="bc595-170">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc595-171"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="bc595-171"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="bc595-172">若干</span><span class="sxs-lookup"><span data-stu-id="bc595-172">bit</span></span></p></td>
<td><p><span data-ttu-id="bc595-173">外部</span><span class="sxs-lookup"><span data-stu-id="bc595-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bc595-174">発信者のユーザーエージェント。</span><span class="sxs-lookup"><span data-stu-id="bc595-174">Caller’s user agent.</span></span> <span data-ttu-id="bc595-175"><a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="bc595-175">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc595-176"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="bc595-176"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="bc595-177">smallint</span><span class="sxs-lookup"><span data-stu-id="bc595-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bc595-178">この通話の優先度。</span><span class="sxs-lookup"><span data-stu-id="bc595-178">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc595-179"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="bc595-179"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="bc595-180">若干</span><span class="sxs-lookup"><span data-stu-id="bc595-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bc595-181">この列は推奨されておらず、Microsoft Lync Server 2013 では使用されていません。</span><span class="sxs-lookup"><span data-stu-id="bc595-181">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="bc595-182">代わりに、この情報はメディアごとの回線ベースで報告されます。</span><span class="sxs-lookup"><span data-stu-id="bc595-182">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="bc595-183">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc595-183">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc595-184"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="bc595-184"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="bc595-185">int</span><span class="sxs-lookup"><span data-stu-id="bc595-185">int</span></span></p></td>
<td><p><span data-ttu-id="bc595-186">外部</span><span class="sxs-lookup"><span data-stu-id="bc595-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bc595-187">P-アサート済み-通話を発信したユーザーの Id。</span><span class="sxs-lookup"><span data-stu-id="bc595-187">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="bc595-188">P アサートされた Id (PAI) は、呼び出しを行ったユーザーの真の id を伝えるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bc595-188">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc595-189"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="bc595-189"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="bc595-190">int</span><span class="sxs-lookup"><span data-stu-id="bc595-190">int</span></span></p></td>
<td><p><span data-ttu-id="bc595-191">外部</span><span class="sxs-lookup"><span data-stu-id="bc595-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bc595-192">通話を受信したエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="bc595-192">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc595-193"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="bc595-193"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="bc595-194">int</span><span class="sxs-lookup"><span data-stu-id="bc595-194">int</span></span></p></td>
<td><p><span data-ttu-id="bc595-195">外部</span><span class="sxs-lookup"><span data-stu-id="bc595-195">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bc595-196">通話を受信したユーザーによって使用されているユーザーエージェント。</span><span class="sxs-lookup"><span data-stu-id="bc595-196">User agent employed by the user who received the call.</span></span> <span data-ttu-id="bc595-197">ユーザーエージェントは、クライアントエンドポイントデバイスを表します。</span><span class="sxs-lookup"><span data-stu-id="bc595-197">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc595-198"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="bc595-198"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="bc595-199">int</span><span class="sxs-lookup"><span data-stu-id="bc595-199">int</span></span></p></td>
<td><p><span data-ttu-id="bc595-200">外部</span><span class="sxs-lookup"><span data-stu-id="bc595-200">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bc595-201">通話を受信したユーザーの SIP URI。</span><span class="sxs-lookup"><span data-stu-id="bc595-201">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

