---
title: 'Lync Server 2013: VideoStreamDetail ビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoStreamDetail view
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49733863
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95cc003a0e136a4a4c123355548b95c9566b4b31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="16840-102">Lync Server 2013 の VideoStreamDetail ビュー</span><span class="sxs-lookup"><span data-stu-id="16840-102">VideoStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16840-103">_**最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="16840-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="16840-104">VideoStreamDetail ビューには、データベース内の各ビデオストリームに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="16840-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="16840-105">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="16840-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16840-106">列</span><span class="sxs-lookup"><span data-stu-id="16840-106">Column</span></span></th>
<th><span data-ttu-id="16840-107">データ型</span><span class="sxs-lookup"><span data-stu-id="16840-107">Data Type</span></span></th>
<th><span data-ttu-id="16840-108">説明</span><span class="sxs-lookup"><span data-stu-id="16840-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16840-109">セッション時間</span><span class="sxs-lookup"><span data-stu-id="16840-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="16840-110">datetime</span><span class="sxs-lookup"><span data-stu-id="16840-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="16840-111"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="16840-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="16840-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="16840-113">int</span><span class="sxs-lookup"><span data-stu-id="16840-113">int</span></span></p></td>
<td><p><span data-ttu-id="16840-114"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="16840-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="16840-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="16840-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="16840-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="16840-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="16840-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-118">StreamId</span><span class="sxs-lookup"><span data-stu-id="16840-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="16840-119">int</span><span class="sxs-lookup"><span data-stu-id="16840-119">int</span></span></p></td>
<td><p><span data-ttu-id="16840-120">メディアライン内の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="16840-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="16840-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="16840-122">datetime</span><span class="sxs-lookup"><span data-stu-id="16840-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="16840-123">セッションの開始時刻。</span><span class="sxs-lookup"><span data-stu-id="16840-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="16840-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="16840-125">datetime</span><span class="sxs-lookup"><span data-stu-id="16840-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="16840-126">セッションの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="16840-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="16840-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="16840-128">int</span><span class="sxs-lookup"><span data-stu-id="16840-128">int</span></span></p></td>
<td><p><span data-ttu-id="16840-129">通話の優先度。</span><span class="sxs-lookup"><span data-stu-id="16840-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="16840-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="16840-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="16840-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="16840-132">発信者番号プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="16840-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="16840-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="16840-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="16840-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="16840-135">呼び出し元プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="16840-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-136">[発信者]</span><span class="sxs-lookup"><span data-stu-id="16840-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="16840-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="16840-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="16840-138">発信者の URI。</span><span class="sxs-lookup"><span data-stu-id="16840-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-139">[呼び出し先]</span><span class="sxs-lookup"><span data-stu-id="16840-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="16840-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="16840-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="16840-141">呼び出し先の URI。</span><span class="sxs-lookup"><span data-stu-id="16840-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="16840-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="16840-143">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="16840-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="16840-144">呼び出し元のユーザーエージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="16840-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="16840-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="16840-146">smallint</span><span class="sxs-lookup"><span data-stu-id="16840-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="16840-147">呼び出し元のユーザーエージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="16840-147">Type of caller’s user agent.</span></span> <span data-ttu-id="16840-148">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16840-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="16840-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="16840-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="16840-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="16840-151">呼び出し元のユーザーエージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="16840-151">Category of caller’s user agent.</span></span> <span data-ttu-id="16840-152">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16840-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="16840-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="16840-154">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="16840-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="16840-155">呼び出し先のユーザーエージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="16840-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="16840-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="16840-157">smallint</span><span class="sxs-lookup"><span data-stu-id="16840-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="16840-158">呼び出し先のユーザーエージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="16840-158">Type of callee’s user agent.</span></span> <span data-ttu-id="16840-159">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16840-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="16840-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="16840-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="16840-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="16840-162">呼び出し先のユーザーエージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="16840-162">Category of callee’s user agent.</span></span> <span data-ttu-id="16840-163">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16840-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="16840-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="16840-165">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="16840-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="16840-166">発信者のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="16840-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="16840-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="16840-168">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="16840-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="16840-169">呼び出し先のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="16840-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-170">CallerOS</span><span class="sxs-lookup"><span data-stu-id="16840-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="16840-171">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="16840-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="16840-172">発信者のエンドポイントのオペレーティングシステム (OS)。</span><span class="sxs-lookup"><span data-stu-id="16840-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="16840-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="16840-174">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="16840-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="16840-175">呼び出し先のエンドポイントのオペレーティングシステム (OS)。</span><span class="sxs-lookup"><span data-stu-id="16840-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-176">Caller</span><span class="sxs-lookup"><span data-stu-id="16840-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="16840-177">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="16840-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="16840-178">呼び出し元のエンドポイントの CPU 名。</span><span class="sxs-lookup"><span data-stu-id="16840-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="16840-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="16840-180">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="16840-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="16840-181">呼び出し先のエンドポイントの CPU 名。</span><span class="sxs-lookup"><span data-stu-id="16840-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-182">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="16840-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="16840-183">smallint</span><span class="sxs-lookup"><span data-stu-id="16840-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="16840-184">呼び出し元のエンドポイントの CPU コアの数。</span><span class="sxs-lookup"><span data-stu-id="16840-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="16840-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="16840-186">smallint</span><span class="sxs-lookup"><span data-stu-id="16840-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="16840-187">呼び出し先のエンドポイントの CPU コアの数。</span><span class="sxs-lookup"><span data-stu-id="16840-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-188">Callerプロセッサーの速度</span><span class="sxs-lookup"><span data-stu-id="16840-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="16840-189">int</span><span class="sxs-lookup"><span data-stu-id="16840-189">int</span></span></p></td>
<td><p><span data-ttu-id="16840-190">発信者のエンドポイントの CPU プロセッサ速度。</span><span class="sxs-lookup"><span data-stu-id="16840-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-191">Calleecpuプロセッサー速度</span><span class="sxs-lookup"><span data-stu-id="16840-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="16840-192">int</span><span class="sxs-lookup"><span data-stu-id="16840-192">int</span></span></p></td>
<td><p><span data-ttu-id="16840-193">呼び出し先のエンドポイントの CPU プロセッサ速度。</span><span class="sxs-lookup"><span data-stu-id="16840-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="16840-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="16840-195">tinyint</span><span class="sxs-lookup"><span data-stu-id="16840-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="16840-196">呼び出し元のシステムが仮想環境で実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="16840-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="16840-197">詳細については、「 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16840-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="16840-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="16840-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="16840-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="16840-200">呼び出し先のシステムが仮想環境で実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="16840-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="16840-201">詳細については、「 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16840-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="16840-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="16840-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="16840-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="16840-204">メディアパスについての情報 (ダイレクトまたは中継など)</span><span class="sxs-lookup"><span data-stu-id="16840-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="16840-205">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16840-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="16840-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="16840-207">int</span><span class="sxs-lookup"><span data-stu-id="16840-207">int</span></span></p></td>
<td><p><span data-ttu-id="16840-208">発信者の bits フラグで説明されている対話型接続確立 (ICE) プロセスに関する情報。</span><span class="sxs-lookup"><span data-stu-id="16840-208">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="16840-209">詳細については、「エクスペリエンスの品質監視サーバープロトコルの仕様」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16840-209">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="16840-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="16840-211">int</span><span class="sxs-lookup"><span data-stu-id="16840-211">int</span></span></p></td>
<td><p><span data-ttu-id="16840-212">対話式接続確立 (ICE) プロセスについて詳しくは、「呼び出し先のビットフラグ」で説明します。</span><span class="sxs-lookup"><span data-stu-id="16840-212">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="16840-213">詳細については、「エクスペリエンスの品質監視サーバープロトコルの仕様」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16840-213">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-214">Transport</span><span class="sxs-lookup"><span data-stu-id="16840-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="16840-215">int</span><span class="sxs-lookup"><span data-stu-id="16840-215">int</span></span></p></td>
<td><p><span data-ttu-id="16840-216">トランスポートの種類: 0 は UDP、1は TCP です。</span><span class="sxs-lookup"><span data-stu-id="16840-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="16840-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="16840-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="16840-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="16840-219">発信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="16840-219">IP address of the caller.</span></span> <span data-ttu-id="16840-220">これは IPv4 または IPv6 アドレスのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="16840-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="16840-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="16840-222">int</span><span class="sxs-lookup"><span data-stu-id="16840-222">int</span></span></p></td>
<td><p><span data-ttu-id="16840-223">発信者によって使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="16840-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="16840-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="16840-225">bit</span><span class="sxs-lookup"><span data-stu-id="16840-225">bit</span></span></p></td>
<td><p><span data-ttu-id="16840-226">発信者が組織のネットワーク内にあるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="16840-226">Indicates whether the caller is inside the organization network.</span></span> <span data-ttu-id="16840-227">1: 発信者がエンタープライズネットワーク内にあることを示します。0は、呼び出し元がネットワークの外部にあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="16840-227">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="16840-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="16840-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="16840-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="16840-230">呼び出し先の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="16840-230">IP address of the callee.</span></span> <span data-ttu-id="16840-231">これは IPv4 または IPv6 アドレスのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="16840-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="16840-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="16840-233">int</span><span class="sxs-lookup"><span data-stu-id="16840-233">int</span></span></p></td>
<td><p><span data-ttu-id="16840-234">呼び出し先によって使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="16840-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="16840-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="16840-236">bit</span><span class="sxs-lookup"><span data-stu-id="16840-236">bit</span></span></p></td>
<td><p><span data-ttu-id="16840-237">発信者が組織のネットワーク内にあるかどうかを示します。1は、呼び出し元がエンタープライズネットワーク内にあることを意味します。0は、呼び出し先がネットワークの外部にあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="16840-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="16840-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="16840-239">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="16840-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="16840-240">発信者のサイトの名前。</span><span class="sxs-lookup"><span data-stu-id="16840-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="16840-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="16840-242">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="16840-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="16840-243">発信者のサイトの国/地域の名前です。</span><span class="sxs-lookup"><span data-stu-id="16840-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="16840-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="16840-245">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="16840-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="16840-246">呼び出し先のサイトの名前。</span><span class="sxs-lookup"><span data-stu-id="16840-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="16840-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="16840-248">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="16840-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="16840-249">呼び出し先のサイトの国/地域の名前です。</span><span class="sxs-lookup"><span data-stu-id="16840-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="16840-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="16840-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="16840-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="16840-252">発信者によって使用される A/V Edge サービスの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="16840-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="16840-253">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16840-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="16840-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="16840-255">int</span><span class="sxs-lookup"><span data-stu-id="16840-255">int</span></span></p></td>
<td><p><span data-ttu-id="16840-256">発信者によって使用される A/V Edge サービス上のポート。</span><span class="sxs-lookup"><span data-stu-id="16840-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="16840-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="16840-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="16840-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="16840-259">呼び出し先によって使用される A/V エッジサービスの IP アドレスキー。</span><span class="sxs-lookup"><span data-stu-id="16840-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="16840-260">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16840-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="16840-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="16840-262">int</span><span class="sxs-lookup"><span data-stu-id="16840-262">int</span></span></p></td>
<td><p><span data-ttu-id="16840-263">呼び出し先によって使用される A/V エッジサービスのポート。</span><span class="sxs-lookup"><span data-stu-id="16840-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="16840-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="16840-265">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="16840-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="16840-266">発信者のキャプチャデバイス名。</span><span class="sxs-lookup"><span data-stu-id="16840-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="16840-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="16840-268">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="16840-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="16840-269">発信者のレンダーデバイス名。</span><span class="sxs-lookup"><span data-stu-id="16840-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="16840-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="16840-271">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="16840-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="16840-272">発信者のキャプチャデバイスドライバー名。</span><span class="sxs-lookup"><span data-stu-id="16840-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="16840-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="16840-274">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="16840-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="16840-275">発信者のレンダーデバイスドライバー名。</span><span class="sxs-lookup"><span data-stu-id="16840-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-276">Calleecapdev</span><span class="sxs-lookup"><span data-stu-id="16840-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="16840-277">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="16840-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="16840-278">呼び出し先のキャプチャデバイス名。</span><span class="sxs-lookup"><span data-stu-id="16840-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-279">Calle・ Enderdev</span><span class="sxs-lookup"><span data-stu-id="16840-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="16840-280">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="16840-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="16840-281">呼び出し先のレンダリングデバイス名。</span><span class="sxs-lookup"><span data-stu-id="16840-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-282">Callecap・ Devdriver</span><span class="sxs-lookup"><span data-stu-id="16840-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="16840-283">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="16840-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="16840-284">呼び出し先のキャプチャデバイスドライバー名。</span><span class="sxs-lookup"><span data-stu-id="16840-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="16840-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="16840-286">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="16840-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="16840-287">呼び出し先のレンダリングデバイスドライバー名。</span><span class="sxs-lookup"><span data-stu-id="16840-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="16840-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="16840-289">tinyint</span><span class="sxs-lookup"><span data-stu-id="16840-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="16840-290">発信者のネットワーク接続の種類: 0 は有線、1はワイヤレス。</span><span class="sxs-lookup"><span data-stu-id="16840-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="16840-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="16840-292">bit</span><span class="sxs-lookup"><span data-stu-id="16840-292">bit</span></span></p></td>
<td><p><span data-ttu-id="16840-293">発信者が仮想プライベートネットワーク経由で接続しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="16840-293">Indicates whether or not the caller connected over a virtual private network.</span></span> <span data-ttu-id="16840-294">1は仮想プライベートネットワーク (VPN)、0は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="16840-294">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="16840-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="16840-296">10進数 (18,)</span><span class="sxs-lookup"><span data-stu-id="16840-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="16840-297">発信者のエンドポイントのネットワークリンク速度 (bps)。</span><span class="sxs-lookup"><span data-stu-id="16840-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="16840-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="16840-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="16840-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="16840-300">呼び出し先のネットワーク接続の種類: 0 は有線、1はワイヤレス。</span><span class="sxs-lookup"><span data-stu-id="16840-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="16840-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="16840-302">bit</span><span class="sxs-lookup"><span data-stu-id="16840-302">bit</span></span></p></td>
<td><p><span data-ttu-id="16840-303">呼び出し先が仮想プライベートネットワーク経由で接続されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="16840-303">Indicates whether or not the callee connected over a virtual private network.</span></span> <span data-ttu-id="16840-304">1は仮想プライベートネットワーク (VPN)、0は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="16840-304">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="16840-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="16840-306">10進数 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="16840-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="16840-307">転送先のエンドポイントのネットワークリンク速度 (bps)。</span><span class="sxs-lookup"><span data-stu-id="16840-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="16840-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="16840-309">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="16840-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="16840-310">オーディオセッションの会話 MOS を Narrowband します (両方のオーディオストリームに基づく)。</span><span class="sxs-lookup"><span data-stu-id="16840-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="16840-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="16840-312">int</span><span class="sxs-lookup"><span data-stu-id="16840-312">int</span></span></p></td>
<td><p><span data-ttu-id="16840-313">さまざまなポリシー設定 (TURN、API、SDP、ポリシーサーバーなど) が指定された send side ストリームに適用される実際の帯域幅。</span><span class="sxs-lookup"><span data-stu-id="16840-313">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="16840-314">これは、帯域幅の推定値に基づいて低帯域幅を使用できるため、有効帯域幅と混同しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="16840-314">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="16840-315">これは基本的に最大帯域幅であり、送信ストリームは、帯域幅の推定値によって課された制限を受けません。</span><span class="sxs-lookup"><span data-stu-id="16840-315">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="16840-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="16840-317">int</span><span class="sxs-lookup"><span data-stu-id="16840-317">int</span></span></p></td>
<td><p><span data-ttu-id="16840-318">リアルタイム制御プロトコル (RTCP) の統計情報からの平均ネットワークジッター。</span><span class="sxs-lookup"><span data-stu-id="16840-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="16840-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="16840-320">int</span><span class="sxs-lookup"><span data-stu-id="16840-320">int</span></span></p></td>
<td><p><span data-ttu-id="16840-321">通話中の最大ネットワークジッター。</span><span class="sxs-lookup"><span data-stu-id="16840-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-322">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="16840-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="16840-323">int</span><span class="sxs-lookup"><span data-stu-id="16840-323">int</span></span></p></td>
<td><p><span data-ttu-id="16840-324">RTCP の統計情報からのラウンドトリップ時間。</span><span class="sxs-lookup"><span data-stu-id="16840-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="16840-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="16840-326">int</span><span class="sxs-lookup"><span data-stu-id="16840-326">int</span></span></p></td>
<td><p><span data-ttu-id="16840-327">オーディオストリームの最大ラウンドトリップ時間。</span><span class="sxs-lookup"><span data-stu-id="16840-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="16840-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="16840-329">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="16840-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="16840-330">通話中の平均パケット損失率。</span><span class="sxs-lookup"><span data-stu-id="16840-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="16840-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="16840-332">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="16840-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="16840-333">通話中に発生したパケット損失の上限。</span><span class="sxs-lookup"><span data-stu-id="16840-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="16840-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="16840-335">int</span><span class="sxs-lookup"><span data-stu-id="16840-335">int</span></span></p></td>
<td><p><span data-ttu-id="16840-336">ビデオストリームのパケット数 (リアルタイムトランスポートプロトコル、RTP)。</span><span class="sxs-lookup"><span data-stu-id="16840-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-337">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="16840-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="16840-338">int</span><span class="sxs-lookup"><span data-stu-id="16840-338">int</span></span></p></td>
<td><p><span data-ttu-id="16840-339">オーディオストリームの帯域幅の推定。</span><span class="sxs-lookup"><span data-stu-id="16840-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="16840-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="16840-341">int</span><span class="sxs-lookup"><span data-stu-id="16840-341">int</span></span></p></td>
<td><p><span data-ttu-id="16840-342">通話に使用されるオーディオコーデック。 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 の PayloadDescription テーブル</a>から参照されています。</span><span class="sxs-lookup"><span data-stu-id="16840-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-343">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="16840-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="16840-344">char (9)</span><span class="sxs-lookup"><span data-stu-id="16840-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="16840-345">ピクセル幅にピクセルの高さを掛けたビデオの解像度。</span><span class="sxs-lookup"><span data-stu-id="16840-345">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="16840-346">文字列として報告されます。</span><span class="sxs-lookup"><span data-stu-id="16840-346">Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="16840-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="16840-348">int</span><span class="sxs-lookup"><span data-stu-id="16840-348">int</span></span></p></td>
<td><p><span data-ttu-id="16840-349">ビデオストリームの平均ビットレート。</span><span class="sxs-lookup"><span data-stu-id="16840-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="16840-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="16840-351">10進数 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="16840-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="16840-352">受信したビデオのフレームレート。</span><span class="sxs-lookup"><span data-stu-id="16840-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="16840-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="16840-354">10進数 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="16840-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="16840-355">送信されたビデオのフレームレート。</span><span class="sxs-lookup"><span data-stu-id="16840-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="16840-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="16840-357">int</span><span class="sxs-lookup"><span data-stu-id="16840-357">int</span></span></p></td>
<td><p><span data-ttu-id="16840-358">ビデオセッション中の最大ビデオビットレート。</span><span class="sxs-lookup"><span data-stu-id="16840-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-359">パケット損失率</span><span class="sxs-lookup"><span data-stu-id="16840-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="16840-360">10進数 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="16840-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="16840-361">ビデオパケットが失われた速度。</span><span class="sxs-lookup"><span data-stu-id="16840-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="16840-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="16840-363">10進数 (9.4)</span><span class="sxs-lookup"><span data-stu-id="16840-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="16840-364">失われたビデオフレームの合計のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="16840-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="16840-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="16840-366">bit</span><span class="sxs-lookup"><span data-stu-id="16840-366">bit</span></span></p></td>
<td><p><span data-ttu-id="16840-367">使用されません。</span><span class="sxs-lookup"><span data-stu-id="16840-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="16840-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="16840-369">int</span><span class="sxs-lookup"><span data-stu-id="16840-369">int</span></span></p></td>
<td><p><span data-ttu-id="16840-370">ビデオに割り当てられている平均帯域幅。</span><span class="sxs-lookup"><span data-stu-id="16840-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16840-371">ビデオ</span><span class="sxs-lookup"><span data-stu-id="16840-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="16840-372">10進数 (9.4)</span><span class="sxs-lookup"><span data-stu-id="16840-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="16840-373">紛失したビデオフレームの合計の割合。</span><span class="sxs-lookup"><span data-stu-id="16840-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16840-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="16840-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="16840-375">bit</span><span class="sxs-lookup"><span data-stu-id="16840-375">bit</span></span></p></td>
<td><p><span data-ttu-id="16840-376">P がアサートした id 情報のストリームの方向。</span><span class="sxs-lookup"><span data-stu-id="16840-376">Stream direction for p-asserted identity information.</span></span> <span data-ttu-id="16840-377">1は、ストリームの方向を呼び出し元から呼び出し先に転送することを意味します。0は、ストリームの方向を呼び出し元から呼び出し元に転送します。</span><span class="sxs-lookup"><span data-stu-id="16840-377">1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

