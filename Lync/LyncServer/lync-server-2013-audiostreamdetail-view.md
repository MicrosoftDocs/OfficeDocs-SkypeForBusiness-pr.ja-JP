---
title: 'Lync Server 2013: AudioStreamDetail ビュー'
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
ms.openlocfilehash: 4a9abfbc214e72cf059250910ecec4ad3bcdba33
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515784"
---
# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="0c23b-102">Lync Server 2013 の AudioStreamDetail ビュー</span><span class="sxs-lookup"><span data-stu-id="0c23b-102">AudioStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c23b-103">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="0c23b-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="0c23b-104">AudioStreamDetail ビューには、データベース内の各音声ストリームに関する情報が格納されています。</span><span class="sxs-lookup"><span data-stu-id="0c23b-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="0c23b-105">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0c23b-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c23b-106">Column</span><span class="sxs-lookup"><span data-stu-id="0c23b-106">Column</span></span></th>
<th><span data-ttu-id="0c23b-107">データ型</span><span class="sxs-lookup"><span data-stu-id="0c23b-107">Data Type</span></span></th>
<th><span data-ttu-id="0c23b-108">詳細</span><span class="sxs-lookup"><span data-stu-id="0c23b-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="0c23b-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="0c23b-110">日付型</span><span class="sxs-lookup"><span data-stu-id="0c23b-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="0c23b-111"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="0c23b-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="0c23b-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="0c23b-113">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-113">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-114"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="0c23b-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-115">StreamId</span><span class="sxs-lookup"><span data-stu-id="0c23b-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="0c23b-116">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-116">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-117">メディア ライン内の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="0c23b-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-118">StartTime</span><span class="sxs-lookup"><span data-stu-id="0c23b-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="0c23b-119">日付型</span><span class="sxs-lookup"><span data-stu-id="0c23b-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="0c23b-120">セッションの開始時刻。</span><span class="sxs-lookup"><span data-stu-id="0c23b-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="0c23b-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="0c23b-122">日付型</span><span class="sxs-lookup"><span data-stu-id="0c23b-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="0c23b-123">セッションの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="0c23b-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-124">' このカテゴリ</span><span class="sxs-lookup"><span data-stu-id="0c23b-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="0c23b-125">若干</span><span class="sxs-lookup"><span data-stu-id="0c23b-125">bit</span></span></p></td>
<td><p><span data-ttu-id="0c23b-126">ダイアログのカテゴリ: 0 は、仲介サーバーに対する Lync サーバーです。1は、PSTN ゲートウェイレグへの仲介サーバーです。</span><span class="sxs-lookup"><span data-stu-id="0c23b-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-127">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="0c23b-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="0c23b-128">若干</span><span class="sxs-lookup"><span data-stu-id="0c23b-128">bit</span></span></p></td>
<td><p><span data-ttu-id="0c23b-129">通話がバイパスされたかどうかを示すフラグ。</span><span class="sxs-lookup"><span data-stu-id="0c23b-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-130">Mediabypasswarnings フラグ</span><span class="sxs-lookup"><span data-stu-id="0c23b-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="0c23b-131">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-131">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p102">存在する場合、バイパス ID が一致したのに通話がバイパスされなかった理由を示します。値は 1 つしか定義されていません。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p102">If present, indicates why a call was not bypassed even if the bypass IDs matched. Only one value is defined:</span></span></p>
<p><span data-ttu-id="0c23b-134">0x0001 - 既定のネットワーク アダプターのバイパス ID が不明です。</span><span class="sxs-lookup"><span data-stu-id="0c23b-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-135">CallPriority</span><span class="sxs-lookup"><span data-stu-id="0c23b-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="0c23b-136">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-136">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-137">通話の優先順位。</span><span class="sxs-lookup"><span data-stu-id="0c23b-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-138">CallerPool</span><span class="sxs-lookup"><span data-stu-id="0c23b-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="0c23b-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0c23b-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-140">発信者プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="0c23b-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-141">CalleePool</span><span class="sxs-lookup"><span data-stu-id="0c23b-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="0c23b-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0c23b-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-143">呼び出し先プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="0c23b-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-144">Caller</span><span class="sxs-lookup"><span data-stu-id="0c23b-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="0c23b-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="0c23b-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-146">発信者の URI。</span><span class="sxs-lookup"><span data-stu-id="0c23b-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-147">側</span><span class="sxs-lookup"><span data-stu-id="0c23b-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="0c23b-148">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="0c23b-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-149">呼び出し先の URI。</span><span class="sxs-lookup"><span data-stu-id="0c23b-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-150">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="0c23b-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="0c23b-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0c23b-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-152">発信者のユーザー エージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="0c23b-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-153">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="0c23b-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="0c23b-154">smallint</span><span class="sxs-lookup"><span data-stu-id="0c23b-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="0c23b-155">発信者のユーザー エージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="0c23b-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="0c23b-156">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c23b-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-157">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="0c23b-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="0c23b-158">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="0c23b-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-159">発信者のユーザー エージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="0c23b-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="0c23b-160">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c23b-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-161">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="0c23b-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="0c23b-162">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0c23b-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-163">呼び出し先のユーザー エージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="0c23b-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-164">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="0c23b-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="0c23b-165">smallint</span><span class="sxs-lookup"><span data-stu-id="0c23b-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="0c23b-166">呼び出し先のユーザー エージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="0c23b-166">Type of callee’s user agent.</span></span> <span data-ttu-id="0c23b-167">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c23b-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-168">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="0c23b-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="0c23b-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="0c23b-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-170">呼び出し先のユーザー エージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="0c23b-170">Category of callee’s user agent.</span></span> <span data-ttu-id="0c23b-171">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c23b-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-172">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="0c23b-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="0c23b-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0c23b-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-174">発信者のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="0c23b-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-175">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="0c23b-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="0c23b-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0c23b-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-177">呼び出し先のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="0c23b-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-178">CallerOS</span><span class="sxs-lookup"><span data-stu-id="0c23b-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="0c23b-179">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0c23b-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-180">発信者のエンドポイントのオペレーティング システム (OS)。</span><span class="sxs-lookup"><span data-stu-id="0c23b-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-181">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="0c23b-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="0c23b-182">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0c23b-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-183">呼び出し先のエンドポイントのオペレーティング システム (OS)。</span><span class="sxs-lookup"><span data-stu-id="0c23b-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-184">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="0c23b-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="0c23b-185">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0c23b-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-186">発信者のエンドポイントの CPU 名。</span><span class="sxs-lookup"><span data-stu-id="0c23b-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-187">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="0c23b-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="0c23b-188">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0c23b-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-189">呼び出し先のエンドポイントの CPU 名。</span><span class="sxs-lookup"><span data-stu-id="0c23b-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-190">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="0c23b-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="0c23b-191">smallint</span><span class="sxs-lookup"><span data-stu-id="0c23b-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="0c23b-192">発信者のエンドポイントの CPU コアの数。</span><span class="sxs-lookup"><span data-stu-id="0c23b-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-193">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="0c23b-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="0c23b-194">smallint</span><span class="sxs-lookup"><span data-stu-id="0c23b-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="0c23b-195">呼び出し先のエンドポイントの CPU コアの数。</span><span class="sxs-lookup"><span data-stu-id="0c23b-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-196">Callercpu プロセッサ速度</span><span class="sxs-lookup"><span data-stu-id="0c23b-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="0c23b-197">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-197">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-198">発信者のエンドポイントの CPU プロセッサ速度。</span><span class="sxs-lookup"><span data-stu-id="0c23b-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-199">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="0c23b-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="0c23b-200">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-200">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-201">呼び出し先のエンドポイントの CPU プロセッサ速度。</span><span class="sxs-lookup"><span data-stu-id="0c23b-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-202">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="0c23b-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="0c23b-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="0c23b-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0c23b-204">発信者のシステムが仮想環境で実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0c23b-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="0c23b-205">詳細については、「 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c23b-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-206">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="0c23b-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="0c23b-207">tinyint</span><span class="sxs-lookup"><span data-stu-id="0c23b-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0c23b-208">呼び出し先のシステムが仮想環境で実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0c23b-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="0c23b-209">詳細については、「 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c23b-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-210">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="0c23b-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0c23b-211">関連付けキー。</span><span class="sxs-lookup"><span data-stu-id="0c23b-211">Correlation key.</span></span> <span data-ttu-id="0c23b-212"><a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 の Sessioncorrelation テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="0c23b-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-213">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="0c23b-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="0c23b-214">tinyint</span><span class="sxs-lookup"><span data-stu-id="0c23b-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0c23b-215">メディア パスに関する情報 (直接、リレーなど)。</span><span class="sxs-lookup"><span data-stu-id="0c23b-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="0c23b-216">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c23b-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-217">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="0c23b-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="0c23b-218">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-218">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p111">発信者のビット フラグに記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-221">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="0c23b-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="0c23b-222">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-222">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p112">呼び出し先のビット フラグに記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-225">Transport</span><span class="sxs-lookup"><span data-stu-id="0c23b-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="0c23b-226">tinyint</span><span class="sxs-lookup"><span data-stu-id="0c23b-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0c23b-227">トランスポートの種類。0 は UDP、1 は TCP です。</span><span class="sxs-lookup"><span data-stu-id="0c23b-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-228">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="0c23b-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="0c23b-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="0c23b-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-230">発信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="0c23b-230">IP address of the caller.</span></span> <span data-ttu-id="0c23b-231">IPv4 または IPv6 のアドレスです。</span><span class="sxs-lookup"><span data-stu-id="0c23b-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-232">CallerPort</span><span class="sxs-lookup"><span data-stu-id="0c23b-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="0c23b-233">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-233">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-234">発信者が使用するポート。</span><span class="sxs-lookup"><span data-stu-id="0c23b-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-235">CallerInside</span><span class="sxs-lookup"><span data-stu-id="0c23b-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="0c23b-236">若干</span><span class="sxs-lookup"><span data-stu-id="0c23b-236">bit</span></span></p></td>
<td><p><span data-ttu-id="0c23b-237">発信者がインターバル ネットワーク内にいるかどうかを示します。1 は、発信者がエンタープライズ ネットワーク内に存在することを示し、0 は、発信者がネットワーク外に存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="0c23b-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-238">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="0c23b-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="0c23b-239">var (50)</span><span class="sxs-lookup"><span data-stu-id="0c23b-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-240">呼び出し先の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="0c23b-240">IP address of the callee.</span></span> <span data-ttu-id="0c23b-241">IPv4 または IPv6 のアドレスです。</span><span class="sxs-lookup"><span data-stu-id="0c23b-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-242">CalleePort</span><span class="sxs-lookup"><span data-stu-id="0c23b-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="0c23b-243">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-243">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-244">呼び出し先が使用するポート。</span><span class="sxs-lookup"><span data-stu-id="0c23b-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-245">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="0c23b-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="0c23b-246">若干</span><span class="sxs-lookup"><span data-stu-id="0c23b-246">bit</span></span></p></td>
<td><p><span data-ttu-id="0c23b-247">呼び出し先がインターバル ネットワーク内にいるかどうかを示します。1 は、呼び出し先がエンタープライズ ネットワーク内に存在することを示し、0 は、呼び出し先がネットワーク外に存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="0c23b-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-248">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="0c23b-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="0c23b-249">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0c23b-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-250">発信者のサイトの名前。</span><span class="sxs-lookup"><span data-stu-id="0c23b-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-251">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="0c23b-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="0c23b-252">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0c23b-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-253">発信者のサイトの国/地域の名前。</span><span class="sxs-lookup"><span data-stu-id="0c23b-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-254">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="0c23b-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="0c23b-255">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0c23b-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-256">呼び出し先のサイトの名前。</span><span class="sxs-lookup"><span data-stu-id="0c23b-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-257">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="0c23b-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="0c23b-258">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0c23b-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-259">呼び出し先のサイトの国/地域の名前。</span><span class="sxs-lookup"><span data-stu-id="0c23b-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-260">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="0c23b-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="0c23b-261">var (50)</span><span class="sxs-lookup"><span data-stu-id="0c23b-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-262">発信者が使用する音声ビデオ エッジ サービスの IPアドレス。</span><span class="sxs-lookup"><span data-stu-id="0c23b-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="0c23b-263">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c23b-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-264">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="0c23b-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="0c23b-265">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-265">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-266">発信者が使用する音声ビデオ エッジ サービスで使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="0c23b-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-267">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="0c23b-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="0c23b-268">var (50)</span><span class="sxs-lookup"><span data-stu-id="0c23b-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-269">呼び出し先が使用する音声ビデオ エッジ サービスの IPアドレス キー。</span><span class="sxs-lookup"><span data-stu-id="0c23b-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="0c23b-270">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c23b-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-271">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="0c23b-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="0c23b-272">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-272">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-273">呼び出し先が使用する音声ビデオ エッジ サービスで使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="0c23b-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-274">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="0c23b-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="0c23b-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="0c23b-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-276">発信者のキャプチャ デバイス名。</span><span class="sxs-lookup"><span data-stu-id="0c23b-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-277">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="0c23b-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="0c23b-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="0c23b-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-279">発信者のレンダー デバイス名。</span><span class="sxs-lookup"><span data-stu-id="0c23b-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-280">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="0c23b-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="0c23b-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="0c23b-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-282">発信者のキャプチャ デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="0c23b-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-283">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="0c23b-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="0c23b-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="0c23b-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-285">発信者のレンダー デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="0c23b-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-286">Calleecapのアーキテクチャ開発</span><span class="sxs-lookup"><span data-stu-id="0c23b-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="0c23b-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="0c23b-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-288">呼び出し先のキャプチャ デバイス名。</span><span class="sxs-lookup"><span data-stu-id="0c23b-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-289">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="0c23b-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="0c23b-290">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="0c23b-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-291">呼び出し先のレンダー デバイス名。</span><span class="sxs-lookup"><span data-stu-id="0c23b-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-292">Calleecapアーキテクチャ Devdriver</span><span class="sxs-lookup"><span data-stu-id="0c23b-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="0c23b-293">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="0c23b-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-294">呼び出し先のキャプチャ デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="0c23b-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-295">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="0c23b-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="0c23b-296">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="0c23b-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-297">呼び出し先のレンダー デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="0c23b-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-298">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="0c23b-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="0c23b-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="0c23b-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0c23b-300">発信者のネットワーク接続の種類。0 は有線、1 はワイヤレスです。</span><span class="sxs-lookup"><span data-stu-id="0c23b-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-301">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="0c23b-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="0c23b-302">若干</span><span class="sxs-lookup"><span data-stu-id="0c23b-302">bit</span></span></p></td>
<td><p><span data-ttu-id="0c23b-303">発信者が仮想プライベート ネットワークで接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="0c23b-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-304">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="0c23b-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="0c23b-305">10進数 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="0c23b-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-306">発信者のエンドポイントのネットワーク リンクの速度 (単位 bps)。</span><span class="sxs-lookup"><span data-stu-id="0c23b-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-307">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="0c23b-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="0c23b-308">tinyint</span><span class="sxs-lookup"><span data-stu-id="0c23b-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0c23b-309">呼び出し先のネットワーク接続の種類。0 は有線、1 はワイヤレスです。</span><span class="sxs-lookup"><span data-stu-id="0c23b-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-310">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="0c23b-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="0c23b-311">若干</span><span class="sxs-lookup"><span data-stu-id="0c23b-311">bit</span></span></p></td>
<td><p><span data-ttu-id="0c23b-312">発信者が仮想プライベート ネットワークで接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="0c23b-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-313">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="0c23b-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="0c23b-314">10進数 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="0c23b-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-315">呼び出し先のエンドポイントのネットワーク リンクの速度 (単位 bps)。</span><span class="sxs-lookup"><span data-stu-id="0c23b-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-316">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="0c23b-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="0c23b-317">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-318">音声セッションの Narrowband Conversational MOS (音声ストリームに基づく)。</span><span class="sxs-lookup"><span data-stu-id="0c23b-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-319">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="0c23b-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="0c23b-320">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-320">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p117">さまざまなポリシー設定 (TURN、API、SDP、ポリシー サーバーなど) が構成された特定の送信側ストリームに適用される実際の帯域幅。この帯域幅を実効帯域幅と見なすことはできません。実効帯域幅は、帯域幅の評価に基づいて実際よりも低くなる可能性があります。これは基本的に、送信ストリームで利用できる最大帯域幅です (帯域幅の評価によって課せられる制限を除く)。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p117">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="0c23b-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="0c23b-325">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-325">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-326">リアルタイム制御プロトコル (RTCP) 統計情報に基づく平均ネットワーク ジッター。</span><span class="sxs-lookup"><span data-stu-id="0c23b-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-327">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="0c23b-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="0c23b-328">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-328">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-329">通話時の最大ネットワーク ジッター。</span><span class="sxs-lookup"><span data-stu-id="0c23b-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="0c23b-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="0c23b-331">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="0c23b-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-332">通話時の平均パケット損失率。</span><span class="sxs-lookup"><span data-stu-id="0c23b-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-333">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="0c23b-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="0c23b-334">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="0c23b-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-335">通話時に観測された最大パケット損失。</span><span class="sxs-lookup"><span data-stu-id="0c23b-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-336">BurstDensity</span><span class="sxs-lookup"><span data-stu-id="0c23b-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="0c23b-337">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="0c23b-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-338">通話時の損失のバーストで発生したパケット損失の平均密度。</span><span class="sxs-lookup"><span data-stu-id="0c23b-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-339">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="0c23b-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="0c23b-340">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-340">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-341">通話時の損失のバーストで発生したパケット損失の平均期間。</span><span class="sxs-lookup"><span data-stu-id="0c23b-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-342">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="0c23b-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="0c23b-343">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="0c23b-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-344">パケット損失のバーストが発生して次のバーストが発生するまでの間に発生したパケット損失の平均密度。</span><span class="sxs-lookup"><span data-stu-id="0c23b-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-345">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="0c23b-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="0c23b-346">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-346">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-347">パケット損失のバーストが発生して次のバーストが発生するまでの平均期間。</span><span class="sxs-lookup"><span data-stu-id="0c23b-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-348">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="0c23b-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="0c23b-349">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-349">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-350">音声ストリームのパケット数。</span><span class="sxs-lookup"><span data-stu-id="0c23b-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-351">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="0c23b-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="0c23b-352">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-352">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-353">音声ストリームの帯域幅の推定。</span><span class="sxs-lookup"><span data-stu-id="0c23b-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-354">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="0c23b-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="0c23b-355">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p118">通話全体でのネットワーク MOS の低下。範囲は 0.0 ～ 5.0 です。この指標は、ジッターとパケット損失に起因する、ネットワーク MOS の低下量を示します。許容範囲に収まる程度の品質を維持するには、この値は 0.5 未満である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p118">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-360">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="0c23b-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="0c23b-361">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-362">通話時のネットワーク MOS の最大低下。</span><span class="sxs-lookup"><span data-stu-id="0c23b-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-363">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="0c23b-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="0c23b-364">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-365">ジッターに起因するネットワーク MOS の低下。</span><span class="sxs-lookup"><span data-stu-id="0c23b-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-366">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="0c23b-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="0c23b-367">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-368">パケット損失に起因するネットワーク MOS の低下。</span><span class="sxs-lookup"><span data-stu-id="0c23b-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="0c23b-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="0c23b-370">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-370">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-371">通話に使用されるオーディオコーデック。 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 の PayloadDescription テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="0c23b-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-372">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="0c23b-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="0c23b-373">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-373">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-374">音声ストリームのサンプリング レート。</span><span class="sxs-lookup"><span data-stu-id="0c23b-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-375">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="0c23b-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="0c23b-376">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-376">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p119">発信者が送信した音声のアナログ後ゲイン制御のオーディオ信号レベル。この測定指標の単位は dBmo です。許容される品質は 30 dBmo 以上です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p119">Post-Analog Gain Control audio signal level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-381">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="0c23b-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="0c23b-382">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-382">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p120">発信者が受信した音声のオーディオ信号レベル。この測定指標の単位は dBmo です。許容される品質は 30 dBmo 以上です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p120">Audio signal level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-387">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="0c23b-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="0c23b-388">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-388">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p121">発信者が送信した音声のアナログ後ゲイン制御のオーディオ ノイズ レベル。この測定指標の単位は dBmo です。許容される品質は 35 dBmo 未満です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p121">Post-Analog Gain Control audio noise level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-393">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="0c23b-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="0c23b-394">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-394">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p122">発信者が受信した音声のアナログ後ゲイン制御のオーディオ ノイズ レベル。この測定指標の単位は dBmo です。許容される品質は 35 dBmo 未満です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p122">Post-Analog Gain Control audio noise level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-399">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="0c23b-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="0c23b-400">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-400">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p123">発信者のエコー リターン ロス エンハンスメント。この測定指標の単位は dB です。値が小さいほど、エコーが少ないことを示します。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p123">Echo Return Loss Enhancement for the caller. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-405">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="0c23b-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="0c23b-406">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-406">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p124">発信者のラウドスピーカー出力での 5 分間の平均障害回数です。良好な品質といえるのは、5 分間に 1 回未満です。音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p124">Average glitches per five minutes for the caller’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-410">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="0c23b-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="0c23b-411">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-411">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p125">発信者のマイク キャプチャでの 5 分間の平均障害回数です。良好な品質といえるのは、5 分間に 1 回未満です。音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p125">Average glitches per five minutes for the caller’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-415">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="0c23b-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="0c23b-416">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-417">CPU クロックに対する発信者のマイク デバイスのクロック誤差の割合です。</span><span class="sxs-lookup"><span data-stu-id="0c23b-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-418">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="0c23b-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="0c23b-419">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-420">CPU クロックに対する発信者のスピーカー デバイスのクロック誤差の割合です。</span><span class="sxs-lookup"><span data-stu-id="0c23b-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-421">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="0c23b-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="0c23b-422">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-423">過去 20 秒間の通話での平均マイク キャプチャ ストリーム タイム スタンプ エラーです (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="0c23b-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-424">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="0c23b-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="0c23b-425">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-426">過去 20 秒間の通話での発信者のスピーカー出力ストリーム タイム スタンプ エラーの平均です (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="0c23b-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-427">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="0c23b-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="0c23b-428">smallint</span><span class="sxs-lookup"><span data-stu-id="0c23b-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="0c23b-429">音声スイッチは、遮断能力が低下した半二重モードです。</span><span class="sxs-lookup"><span data-stu-id="0c23b-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="0c23b-430">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c23b-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-431">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="0c23b-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="0c23b-432">tinyint</span><span class="sxs-lookup"><span data-stu-id="0c23b-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0c23b-433">発信者のエコー イベントの原因です。</span><span class="sxs-lookup"><span data-stu-id="0c23b-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="0c23b-434">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c23b-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-435">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="0c23b-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="0c23b-436">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p128">発信者のマイク キャプチャ ストリームでエコーが検出された時間の割合です。ヘッドセットを使用している場合は、この値が低い必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p128">Percentage of time when echo is detected in the caller’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-439">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="0c23b-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="0c23b-440">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p129">発信者の送信ストリームでエコーが検出された時間の割合です。送信ストリームでの高いエコー率は、エコー リークを示しています。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p129">Percentage of time when echo is detected in the caller’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-443">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="0c23b-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="0c23b-444">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-444">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p130">仲介サーバーでのゲートウェイからの発信者の音声についての受信信号レベルです。この値は、仲介サーバーに対してのみ適用されます。この測定指標の単位は dBoV です。良好な品質として許容される範囲は、-30 ～ -18 dBoV です。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p130">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-448">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="0c23b-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="0c23b-449">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-449">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p131">仲介サーバーでのゲートウェイからの発信者の音声についての受信信号レベルです。この値は、仲介サーバーに対してのみ適用されます。この測定指標の単位は dBoV です。良好な品質として許容される範囲は、-50 dBoV 未満です。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p131">Received signal level on the Mediation Server from the Gateway for the caller’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-454">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="0c23b-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="0c23b-455">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-455">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-456">発信者の音声に対して適用される、仲介サーバー側での自動ゲイン制御 (AGC) です。</span><span class="sxs-lookup"><span data-stu-id="0c23b-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-457">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="0c23b-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="0c23b-458">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="0c23b-458">float</span></span></p></td>
<td><p><span data-ttu-id="0c23b-459">通話の最初の最大 30 秒間における発信者に対する着信信号の二重平均 (RMS) です。</span><span class="sxs-lookup"><span data-stu-id="0c23b-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-460">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="0c23b-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="0c23b-461">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-461">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p132">呼び出し先が送信した音声のアナログ後ゲイン制御のオーディオ信号レベルを表します。この測定指標の単位は dBmo です。許容される品質は 30 dBmo 以上です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p132">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-466">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="0c23b-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="0c23b-467">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-467">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p133">呼び出し先が受信した音声のオーディオ信号レベル。この測定指標の単位は dBmo です。許容される品質は 30 dBmo 以上です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p133">Audio signal level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-472">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="0c23b-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="0c23b-473">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-473">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p134">呼び出し先が送信した音声のアナログ後ゲイン制御のオーディオ ノイズ レベル。この測定指標の単位は dBmo です。許容される品質は 35 dBmo 未満です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p134">Post-Analog Gain Control audio noise level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-478">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="0c23b-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="0c23b-479">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-479">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p135">呼び出し先が受信した音声のアナログ後ゲイン制御のオーディオ ノイズ レベル。この測定指標の単位は dBmo です。許容される品質は 35 dBmo 未満です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p135">Post-Analog Gain Control audio noise level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-484">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="0c23b-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="0c23b-485">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-485">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p136">呼び出し先のエコー リターン ロス エンハンスメント。この測定指標の単位は dB です。値が小さいほど、エコーが少ないことを示します。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p136">Echo Return Loss Enhancement for the callee. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-490">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="0c23b-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="0c23b-491">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-491">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p137">呼び出し先のラウドスピーカー出力での 5 分間の平均障害回数です。良好な品質といえるのは、5 分間に 1 回未満です。音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p137">Average glitches per five minutes for the callee’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-495">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="0c23b-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="0c23b-496">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-496">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p138">呼び出し先のマイク キャプチャでの 5 分間の平均障害回数です。良好な品質といえるのは、5 分間に 1 回未満です。音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p138">Average glitches per five minutes for the callee’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-500">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="0c23b-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="0c23b-501">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-502">CPU クロックに対する呼び出し先のマイク デバイスのクロック誤差の割合です。</span><span class="sxs-lookup"><span data-stu-id="0c23b-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-503">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="0c23b-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="0c23b-504">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-505">CPU クロックに対する呼び出し先のスピーカー デバイスのクロック誤差の割合です。</span><span class="sxs-lookup"><span data-stu-id="0c23b-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-506">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="0c23b-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="0c23b-507">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-508">過去 20 秒間の通話での平均マイク キャプチャ ストリーム タイム スタンプ エラーです (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="0c23b-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-509">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="0c23b-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="0c23b-510">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-511">過去 20 秒間の通話での呼び出し先のスピーカー出力ストリーム タイム スタンプ エラーの平均です (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="0c23b-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-512">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="0c23b-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="0c23b-513">smallint</span><span class="sxs-lookup"><span data-stu-id="0c23b-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="0c23b-514">音声スイッチは、遮断能力が低下した半二重モードです。</span><span class="sxs-lookup"><span data-stu-id="0c23b-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="0c23b-515">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c23b-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-516">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="0c23b-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="0c23b-517">tinyint</span><span class="sxs-lookup"><span data-stu-id="0c23b-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0c23b-518">呼び出し先のエコー イベントの原因です。</span><span class="sxs-lookup"><span data-stu-id="0c23b-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="0c23b-519">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c23b-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-520">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="0c23b-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="0c23b-521">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p141">呼び出し先のマイク キャプチャ ストリームでエコーが検出された時間の割合です。ヘッドセットを使用している場合は、この値が低い必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p141">Percentage of time when echo is detected in the callee’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-524">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="0c23b-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="0c23b-525">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p142">呼び出し先の送信ストリームでエコーが検出された時間の割合です。送信ストリームでの高いエコー率は、エコー リークを示しています。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p142">Percentage of time when echo is detected in the callee’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-528">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="0c23b-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="0c23b-529">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-529">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p143">仲介サーバーでのゲートウェイからの呼び出し先の音声についての受信信号レベルです。この値は、仲介サーバーに対してのみ適用されます。この測定指標の単位は dBoV です。良好な品質として許容される範囲は、-30 ～ -18 dBoV です。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p143">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-533">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="0c23b-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="0c23b-534">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-534">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p144">仲介サーバーでのゲートウェイからの呼び出し先の音声についての受信信号レベルです。この値は、仲介サーバーに対してのみ適用されます。この測定指標の単位は dBoV です。良好な品質として許容される範囲は、-50 dBoV 未満です。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p144">Received signal level on the Mediation Server from the Gateway for the callee’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-539">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="0c23b-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="0c23b-540">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-540">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-541">呼び出し先の音声に対して適用される、仲介サーバー側での自動ゲイン制御 (AGC) です。</span><span class="sxs-lookup"><span data-stu-id="0c23b-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-542">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="0c23b-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="0c23b-543">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="0c23b-543">float</span></span></p></td>
<td><p><span data-ttu-id="0c23b-544">通話の最初の最大 30 秒間における呼び出し先に対する着信信号の二重平均 (RMS) です。</span><span class="sxs-lookup"><span data-stu-id="0c23b-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="0c23b-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="0c23b-546">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-547">標準サンプルへの音声復旧によって生成される隠しサンプルの平均比率。</span><span class="sxs-lookup"><span data-stu-id="0c23b-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-548">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="0c23b-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="0c23b-549">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-550">標準サンプルへの音声復旧によって生成される引き伸ばしサンプルの平均比率。</span><span class="sxs-lookup"><span data-stu-id="0c23b-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-551">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="0c23b-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="0c23b-552">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-553">標準サンプルへの音声復旧によって生成される圧縮サンプルの平均比率。</span><span class="sxs-lookup"><span data-stu-id="0c23b-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-554">要し</span><span class="sxs-lookup"><span data-stu-id="0c23b-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="0c23b-555">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-555">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-556">RTCP 統計情報に基づく往復時間。</span><span class="sxs-lookup"><span data-stu-id="0c23b-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-557">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="0c23b-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="0c23b-558">int</span><span class="sxs-lookup"><span data-stu-id="0c23b-558">int</span></span></p></td>
<td><p><span data-ttu-id="0c23b-559">音声ストリームの最大往復時間。</span><span class="sxs-lookup"><span data-stu-id="0c23b-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-560">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="0c23b-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="0c23b-561">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-p145">通話の広帯域ネットワーク MOS の平均値。この指標は、パケット損失、ジッター、および使用されるコーデックによって異なります。範囲は 1.0 ～ 5.0 です。</span><span class="sxs-lookup"><span data-stu-id="0c23b-p145">Average wideband Network MOS for the call. This metric depends on the packet loss, jitter, and codec used. Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-565">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="0c23b-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="0c23b-566">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-567">通話の広帯域ネットワーク MOS の最小値。</span><span class="sxs-lookup"><span data-stu-id="0c23b-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-568">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="0c23b-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="0c23b-569">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-570">スピーチ レベル、ノイズ レベル、キャプチャ デバイス特性など、送信される音声の広帯域受聴 MOS スコアの平均予測値。</span><span class="sxs-lookup"><span data-stu-id="0c23b-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-571">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="0c23b-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="0c23b-572">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-573">通話の SendListenMOS の最小値。</span><span class="sxs-lookup"><span data-stu-id="0c23b-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-574">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="0c23b-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="0c23b-575">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-576">スピーチ レベル、ノイズ レベル、キャプチャ デバイス特性など、ネットワークから受信される音声の広帯域受聴 MOS スコアの平均予測値。</span><span class="sxs-lookup"><span data-stu-id="0c23b-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-577">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="0c23b-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="0c23b-578">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="0c23b-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="0c23b-579">通話の RecvListenMOS の最小値。</span><span class="sxs-lookup"><span data-stu-id="0c23b-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c23b-580">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="0c23b-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="0c23b-581">若干</span><span class="sxs-lookup"><span data-stu-id="0c23b-581">bit</span></span></p></td>
<td><p><span data-ttu-id="0c23b-582">音声 FEC が通話で使用されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0c23b-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c23b-583">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="0c23b-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="0c23b-584">若干</span><span class="sxs-lookup"><span data-stu-id="0c23b-584">bit</span></span></p></td>
<td><p><span data-ttu-id="0c23b-585">P-Asserted Identity 情報の方向を示します。1 は、ストリームの方向が発信者から呼び出し先へ向かうことを意味します。0 は、ストリームの方向が呼び出し先から発信者へ向かうことを意味します。</span><span class="sxs-lookup"><span data-stu-id="0c23b-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

