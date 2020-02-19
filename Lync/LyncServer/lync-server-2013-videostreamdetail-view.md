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
ms.openlocfilehash: 8163915a7af190ad91da50f84bfdb4f57eb023b2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136885"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="e74dd-102">Lync Server 2013 の VideoStreamDetail ビュー</span><span class="sxs-lookup"><span data-stu-id="e74dd-102">VideoStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e74dd-103">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="e74dd-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="e74dd-104">VideoStreamDetail ビューには、データベース内の各ビデオ ストリームに関する情報が格納されています。</span><span class="sxs-lookup"><span data-stu-id="e74dd-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="e74dd-105">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e74dd-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e74dd-106">列</span><span class="sxs-lookup"><span data-stu-id="e74dd-106">Column</span></span></th>
<th><span data-ttu-id="e74dd-107">データ型</span><span class="sxs-lookup"><span data-stu-id="e74dd-107">Data Type</span></span></th>
<th><span data-ttu-id="e74dd-108">説明</span><span class="sxs-lookup"><span data-stu-id="e74dd-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="e74dd-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="e74dd-110">日付型</span><span class="sxs-lookup"><span data-stu-id="e74dd-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="e74dd-111"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="e74dd-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="e74dd-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="e74dd-113">int</span><span class="sxs-lookup"><span data-stu-id="e74dd-113">int</span></span></p></td>
<td><p><span data-ttu-id="e74dd-114"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="e74dd-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="e74dd-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="e74dd-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="e74dd-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e74dd-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="e74dd-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-118">StreamId</span><span class="sxs-lookup"><span data-stu-id="e74dd-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="e74dd-119">int</span><span class="sxs-lookup"><span data-stu-id="e74dd-119">int</span></span></p></td>
<td><p><span data-ttu-id="e74dd-120">メディア ライン内の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="e74dd-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="e74dd-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="e74dd-122">日付型</span><span class="sxs-lookup"><span data-stu-id="e74dd-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="e74dd-123">セッションの開始時刻。</span><span class="sxs-lookup"><span data-stu-id="e74dd-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="e74dd-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="e74dd-125">日付型</span><span class="sxs-lookup"><span data-stu-id="e74dd-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="e74dd-126">セッションの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="e74dd-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="e74dd-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="e74dd-128">int</span><span class="sxs-lookup"><span data-stu-id="e74dd-128">int</span></span></p></td>
<td><p><span data-ttu-id="e74dd-129">通話の優先順位。</span><span class="sxs-lookup"><span data-stu-id="e74dd-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="e74dd-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="e74dd-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e74dd-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-132">発信者プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="e74dd-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="e74dd-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="e74dd-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e74dd-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-135">呼び出し先プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="e74dd-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-136">Caller</span><span class="sxs-lookup"><span data-stu-id="e74dd-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="e74dd-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e74dd-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-138">発信者の URI。</span><span class="sxs-lookup"><span data-stu-id="e74dd-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-139">側</span><span class="sxs-lookup"><span data-stu-id="e74dd-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="e74dd-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e74dd-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-141">呼び出し先の URI。</span><span class="sxs-lookup"><span data-stu-id="e74dd-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="e74dd-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="e74dd-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e74dd-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-144">発信者のユーザー エージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="e74dd-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="e74dd-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="e74dd-146">smallint</span><span class="sxs-lookup"><span data-stu-id="e74dd-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="e74dd-147">発信者のユーザー エージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="e74dd-147">Type of caller’s user agent.</span></span> <span data-ttu-id="e74dd-148">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e74dd-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="e74dd-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="e74dd-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e74dd-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-151">発信者のユーザー エージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="e74dd-151">Category of caller’s user agent.</span></span> <span data-ttu-id="e74dd-152">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e74dd-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="e74dd-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="e74dd-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e74dd-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-155">呼び出し先のユーザー エージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="e74dd-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="e74dd-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="e74dd-157">smallint</span><span class="sxs-lookup"><span data-stu-id="e74dd-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="e74dd-158">呼び出し先のユーザー エージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="e74dd-158">Type of callee’s user agent.</span></span> <span data-ttu-id="e74dd-159">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e74dd-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="e74dd-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="e74dd-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e74dd-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-162">呼び出し先のユーザー エージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="e74dd-162">Category of callee’s user agent.</span></span> <span data-ttu-id="e74dd-163">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e74dd-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="e74dd-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="e74dd-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e74dd-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-166">発信者のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="e74dd-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="e74dd-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="e74dd-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e74dd-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-169">呼び出し先のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="e74dd-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-170">CallerOS</span><span class="sxs-lookup"><span data-stu-id="e74dd-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="e74dd-171">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e74dd-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-172">発信者のエンドポイントのオペレーティング システム (OS)。</span><span class="sxs-lookup"><span data-stu-id="e74dd-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="e74dd-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="e74dd-174">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e74dd-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-175">呼び出し先のエンドポイントのオペレーティング システム (OS)。</span><span class="sxs-lookup"><span data-stu-id="e74dd-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-176">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="e74dd-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="e74dd-177">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e74dd-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-178">発信者のエンドポイントの CPU 名。</span><span class="sxs-lookup"><span data-stu-id="e74dd-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="e74dd-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="e74dd-180">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e74dd-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-181">呼び出し先のエンドポイントの CPU 名。</span><span class="sxs-lookup"><span data-stu-id="e74dd-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-182">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="e74dd-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="e74dd-183">smallint</span><span class="sxs-lookup"><span data-stu-id="e74dd-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="e74dd-184">発信者のエンドポイントの CPU コアの数。</span><span class="sxs-lookup"><span data-stu-id="e74dd-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="e74dd-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="e74dd-186">smallint</span><span class="sxs-lookup"><span data-stu-id="e74dd-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="e74dd-187">呼び出し先のエンドポイントの CPU コアの数。</span><span class="sxs-lookup"><span data-stu-id="e74dd-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-188">Callercpu プロセッサ速度</span><span class="sxs-lookup"><span data-stu-id="e74dd-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="e74dd-189">int</span><span class="sxs-lookup"><span data-stu-id="e74dd-189">int</span></span></p></td>
<td><p><span data-ttu-id="e74dd-190">発信者のエンドポイントの CPU プロセッサ速度。</span><span class="sxs-lookup"><span data-stu-id="e74dd-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-191">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="e74dd-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="e74dd-192">int</span><span class="sxs-lookup"><span data-stu-id="e74dd-192">int</span></span></p></td>
<td><p><span data-ttu-id="e74dd-193">呼び出し先のエンドポイントの CPU プロセッサ速度。</span><span class="sxs-lookup"><span data-stu-id="e74dd-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="e74dd-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="e74dd-195">tinyint</span><span class="sxs-lookup"><span data-stu-id="e74dd-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e74dd-196">発信者のシステムが仮想環境で実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e74dd-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="e74dd-197">詳細については、「 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e74dd-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="e74dd-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="e74dd-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="e74dd-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e74dd-200">呼び出し先のシステムが仮想環境で実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e74dd-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="e74dd-201">詳細については、「 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e74dd-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="e74dd-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="e74dd-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="e74dd-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e74dd-204">メディア パスに関する情報 (直接、リレーなど)。</span><span class="sxs-lookup"><span data-stu-id="e74dd-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="e74dd-205">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e74dd-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="e74dd-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="e74dd-207">int</span><span class="sxs-lookup"><span data-stu-id="e74dd-207">int</span></span></p></td>
<td><p><span data-ttu-id="e74dd-p109">発信者のビット フラグに記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e74dd-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="e74dd-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="e74dd-211">int</span><span class="sxs-lookup"><span data-stu-id="e74dd-211">int</span></span></p></td>
<td><p><span data-ttu-id="e74dd-p110">呼び出し先のビット フラグに記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e74dd-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-214">Transport</span><span class="sxs-lookup"><span data-stu-id="e74dd-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="e74dd-215">int</span><span class="sxs-lookup"><span data-stu-id="e74dd-215">int</span></span></p></td>
<td><p><span data-ttu-id="e74dd-216">トランスポートの種類。0 は UDP、1 は TCP です。</span><span class="sxs-lookup"><span data-stu-id="e74dd-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="e74dd-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e74dd-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="e74dd-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-219">発信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="e74dd-219">IP address of the caller.</span></span> <span data-ttu-id="e74dd-220">IPv4 または IPv6 のアドレスです。</span><span class="sxs-lookup"><span data-stu-id="e74dd-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="e74dd-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="e74dd-222">int</span><span class="sxs-lookup"><span data-stu-id="e74dd-222">int</span></span></p></td>
<td><p><span data-ttu-id="e74dd-223">発信者が使用するポート。</span><span class="sxs-lookup"><span data-stu-id="e74dd-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="e74dd-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="e74dd-225">若干</span><span class="sxs-lookup"><span data-stu-id="e74dd-225">bit</span></span></p></td>
<td><p><span data-ttu-id="e74dd-p112">発信者が組織ネットワーク内にいるかどうかを示します。1 は、発信者がエンタープライズ ネットワーク内に存在することを示し、0 は、発信者がネットワーク外に存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="e74dd-p112">Indicates whether the caller is inside the organization network. 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="e74dd-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e74dd-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="e74dd-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-230">呼び出し先の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="e74dd-230">IP address of the callee.</span></span> <span data-ttu-id="e74dd-231">IPv4 または IPv6 のアドレスです。</span><span class="sxs-lookup"><span data-stu-id="e74dd-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="e74dd-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="e74dd-233">int</span><span class="sxs-lookup"><span data-stu-id="e74dd-233">int</span></span></p></td>
<td><p><span data-ttu-id="e74dd-234">呼び出し先が使用するポート。</span><span class="sxs-lookup"><span data-stu-id="e74dd-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="e74dd-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="e74dd-236">若干</span><span class="sxs-lookup"><span data-stu-id="e74dd-236">bit</span></span></p></td>
<td><p><span data-ttu-id="e74dd-237">呼び出し先が組織ネットワーク内にいるかどうかを示します。1 は、呼び出し先がエンタープライズ ネットワーク内に存在することを示し、0 は、呼び出し先がネットワーク外に存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="e74dd-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="e74dd-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="e74dd-239">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e74dd-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-240">発信者のサイトの名前。</span><span class="sxs-lookup"><span data-stu-id="e74dd-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="e74dd-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="e74dd-242">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e74dd-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-243">発信者のサイトの国/地域の名前。</span><span class="sxs-lookup"><span data-stu-id="e74dd-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="e74dd-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="e74dd-245">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e74dd-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-246">呼び出し先のサイトの名前。</span><span class="sxs-lookup"><span data-stu-id="e74dd-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="e74dd-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="e74dd-248">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e74dd-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-249">呼び出し先のサイトの国/地域の名前。</span><span class="sxs-lookup"><span data-stu-id="e74dd-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="e74dd-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e74dd-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="e74dd-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-252">発信者が使用する音声ビデオ エッジ サービスの IPアドレス。</span><span class="sxs-lookup"><span data-stu-id="e74dd-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="e74dd-253">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e74dd-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="e74dd-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="e74dd-255">int</span><span class="sxs-lookup"><span data-stu-id="e74dd-255">int</span></span></p></td>
<td><p><span data-ttu-id="e74dd-256">発信者が使用する音声ビデオ エッジ サービスのポート。</span><span class="sxs-lookup"><span data-stu-id="e74dd-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="e74dd-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e74dd-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="e74dd-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-259">呼び出し先が使用する音声ビデオ エッジ サービスの IPアドレス キー。</span><span class="sxs-lookup"><span data-stu-id="e74dd-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="e74dd-260">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e74dd-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="e74dd-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="e74dd-262">int</span><span class="sxs-lookup"><span data-stu-id="e74dd-262">int</span></span></p></td>
<td><p><span data-ttu-id="e74dd-263">呼び出し先が使用する音声ビデオ エッジ サービスのポート。</span><span class="sxs-lookup"><span data-stu-id="e74dd-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="e74dd-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="e74dd-265">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e74dd-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-266">発信者のキャプチャ デバイス名。</span><span class="sxs-lookup"><span data-stu-id="e74dd-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="e74dd-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="e74dd-268">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e74dd-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-269">発信者のレンダー デバイス名。</span><span class="sxs-lookup"><span data-stu-id="e74dd-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="e74dd-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e74dd-271">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e74dd-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-272">発信者のキャプチャ デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="e74dd-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="e74dd-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e74dd-274">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e74dd-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-275">発信者のレンダー デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="e74dd-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-276">Calleecapのアーキテクチャ開発</span><span class="sxs-lookup"><span data-stu-id="e74dd-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="e74dd-277">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e74dd-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-278">呼び出し先のキャプチャ デバイス名。</span><span class="sxs-lookup"><span data-stu-id="e74dd-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-279">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="e74dd-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="e74dd-280">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e74dd-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-281">呼び出し先のレンダー デバイス名。</span><span class="sxs-lookup"><span data-stu-id="e74dd-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-282">Callecapん Devdriver</span><span class="sxs-lookup"><span data-stu-id="e74dd-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e74dd-283">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e74dd-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-284">呼び出し先のキャプチャ デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="e74dd-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="e74dd-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e74dd-286">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e74dd-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-287">呼び出し先のレンダー デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="e74dd-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="e74dd-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="e74dd-289">tinyint</span><span class="sxs-lookup"><span data-stu-id="e74dd-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e74dd-290">発信者のネットワーク接続の種類。0 は有線、1 はワイヤレスです。</span><span class="sxs-lookup"><span data-stu-id="e74dd-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="e74dd-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="e74dd-292">若干</span><span class="sxs-lookup"><span data-stu-id="e74dd-292">bit</span></span></p></td>
<td><p><span data-ttu-id="e74dd-p116">発信者が仮想プライベート ネットワークで接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="e74dd-p116">Indicates whether or not the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="e74dd-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="e74dd-296">10進数 (18)</span><span class="sxs-lookup"><span data-stu-id="e74dd-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-297">発信者のエンドポイントのネットワーク リンクの速度 (単位 bps)。</span><span class="sxs-lookup"><span data-stu-id="e74dd-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="e74dd-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="e74dd-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="e74dd-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e74dd-300">呼び出し先のネットワーク接続の種類。0 は有線、1 はワイヤレスです。</span><span class="sxs-lookup"><span data-stu-id="e74dd-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="e74dd-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="e74dd-302">若干</span><span class="sxs-lookup"><span data-stu-id="e74dd-302">bit</span></span></p></td>
<td><p><span data-ttu-id="e74dd-p117">呼び出し先が仮想プライベート ネットワークで接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="e74dd-p117">Indicates whether or not the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="e74dd-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="e74dd-306">10進数 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="e74dd-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-307">呼び出し先のエンドポイントのネットワーク リンクの速度 (単位 bps)。</span><span class="sxs-lookup"><span data-stu-id="e74dd-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="e74dd-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="e74dd-309">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="e74dd-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-310">音声セッションの Narrowband Conversational MOS (音声ストリームに基づく)。</span><span class="sxs-lookup"><span data-stu-id="e74dd-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="e74dd-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="e74dd-312">int</span><span class="sxs-lookup"><span data-stu-id="e74dd-312">int</span></span></p></td>
<td><p><span data-ttu-id="e74dd-p118">さまざまなポリシー設定 (TURN、API、SDP、ポリシー サーバーなど) が構成された特定の送信側ストリームに適用される実際の帯域幅。この帯域幅を実効帯域幅と見なすことはできません。実効帯域幅は、帯域幅の評価に基づいて実際よりも低くなる可能性があります。これは基本的に、送信ストリームで利用できる最大帯域幅です (帯域幅の評価によって課せられる制限を除く)。</span><span class="sxs-lookup"><span data-stu-id="e74dd-p118">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="e74dd-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="e74dd-317">int</span><span class="sxs-lookup"><span data-stu-id="e74dd-317">int</span></span></p></td>
<td><p><span data-ttu-id="e74dd-318">リアルタイム制御プロトコル (RTCP) 統計情報に基づく平均ネットワーク ジッター。</span><span class="sxs-lookup"><span data-stu-id="e74dd-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="e74dd-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="e74dd-320">int</span><span class="sxs-lookup"><span data-stu-id="e74dd-320">int</span></span></p></td>
<td><p><span data-ttu-id="e74dd-321">通話時の最大ネットワーク ジッター。</span><span class="sxs-lookup"><span data-stu-id="e74dd-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-322">要し</span><span class="sxs-lookup"><span data-stu-id="e74dd-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="e74dd-323">int</span><span class="sxs-lookup"><span data-stu-id="e74dd-323">int</span></span></p></td>
<td><p><span data-ttu-id="e74dd-324">RTCP 統計情報に基づく往復時間。</span><span class="sxs-lookup"><span data-stu-id="e74dd-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="e74dd-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="e74dd-326">int</span><span class="sxs-lookup"><span data-stu-id="e74dd-326">int</span></span></p></td>
<td><p><span data-ttu-id="e74dd-327">音声ストリームの最大往復時間。</span><span class="sxs-lookup"><span data-stu-id="e74dd-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="e74dd-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="e74dd-329">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="e74dd-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-330">通話時の平均パケット損失率。</span><span class="sxs-lookup"><span data-stu-id="e74dd-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="e74dd-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="e74dd-332">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="e74dd-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-333">通話時に観測された最大パケット損失。</span><span class="sxs-lookup"><span data-stu-id="e74dd-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="e74dd-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="e74dd-335">int</span><span class="sxs-lookup"><span data-stu-id="e74dd-335">int</span></span></p></td>
<td><p><span data-ttu-id="e74dd-336">ビデオ ストリームのパケット数 (リアルタイム転送プロトコル、RTP)。</span><span class="sxs-lookup"><span data-stu-id="e74dd-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-337">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="e74dd-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="e74dd-338">int</span><span class="sxs-lookup"><span data-stu-id="e74dd-338">int</span></span></p></td>
<td><p><span data-ttu-id="e74dd-339">音声ストリームの帯域幅の推定。</span><span class="sxs-lookup"><span data-stu-id="e74dd-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="e74dd-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="e74dd-341">int</span><span class="sxs-lookup"><span data-stu-id="e74dd-341">int</span></span></p></td>
<td><p><span data-ttu-id="e74dd-342">通話に使用されるオーディオコーデック。 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 の PayloadDescription テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="e74dd-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-343">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="e74dd-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="e74dd-344">文字 (9)</span><span class="sxs-lookup"><span data-stu-id="e74dd-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-p119">幅×高さで示すビデオの解像度 (単位ピクセル)。文字列で報告されます。</span><span class="sxs-lookup"><span data-stu-id="e74dd-p119">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="e74dd-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="e74dd-348">int</span><span class="sxs-lookup"><span data-stu-id="e74dd-348">int</span></span></p></td>
<td><p><span data-ttu-id="e74dd-349">ビデオ ストリームの平均ビット レート。</span><span class="sxs-lookup"><span data-stu-id="e74dd-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="e74dd-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="e74dd-351">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="e74dd-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-352">ビデオの受信フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="e74dd-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="e74dd-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="e74dd-354">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="e74dd-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-355">ビデオの送信フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="e74dd-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="e74dd-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="e74dd-357">int</span><span class="sxs-lookup"><span data-stu-id="e74dd-357">int</span></span></p></td>
<td><p><span data-ttu-id="e74dd-358">ビデオ セッション時の最大ビデオ ビット レート。</span><span class="sxs-lookup"><span data-stu-id="e74dd-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-359">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="e74dd-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="e74dd-360">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="e74dd-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-361">失われたビデオ パケット数の割合。</span><span class="sxs-lookup"><span data-stu-id="e74dd-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="e74dd-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="e74dd-363">10進法 (9.4)</span><span class="sxs-lookup"><span data-stu-id="e74dd-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-364">失われた合計ビデオ フレーム数の割合。</span><span class="sxs-lookup"><span data-stu-id="e74dd-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="e74dd-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="e74dd-366">若干</span><span class="sxs-lookup"><span data-stu-id="e74dd-366">bit</span></span></p></td>
<td><p><span data-ttu-id="e74dd-367">不使用。</span><span class="sxs-lookup"><span data-stu-id="e74dd-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="e74dd-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="e74dd-369">int</span><span class="sxs-lookup"><span data-stu-id="e74dd-369">int</span></span></p></td>
<td><p><span data-ttu-id="e74dd-370">ビデオに割り当てられた帯域幅の平均。</span><span class="sxs-lookup"><span data-stu-id="e74dd-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74dd-371">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="e74dd-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="e74dd-372">10進法 (9.4)</span><span class="sxs-lookup"><span data-stu-id="e74dd-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="e74dd-373">失われた合計ビデオ フレーム数の割合。</span><span class="sxs-lookup"><span data-stu-id="e74dd-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74dd-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="e74dd-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="e74dd-375">若干</span><span class="sxs-lookup"><span data-stu-id="e74dd-375">bit</span></span></p></td>
<td><p><span data-ttu-id="e74dd-p120">P-Asserted Identity 情報のストリームの方向。1 は、ストリームの方向が発信者から呼び出し先へ向かうことを意味します。0 は、ストリームの方向が呼び出し先から発信者へ向かうことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e74dd-p120">Stream direction for p-asserted identity information. 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

