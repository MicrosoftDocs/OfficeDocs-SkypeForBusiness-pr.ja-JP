---
title: 'Lync Server 2013: セッションビュー'
description: 'Lync Server 2013: セッションビュー。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff4bc4abbd55e073006693d28f092f077698ef75
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545013"
---
# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="0762d-103">Lync Server 2013 のセッションビュー</span><span class="sxs-lookup"><span data-stu-id="0762d-103">Session view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0762d-104">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="0762d-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="0762d-105">セッション ビューには、データベースにレコードがあるセッションに関する情報が保存されます。</span><span class="sxs-lookup"><span data-stu-id="0762d-105">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="0762d-106">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0762d-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0762d-107">Column</span><span class="sxs-lookup"><span data-stu-id="0762d-107">Column</span></span></th>
<th><span data-ttu-id="0762d-108">データ型</span><span class="sxs-lookup"><span data-stu-id="0762d-108">Data Type</span></span></th>
<th><span data-ttu-id="0762d-109">詳細</span><span class="sxs-lookup"><span data-stu-id="0762d-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0762d-110">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="0762d-110">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="0762d-111">日付型</span><span class="sxs-lookup"><span data-stu-id="0762d-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="0762d-112">MediaLine テーブルから参照されます。</span><span class="sxs-lookup"><span data-stu-id="0762d-112">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0762d-113">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="0762d-113">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="0762d-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="0762d-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="0762d-115">これが会議の場合は会議 URI、ピアツーピア セッションの場合は DialogID です。</span><span class="sxs-lookup"><span data-stu-id="0762d-115">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0762d-116">関連付け</span><span class="sxs-lookup"><span data-stu-id="0762d-116">Correlation</span></span></p></td>
<td><p><span data-ttu-id="0762d-117">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="0762d-117">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="0762d-118">セッションの関連付け ID。</span><span class="sxs-lookup"><span data-stu-id="0762d-118">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0762d-119">' このカテゴリ</span><span class="sxs-lookup"><span data-stu-id="0762d-119">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="0762d-120">若干</span><span class="sxs-lookup"><span data-stu-id="0762d-120">bit</span></span></p></td>
<td><p><span data-ttu-id="0762d-121">ダイアログのカテゴリ。0は Lync Server から仲介サーバーまでです。1は仲介サーバーから PSTN ゲートウェイレグになります。</span><span class="sxs-lookup"><span data-stu-id="0762d-121">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0762d-122">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="0762d-122">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="0762d-123">若干</span><span class="sxs-lookup"><span data-stu-id="0762d-123">bit</span></span></p></td>
<td><p><span data-ttu-id="0762d-124">通話がバイパスされたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0762d-124">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0762d-125">Mediabypasswarnings フラグ</span><span class="sxs-lookup"><span data-stu-id="0762d-125">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="0762d-126">int</span><span class="sxs-lookup"><span data-stu-id="0762d-126">int</span></span></p></td>
<td><p><span data-ttu-id="0762d-127">このフィールドは、(存在する場合) バイパス ID が一致したのに通話がバイパスされなかった理由を示します。</span><span class="sxs-lookup"><span data-stu-id="0762d-127">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="0762d-128">Lync Server の場合は、1つの値のみが定義されます。</span><span class="sxs-lookup"><span data-stu-id="0762d-128">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="0762d-129">0x0001 - 既定のネットワーク アダプターのバイパス ID が不明です。</span><span class="sxs-lookup"><span data-stu-id="0762d-129">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0762d-130">StartTime</span><span class="sxs-lookup"><span data-stu-id="0762d-130">StartTime</span></span></p></td>
<td><p><span data-ttu-id="0762d-131">日付型</span><span class="sxs-lookup"><span data-stu-id="0762d-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="0762d-132">通話の開始時刻。</span><span class="sxs-lookup"><span data-stu-id="0762d-132">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0762d-133">EndTime</span><span class="sxs-lookup"><span data-stu-id="0762d-133">EndTime</span></span></p></td>
<td><p><span data-ttu-id="0762d-134">日付型</span><span class="sxs-lookup"><span data-stu-id="0762d-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="0762d-135">通話の終了時刻。</span><span class="sxs-lookup"><span data-stu-id="0762d-135">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0762d-136">CallerPool</span><span class="sxs-lookup"><span data-stu-id="0762d-136">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="0762d-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0762d-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0762d-138">発信者プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="0762d-138">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0762d-139">CalleePool</span><span class="sxs-lookup"><span data-stu-id="0762d-139">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="0762d-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0762d-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0762d-141">呼び出し先プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="0762d-141">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0762d-142">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="0762d-142">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="0762d-143">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="0762d-143">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="0762d-144">発信者の P-Asserted-Identity (PAI) URI。</span><span class="sxs-lookup"><span data-stu-id="0762d-144">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0762d-145">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="0762d-145">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="0762d-146">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="0762d-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="0762d-147">呼び出し先の P-Asserted-Identity (PAI) URI。</span><span class="sxs-lookup"><span data-stu-id="0762d-147">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0762d-148">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="0762d-148">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="0762d-149">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0762d-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0762d-150">発信者のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="0762d-150">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0762d-151">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="0762d-151">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="0762d-152">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0762d-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0762d-153">発信者のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="0762d-153">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0762d-154">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="0762d-154">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="0762d-155">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0762d-155">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0762d-156">発信者のユーザー エージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="0762d-156">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0762d-157">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="0762d-157">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="0762d-158">smallint</span><span class="sxs-lookup"><span data-stu-id="0762d-158">smallint</span></span></p></td>
<td><p><span data-ttu-id="0762d-159">発信者のユーザー エージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="0762d-159">Type of caller’s user agent.</span></span> <span data-ttu-id="0762d-160">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0762d-160">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0762d-161">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="0762d-161">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="0762d-162">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="0762d-162">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="0762d-163">発信者のユーザー エージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="0762d-163">Category of caller’s user agent.</span></span> <span data-ttu-id="0762d-164">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0762d-164">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0762d-165">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="0762d-165">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="0762d-166">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0762d-166">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0762d-167">呼び出し先のユーザー エージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="0762d-167">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0762d-168">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="0762d-168">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="0762d-169">smallint</span><span class="sxs-lookup"><span data-stu-id="0762d-169">smallint</span></span></p></td>
<td><p><span data-ttu-id="0762d-170">呼び出し先のユーザー エージェント タイプ。</span><span class="sxs-lookup"><span data-stu-id="0762d-170">Type of user agent for the callee.</span></span> <span data-ttu-id="0762d-171">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0762d-171">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0762d-172">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="0762d-172">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="0762d-173">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="0762d-173">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="0762d-174">呼び出し先のユーザー エージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="0762d-174">User agent category for the callee.</span></span> <span data-ttu-id="0762d-175">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0762d-175">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0762d-176">CallerURI</span><span class="sxs-lookup"><span data-stu-id="0762d-176">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="0762d-177">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="0762d-177">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="0762d-178">発信者の URI。</span><span class="sxs-lookup"><span data-stu-id="0762d-178">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0762d-179">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="0762d-179">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="0762d-180">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="0762d-180">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="0762d-181">呼び出し先の URI。</span><span class="sxs-lookup"><span data-stu-id="0762d-181">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0762d-182">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="0762d-182">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="0762d-183">int</span><span class="sxs-lookup"><span data-stu-id="0762d-183">int</span></span></p></td>
<td><p><span data-ttu-id="0762d-184">通話の優先順位。</span><span class="sxs-lookup"><span data-stu-id="0762d-184">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

