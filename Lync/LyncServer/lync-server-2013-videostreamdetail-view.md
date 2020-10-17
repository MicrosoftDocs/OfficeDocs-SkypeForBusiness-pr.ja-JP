---
title: 'Lync Server 2013: VideoStreamDetail ビュー'
description: 'Lync Server 2013: VideoStreamDetail ビュー。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStreamDetail view
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49733863
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3f420c292627d15fd0d54f2eba01c565a49a72d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567973"
---
# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="1a52f-103">Lync Server 2013 の VideoStreamDetail ビュー</span><span class="sxs-lookup"><span data-stu-id="1a52f-103">VideoStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a52f-104">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="1a52f-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="1a52f-105">VideoStreamDetail ビューには、データベース内の各ビデオ ストリームに関する情報が格納されています。</span><span class="sxs-lookup"><span data-stu-id="1a52f-105">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="1a52f-106">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="1a52f-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a52f-107">Column</span><span class="sxs-lookup"><span data-stu-id="1a52f-107">Column</span></span></th>
<th><span data-ttu-id="1a52f-108">データ型</span><span class="sxs-lookup"><span data-stu-id="1a52f-108">Data Type</span></span></th>
<th><span data-ttu-id="1a52f-109">説明</span><span class="sxs-lookup"><span data-stu-id="1a52f-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-110">SessionTime</span><span class="sxs-lookup"><span data-stu-id="1a52f-110">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="1a52f-111">日付型</span><span class="sxs-lookup"><span data-stu-id="1a52f-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="1a52f-112"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="1a52f-112">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-113">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="1a52f-113">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="1a52f-114">int</span><span class="sxs-lookup"><span data-stu-id="1a52f-114">int</span></span></p></td>
<td><p><span data-ttu-id="1a52f-115"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="1a52f-115">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-116">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="1a52f-116">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="1a52f-117">tinyint</span><span class="sxs-lookup"><span data-stu-id="1a52f-117">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1a52f-118"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="1a52f-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-119">StreamId</span><span class="sxs-lookup"><span data-stu-id="1a52f-119">StreamId</span></span></p></td>
<td><p><span data-ttu-id="1a52f-120">int</span><span class="sxs-lookup"><span data-stu-id="1a52f-120">int</span></span></p></td>
<td><p><span data-ttu-id="1a52f-121">メディア ライン内の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="1a52f-121">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-122">StartTime</span><span class="sxs-lookup"><span data-stu-id="1a52f-122">StartTime</span></span></p></td>
<td><p><span data-ttu-id="1a52f-123">日付型</span><span class="sxs-lookup"><span data-stu-id="1a52f-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="1a52f-124">セッションの開始時刻。</span><span class="sxs-lookup"><span data-stu-id="1a52f-124">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-125">EndTime</span><span class="sxs-lookup"><span data-stu-id="1a52f-125">EndTime</span></span></p></td>
<td><p><span data-ttu-id="1a52f-126">日付型</span><span class="sxs-lookup"><span data-stu-id="1a52f-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="1a52f-127">セッションの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="1a52f-127">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-128">CallPriority</span><span class="sxs-lookup"><span data-stu-id="1a52f-128">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="1a52f-129">int</span><span class="sxs-lookup"><span data-stu-id="1a52f-129">int</span></span></p></td>
<td><p><span data-ttu-id="1a52f-130">通話の優先順位。</span><span class="sxs-lookup"><span data-stu-id="1a52f-130">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-131">CallerPool</span><span class="sxs-lookup"><span data-stu-id="1a52f-131">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="1a52f-132">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1a52f-132">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-133">発信者プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="1a52f-133">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-134">CalleePool</span><span class="sxs-lookup"><span data-stu-id="1a52f-134">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="1a52f-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1a52f-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-136">呼び出し先プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="1a52f-136">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-137">Caller</span><span class="sxs-lookup"><span data-stu-id="1a52f-137">Caller</span></span></p></td>
<td><p><span data-ttu-id="1a52f-138">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1a52f-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-139">発信者の URI。</span><span class="sxs-lookup"><span data-stu-id="1a52f-139">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-140">側</span><span class="sxs-lookup"><span data-stu-id="1a52f-140">Callee</span></span></p></td>
<td><p><span data-ttu-id="1a52f-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1a52f-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-142">呼び出し先の URI。</span><span class="sxs-lookup"><span data-stu-id="1a52f-142">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-143">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="1a52f-143">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="1a52f-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1a52f-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-145">発信者のユーザー エージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="1a52f-145">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-146">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="1a52f-146">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="1a52f-147">smallint</span><span class="sxs-lookup"><span data-stu-id="1a52f-147">smallint</span></span></p></td>
<td><p><span data-ttu-id="1a52f-148">発信者のユーザー エージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="1a52f-148">Type of caller’s user agent.</span></span> <span data-ttu-id="1a52f-149">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a52f-149">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-150">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="1a52f-150">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="1a52f-151">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="1a52f-151">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-152">発信者のユーザー エージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="1a52f-152">Category of caller’s user agent.</span></span> <span data-ttu-id="1a52f-153">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a52f-153">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-154">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="1a52f-154">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="1a52f-155">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1a52f-155">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-156">呼び出し先のユーザー エージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="1a52f-156">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-157">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="1a52f-157">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="1a52f-158">smallint</span><span class="sxs-lookup"><span data-stu-id="1a52f-158">smallint</span></span></p></td>
<td><p><span data-ttu-id="1a52f-159">呼び出し先のユーザー エージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="1a52f-159">Type of callee’s user agent.</span></span> <span data-ttu-id="1a52f-160">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a52f-160">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-161">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="1a52f-161">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="1a52f-162">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="1a52f-162">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-163">呼び出し先のユーザー エージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="1a52f-163">Category of callee’s user agent.</span></span> <span data-ttu-id="1a52f-164">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a52f-164">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-165">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="1a52f-165">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="1a52f-166">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1a52f-166">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-167">発信者のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="1a52f-167">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-168">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="1a52f-168">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="1a52f-169">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1a52f-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-170">呼び出し先のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="1a52f-170">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-171">CallerOS</span><span class="sxs-lookup"><span data-stu-id="1a52f-171">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="1a52f-172">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="1a52f-172">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-173">発信者のエンドポイントのオペレーティング システム (OS)。</span><span class="sxs-lookup"><span data-stu-id="1a52f-173">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-174">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="1a52f-174">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="1a52f-175">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="1a52f-175">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-176">呼び出し先のエンドポイントのオペレーティング システム (OS)。</span><span class="sxs-lookup"><span data-stu-id="1a52f-176">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-177">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="1a52f-177">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="1a52f-178">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="1a52f-178">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-179">発信者のエンドポイントの CPU 名。</span><span class="sxs-lookup"><span data-stu-id="1a52f-179">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-180">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="1a52f-180">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="1a52f-181">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="1a52f-181">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-182">呼び出し先のエンドポイントの CPU 名。</span><span class="sxs-lookup"><span data-stu-id="1a52f-182">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-183">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="1a52f-183">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="1a52f-184">smallint</span><span class="sxs-lookup"><span data-stu-id="1a52f-184">smallint</span></span></p></td>
<td><p><span data-ttu-id="1a52f-185">発信者のエンドポイントの CPU コアの数。</span><span class="sxs-lookup"><span data-stu-id="1a52f-185">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-186">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="1a52f-186">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="1a52f-187">smallint</span><span class="sxs-lookup"><span data-stu-id="1a52f-187">smallint</span></span></p></td>
<td><p><span data-ttu-id="1a52f-188">呼び出し先のエンドポイントの CPU コアの数。</span><span class="sxs-lookup"><span data-stu-id="1a52f-188">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-189">Callercpu プロセッサ速度</span><span class="sxs-lookup"><span data-stu-id="1a52f-189">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="1a52f-190">int</span><span class="sxs-lookup"><span data-stu-id="1a52f-190">int</span></span></p></td>
<td><p><span data-ttu-id="1a52f-191">発信者のエンドポイントの CPU プロセッサ速度。</span><span class="sxs-lookup"><span data-stu-id="1a52f-191">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-192">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="1a52f-192">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="1a52f-193">int</span><span class="sxs-lookup"><span data-stu-id="1a52f-193">int</span></span></p></td>
<td><p><span data-ttu-id="1a52f-194">呼び出し先のエンドポイントの CPU プロセッサ速度。</span><span class="sxs-lookup"><span data-stu-id="1a52f-194">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-195">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="1a52f-195">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="1a52f-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="1a52f-196">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1a52f-197">発信者のシステムが仮想環境で実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="1a52f-197">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="1a52f-198">詳細については、「 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a52f-198">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-199">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="1a52f-199">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="1a52f-200">tinyint</span><span class="sxs-lookup"><span data-stu-id="1a52f-200">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1a52f-201">呼び出し先のシステムが仮想環境で実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="1a52f-201">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="1a52f-202">詳細については、「 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a52f-202">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-203">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="1a52f-203">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="1a52f-204">tinyint</span><span class="sxs-lookup"><span data-stu-id="1a52f-204">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1a52f-205">メディア パスに関する情報 (直接、リレーなど)。</span><span class="sxs-lookup"><span data-stu-id="1a52f-205">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="1a52f-206">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a52f-206">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-207">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="1a52f-207">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="1a52f-208">int</span><span class="sxs-lookup"><span data-stu-id="1a52f-208">int</span></span></p></td>
<td><p><span data-ttu-id="1a52f-p109">発信者のビット フラグに記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a52f-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-211">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="1a52f-211">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="1a52f-212">int</span><span class="sxs-lookup"><span data-stu-id="1a52f-212">int</span></span></p></td>
<td><p><span data-ttu-id="1a52f-p110">呼び出し先のビット フラグに記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a52f-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-215">Transport</span><span class="sxs-lookup"><span data-stu-id="1a52f-215">Transport</span></span></p></td>
<td><p><span data-ttu-id="1a52f-216">int</span><span class="sxs-lookup"><span data-stu-id="1a52f-216">int</span></span></p></td>
<td><p><span data-ttu-id="1a52f-217">トランスポートの種類。0 は UDP、1 は TCP です。</span><span class="sxs-lookup"><span data-stu-id="1a52f-217">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-218">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="1a52f-218">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="1a52f-219">var (50)</span><span class="sxs-lookup"><span data-stu-id="1a52f-219">var(50)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-220">発信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="1a52f-220">IP address of the caller.</span></span> <span data-ttu-id="1a52f-221">IPv4 または IPv6 のアドレスです。</span><span class="sxs-lookup"><span data-stu-id="1a52f-221">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-222">CallerPort</span><span class="sxs-lookup"><span data-stu-id="1a52f-222">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="1a52f-223">int</span><span class="sxs-lookup"><span data-stu-id="1a52f-223">int</span></span></p></td>
<td><p><span data-ttu-id="1a52f-224">発信者が使用するポート。</span><span class="sxs-lookup"><span data-stu-id="1a52f-224">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-225">CallerInside</span><span class="sxs-lookup"><span data-stu-id="1a52f-225">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="1a52f-226">若干</span><span class="sxs-lookup"><span data-stu-id="1a52f-226">bit</span></span></p></td>
<td><p><span data-ttu-id="1a52f-p112">発信者が組織ネットワーク内にいるかどうかを示します。1 は、発信者がエンタープライズ ネットワーク内に存在することを示し、0 は、発信者がネットワーク外に存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="1a52f-p112">Indicates whether the caller is inside the organization network. 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-229">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="1a52f-229">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="1a52f-230">var (50)</span><span class="sxs-lookup"><span data-stu-id="1a52f-230">var(50)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-231">呼び出し先の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="1a52f-231">IP address of the callee.</span></span> <span data-ttu-id="1a52f-232">IPv4 または IPv6 のアドレスです。</span><span class="sxs-lookup"><span data-stu-id="1a52f-232">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-233">CalleePort</span><span class="sxs-lookup"><span data-stu-id="1a52f-233">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="1a52f-234">int</span><span class="sxs-lookup"><span data-stu-id="1a52f-234">int</span></span></p></td>
<td><p><span data-ttu-id="1a52f-235">呼び出し先が使用するポート。</span><span class="sxs-lookup"><span data-stu-id="1a52f-235">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-236">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="1a52f-236">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="1a52f-237">若干</span><span class="sxs-lookup"><span data-stu-id="1a52f-237">bit</span></span></p></td>
<td><p><span data-ttu-id="1a52f-238">呼び出し先が組織ネットワーク内にいるかどうかを示します。1 は、呼び出し先がエンタープライズ ネットワーク内に存在することを示し、0 は、呼び出し先がネットワーク外に存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="1a52f-238">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-239">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="1a52f-239">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="1a52f-240">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="1a52f-240">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-241">発信者のサイトの名前。</span><span class="sxs-lookup"><span data-stu-id="1a52f-241">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-242">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="1a52f-242">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="1a52f-243">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="1a52f-243">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-244">発信者のサイトの国/地域の名前。</span><span class="sxs-lookup"><span data-stu-id="1a52f-244">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-245">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="1a52f-245">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="1a52f-246">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="1a52f-246">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-247">呼び出し先のサイトの名前。</span><span class="sxs-lookup"><span data-stu-id="1a52f-247">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-248">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="1a52f-248">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="1a52f-249">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="1a52f-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-250">呼び出し先のサイトの国/地域の名前。</span><span class="sxs-lookup"><span data-stu-id="1a52f-250">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-251">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="1a52f-251">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="1a52f-252">var (50)</span><span class="sxs-lookup"><span data-stu-id="1a52f-252">var(50)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-253">発信者が使用する音声ビデオ エッジ サービスの IPアドレス。</span><span class="sxs-lookup"><span data-stu-id="1a52f-253">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="1a52f-254">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a52f-254">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-255">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="1a52f-255">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="1a52f-256">int</span><span class="sxs-lookup"><span data-stu-id="1a52f-256">int</span></span></p></td>
<td><p><span data-ttu-id="1a52f-257">発信者が使用する音声ビデオ エッジ サービスのポート。</span><span class="sxs-lookup"><span data-stu-id="1a52f-257">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-258">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="1a52f-258">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="1a52f-259">var (50)</span><span class="sxs-lookup"><span data-stu-id="1a52f-259">var(50)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-260">呼び出し先が使用する音声ビデオ エッジ サービスの IPアドレス キー。</span><span class="sxs-lookup"><span data-stu-id="1a52f-260">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="1a52f-261">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a52f-261">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-262">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="1a52f-262">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="1a52f-263">int</span><span class="sxs-lookup"><span data-stu-id="1a52f-263">int</span></span></p></td>
<td><p><span data-ttu-id="1a52f-264">呼び出し先が使用する音声ビデオ エッジ サービスのポート。</span><span class="sxs-lookup"><span data-stu-id="1a52f-264">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-265">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="1a52f-265">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="1a52f-266">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1a52f-266">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-267">発信者のキャプチャ デバイス名。</span><span class="sxs-lookup"><span data-stu-id="1a52f-267">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-268">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="1a52f-268">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="1a52f-269">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1a52f-269">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-270">発信者のレンダー デバイス名。</span><span class="sxs-lookup"><span data-stu-id="1a52f-270">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-271">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="1a52f-271">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="1a52f-272">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1a52f-272">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-273">発信者のキャプチャ デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="1a52f-273">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-274">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="1a52f-274">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="1a52f-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1a52f-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-276">発信者のレンダー デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="1a52f-276">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-277">Calleecapのアーキテクチャ開発</span><span class="sxs-lookup"><span data-stu-id="1a52f-277">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="1a52f-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1a52f-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-279">呼び出し先のキャプチャ デバイス名。</span><span class="sxs-lookup"><span data-stu-id="1a52f-279">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-280">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="1a52f-280">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="1a52f-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1a52f-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-282">呼び出し先のレンダー デバイス名。</span><span class="sxs-lookup"><span data-stu-id="1a52f-282">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-283">Callecapん Devdriver</span><span class="sxs-lookup"><span data-stu-id="1a52f-283">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="1a52f-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1a52f-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-285">呼び出し先のキャプチャ デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="1a52f-285">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-286">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="1a52f-286">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="1a52f-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1a52f-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-288">呼び出し先のレンダー デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="1a52f-288">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-289">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="1a52f-289">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="1a52f-290">tinyint</span><span class="sxs-lookup"><span data-stu-id="1a52f-290">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1a52f-291">発信者のネットワーク接続の種類。0 は有線、1 はワイヤレスです。</span><span class="sxs-lookup"><span data-stu-id="1a52f-291">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-292">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="1a52f-292">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="1a52f-293">若干</span><span class="sxs-lookup"><span data-stu-id="1a52f-293">bit</span></span></p></td>
<td><p><span data-ttu-id="1a52f-p116">発信者が仮想プライベート ネットワークで接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="1a52f-p116">Indicates whether or not the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-296">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="1a52f-296">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="1a52f-297">10進数 (18)</span><span class="sxs-lookup"><span data-stu-id="1a52f-297">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-298">発信者のエンドポイントのネットワーク リンクの速度 (単位 bps)。</span><span class="sxs-lookup"><span data-stu-id="1a52f-298">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-299">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="1a52f-299">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="1a52f-300">tinyint</span><span class="sxs-lookup"><span data-stu-id="1a52f-300">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1a52f-301">呼び出し先のネットワーク接続の種類。0 は有線、1 はワイヤレスです。</span><span class="sxs-lookup"><span data-stu-id="1a52f-301">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-302">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="1a52f-302">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="1a52f-303">若干</span><span class="sxs-lookup"><span data-stu-id="1a52f-303">bit</span></span></p></td>
<td><p><span data-ttu-id="1a52f-p117">呼び出し先が仮想プライベート ネットワークで接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="1a52f-p117">Indicates whether or not the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-306">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="1a52f-306">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="1a52f-307">10進数 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="1a52f-307">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-308">呼び出し先のエンドポイントのネットワーク リンクの速度 (単位 bps)。</span><span class="sxs-lookup"><span data-stu-id="1a52f-308">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-309">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="1a52f-309">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="1a52f-310">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="1a52f-310">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-311">音声セッションの Narrowband Conversational MOS (音声ストリームに基づく)。</span><span class="sxs-lookup"><span data-stu-id="1a52f-311">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-312">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="1a52f-312">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="1a52f-313">int</span><span class="sxs-lookup"><span data-stu-id="1a52f-313">int</span></span></p></td>
<td><p><span data-ttu-id="1a52f-p118">さまざまなポリシー設定 (TURN、API、SDP、ポリシー サーバーなど) が構成された特定の送信側ストリームに適用される実際の帯域幅。この帯域幅を実効帯域幅と見なすことはできません。実効帯域幅は、帯域幅の評価に基づいて実際よりも低くなる可能性があります。これは基本的に、送信ストリームで利用できる最大帯域幅です (帯域幅の評価によって課せられる制限を除く)。</span><span class="sxs-lookup"><span data-stu-id="1a52f-p118">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-317">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="1a52f-317">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="1a52f-318">int</span><span class="sxs-lookup"><span data-stu-id="1a52f-318">int</span></span></p></td>
<td><p><span data-ttu-id="1a52f-319">リアルタイム制御プロトコル (RTCP) 統計情報に基づく平均ネットワーク ジッター。</span><span class="sxs-lookup"><span data-stu-id="1a52f-319">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-320">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="1a52f-320">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="1a52f-321">int</span><span class="sxs-lookup"><span data-stu-id="1a52f-321">int</span></span></p></td>
<td><p><span data-ttu-id="1a52f-322">通話時の最大ネットワーク ジッター。</span><span class="sxs-lookup"><span data-stu-id="1a52f-322">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-323">要し</span><span class="sxs-lookup"><span data-stu-id="1a52f-323">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="1a52f-324">int</span><span class="sxs-lookup"><span data-stu-id="1a52f-324">int</span></span></p></td>
<td><p><span data-ttu-id="1a52f-325">RTCP 統計情報に基づく往復時間。</span><span class="sxs-lookup"><span data-stu-id="1a52f-325">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-326">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="1a52f-326">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="1a52f-327">int</span><span class="sxs-lookup"><span data-stu-id="1a52f-327">int</span></span></p></td>
<td><p><span data-ttu-id="1a52f-328">音声ストリームの最大往復時間。</span><span class="sxs-lookup"><span data-stu-id="1a52f-328">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-329">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="1a52f-329">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="1a52f-330">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="1a52f-330">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-331">通話時の平均パケット損失率。</span><span class="sxs-lookup"><span data-stu-id="1a52f-331">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-332">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="1a52f-332">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="1a52f-333">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="1a52f-333">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-334">通話時に観測された最大パケット損失。</span><span class="sxs-lookup"><span data-stu-id="1a52f-334">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-335">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="1a52f-335">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="1a52f-336">int</span><span class="sxs-lookup"><span data-stu-id="1a52f-336">int</span></span></p></td>
<td><p><span data-ttu-id="1a52f-337">ビデオ ストリームのパケット数 (リアルタイム転送プロトコル、RTP)。</span><span class="sxs-lookup"><span data-stu-id="1a52f-337">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-338">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="1a52f-338">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="1a52f-339">int</span><span class="sxs-lookup"><span data-stu-id="1a52f-339">int</span></span></p></td>
<td><p><span data-ttu-id="1a52f-340">音声ストリームの帯域幅の推定。</span><span class="sxs-lookup"><span data-stu-id="1a52f-340">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-341">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="1a52f-341">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="1a52f-342">int</span><span class="sxs-lookup"><span data-stu-id="1a52f-342">int</span></span></p></td>
<td><p><span data-ttu-id="1a52f-343">通話に使用されるオーディオコーデック。 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 の PayloadDescription テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="1a52f-343">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-344">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="1a52f-344">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="1a52f-345">文字 (9)</span><span class="sxs-lookup"><span data-stu-id="1a52f-345">char(9)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-p119">幅×高さで示すビデオの解像度 (単位ピクセル)。文字列で報告されます。</span><span class="sxs-lookup"><span data-stu-id="1a52f-p119">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-348">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="1a52f-348">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="1a52f-349">int</span><span class="sxs-lookup"><span data-stu-id="1a52f-349">int</span></span></p></td>
<td><p><span data-ttu-id="1a52f-350">ビデオ ストリームの平均ビット レート。</span><span class="sxs-lookup"><span data-stu-id="1a52f-350">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-351">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="1a52f-351">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="1a52f-352">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="1a52f-352">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-353">ビデオの受信フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="1a52f-353">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-354">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="1a52f-354">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="1a52f-355">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="1a52f-355">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-356">ビデオの送信フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="1a52f-356">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-357">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="1a52f-357">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="1a52f-358">int</span><span class="sxs-lookup"><span data-stu-id="1a52f-358">int</span></span></p></td>
<td><p><span data-ttu-id="1a52f-359">ビデオ セッション時の最大ビデオ ビット レート。</span><span class="sxs-lookup"><span data-stu-id="1a52f-359">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-360">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="1a52f-360">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="1a52f-361">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="1a52f-361">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-362">失われたビデオ パケット数の割合。</span><span class="sxs-lookup"><span data-stu-id="1a52f-362">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-363">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="1a52f-363">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="1a52f-364">10進法 (9.4)</span><span class="sxs-lookup"><span data-stu-id="1a52f-364">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-365">失われた合計ビデオ フレーム数の割合。</span><span class="sxs-lookup"><span data-stu-id="1a52f-365">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-366">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="1a52f-366">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="1a52f-367">若干</span><span class="sxs-lookup"><span data-stu-id="1a52f-367">bit</span></span></p></td>
<td><p><span data-ttu-id="1a52f-368">不使用。</span><span class="sxs-lookup"><span data-stu-id="1a52f-368">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-369">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="1a52f-369">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="1a52f-370">int</span><span class="sxs-lookup"><span data-stu-id="1a52f-370">int</span></span></p></td>
<td><p><span data-ttu-id="1a52f-371">ビデオに割り当てられた帯域幅の平均。</span><span class="sxs-lookup"><span data-stu-id="1a52f-371">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a52f-372">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="1a52f-372">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="1a52f-373">10進法 (9.4)</span><span class="sxs-lookup"><span data-stu-id="1a52f-373">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="1a52f-374">失われた合計ビデオ フレーム数の割合。</span><span class="sxs-lookup"><span data-stu-id="1a52f-374">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a52f-375">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="1a52f-375">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="1a52f-376">若干</span><span class="sxs-lookup"><span data-stu-id="1a52f-376">bit</span></span></p></td>
<td><p><span data-ttu-id="1a52f-p120">P-Asserted Identity 情報のストリームの方向。1 は、ストリームの方向が発信者から呼び出し先へ向かうことを意味します。0 は、ストリームの方向が呼び出し先から発信者へ向かうことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1a52f-p120">Stream direction for p-asserted identity information. 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

