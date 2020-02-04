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
ms.openlocfilehash: 81b97d6a7521add62817147ae87995508b841f2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="98041-102">Lync Server 2013 の Session テーブル</span><span class="sxs-lookup"><span data-stu-id="98041-102">Session table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98041-103">_**最終更新日:** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="98041-103">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="98041-104">各レコードは、オーディオまたはオーディオとビデオを含む1つのセッションを表します。</span><span class="sxs-lookup"><span data-stu-id="98041-104">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="98041-105">セッションに関する全体的な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="98041-105">It contains overall information about the session.</span></span> <span data-ttu-id="98041-106">セッションは、2つのエンドポイント間のオーディオまたはビデオセッションの開始プロトコル (SIP) ダイアログとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="98041-106">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98041-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="98041-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="98041-108"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="98041-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="98041-109"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="98041-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="98041-110"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="98041-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98041-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="98041-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="98041-112">datetime</span><span class="sxs-lookup"><span data-stu-id="98041-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="98041-113">Primary</span><span class="sxs-lookup"><span data-stu-id="98041-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="98041-114"><a href="lync-server-2013-dialog-table.md">Lync Server 2013 のダイアログテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="98041-114">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98041-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="98041-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="98041-116">int</span><span class="sxs-lookup"><span data-stu-id="98041-116">int</span></span></p></td>
<td><p><span data-ttu-id="98041-117">Primary</span><span class="sxs-lookup"><span data-stu-id="98041-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="98041-118"><a href="lync-server-2013-dialog-table.md">Lync Server 2013 のダイアログテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="98041-118">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98041-119"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="98041-119"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="98041-120">int</span><span class="sxs-lookup"><span data-stu-id="98041-120">int</span></span></p></td>
<td><p><span data-ttu-id="98041-121">外部</span><span class="sxs-lookup"><span data-stu-id="98041-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="98041-122">会議キー。</span><span class="sxs-lookup"><span data-stu-id="98041-122">Conference key.</span></span> <span data-ttu-id="98041-123"><a href="lync-server-2013-conference-table.md">Lync Server 2013 の会議テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="98041-123">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98041-124"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="98041-124"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="98041-125">int</span><span class="sxs-lookup"><span data-stu-id="98041-125">int</span></span></p></td>
<td><p><span data-ttu-id="98041-126">外部</span><span class="sxs-lookup"><span data-stu-id="98041-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="98041-127">相関関係キー。</span><span class="sxs-lookup"><span data-stu-id="98041-127">Correlation key.</span></span> <span data-ttu-id="98041-128"><a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 の Sessioncorrelation テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="98041-128">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98041-129"><strong>このカテゴリ</strong></span><span class="sxs-lookup"><span data-stu-id="98041-129"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="98041-130">bit</span><span class="sxs-lookup"><span data-stu-id="98041-130">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="98041-131">ダイアログカテゴリ0は Lync Server、仲介サーバーの区間、1は、PSTN ゲートウェイ区間への仲介サーバーです。</span><span class="sxs-lookup"><span data-stu-id="98041-131">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98041-132"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="98041-132"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="98041-133">bit</span><span class="sxs-lookup"><span data-stu-id="98041-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="98041-134">通話がバイパスされたかどうかを示すフラグ。</span><span class="sxs-lookup"><span data-stu-id="98041-134">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98041-135"><strong>Mediabypasswarnings フラグ</strong></span><span class="sxs-lookup"><span data-stu-id="98041-135"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="98041-136">int</span><span class="sxs-lookup"><span data-stu-id="98041-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="98041-137">このフィールドは、バイパス Id が一致した場合でも、着信がバイパスされなかった理由を示します (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="98041-137">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="98041-138">Lync Server の場合、1つの値のみが定義されます。</span><span class="sxs-lookup"><span data-stu-id="98041-138">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="98041-139">0x0001 –既定のネットワークアダプターの不明なバイパス ID。</span><span class="sxs-lookup"><span data-stu-id="98041-139">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98041-140"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="98041-140"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="98041-141">datetime</span><span class="sxs-lookup"><span data-stu-id="98041-141">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="98041-142">通話開始時刻。</span><span class="sxs-lookup"><span data-stu-id="98041-142">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98041-143"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="98041-143"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="98041-144">datetime</span><span class="sxs-lookup"><span data-stu-id="98041-144">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="98041-145">通話終了時刻。</span><span class="sxs-lookup"><span data-stu-id="98041-145">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98041-146"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="98041-146"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="98041-147">int</span><span class="sxs-lookup"><span data-stu-id="98041-147">int</span></span></p></td>
<td><p><span data-ttu-id="98041-148">外部</span><span class="sxs-lookup"><span data-stu-id="98041-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="98041-149">発信者のプール。</span><span class="sxs-lookup"><span data-stu-id="98041-149">The pool of the caller.</span></span> <span data-ttu-id="98041-150"><a href="lync-server-2013-pool-table.md">Lync Server 2013 のプールテーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="98041-150">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98041-151"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="98041-151"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="98041-152">int</span><span class="sxs-lookup"><span data-stu-id="98041-152">int</span></span></p></td>
<td><p><span data-ttu-id="98041-153">外部</span><span class="sxs-lookup"><span data-stu-id="98041-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="98041-154">通話受信者のプール。</span><span class="sxs-lookup"><span data-stu-id="98041-154">The pool of the call receiver.</span></span> <span data-ttu-id="98041-155"><a href="lync-server-2013-pool-table.md">Lync Server 2013 のプールテーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="98041-155">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98041-156"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="98041-156"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="98041-157">int</span><span class="sxs-lookup"><span data-stu-id="98041-157">int</span></span></p></td>
<td><p><span data-ttu-id="98041-158">外部</span><span class="sxs-lookup"><span data-stu-id="98041-158">Foreign</span></span></p></td>
<td><p><span data-ttu-id="98041-159">受信エンドポイントの SIP p-アサートされた id (PAI) の SIP URI。</span><span class="sxs-lookup"><span data-stu-id="98041-159">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="98041-160"><a href="lync-server-2013-user-table.md">Lync Server 2013 のユーザーテーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="98041-160">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98041-161"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="98041-161"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="98041-162">int</span><span class="sxs-lookup"><span data-stu-id="98041-162">int</span></span></p></td>
<td><p><span data-ttu-id="98041-163">外部</span><span class="sxs-lookup"><span data-stu-id="98041-163">Foreign</span></span></p></td>
<td><p><span data-ttu-id="98041-164">発信者の URI。</span><span class="sxs-lookup"><span data-stu-id="98041-164">Caller’s URI.</span></span> <span data-ttu-id="98041-165"><a href="lync-server-2013-user-table.md">Lync Server 2013 のユーザーテーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="98041-165">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98041-166"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="98041-166"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="98041-167">int</span><span class="sxs-lookup"><span data-stu-id="98041-167">int</span></span></p></td>
<td><p><span data-ttu-id="98041-168">外部</span><span class="sxs-lookup"><span data-stu-id="98041-168">Foreign</span></span></p></td>
<td><p><span data-ttu-id="98041-169">発信者のエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="98041-169">Caller’s endpoint.</span></span> <span data-ttu-id="98041-170"><a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントテーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="98041-170">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98041-171"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="98041-171"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="98041-172">bit</span><span class="sxs-lookup"><span data-stu-id="98041-172">bit</span></span></p></td>
<td><p><span data-ttu-id="98041-173">外部</span><span class="sxs-lookup"><span data-stu-id="98041-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="98041-174">発信者のユーザーエージェント。</span><span class="sxs-lookup"><span data-stu-id="98041-174">Caller’s user agent.</span></span> <span data-ttu-id="98041-175"><a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="98041-175">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98041-176"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="98041-176"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="98041-177">smallint</span><span class="sxs-lookup"><span data-stu-id="98041-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="98041-178">この通話の優先度。</span><span class="sxs-lookup"><span data-stu-id="98041-178">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98041-179"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="98041-179"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="98041-180">bit</span><span class="sxs-lookup"><span data-stu-id="98041-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="98041-181">この列は廃止され、Microsoft Lync Server 2013 では使用されません。</span><span class="sxs-lookup"><span data-stu-id="98041-181">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="98041-182">代わりに、この情報はメディアラインベースごとに報告されます。</span><span class="sxs-lookup"><span data-stu-id="98041-182">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="98041-183">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 で MediaLine の表</a>を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98041-183">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98041-184"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="98041-184"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="98041-185">int</span><span class="sxs-lookup"><span data-stu-id="98041-185">int</span></span></p></td>
<td><p><span data-ttu-id="98041-186">外部</span><span class="sxs-lookup"><span data-stu-id="98041-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="98041-187">P-アサート済み-通話を発信したユーザーの Id です。</span><span class="sxs-lookup"><span data-stu-id="98041-187">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="98041-188">P がアサートされた Id (PAI) を使って、通話を発信したユーザーの実際の id を伝えます。</span><span class="sxs-lookup"><span data-stu-id="98041-188">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98041-189"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="98041-189"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="98041-190">int</span><span class="sxs-lookup"><span data-stu-id="98041-190">int</span></span></p></td>
<td><p><span data-ttu-id="98041-191">外部</span><span class="sxs-lookup"><span data-stu-id="98041-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="98041-192">通話を受信したエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="98041-192">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98041-193"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="98041-193"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="98041-194">int</span><span class="sxs-lookup"><span data-stu-id="98041-194">int</span></span></p></td>
<td><p><span data-ttu-id="98041-195">外部</span><span class="sxs-lookup"><span data-stu-id="98041-195">Foreign</span></span></p></td>
<td><p><span data-ttu-id="98041-196">通話を受信したユーザーが採用したユーザーエージェント。</span><span class="sxs-lookup"><span data-stu-id="98041-196">User agent employed by the user who received the call.</span></span> <span data-ttu-id="98041-197">ユーザーエージェントは、クライアントエンドポイントデバイスを表します。</span><span class="sxs-lookup"><span data-stu-id="98041-197">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98041-198"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="98041-198"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="98041-199">int</span><span class="sxs-lookup"><span data-stu-id="98041-199">int</span></span></p></td>
<td><p><span data-ttu-id="98041-200">外部</span><span class="sxs-lookup"><span data-stu-id="98041-200">Foreign</span></span></p></td>
<td><p><span data-ttu-id="98041-201">通話を受信したユーザーの SIP URI。</span><span class="sxs-lookup"><span data-stu-id="98041-201">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

