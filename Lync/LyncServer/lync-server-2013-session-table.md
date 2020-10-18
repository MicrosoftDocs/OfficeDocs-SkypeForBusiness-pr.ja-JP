---
title: 'Lync Server 2013: Session テーブル'
description: 'Lync Server 2013: Session テーブル。'
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
ms.openlocfilehash: e1a52813dfea808253cc934f71a9d4c846c2dbbd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576453"
---
# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="4f5e0-103">Lync Server 2013 の Session テーブル</span><span class="sxs-lookup"><span data-stu-id="4f5e0-103">Session table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f5e0-104">_**トピックの最終更新日:** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="4f5e0-104">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="4f5e0-105">各レコードは、音声またはオーディオとビデオを含む1つのセッションを表します。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-105">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="4f5e0-106">このファイルには、セッションに関する全体的な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-106">It contains overall information about the session.</span></span> <span data-ttu-id="4f5e0-107">セッションは、2つのエンドポイント間のオーディオまたはビデオセッション開始プロトコル (SIP) ダイアログとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-107">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f5e0-108"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="4f5e0-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="4f5e0-109"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="4f5e0-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="4f5e0-110"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="4f5e0-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="4f5e0-111"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="4f5e0-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f5e0-112"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="4f5e0-112"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4f5e0-113">日付型</span><span class="sxs-lookup"><span data-stu-id="4f5e0-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-114">Primary</span><span class="sxs-lookup"><span data-stu-id="4f5e0-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-115"><a href="lync-server-2013-dialog-table.md">Lync Server 2013 のダイアログテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-115">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5e0-116"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4f5e0-116"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4f5e0-117">int</span><span class="sxs-lookup"><span data-stu-id="4f5e0-117">int</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-118">Primary</span><span class="sxs-lookup"><span data-stu-id="4f5e0-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-119"><a href="lync-server-2013-dialog-table.md">Lync Server 2013 のダイアログテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-119">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5e0-120"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="4f5e0-120"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="4f5e0-121">int</span><span class="sxs-lookup"><span data-stu-id="4f5e0-121">int</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-122">外部</span><span class="sxs-lookup"><span data-stu-id="4f5e0-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-123">電話会議キー。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-123">Conference key.</span></span> <span data-ttu-id="4f5e0-124"><a href="lync-server-2013-conference-table.md">Lync Server 2013 の会議テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-124">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5e0-125"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="4f5e0-125"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="4f5e0-126">int</span><span class="sxs-lookup"><span data-stu-id="4f5e0-126">int</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-127">外部</span><span class="sxs-lookup"><span data-stu-id="4f5e0-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-128">関連付けキー。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-128">Correlation key.</span></span> <span data-ttu-id="4f5e0-129"><a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 の Sessioncorrelation テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-129">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5e0-130"><strong>' このカテゴリ</strong></span><span class="sxs-lookup"><span data-stu-id="4f5e0-130"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="4f5e0-131">若干</span><span class="sxs-lookup"><span data-stu-id="4f5e0-131">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f5e0-132">ダイアログのカテゴリ。0は Lync Server から仲介サーバーまでです。1は仲介サーバーから PSTN ゲートウェイレグになります。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-132">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5e0-133"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="4f5e0-133"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="4f5e0-134">若干</span><span class="sxs-lookup"><span data-stu-id="4f5e0-134">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f5e0-135">通話がバイパスされたかどうかを示すフラグ。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-135">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5e0-136"><strong>Mediabypasswarnings フラグ</strong></span><span class="sxs-lookup"><span data-stu-id="4f5e0-136"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="4f5e0-137">int</span><span class="sxs-lookup"><span data-stu-id="4f5e0-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f5e0-138">このフィールドは、(存在する場合) バイパス ID が一致したのに通話がバイパスされなかった理由を示します。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-138">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="4f5e0-139">Lync Server では、1つの値のみが定義されています。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-139">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="4f5e0-140">0x0001 - 既定のネットワーク アダプターのバイパス ID が不明です。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-140">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5e0-141"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="4f5e0-141"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4f5e0-142">日付型</span><span class="sxs-lookup"><span data-stu-id="4f5e0-142">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f5e0-143">通話の開始時刻。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-143">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5e0-144"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="4f5e0-144"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4f5e0-145">日付型</span><span class="sxs-lookup"><span data-stu-id="4f5e0-145">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f5e0-146">通話の終了時刻。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-146">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5e0-147"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="4f5e0-147"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="4f5e0-148">int</span><span class="sxs-lookup"><span data-stu-id="4f5e0-148">int</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-149">外部</span><span class="sxs-lookup"><span data-stu-id="4f5e0-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-150">発信者のプール。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-150">The pool of the caller.</span></span> <span data-ttu-id="4f5e0-151"><a href="lync-server-2013-pool-table.md">Lync Server 2013 のプールテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-151">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5e0-152"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="4f5e0-152"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="4f5e0-153">int</span><span class="sxs-lookup"><span data-stu-id="4f5e0-153">int</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-154">外部</span><span class="sxs-lookup"><span data-stu-id="4f5e0-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-155">通話受信者のプール。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-155">The pool of the call receiver.</span></span> <span data-ttu-id="4f5e0-156"><a href="lync-server-2013-pool-table.md">Lync Server 2013 のプールテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-156">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5e0-157"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="4f5e0-157"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="4f5e0-158">int</span><span class="sxs-lookup"><span data-stu-id="4f5e0-158">int</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-159">外部</span><span class="sxs-lookup"><span data-stu-id="4f5e0-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-160">受信エンドポイントの SIP p アサートされた id (PAI) の SIP URI。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-160">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="4f5e0-161"><a href="lync-server-2013-user-table.md">Lync Server 2013 のユーザーテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-161">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5e0-162"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="4f5e0-162"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="4f5e0-163">int</span><span class="sxs-lookup"><span data-stu-id="4f5e0-163">int</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-164">外部</span><span class="sxs-lookup"><span data-stu-id="4f5e0-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-165">発信者の URI。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-165">Caller’s URI.</span></span> <span data-ttu-id="4f5e0-166"><a href="lync-server-2013-user-table.md">Lync Server 2013 のユーザーテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-166">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5e0-167"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="4f5e0-167"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="4f5e0-168">int</span><span class="sxs-lookup"><span data-stu-id="4f5e0-168">int</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-169">外部</span><span class="sxs-lookup"><span data-stu-id="4f5e0-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-170">発信者のエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-170">Caller’s endpoint.</span></span> <span data-ttu-id="4f5e0-171"><a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-171">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5e0-172"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="4f5e0-172"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="4f5e0-173">若干</span><span class="sxs-lookup"><span data-stu-id="4f5e0-173">bit</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-174">外部</span><span class="sxs-lookup"><span data-stu-id="4f5e0-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-175">発信者のユーザーエージェント。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-175">Caller’s user agent.</span></span> <span data-ttu-id="4f5e0-176"><a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-176">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5e0-177"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="4f5e0-177"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="4f5e0-178">smallint</span><span class="sxs-lookup"><span data-stu-id="4f5e0-178">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f5e0-179">この通話の優先度。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-179">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5e0-180"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="4f5e0-180"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="4f5e0-181">若干</span><span class="sxs-lookup"><span data-stu-id="4f5e0-181">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f5e0-182">この列は推奨されておらず、Microsoft Lync Server 2013 では使用されていません。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-182">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="4f5e0-183">代わりに、この情報はメディアごとの回線ベースで報告されます。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-183">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="4f5e0-184">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-184">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5e0-185"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="4f5e0-185"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="4f5e0-186">int</span><span class="sxs-lookup"><span data-stu-id="4f5e0-186">int</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-187">外部</span><span class="sxs-lookup"><span data-stu-id="4f5e0-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-188">P-アサート済み-通話を発信したユーザーの Id。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-188">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="4f5e0-189">P アサートされた Id (PAI) は、呼び出しを行ったユーザーの真の id を伝えるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-189">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5e0-190"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="4f5e0-190"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="4f5e0-191">int</span><span class="sxs-lookup"><span data-stu-id="4f5e0-191">int</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-192">外部</span><span class="sxs-lookup"><span data-stu-id="4f5e0-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-193">通話を受信したエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-193">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5e0-194"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="4f5e0-194"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="4f5e0-195">int</span><span class="sxs-lookup"><span data-stu-id="4f5e0-195">int</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-196">外部</span><span class="sxs-lookup"><span data-stu-id="4f5e0-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-197">通話を受信したユーザーによって使用されているユーザーエージェント。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-197">User agent employed by the user who received the call.</span></span> <span data-ttu-id="4f5e0-198">ユーザーエージェントは、クライアントエンドポイントデバイスを表します。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-198">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5e0-199"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="4f5e0-199"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="4f5e0-200">int</span><span class="sxs-lookup"><span data-stu-id="4f5e0-200">int</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-201">外部</span><span class="sxs-lookup"><span data-stu-id="4f5e0-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f5e0-202">通話を受信したユーザーの SIP URI。</span><span class="sxs-lookup"><span data-stu-id="4f5e0-202">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

