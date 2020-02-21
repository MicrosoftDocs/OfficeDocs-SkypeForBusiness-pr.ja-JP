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
ms.openlocfilehash: fe995d08bf334308603512b4812b02c672d400f4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="eaf2a-102">Lync Server 2013 の AudioStreamDetail ビュー</span><span class="sxs-lookup"><span data-stu-id="eaf2a-102">AudioStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eaf2a-103">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="eaf2a-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="eaf2a-104">AudioStreamDetail ビューには、データベース内の各音声ストリームに関する情報が格納されています。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="eaf2a-105">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eaf2a-106">列</span><span class="sxs-lookup"><span data-stu-id="eaf2a-106">Column</span></span></th>
<th><span data-ttu-id="eaf2a-107">データ型</span><span class="sxs-lookup"><span data-stu-id="eaf2a-107">Data Type</span></span></th>
<th><span data-ttu-id="eaf2a-108">詳細</span><span class="sxs-lookup"><span data-stu-id="eaf2a-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="eaf2a-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-110">日付型</span><span class="sxs-lookup"><span data-stu-id="eaf2a-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-111"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="eaf2a-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-113">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-113">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-114"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-115">StreamId</span><span class="sxs-lookup"><span data-stu-id="eaf2a-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-116">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-116">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-117">メディア ライン内の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-118">StartTime</span><span class="sxs-lookup"><span data-stu-id="eaf2a-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-119">日付型</span><span class="sxs-lookup"><span data-stu-id="eaf2a-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-120">セッションの開始時刻。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="eaf2a-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-122">日付型</span><span class="sxs-lookup"><span data-stu-id="eaf2a-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-123">セッションの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-124">' このカテゴリ</span><span class="sxs-lookup"><span data-stu-id="eaf2a-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-125">若干</span><span class="sxs-lookup"><span data-stu-id="eaf2a-125">bit</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-126">ダイアログのカテゴリ: 0 は、仲介サーバーに対する Lync サーバーです。1は、PSTN ゲートウェイレグへの仲介サーバーです。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-127">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="eaf2a-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-128">若干</span><span class="sxs-lookup"><span data-stu-id="eaf2a-128">bit</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-129">通話がバイパスされたかどうかを示すフラグ。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-130">Mediabypasswarnings フラグ</span><span class="sxs-lookup"><span data-stu-id="eaf2a-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-131">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-131">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p102">存在する場合、バイパス ID が一致したのに通話がバイパスされなかった理由を示します。値は 1 つしか定義されていません。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p102">If present, indicates why a call was not bypassed even if the bypass IDs matched. Only one value is defined:</span></span></p>
<p><span data-ttu-id="eaf2a-134">0x0001 - 既定のネットワーク アダプターのバイパス ID が不明です。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-135">CallPriority</span><span class="sxs-lookup"><span data-stu-id="eaf2a-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-136">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-136">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-137">通話の優先順位。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-138">CallerPool</span><span class="sxs-lookup"><span data-stu-id="eaf2a-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-140">発信者プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-141">CalleePool</span><span class="sxs-lookup"><span data-stu-id="eaf2a-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-143">呼び出し先プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-144">Caller</span><span class="sxs-lookup"><span data-stu-id="eaf2a-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-146">発信者の URI。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-147">側</span><span class="sxs-lookup"><span data-stu-id="eaf2a-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-148">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-149">呼び出し先の URI。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-150">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="eaf2a-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-152">発信者のユーザー エージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-153">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="eaf2a-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-154">smallint</span><span class="sxs-lookup"><span data-stu-id="eaf2a-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-155">発信者のユーザー エージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="eaf2a-156">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-157">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="eaf2a-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-158">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-159">発信者のユーザー エージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="eaf2a-160">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-161">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="eaf2a-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-162">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-163">呼び出し先のユーザー エージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-164">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="eaf2a-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-165">smallint</span><span class="sxs-lookup"><span data-stu-id="eaf2a-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-166">呼び出し先のユーザー エージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-166">Type of callee’s user agent.</span></span> <span data-ttu-id="eaf2a-167">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-168">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="eaf2a-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-170">呼び出し先のユーザー エージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-170">Category of callee’s user agent.</span></span> <span data-ttu-id="eaf2a-171">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-172">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="eaf2a-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-174">発信者のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-175">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="eaf2a-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-177">呼び出し先のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-178">CallerOS</span><span class="sxs-lookup"><span data-stu-id="eaf2a-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-179">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="eaf2a-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-180">発信者のエンドポイントのオペレーティング システム (OS)。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-181">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="eaf2a-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-182">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="eaf2a-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-183">呼び出し先のエンドポイントのオペレーティング システム (OS)。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-184">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="eaf2a-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-185">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="eaf2a-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-186">発信者のエンドポイントの CPU 名。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-187">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="eaf2a-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-188">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="eaf2a-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-189">呼び出し先のエンドポイントの CPU 名。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-190">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="eaf2a-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-191">smallint</span><span class="sxs-lookup"><span data-stu-id="eaf2a-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-192">発信者のエンドポイントの CPU コアの数。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-193">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="eaf2a-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-194">smallint</span><span class="sxs-lookup"><span data-stu-id="eaf2a-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-195">呼び出し先のエンドポイントの CPU コアの数。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-196">Callercpu プロセッサ速度</span><span class="sxs-lookup"><span data-stu-id="eaf2a-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-197">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-197">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-198">発信者のエンドポイントの CPU プロセッサ速度。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-199">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="eaf2a-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-200">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-200">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-201">呼び出し先のエンドポイントの CPU プロセッサ速度。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-202">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="eaf2a-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="eaf2a-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-204">発信者のシステムが仮想環境で実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="eaf2a-205">詳細については、「 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-206">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="eaf2a-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-207">tinyint</span><span class="sxs-lookup"><span data-stu-id="eaf2a-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-208">呼び出し先のシステムが仮想環境で実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="eaf2a-209">詳細については、「 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-210">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="eaf2a-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eaf2a-211">関連付けキー。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-211">Correlation key.</span></span> <span data-ttu-id="eaf2a-212"><a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 の Sessioncorrelation テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-213">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="eaf2a-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-214">tinyint</span><span class="sxs-lookup"><span data-stu-id="eaf2a-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-215">メディア パスに関する情報 (直接、リレーなど)。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="eaf2a-216">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-217">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="eaf2a-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-218">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-218">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p111">発信者のビット フラグに記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-221">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="eaf2a-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-222">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-222">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p112">呼び出し先のビット フラグに記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-225">Transport</span><span class="sxs-lookup"><span data-stu-id="eaf2a-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-226">tinyint</span><span class="sxs-lookup"><span data-stu-id="eaf2a-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-227">トランスポートの種類。0 は UDP、1 は TCP です。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-228">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="eaf2a-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-230">発信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-230">IP address of the caller.</span></span> <span data-ttu-id="eaf2a-231">IPv4 または IPv6 のアドレスです。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-232">CallerPort</span><span class="sxs-lookup"><span data-stu-id="eaf2a-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-233">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-233">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-234">発信者が使用するポート。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-235">CallerInside</span><span class="sxs-lookup"><span data-stu-id="eaf2a-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-236">若干</span><span class="sxs-lookup"><span data-stu-id="eaf2a-236">bit</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-237">発信者がインターバル ネットワーク内にいるかどうかを示します。1 は、発信者がエンタープライズ ネットワーク内に存在することを示し、0 は、発信者がネットワーク外に存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-238">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="eaf2a-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-239">var (50)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-240">呼び出し先の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-240">IP address of the callee.</span></span> <span data-ttu-id="eaf2a-241">IPv4 または IPv6 のアドレスです。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-242">CalleePort</span><span class="sxs-lookup"><span data-stu-id="eaf2a-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-243">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-243">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-244">呼び出し先が使用するポート。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-245">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="eaf2a-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-246">若干</span><span class="sxs-lookup"><span data-stu-id="eaf2a-246">bit</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-247">呼び出し先がインターバル ネットワーク内にいるかどうかを示します。1 は、呼び出し先がエンタープライズ ネットワーク内に存在することを示し、0 は、呼び出し先がネットワーク外に存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-248">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="eaf2a-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-249">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="eaf2a-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-250">発信者のサイトの名前。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-251">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="eaf2a-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-252">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="eaf2a-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-253">発信者のサイトの国/地域の名前。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-254">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="eaf2a-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-255">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="eaf2a-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-256">呼び出し先のサイトの名前。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-257">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="eaf2a-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-258">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="eaf2a-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-259">呼び出し先のサイトの国/地域の名前。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-260">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="eaf2a-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-261">var (50)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-262">発信者が使用する音声ビデオ エッジ サービスの IPアドレス。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="eaf2a-263">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-264">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="eaf2a-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-265">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-265">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-266">発信者が使用する音声ビデオ エッジ サービスで使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-267">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="eaf2a-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-268">var (50)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-269">呼び出し先が使用する音声ビデオ エッジ サービスの IPアドレス キー。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="eaf2a-270">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-271">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="eaf2a-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-272">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-272">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-273">呼び出し先が使用する音声ビデオ エッジ サービスで使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-274">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="eaf2a-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-276">発信者のキャプチャ デバイス名。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-277">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="eaf2a-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-279">発信者のレンダー デバイス名。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-280">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="eaf2a-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-282">発信者のキャプチャ デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-283">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="eaf2a-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-285">発信者のレンダー デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-286">Calleecapのアーキテクチャ開発</span><span class="sxs-lookup"><span data-stu-id="eaf2a-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-288">呼び出し先のキャプチャ デバイス名。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-289">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="eaf2a-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-290">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-291">呼び出し先のレンダー デバイス名。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-292">Calleecapアーキテクチャ Devdriver</span><span class="sxs-lookup"><span data-stu-id="eaf2a-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-293">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-294">呼び出し先のキャプチャ デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-295">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="eaf2a-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-296">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-297">呼び出し先のレンダー デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-298">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="eaf2a-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="eaf2a-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-300">発信者のネットワーク接続の種類。0 は有線、1 はワイヤレスです。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-301">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="eaf2a-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-302">若干</span><span class="sxs-lookup"><span data-stu-id="eaf2a-302">bit</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-303">発信者が仮想プライベート ネットワークで接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-304">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="eaf2a-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-305">10進数 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-306">発信者のエンドポイントのネットワーク リンクの速度 (単位 bps)。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-307">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="eaf2a-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-308">tinyint</span><span class="sxs-lookup"><span data-stu-id="eaf2a-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-309">呼び出し先のネットワーク接続の種類。0 は有線、1 はワイヤレスです。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-310">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="eaf2a-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-311">若干</span><span class="sxs-lookup"><span data-stu-id="eaf2a-311">bit</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-312">発信者が仮想プライベート ネットワークで接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-313">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="eaf2a-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-314">10進数 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-315">呼び出し先のエンドポイントのネットワーク リンクの速度 (単位 bps)。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-316">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="eaf2a-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-317">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-318">音声セッションの Narrowband Conversational MOS (音声ストリームに基づく)。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-319">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="eaf2a-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-320">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-320">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p117">さまざまなポリシー設定 (TURN、API、SDP、ポリシー サーバーなど) が構成された特定の送信側ストリームに適用される実際の帯域幅。この帯域幅を実効帯域幅と見なすことはできません。実効帯域幅は、帯域幅の評価に基づいて実際よりも低くなる可能性があります。これは基本的に、送信ストリームで利用できる最大帯域幅です (帯域幅の評価によって課せられる制限を除く)。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p117">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="eaf2a-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-325">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-325">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-326">リアルタイム制御プロトコル (RTCP) 統計情報に基づく平均ネットワーク ジッター。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-327">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="eaf2a-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-328">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-328">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-329">通話時の最大ネットワーク ジッター。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="eaf2a-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-331">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-332">通話時の平均パケット損失率。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-333">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="eaf2a-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-334">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-335">通話時に観測された最大パケット損失。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-336">BurstDensity</span><span class="sxs-lookup"><span data-stu-id="eaf2a-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-337">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-338">通話時の損失のバーストで発生したパケット損失の平均密度。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-339">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="eaf2a-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-340">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-340">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-341">通話時の損失のバーストで発生したパケット損失の平均期間。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-342">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="eaf2a-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-343">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-344">パケット損失のバーストが発生して次のバーストが発生するまでの間に発生したパケット損失の平均密度。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-345">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="eaf2a-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-346">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-346">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-347">パケット損失のバーストが発生して次のバーストが発生するまでの平均期間。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-348">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="eaf2a-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-349">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-349">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-350">音声ストリームのパケット数。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-351">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="eaf2a-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-352">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-352">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-353">音声ストリームの帯域幅の推定。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-354">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="eaf2a-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-355">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p118">通話全体でのネットワーク MOS の低下。範囲は 0.0 ～ 5.0 です。この指標は、ジッターとパケット損失に起因する、ネットワーク MOS の低下量を示します。許容範囲に収まる程度の品質を維持するには、この値は 0.5 未満である必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p118">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-360">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="eaf2a-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-361">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-362">通話時のネットワーク MOS の最大低下。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-363">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="eaf2a-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-364">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-365">ジッターに起因するネットワーク MOS の低下。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-366">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="eaf2a-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-367">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-368">パケット損失に起因するネットワーク MOS の低下。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="eaf2a-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-370">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-370">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-371">通話に使用されるオーディオコーデック。 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 の PayloadDescription テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-372">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="eaf2a-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-373">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-373">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-374">音声ストリームのサンプリング レート。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-375">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="eaf2a-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-376">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-376">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p119">発信者が送信した音声のアナログ後ゲイン制御のオーディオ信号レベル。この測定指標の単位は dBmo です。許容される品質は 30 dBmo 以上です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p119">Post-Analog Gain Control audio signal level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-381">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="eaf2a-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-382">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-382">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p120">発信者が受信した音声のオーディオ信号レベル。この測定指標の単位は dBmo です。許容される品質は 30 dBmo 以上です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p120">Audio signal level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-387">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="eaf2a-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-388">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-388">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p121">発信者が送信した音声のアナログ後ゲイン制御のオーディオ ノイズ レベル。この測定指標の単位は dBmo です。許容される品質は 35 dBmo 未満です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p121">Post-Analog Gain Control audio noise level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-393">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="eaf2a-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-394">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-394">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p122">発信者が受信した音声のアナログ後ゲイン制御のオーディオ ノイズ レベル。この測定指標の単位は dBmo です。許容される品質は 35 dBmo 未満です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p122">Post-Analog Gain Control audio noise level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-399">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="eaf2a-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-400">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-400">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p123">発信者のエコー リターン ロス エンハンスメント。この測定指標の単位は dB です。値が小さいほど、エコーが少ないことを示します。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p123">Echo Return Loss Enhancement for the caller. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-405">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="eaf2a-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-406">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-406">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p124">発信者のラウドスピーカー出力での 5 分間の平均障害回数です。良好な品質といえるのは、5 分間に 1 回未満です。音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p124">Average glitches per five minutes for the caller’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-410">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="eaf2a-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-411">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-411">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p125">発信者のマイク キャプチャでの 5 分間の平均障害回数です。良好な品質といえるのは、5 分間に 1 回未満です。音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p125">Average glitches per five minutes for the caller’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-415">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="eaf2a-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-416">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-417">CPU クロックに対する発信者のマイク デバイスのクロック誤差の割合です。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-418">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="eaf2a-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-419">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-420">CPU クロックに対する発信者のスピーカー デバイスのクロック誤差の割合です。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-421">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="eaf2a-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-422">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-423">過去 20 秒間の通話での平均マイク キャプチャ ストリーム タイム スタンプ エラーです (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-424">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="eaf2a-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-425">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-426">過去 20 秒間の通話での発信者のスピーカー出力ストリーム タイム スタンプ エラーの平均です (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-427">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="eaf2a-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-428">smallint</span><span class="sxs-lookup"><span data-stu-id="eaf2a-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-429">音声スイッチは、遮断能力が低下した半二重モードです。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="eaf2a-430">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-431">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="eaf2a-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-432">tinyint</span><span class="sxs-lookup"><span data-stu-id="eaf2a-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-433">発信者のエコー イベントの原因です。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="eaf2a-434">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-435">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="eaf2a-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-436">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p128">発信者のマイク キャプチャ ストリームでエコーが検出された時間の割合です。ヘッドセットを使用している場合は、この値が低い必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p128">Percentage of time when echo is detected in the caller’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-439">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="eaf2a-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-440">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p129">発信者の送信ストリームでエコーが検出された時間の割合です。送信ストリームでの高いエコー率は、エコー リークを示しています。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p129">Percentage of time when echo is detected in the caller’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-443">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="eaf2a-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-444">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-444">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p130">仲介サーバーでのゲートウェイからの発信者の音声についての受信信号レベルです。この値は、仲介サーバーに対してのみ適用されます。この測定指標の単位は dBoV です。良好な品質として許容される範囲は、-30 ～ -18 dBoV です。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p130">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-448">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="eaf2a-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-449">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-449">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p131">仲介サーバーでのゲートウェイからの発信者の音声についての受信信号レベルです。この値は、仲介サーバーに対してのみ適用されます。この測定指標の単位は dBoV です。良好な品質として許容される範囲は、-50 dBoV 未満です。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p131">Received signal level on the Mediation Server from the Gateway for the caller’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-454">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="eaf2a-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-455">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-455">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-456">発信者の音声に対して適用される、仲介サーバー側での自動ゲイン制御 (AGC) です。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-457">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="eaf2a-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-458">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="eaf2a-458">float</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-459">通話の最初の最大 30 秒間における発信者に対する着信信号の二重平均 (RMS) です。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-460">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="eaf2a-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-461">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-461">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p132">呼び出し先が送信した音声のアナログ後ゲイン制御のオーディオ信号レベルを表します。この測定指標の単位は dBmo です。許容される品質は 30 dBmo 以上です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p132">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-466">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="eaf2a-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-467">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-467">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p133">呼び出し先が受信した音声のオーディオ信号レベル。この測定指標の単位は dBmo です。許容される品質は 30 dBmo 以上です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p133">Audio signal level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-472">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="eaf2a-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-473">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-473">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p134">呼び出し先が送信した音声のアナログ後ゲイン制御のオーディオ ノイズ レベル。この測定指標の単位は dBmo です。許容される品質は 35 dBmo 未満です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p134">Post-Analog Gain Control audio noise level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-478">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="eaf2a-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-479">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-479">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p135">呼び出し先が受信した音声のアナログ後ゲイン制御のオーディオ ノイズ レベル。この測定指標の単位は dBmo です。許容される品質は 35 dBmo 未満です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p135">Post-Analog Gain Control audio noise level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-484">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="eaf2a-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-485">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-485">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p136">呼び出し先のエコー リターン ロス エンハンスメント。この測定指標の単位は dB です。値が小さいほど、エコーが少ないことを示します。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p136">Echo Return Loss Enhancement for the callee. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-490">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="eaf2a-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-491">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-491">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p137">呼び出し先のラウドスピーカー出力での 5 分間の平均障害回数です。良好な品質といえるのは、5 分間に 1 回未満です。音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p137">Average glitches per five minutes for the callee’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-495">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="eaf2a-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-496">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-496">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p138">呼び出し先のマイク キャプチャでの 5 分間の平均障害回数です。良好な品質といえるのは、5 分間に 1 回未満です。音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p138">Average glitches per five minutes for the callee’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-500">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="eaf2a-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-501">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-502">CPU クロックに対する呼び出し先のマイク デバイスのクロック誤差の割合です。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-503">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="eaf2a-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-504">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-505">CPU クロックに対する呼び出し先のスピーカー デバイスのクロック誤差の割合です。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-506">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="eaf2a-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-507">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-508">過去 20 秒間の通話での平均マイク キャプチャ ストリーム タイム スタンプ エラーです (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-509">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="eaf2a-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-510">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-511">過去 20 秒間の通話での呼び出し先のスピーカー出力ストリーム タイム スタンプ エラーの平均です (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-512">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="eaf2a-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-513">smallint</span><span class="sxs-lookup"><span data-stu-id="eaf2a-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-514">音声スイッチは、遮断能力が低下した半二重モードです。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="eaf2a-515">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-516">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="eaf2a-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-517">tinyint</span><span class="sxs-lookup"><span data-stu-id="eaf2a-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-518">呼び出し先のエコー イベントの原因です。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="eaf2a-519">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-520">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="eaf2a-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-521">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p141">呼び出し先のマイク キャプチャ ストリームでエコーが検出された時間の割合です。ヘッドセットを使用している場合は、この値が低い必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p141">Percentage of time when echo is detected in the callee’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-524">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="eaf2a-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-525">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p142">呼び出し先の送信ストリームでエコーが検出された時間の割合です。送信ストリームでの高いエコー率は、エコー リークを示しています。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p142">Percentage of time when echo is detected in the callee’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-528">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="eaf2a-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-529">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-529">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p143">仲介サーバーでのゲートウェイからの呼び出し先の音声についての受信信号レベルです。この値は、仲介サーバーに対してのみ適用されます。この測定指標の単位は dBoV です。良好な品質として許容される範囲は、-30 ～ -18 dBoV です。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p143">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-533">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="eaf2a-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-534">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-534">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p144">仲介サーバーでのゲートウェイからの呼び出し先の音声についての受信信号レベルです。この値は、仲介サーバーに対してのみ適用されます。この測定指標の単位は dBoV です。良好な品質として許容される範囲は、-50 dBoV 未満です。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p144">Received signal level on the Mediation Server from the Gateway for the callee’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-539">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="eaf2a-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-540">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-540">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-541">呼び出し先の音声に対して適用される、仲介サーバー側での自動ゲイン制御 (AGC) です。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-542">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="eaf2a-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-543">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="eaf2a-543">float</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-544">通話の最初の最大 30 秒間における呼び出し先に対する着信信号の二重平均 (RMS) です。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="eaf2a-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-546">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-547">標準サンプルへの音声復旧によって生成される隠しサンプルの平均比率。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-548">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="eaf2a-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-549">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-550">標準サンプルへの音声復旧によって生成される引き伸ばしサンプルの平均比率。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-551">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="eaf2a-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-552">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-553">標準サンプルへの音声復旧によって生成される圧縮サンプルの平均比率。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-554">要し</span><span class="sxs-lookup"><span data-stu-id="eaf2a-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-555">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-555">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-556">RTCP 統計情報に基づく往復時間。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-557">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="eaf2a-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-558">int</span><span class="sxs-lookup"><span data-stu-id="eaf2a-558">int</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-559">音声ストリームの最大往復時間。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-560">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="eaf2a-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-561">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-p145">通話の広帯域ネットワーク MOS の平均値。この指標は、パケット損失、ジッター、および使用されるコーデックによって異なります。範囲は 1.0 ～ 5.0 です。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-p145">Average wideband Network MOS for the call. This metric depends on the packet loss, jitter, and codec used. Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-565">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="eaf2a-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-566">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-567">通話の広帯域ネットワーク MOS の最小値。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-568">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="eaf2a-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-569">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-570">スピーチ レベル、ノイズ レベル、キャプチャ デバイス特性など、送信される音声の広帯域受聴 MOS スコアの平均予測値。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-571">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="eaf2a-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-572">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-573">通話の SendListenMOS の最小値。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-574">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="eaf2a-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-575">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-576">スピーチ レベル、ノイズ レベル、キャプチャ デバイス特性など、ネットワークから受信される音声の広帯域受聴 MOS スコアの平均予測値。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-577">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="eaf2a-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-578">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="eaf2a-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-579">通話の RecvListenMOS の最小値。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaf2a-580">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="eaf2a-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-581">若干</span><span class="sxs-lookup"><span data-stu-id="eaf2a-581">bit</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-582">音声 FEC が通話で使用されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaf2a-583">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="eaf2a-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-584">若干</span><span class="sxs-lookup"><span data-stu-id="eaf2a-584">bit</span></span></p></td>
<td><p><span data-ttu-id="eaf2a-585">P-Asserted Identity 情報の方向を示します。1 は、ストリームの方向が発信者から呼び出し先へ向かうことを意味します。0 は、ストリームの方向が呼び出し先から発信者へ向かうことを意味します。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

