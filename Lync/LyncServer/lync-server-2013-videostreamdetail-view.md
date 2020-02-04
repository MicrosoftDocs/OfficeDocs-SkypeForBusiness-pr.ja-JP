---
title: 'Lync Server 2013: VideoStreamDetail ビュー'
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
ms.openlocfilehash: dfa754fbcc24377b07bab3b13473adb1c5e953ea
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="4f5fd-102">Lync Server 2013 の VideoStreamDetail ビュー</span><span class="sxs-lookup"><span data-stu-id="4f5fd-102">VideoStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f5fd-103">_**最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="4f5fd-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="4f5fd-104">VideoStreamDetail ビューには、データベース内の各ビデオストリームに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="4f5fd-105">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f5fd-106">列</span><span class="sxs-lookup"><span data-stu-id="4f5fd-106">Column</span></span></th>
<th><span data-ttu-id="4f5fd-107">データ型</span><span class="sxs-lookup"><span data-stu-id="4f5fd-107">Data Type</span></span></th>
<th><span data-ttu-id="4f5fd-108">説明</span><span class="sxs-lookup"><span data-stu-id="4f5fd-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-109">セッション時間</span><span class="sxs-lookup"><span data-stu-id="4f5fd-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-110">datetime</span><span class="sxs-lookup"><span data-stu-id="4f5fd-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-111"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="4f5fd-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-113">int</span><span class="sxs-lookup"><span data-stu-id="4f5fd-113">int</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-114"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="4f5fd-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="4f5fd-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-118">StreamId</span><span class="sxs-lookup"><span data-stu-id="4f5fd-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-119">int</span><span class="sxs-lookup"><span data-stu-id="4f5fd-119">int</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-120">メディアライン内の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="4f5fd-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-122">datetime</span><span class="sxs-lookup"><span data-stu-id="4f5fd-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-123">セッションの開始時刻。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="4f5fd-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-125">datetime</span><span class="sxs-lookup"><span data-stu-id="4f5fd-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-126">セッションの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="4f5fd-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-128">int</span><span class="sxs-lookup"><span data-stu-id="4f5fd-128">int</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-129">通話の優先度。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="4f5fd-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-132">発信者番号プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="4f5fd-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-135">呼び出し元プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-136">[発信者]</span><span class="sxs-lookup"><span data-stu-id="4f5fd-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-138">発信者の URI。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-139">[呼び出し先]</span><span class="sxs-lookup"><span data-stu-id="4f5fd-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-141">呼び出し先の URI。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="4f5fd-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-143">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-144">呼び出し元のユーザーエージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="4f5fd-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-146">smallint</span><span class="sxs-lookup"><span data-stu-id="4f5fd-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-147">呼び出し元のユーザーエージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-147">Type of caller’s user agent.</span></span> <span data-ttu-id="4f5fd-148">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="4f5fd-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-151">呼び出し元のユーザーエージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-151">Category of caller’s user agent.</span></span> <span data-ttu-id="4f5fd-152">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="4f5fd-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-154">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-155">呼び出し先のユーザーエージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="4f5fd-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-157">smallint</span><span class="sxs-lookup"><span data-stu-id="4f5fd-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-158">呼び出し先のユーザーエージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-158">Type of callee’s user agent.</span></span> <span data-ttu-id="4f5fd-159">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="4f5fd-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-162">呼び出し先のユーザーエージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-162">Category of callee’s user agent.</span></span> <span data-ttu-id="4f5fd-163">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="4f5fd-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-165">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-166">発信者のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="4f5fd-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-168">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-169">呼び出し先のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-170">CallerOS</span><span class="sxs-lookup"><span data-stu-id="4f5fd-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-171">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4f5fd-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-172">発信者のエンドポイントのオペレーティングシステム (OS)。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="4f5fd-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-174">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4f5fd-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-175">呼び出し先のエンドポイントのオペレーティングシステム (OS)。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-176">Caller</span><span class="sxs-lookup"><span data-stu-id="4f5fd-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-177">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4f5fd-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-178">呼び出し元のエンドポイントの CPU 名。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="4f5fd-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-180">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4f5fd-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-181">呼び出し先のエンドポイントの CPU 名。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-182">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="4f5fd-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-183">smallint</span><span class="sxs-lookup"><span data-stu-id="4f5fd-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-184">呼び出し元のエンドポイントの CPU コアの数。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="4f5fd-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-186">smallint</span><span class="sxs-lookup"><span data-stu-id="4f5fd-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-187">呼び出し先のエンドポイントの CPU コアの数。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-188">Callerプロセッサーの速度</span><span class="sxs-lookup"><span data-stu-id="4f5fd-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-189">int</span><span class="sxs-lookup"><span data-stu-id="4f5fd-189">int</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-190">発信者のエンドポイントの CPU プロセッサ速度。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-191">Calleecpuプロセッサー速度</span><span class="sxs-lookup"><span data-stu-id="4f5fd-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-192">int</span><span class="sxs-lookup"><span data-stu-id="4f5fd-192">int</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-193">呼び出し先のエンドポイントの CPU プロセッサ速度。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="4f5fd-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-195">tinyint</span><span class="sxs-lookup"><span data-stu-id="4f5fd-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-196">呼び出し元のシステムが仮想環境で実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="4f5fd-197">詳細については、「 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="4f5fd-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="4f5fd-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-200">呼び出し先のシステムが仮想環境で実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="4f5fd-201">詳細については、「 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="4f5fd-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="4f5fd-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-204">メディアパスについての情報 (ダイレクトまたは中継など)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="4f5fd-205">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="4f5fd-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-207">int</span><span class="sxs-lookup"><span data-stu-id="4f5fd-207">int</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-208">発信者の bits フラグで説明されている対話型接続確立 (ICE) プロセスに関する情報。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-208">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="4f5fd-209">詳細については、「エクスペリエンスの品質監視サーバープロトコルの仕様」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-209">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="4f5fd-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-211">int</span><span class="sxs-lookup"><span data-stu-id="4f5fd-211">int</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-212">対話式接続確立 (ICE) プロセスについて詳しくは、「呼び出し先のビットフラグ」で説明します。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-212">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="4f5fd-213">詳細については、「エクスペリエンスの品質監視サーバープロトコルの仕様」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-213">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-214">Transport</span><span class="sxs-lookup"><span data-stu-id="4f5fd-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-215">int</span><span class="sxs-lookup"><span data-stu-id="4f5fd-215">int</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-216">トランスポートの種類: 0 は UDP、1は TCP です。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="4f5fd-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-219">発信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-219">IP address of the caller.</span></span> <span data-ttu-id="4f5fd-220">これは IPv4 または IPv6 アドレスのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="4f5fd-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-222">int</span><span class="sxs-lookup"><span data-stu-id="4f5fd-222">int</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-223">発信者によって使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="4f5fd-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-225">bit</span><span class="sxs-lookup"><span data-stu-id="4f5fd-225">bit</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-226">発信者が組織のネットワーク内にあるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-226">Indicates whether the caller is inside the organization network.</span></span> <span data-ttu-id="4f5fd-227">1: 発信者がエンタープライズネットワーク内にあることを示します。0は、呼び出し元がネットワークの外部にあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-227">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="4f5fd-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-230">呼び出し先の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-230">IP address of the callee.</span></span> <span data-ttu-id="4f5fd-231">これは IPv4 または IPv6 アドレスのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="4f5fd-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-233">int</span><span class="sxs-lookup"><span data-stu-id="4f5fd-233">int</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-234">呼び出し先によって使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="4f5fd-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-236">bit</span><span class="sxs-lookup"><span data-stu-id="4f5fd-236">bit</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-237">発信者が組織のネットワーク内にあるかどうかを示します。1は、呼び出し元がエンタープライズネットワーク内にあることを意味します。0は、呼び出し先がネットワークの外部にあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="4f5fd-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-239">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4f5fd-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-240">発信者のサイトの名前。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="4f5fd-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-242">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4f5fd-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-243">発信者のサイトの国/地域の名前です。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="4f5fd-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-245">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4f5fd-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-246">呼び出し先のサイトの名前。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="4f5fd-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-248">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4f5fd-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-249">呼び出し先のサイトの国/地域の名前です。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="4f5fd-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-252">発信者によって使用される A/V Edge サービスの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="4f5fd-253">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="4f5fd-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-255">int</span><span class="sxs-lookup"><span data-stu-id="4f5fd-255">int</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-256">発信者によって使用される A/V Edge サービス上のポート。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="4f5fd-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-259">呼び出し先によって使用される A/V エッジサービスの IP アドレスキー。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="4f5fd-260">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="4f5fd-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-262">int</span><span class="sxs-lookup"><span data-stu-id="4f5fd-262">int</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-263">呼び出し先によって使用される A/V エッジサービスのポート。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="4f5fd-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-265">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-266">発信者のキャプチャデバイス名。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="4f5fd-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-268">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-269">発信者のレンダーデバイス名。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="4f5fd-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-271">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-272">発信者のキャプチャデバイスドライバー名。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="4f5fd-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-274">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-275">発信者のレンダーデバイスドライバー名。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-276">Calleecapdev</span><span class="sxs-lookup"><span data-stu-id="4f5fd-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-277">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-278">呼び出し先のキャプチャデバイス名。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-279">Calle・ Enderdev</span><span class="sxs-lookup"><span data-stu-id="4f5fd-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-280">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-281">呼び出し先のレンダリングデバイス名。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-282">Callecap・ Devdriver</span><span class="sxs-lookup"><span data-stu-id="4f5fd-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-283">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-284">呼び出し先のキャプチャデバイスドライバー名。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="4f5fd-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-286">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-287">呼び出し先のレンダリングデバイスドライバー名。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="4f5fd-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-289">tinyint</span><span class="sxs-lookup"><span data-stu-id="4f5fd-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-290">発信者のネットワーク接続の種類: 0 は有線、1はワイヤレス。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="4f5fd-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-292">bit</span><span class="sxs-lookup"><span data-stu-id="4f5fd-292">bit</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-293">発信者が仮想プライベートネットワーク経由で接続しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-293">Indicates whether or not the caller connected over a virtual private network.</span></span> <span data-ttu-id="4f5fd-294">1は仮想プライベートネットワーク (VPN)、0は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-294">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="4f5fd-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-296">10進数 (18,)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-297">発信者のエンドポイントのネットワークリンク速度 (bps)。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="4f5fd-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="4f5fd-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-300">呼び出し先のネットワーク接続の種類: 0 は有線、1はワイヤレス。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="4f5fd-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-302">bit</span><span class="sxs-lookup"><span data-stu-id="4f5fd-302">bit</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-303">呼び出し先が仮想プライベートネットワーク経由で接続されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-303">Indicates whether or not the callee connected over a virtual private network.</span></span> <span data-ttu-id="4f5fd-304">1は仮想プライベートネットワーク (VPN)、0は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-304">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="4f5fd-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-306">10進数 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-307">転送先のエンドポイントのネットワークリンク速度 (bps)。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="4f5fd-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-309">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-310">オーディオセッションの会話 MOS を Narrowband します (両方のオーディオストリームに基づく)。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="4f5fd-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-312">int</span><span class="sxs-lookup"><span data-stu-id="4f5fd-312">int</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-313">さまざまなポリシー設定 (TURN、API、SDP、ポリシーサーバーなど) が指定された send side ストリームに適用される実際の帯域幅。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-313">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="4f5fd-314">これは、帯域幅の推定値に基づいて低帯域幅を使用できるため、有効帯域幅と混同しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-314">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="4f5fd-315">これは基本的に最大帯域幅であり、送信ストリームは、帯域幅の推定値によって課された制限を受けません。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-315">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="4f5fd-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-317">int</span><span class="sxs-lookup"><span data-stu-id="4f5fd-317">int</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-318">リアルタイム制御プロトコル (RTCP) の統計情報からの平均ネットワークジッター。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="4f5fd-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-320">int</span><span class="sxs-lookup"><span data-stu-id="4f5fd-320">int</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-321">通話中の最大ネットワークジッター。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-322">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="4f5fd-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-323">int</span><span class="sxs-lookup"><span data-stu-id="4f5fd-323">int</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-324">RTCP の統計情報からのラウンドトリップ時間。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="4f5fd-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-326">int</span><span class="sxs-lookup"><span data-stu-id="4f5fd-326">int</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-327">オーディオストリームの最大ラウンドトリップ時間。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="4f5fd-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-329">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-330">通話中の平均パケット損失率。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="4f5fd-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-332">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-333">通話中に発生したパケット損失の上限。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="4f5fd-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-335">int</span><span class="sxs-lookup"><span data-stu-id="4f5fd-335">int</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-336">ビデオストリームのパケット数 (リアルタイムトランスポートプロトコル、RTP)。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-337">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="4f5fd-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-338">int</span><span class="sxs-lookup"><span data-stu-id="4f5fd-338">int</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-339">オーディオストリームの帯域幅の推定。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="4f5fd-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-341">int</span><span class="sxs-lookup"><span data-stu-id="4f5fd-341">int</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-342">通話に使用されるオーディオコーデック。 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 の PayloadDescription テーブル</a>から参照されています。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-343">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="4f5fd-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-344">char (9)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-345">ピクセル幅にピクセルの高さを掛けたビデオの解像度。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-345">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="4f5fd-346">文字列として報告されます。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-346">Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="4f5fd-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-348">int</span><span class="sxs-lookup"><span data-stu-id="4f5fd-348">int</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-349">ビデオストリームの平均ビットレート。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="4f5fd-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-351">10進数 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-352">受信したビデオのフレームレート。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="4f5fd-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-354">10進数 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-355">送信されたビデオのフレームレート。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="4f5fd-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-357">int</span><span class="sxs-lookup"><span data-stu-id="4f5fd-357">int</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-358">ビデオセッション中の最大ビデオビットレート。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-359">パケット損失率</span><span class="sxs-lookup"><span data-stu-id="4f5fd-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-360">10進数 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-361">ビデオパケットが失われた速度。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="4f5fd-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-363">10進数 (9.4)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-364">失われたビデオフレームの合計のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="4f5fd-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-366">bit</span><span class="sxs-lookup"><span data-stu-id="4f5fd-366">bit</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-367">使用されません。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="4f5fd-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-369">int</span><span class="sxs-lookup"><span data-stu-id="4f5fd-369">int</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-370">ビデオに割り当てられている平均帯域幅。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f5fd-371">ビデオ</span><span class="sxs-lookup"><span data-stu-id="4f5fd-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-372">10進数 (9.4)</span><span class="sxs-lookup"><span data-stu-id="4f5fd-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-373">紛失したビデオフレームの合計の割合。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f5fd-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="4f5fd-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-375">bit</span><span class="sxs-lookup"><span data-stu-id="4f5fd-375">bit</span></span></p></td>
<td><p><span data-ttu-id="4f5fd-376">P がアサートした id 情報のストリームの方向。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-376">Stream direction for p-asserted identity information.</span></span> <span data-ttu-id="4f5fd-377">1は、ストリームの方向を呼び出し元から呼び出し先に転送することを意味します。0は、ストリームの方向を呼び出し元から呼び出し元に転送します。</span><span class="sxs-lookup"><span data-stu-id="4f5fd-377">1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

