---
title: 'Lync Server 2013: AudioStreamDetail ビュー'
description: 'Lync Server 2013: AudioStreamDetail ビュー。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStreamDetail view
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49733792
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92c4c9bbb4f126e242e28d835222f6ba2af89d8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573053"
---
# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="ca3e2-103">Lync Server 2013 の AudioStreamDetail ビュー</span><span class="sxs-lookup"><span data-stu-id="ca3e2-103">AudioStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca3e2-104">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="ca3e2-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="ca3e2-105">AudioStreamDetail ビューには、データベース内の各音声ストリームに関する情報が格納されています。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-105">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="ca3e2-106">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca3e2-107">Column</span><span class="sxs-lookup"><span data-stu-id="ca3e2-107">Column</span></span></th>
<th><span data-ttu-id="ca3e2-108">データ型</span><span class="sxs-lookup"><span data-stu-id="ca3e2-108">Data Type</span></span></th>
<th><span data-ttu-id="ca3e2-109">詳細</span><span class="sxs-lookup"><span data-stu-id="ca3e2-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-110">SessionTime</span><span class="sxs-lookup"><span data-stu-id="ca3e2-110">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-111">日付型</span><span class="sxs-lookup"><span data-stu-id="ca3e2-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-112"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-112">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-113">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="ca3e2-113">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-114">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-114">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-115"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-115">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-116">StreamId</span><span class="sxs-lookup"><span data-stu-id="ca3e2-116">StreamId</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-117">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-117">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-118">メディア ライン内の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-118">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-119">StartTime</span><span class="sxs-lookup"><span data-stu-id="ca3e2-119">StartTime</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-120">日付型</span><span class="sxs-lookup"><span data-stu-id="ca3e2-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-121">セッションの開始時刻。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-121">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-122">EndTime</span><span class="sxs-lookup"><span data-stu-id="ca3e2-122">EndTime</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-123">日付型</span><span class="sxs-lookup"><span data-stu-id="ca3e2-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-124">セッションの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-124">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-125">' このカテゴリ</span><span class="sxs-lookup"><span data-stu-id="ca3e2-125">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-126">若干</span><span class="sxs-lookup"><span data-stu-id="ca3e2-126">bit</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-127">ダイアログのカテゴリ: 0 は、仲介サーバーに対する Lync サーバーです。1は、PSTN ゲートウェイレグへの仲介サーバーです。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-127">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-128">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="ca3e2-128">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-129">若干</span><span class="sxs-lookup"><span data-stu-id="ca3e2-129">bit</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-130">通話がバイパスされたかどうかを示すフラグ。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-130">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-131">Mediabypasswarnings フラグ</span><span class="sxs-lookup"><span data-stu-id="ca3e2-131">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-132">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-132">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p102">存在する場合、バイパス ID が一致したのに通話がバイパスされなかった理由を示します。値は 1 つしか定義されていません。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p102">If present, indicates why a call was not bypassed even if the bypass IDs matched. Only one value is defined:</span></span></p>
<p><span data-ttu-id="ca3e2-135">0x0001 - 既定のネットワーク アダプターのバイパス ID が不明です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-135">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-136">CallPriority</span><span class="sxs-lookup"><span data-stu-id="ca3e2-136">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-137">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-137">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-138">通話の優先順位。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-138">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-139">CallerPool</span><span class="sxs-lookup"><span data-stu-id="ca3e2-139">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-141">発信者プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-141">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-142">CalleePool</span><span class="sxs-lookup"><span data-stu-id="ca3e2-142">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-144">呼び出し先プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-144">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-145">Caller</span><span class="sxs-lookup"><span data-stu-id="ca3e2-145">Caller</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-146">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-147">発信者の URI。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-147">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-148">側</span><span class="sxs-lookup"><span data-stu-id="ca3e2-148">Callee</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-149">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-149">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-150">呼び出し先の URI。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-150">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-151">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="ca3e2-151">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-152">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-153">発信者のユーザー エージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-153">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-154">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="ca3e2-154">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-155">smallint</span><span class="sxs-lookup"><span data-stu-id="ca3e2-155">smallint</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-156">発信者のユーザー エージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-156">Type of the caller’s user agent.</span></span> <span data-ttu-id="ca3e2-157">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-157">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-158">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="ca3e2-158">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-159">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-159">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-160">発信者のユーザー エージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-160">Category of the caller’s user agent.</span></span> <span data-ttu-id="ca3e2-161">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-161">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-162">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="ca3e2-162">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-163">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-163">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-164">呼び出し先のユーザー エージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-164">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-165">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="ca3e2-165">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-166">smallint</span><span class="sxs-lookup"><span data-stu-id="ca3e2-166">smallint</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-167">呼び出し先のユーザー エージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-167">Type of callee’s user agent.</span></span> <span data-ttu-id="ca3e2-168">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-168">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-169">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="ca3e2-169">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-170">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-170">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-171">呼び出し先のユーザー エージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-171">Category of callee’s user agent.</span></span> <span data-ttu-id="ca3e2-172">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-172">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-173">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="ca3e2-173">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-175">発信者のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-175">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-176">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="ca3e2-176">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-177">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-177">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-178">呼び出し先のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-178">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-179">CallerOS</span><span class="sxs-lookup"><span data-stu-id="ca3e2-179">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-180">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ca3e2-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-181">発信者のエンドポイントのオペレーティング システム (OS)。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-181">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-182">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="ca3e2-182">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-183">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ca3e2-183">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-184">呼び出し先のエンドポイントのオペレーティング システム (OS)。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-184">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-185">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="ca3e2-185">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-186">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ca3e2-186">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-187">発信者のエンドポイントの CPU 名。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-187">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-188">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="ca3e2-188">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-189">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ca3e2-189">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-190">呼び出し先のエンドポイントの CPU 名。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-190">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-191">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="ca3e2-191">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-192">smallint</span><span class="sxs-lookup"><span data-stu-id="ca3e2-192">smallint</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-193">発信者のエンドポイントの CPU コアの数。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-193">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-194">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="ca3e2-194">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-195">smallint</span><span class="sxs-lookup"><span data-stu-id="ca3e2-195">smallint</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-196">呼び出し先のエンドポイントの CPU コアの数。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-196">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-197">Callercpu プロセッサ速度</span><span class="sxs-lookup"><span data-stu-id="ca3e2-197">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-198">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-198">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-199">発信者のエンドポイントの CPU プロセッサ速度。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-199">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-200">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="ca3e2-200">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-201">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-201">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-202">呼び出し先のエンドポイントの CPU プロセッサ速度。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-202">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-203">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="ca3e2-203">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-204">tinyint</span><span class="sxs-lookup"><span data-stu-id="ca3e2-204">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-205">発信者のシステムが仮想環境で実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-205">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="ca3e2-206">詳細については、「 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-206">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-207">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="ca3e2-207">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-208">tinyint</span><span class="sxs-lookup"><span data-stu-id="ca3e2-208">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-209">呼び出し先のシステムが仮想環境で実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-209">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="ca3e2-210">詳細については、「 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-210">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-211">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="ca3e2-211">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ca3e2-212">関連付けキー。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-212">Correlation key.</span></span> <span data-ttu-id="ca3e2-213"><a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 の Sessioncorrelation テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-213">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-214">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="ca3e2-214">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-215">tinyint</span><span class="sxs-lookup"><span data-stu-id="ca3e2-215">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-216">メディア パスに関する情報 (直接、リレーなど)。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-216">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="ca3e2-217">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-217">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-218">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="ca3e2-218">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-219">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-219">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p111">発信者のビット フラグに記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-222">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="ca3e2-222">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-223">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-223">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p112">呼び出し先のビット フラグに記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-226">Transport</span><span class="sxs-lookup"><span data-stu-id="ca3e2-226">Transport</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-227">tinyint</span><span class="sxs-lookup"><span data-stu-id="ca3e2-227">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-228">トランスポートの種類。0 は UDP、1 は TCP です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-228">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-229">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="ca3e2-229">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-230">var (50)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-230">var(50)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-231">発信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-231">IP address of the caller.</span></span> <span data-ttu-id="ca3e2-232">IPv4 または IPv6 のアドレスです。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-232">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-233">CallerPort</span><span class="sxs-lookup"><span data-stu-id="ca3e2-233">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-234">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-234">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-235">発信者が使用するポート。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-235">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-236">CallerInside</span><span class="sxs-lookup"><span data-stu-id="ca3e2-236">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-237">若干</span><span class="sxs-lookup"><span data-stu-id="ca3e2-237">bit</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-238">発信者がインターバル ネットワーク内にいるかどうかを示します。1 は、発信者がエンタープライズ ネットワーク内に存在することを示し、0 は、発信者がネットワーク外に存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-238">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-239">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="ca3e2-239">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-240">var (50)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-240">var(50)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-241">呼び出し先の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-241">IP address of the callee.</span></span> <span data-ttu-id="ca3e2-242">IPv4 または IPv6 のアドレスです。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-242">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-243">CalleePort</span><span class="sxs-lookup"><span data-stu-id="ca3e2-243">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-244">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-244">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-245">呼び出し先が使用するポート。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-245">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-246">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="ca3e2-246">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-247">若干</span><span class="sxs-lookup"><span data-stu-id="ca3e2-247">bit</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-248">呼び出し先がインターバル ネットワーク内にいるかどうかを示します。1 は、呼び出し先がエンタープライズ ネットワーク内に存在することを示し、0 は、呼び出し先がネットワーク外に存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-248">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-249">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="ca3e2-249">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-250">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ca3e2-250">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-251">発信者のサイトの名前。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-251">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-252">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="ca3e2-252">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-253">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ca3e2-253">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-254">発信者のサイトの国/地域の名前。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-254">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-255">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="ca3e2-255">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-256">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ca3e2-256">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-257">呼び出し先のサイトの名前。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-257">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-258">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="ca3e2-258">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-259">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ca3e2-259">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-260">呼び出し先のサイトの国/地域の名前。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-260">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-261">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="ca3e2-261">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-262">var (50)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-262">var(50)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-263">発信者が使用する音声ビデオ エッジ サービスの IPアドレス。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-263">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="ca3e2-264">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-264">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-265">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="ca3e2-265">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-266">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-266">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-267">発信者が使用する音声ビデオ エッジ サービスで使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-267">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-268">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="ca3e2-268">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-269">var (50)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-269">var(50)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-270">呼び出し先が使用する音声ビデオ エッジ サービスの IPアドレス キー。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-270">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="ca3e2-271">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-271">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-272">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="ca3e2-272">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-273">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-273">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-274">呼び出し先が使用する音声ビデオ エッジ サービスで使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-274">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-275">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="ca3e2-275">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-276">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-276">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-277">発信者のキャプチャ デバイス名。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-277">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-278">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="ca3e2-278">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-279">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-279">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-280">発信者のレンダー デバイス名。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-280">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-281">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="ca3e2-281">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-282">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-282">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-283">発信者のキャプチャ デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-283">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-284">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="ca3e2-284">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-285">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-285">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-286">発信者のレンダー デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-286">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-287">Calleecapのアーキテクチャ開発</span><span class="sxs-lookup"><span data-stu-id="ca3e2-287">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-288">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-288">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-289">呼び出し先のキャプチャ デバイス名。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-289">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-290">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="ca3e2-290">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-291">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-291">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-292">呼び出し先のレンダー デバイス名。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-292">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-293">Calleecapアーキテクチャ Devdriver</span><span class="sxs-lookup"><span data-stu-id="ca3e2-293">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-294">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-294">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-295">呼び出し先のキャプチャ デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-295">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-296">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="ca3e2-296">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-297">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-297">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-298">呼び出し先のレンダー デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-298">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-299">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="ca3e2-299">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-300">tinyint</span><span class="sxs-lookup"><span data-stu-id="ca3e2-300">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-301">発信者のネットワーク接続の種類。0 は有線、1 はワイヤレスです。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-301">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-302">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="ca3e2-302">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-303">若干</span><span class="sxs-lookup"><span data-stu-id="ca3e2-303">bit</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-304">発信者が仮想プライベート ネットワークで接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-304">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-305">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="ca3e2-305">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-306">10進数 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-307">発信者のエンドポイントのネットワーク リンクの速度 (単位 bps)。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-307">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-308">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="ca3e2-308">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-309">tinyint</span><span class="sxs-lookup"><span data-stu-id="ca3e2-309">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-310">呼び出し先のネットワーク接続の種類。0 は有線、1 はワイヤレスです。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-310">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-311">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="ca3e2-311">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-312">若干</span><span class="sxs-lookup"><span data-stu-id="ca3e2-312">bit</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-313">発信者が仮想プライベート ネットワークで接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-313">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-314">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="ca3e2-314">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-315">10進数 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-315">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-316">呼び出し先のエンドポイントのネットワーク リンクの速度 (単位 bps)。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-316">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-317">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="ca3e2-317">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-318">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-318">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-319">音声セッションの Narrowband Conversational MOS (音声ストリームに基づく)。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-319">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-320">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="ca3e2-320">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-321">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-321">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p117">さまざまなポリシー設定 (TURN、API、SDP、ポリシー サーバーなど) が構成された特定の送信側ストリームに適用される実際の帯域幅。この帯域幅を実効帯域幅と見なすことはできません。実効帯域幅は、帯域幅の評価に基づいて実際よりも低くなる可能性があります。これは基本的に、送信ストリームで利用できる最大帯域幅です (帯域幅の評価によって課せられる制限を除く)。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p117">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-325">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="ca3e2-325">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-326">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-326">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-327">リアルタイム制御プロトコル (RTCP) 統計情報に基づく平均ネットワーク ジッター。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-327">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-328">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="ca3e2-328">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-329">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-329">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-330">通話時の最大ネットワーク ジッター。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-330">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-331">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="ca3e2-331">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-332">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-333">通話時の平均パケット損失率。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-333">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-334">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="ca3e2-334">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-335">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-335">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-336">通話時に観測された最大パケット損失。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-336">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-337">BurstDensity</span><span class="sxs-lookup"><span data-stu-id="ca3e2-337">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-338">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-338">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-339">通話時の損失のバーストで発生したパケット損失の平均密度。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-339">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-340">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="ca3e2-340">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-341">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-341">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-342">通話時の損失のバーストで発生したパケット損失の平均期間。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-342">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-343">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="ca3e2-343">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-344">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-344">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-345">パケット損失のバーストが発生して次のバーストが発生するまでの間に発生したパケット損失の平均密度。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-345">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-346">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="ca3e2-346">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-347">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-347">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-348">パケット損失のバーストが発生して次のバーストが発生するまでの平均期間。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-348">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-349">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="ca3e2-349">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-350">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-350">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-351">音声ストリームのパケット数。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-351">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-352">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="ca3e2-352">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-353">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-353">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-354">音声ストリームの帯域幅の推定。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-354">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-355">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="ca3e2-355">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-356">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-356">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p118">通話全体でのネットワーク MOS の低下。範囲は 0.0 ～ 5.0 です。この指標は、ジッターとパケット損失に起因する、ネットワーク MOS の低下量を示します。許容範囲に収まる程度の品質を維持するには、この値は 0.5 未満である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p118">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-361">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="ca3e2-361">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-362">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-362">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-363">通話時のネットワーク MOS の最大低下。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-363">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-364">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="ca3e2-364">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-365">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-365">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-366">ジッターに起因するネットワーク MOS の低下。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-366">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-367">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="ca3e2-367">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-368">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-368">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-369">パケット損失に起因するネットワーク MOS の低下。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-369">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-370">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="ca3e2-370">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-371">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-371">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-372">通話に使用されるオーディオコーデック。 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 の PayloadDescription テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-372">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-373">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="ca3e2-373">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-374">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-374">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-375">音声ストリームのサンプリング レート。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-375">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-376">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="ca3e2-376">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-377">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-377">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p119">発信者が送信した音声のアナログ後ゲイン制御のオーディオ信号レベル。この測定指標の単位は dBmo です。許容される品質は 30 dBmo 以上です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p119">Post-Analog Gain Control audio signal level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-382">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="ca3e2-382">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-383">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-383">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p120">発信者が受信した音声のオーディオ信号レベル。この測定指標の単位は dBmo です。許容される品質は 30 dBmo 以上です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p120">Audio signal level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-388">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="ca3e2-388">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-389">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-389">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p121">発信者が送信した音声のアナログ後ゲイン制御のオーディオ ノイズ レベル。この測定指標の単位は dBmo です。許容される品質は 35 dBmo 未満です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p121">Post-Analog Gain Control audio noise level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-394">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="ca3e2-394">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-395">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-395">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p122">発信者が受信した音声のアナログ後ゲイン制御のオーディオ ノイズ レベル。この測定指標の単位は dBmo です。許容される品質は 35 dBmo 未満です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p122">Post-Analog Gain Control audio noise level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-400">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="ca3e2-400">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-401">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-401">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p123">発信者のエコー リターン ロス エンハンスメント。この測定指標の単位は dB です。値が小さいほど、エコーが少ないことを示します。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p123">Echo Return Loss Enhancement for the caller. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-406">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="ca3e2-406">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-407">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-407">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p124">発信者のラウドスピーカー出力での 5 分間の平均障害回数です。良好な品質といえるのは、5 分間に 1 回未満です。音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p124">Average glitches per five minutes for the caller’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-411">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="ca3e2-411">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-412">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-412">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p125">発信者のマイク キャプチャでの 5 分間の平均障害回数です。良好な品質といえるのは、5 分間に 1 回未満です。音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p125">Average glitches per five minutes for the caller’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-416">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="ca3e2-416">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-417">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-417">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-418">CPU クロックに対する発信者のマイク デバイスのクロック誤差の割合です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-418">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-419">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="ca3e2-419">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-420">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-420">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-421">CPU クロックに対する発信者のスピーカー デバイスのクロック誤差の割合です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-421">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-422">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="ca3e2-422">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-423">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-423">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-424">過去 20 秒間の通話での平均マイク キャプチャ ストリーム タイム スタンプ エラーです (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-424">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-425">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="ca3e2-425">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-426">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-426">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-427">過去 20 秒間の通話での発信者のスピーカー出力ストリーム タイム スタンプ エラーの平均です (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-427">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-428">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="ca3e2-428">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-429">smallint</span><span class="sxs-lookup"><span data-stu-id="ca3e2-429">smallint</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-430">音声スイッチは、遮断能力が低下した半二重モードです。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-430">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="ca3e2-431">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-431">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-432">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="ca3e2-432">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-433">tinyint</span><span class="sxs-lookup"><span data-stu-id="ca3e2-433">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-434">発信者のエコー イベントの原因です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-434">Causes of an echo event for the caller.</span></span> <span data-ttu-id="ca3e2-435">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-435">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-436">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="ca3e2-436">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-437">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-437">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p128">発信者のマイク キャプチャ ストリームでエコーが検出された時間の割合です。ヘッドセットを使用している場合は、この値が低い必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p128">Percentage of time when echo is detected in the caller’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-440">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="ca3e2-440">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-441">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-441">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p129">発信者の送信ストリームでエコーが検出された時間の割合です。送信ストリームでの高いエコー率は、エコー リークを示しています。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p129">Percentage of time when echo is detected in the caller’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-444">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="ca3e2-444">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-445">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-445">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p130">仲介サーバーでのゲートウェイからの発信者の音声についての受信信号レベルです。この値は、仲介サーバーに対してのみ適用されます。この測定指標の単位は dBoV です。良好な品質として許容される範囲は、-30 ～ -18 dBoV です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p130">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-449">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="ca3e2-449">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-450">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-450">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p131">仲介サーバーでのゲートウェイからの発信者の音声についての受信信号レベルです。この値は、仲介サーバーに対してのみ適用されます。この測定指標の単位は dBoV です。良好な品質として許容される範囲は、-50 dBoV 未満です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p131">Received signal level on the Mediation Server from the Gateway for the caller’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-455">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="ca3e2-455">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-456">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-456">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-457">発信者の音声に対して適用される、仲介サーバー側での自動ゲイン制御 (AGC) です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-457">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-458">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="ca3e2-458">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-459">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="ca3e2-459">float</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-460">通話の最初の最大 30 秒間における発信者に対する着信信号の二重平均 (RMS) です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-460">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-461">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="ca3e2-461">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-462">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-462">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p132">呼び出し先が送信した音声のアナログ後ゲイン制御のオーディオ信号レベルを表します。この測定指標の単位は dBmo です。許容される品質は 30 dBmo 以上です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p132">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-467">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="ca3e2-467">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-468">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-468">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p133">呼び出し先が受信した音声のオーディオ信号レベル。この測定指標の単位は dBmo です。許容される品質は 30 dBmo 以上です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p133">Audio signal level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-473">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="ca3e2-473">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-474">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-474">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p134">呼び出し先が送信した音声のアナログ後ゲイン制御のオーディオ ノイズ レベル。この測定指標の単位は dBmo です。許容される品質は 35 dBmo 未満です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p134">Post-Analog Gain Control audio noise level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-479">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="ca3e2-479">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-480">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-480">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p135">呼び出し先が受信した音声のアナログ後ゲイン制御のオーディオ ノイズ レベル。この測定指標の単位は dBmo です。許容される品質は 35 dBmo 未満です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p135">Post-Analog Gain Control audio noise level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-485">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="ca3e2-485">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-486">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-486">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p136">呼び出し先のエコー リターン ロス エンハンスメント。この測定指標の単位は dB です。値が小さいほど、エコーが少ないことを示します。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p136">Echo Return Loss Enhancement for the callee. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-491">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="ca3e2-491">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-492">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-492">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p137">呼び出し先のラウドスピーカー出力での 5 分間の平均障害回数です。良好な品質といえるのは、5 分間に 1 回未満です。音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p137">Average glitches per five minutes for the callee’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-496">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="ca3e2-496">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-497">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-497">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p138">呼び出し先のマイク キャプチャでの 5 分間の平均障害回数です。良好な品質といえるのは、5 分間に 1 回未満です。音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p138">Average glitches per five minutes for the callee’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-501">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="ca3e2-501">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-502">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-502">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-503">CPU クロックに対する呼び出し先のマイク デバイスのクロック誤差の割合です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-503">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-504">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="ca3e2-504">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-505">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-505">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-506">CPU クロックに対する呼び出し先のスピーカー デバイスのクロック誤差の割合です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-506">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-507">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="ca3e2-507">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-508">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-508">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-509">過去 20 秒間の通話での平均マイク キャプチャ ストリーム タイム スタンプ エラーです (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-509">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-510">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="ca3e2-510">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-511">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-511">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-512">過去 20 秒間の通話での呼び出し先のスピーカー出力ストリーム タイム スタンプ エラーの平均です (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-512">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-513">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="ca3e2-513">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-514">smallint</span><span class="sxs-lookup"><span data-stu-id="ca3e2-514">smallint</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-515">音声スイッチは、遮断能力が低下した半二重モードです。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-515">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="ca3e2-516">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-516">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-517">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="ca3e2-517">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-518">tinyint</span><span class="sxs-lookup"><span data-stu-id="ca3e2-518">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-519">呼び出し先のエコー イベントの原因です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-519">Causes of an echo event for the callee.</span></span> <span data-ttu-id="ca3e2-520">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-520">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-521">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="ca3e2-521">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-522">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-522">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p141">呼び出し先のマイク キャプチャ ストリームでエコーが検出された時間の割合です。ヘッドセットを使用している場合は、この値が低い必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p141">Percentage of time when echo is detected in the callee’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-525">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="ca3e2-525">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-526">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-526">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p142">呼び出し先の送信ストリームでエコーが検出された時間の割合です。送信ストリームでの高いエコー率は、エコー リークを示しています。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p142">Percentage of time when echo is detected in the callee’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-529">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="ca3e2-529">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-530">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-530">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p143">仲介サーバーでのゲートウェイからの呼び出し先の音声についての受信信号レベルです。この値は、仲介サーバーに対してのみ適用されます。この測定指標の単位は dBoV です。良好な品質として許容される範囲は、-30 ～ -18 dBoV です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p143">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-534">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="ca3e2-534">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-535">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-535">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p144">仲介サーバーでのゲートウェイからの呼び出し先の音声についての受信信号レベルです。この値は、仲介サーバーに対してのみ適用されます。この測定指標の単位は dBoV です。良好な品質として許容される範囲は、-50 dBoV 未満です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p144">Received signal level on the Mediation Server from the Gateway for the callee’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-540">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="ca3e2-540">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-541">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-541">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-542">呼び出し先の音声に対して適用される、仲介サーバー側での自動ゲイン制御 (AGC) です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-542">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-543">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="ca3e2-543">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-544">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="ca3e2-544">float</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-545">通話の最初の最大 30 秒間における呼び出し先に対する着信信号の二重平均 (RMS) です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-545">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-546">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="ca3e2-546">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-547">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-547">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-548">標準サンプルへの音声復旧によって生成される隠しサンプルの平均比率。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-548">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-549">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="ca3e2-549">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-550">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-550">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-551">標準サンプルへの音声復旧によって生成される引き伸ばしサンプルの平均比率。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-551">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-552">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="ca3e2-552">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-553">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-553">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-554">標準サンプルへの音声復旧によって生成される圧縮サンプルの平均比率。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-554">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-555">要し</span><span class="sxs-lookup"><span data-stu-id="ca3e2-555">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-556">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-556">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-557">RTCP 統計情報に基づく往復時間。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-557">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-558">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="ca3e2-558">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-559">int</span><span class="sxs-lookup"><span data-stu-id="ca3e2-559">int</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-560">音声ストリームの最大往復時間。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-560">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-561">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="ca3e2-561">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-562">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-562">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-p145">通話の広帯域ネットワーク MOS の平均値。この指標は、パケット損失、ジッター、および使用されるコーデックによって異なります。範囲は 1.0 ～ 5.0 です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-p145">Average wideband Network MOS for the call. This metric depends on the packet loss, jitter, and codec used. Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-566">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="ca3e2-566">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-567">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-567">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-568">通話の広帯域ネットワーク MOS の最小値。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-568">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-569">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="ca3e2-569">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-570">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-570">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-571">スピーチ レベル、ノイズ レベル、キャプチャ デバイス特性など、送信される音声の広帯域受聴 MOS スコアの平均予測値。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-571">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-572">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="ca3e2-572">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-573">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-573">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-574">通話の SendListenMOS の最小値。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-574">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-575">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="ca3e2-575">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-576">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-576">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-577">スピーチ レベル、ノイズ レベル、キャプチャ デバイス特性など、ネットワークから受信される音声の広帯域受聴 MOS スコアの平均予測値。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-577">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-578">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="ca3e2-578">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-579">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-579">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-580">通話の RecvListenMOS の最小値。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-580">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca3e2-581">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="ca3e2-581">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-582">若干</span><span class="sxs-lookup"><span data-stu-id="ca3e2-582">bit</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-583">音声 FEC が通話で使用されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-583">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca3e2-584">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="ca3e2-584">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-585">若干</span><span class="sxs-lookup"><span data-stu-id="ca3e2-585">bit</span></span></p></td>
<td><p><span data-ttu-id="ca3e2-586">P-Asserted Identity 情報の方向を示します。1 は、ストリームの方向が発信者から呼び出し先へ向かうことを意味します。0 は、ストリームの方向が呼び出し先から発信者へ向かうことを意味します。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-586">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

