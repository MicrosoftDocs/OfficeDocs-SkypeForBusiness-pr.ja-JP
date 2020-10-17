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
ms.openlocfilehash: 3d419800842fed080efe4005e7282a25c91f29df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518524"
---
# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="4ab94-102">Lync Server 2013 の VideoStreamDetail ビュー</span><span class="sxs-lookup"><span data-stu-id="4ab94-102">VideoStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ab94-103">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="4ab94-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="4ab94-104">VideoStreamDetail ビューには、データベース内の各ビデオ ストリームに関する情報が格納されています。</span><span class="sxs-lookup"><span data-stu-id="4ab94-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="4ab94-105">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4ab94-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4ab94-106">Column</span><span class="sxs-lookup"><span data-stu-id="4ab94-106">Column</span></span></th>
<th><span data-ttu-id="4ab94-107">データ型</span><span class="sxs-lookup"><span data-stu-id="4ab94-107">Data Type</span></span></th>
<th><span data-ttu-id="4ab94-108">説明</span><span class="sxs-lookup"><span data-stu-id="4ab94-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="4ab94-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="4ab94-110">日付型</span><span class="sxs-lookup"><span data-stu-id="4ab94-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="4ab94-111"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="4ab94-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="4ab94-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="4ab94-113">int</span><span class="sxs-lookup"><span data-stu-id="4ab94-113">int</span></span></p></td>
<td><p><span data-ttu-id="4ab94-114"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="4ab94-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="4ab94-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="4ab94-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="4ab94-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4ab94-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="4ab94-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-118">StreamId</span><span class="sxs-lookup"><span data-stu-id="4ab94-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="4ab94-119">int</span><span class="sxs-lookup"><span data-stu-id="4ab94-119">int</span></span></p></td>
<td><p><span data-ttu-id="4ab94-120">メディア ライン内の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="4ab94-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="4ab94-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="4ab94-122">日付型</span><span class="sxs-lookup"><span data-stu-id="4ab94-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="4ab94-123">セッションの開始時刻。</span><span class="sxs-lookup"><span data-stu-id="4ab94-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="4ab94-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="4ab94-125">日付型</span><span class="sxs-lookup"><span data-stu-id="4ab94-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="4ab94-126">セッションの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="4ab94-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="4ab94-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="4ab94-128">int</span><span class="sxs-lookup"><span data-stu-id="4ab94-128">int</span></span></p></td>
<td><p><span data-ttu-id="4ab94-129">通話の優先順位。</span><span class="sxs-lookup"><span data-stu-id="4ab94-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="4ab94-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="4ab94-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4ab94-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-132">発信者プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="4ab94-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="4ab94-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="4ab94-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4ab94-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-135">呼び出し先プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="4ab94-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-136">Caller</span><span class="sxs-lookup"><span data-stu-id="4ab94-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="4ab94-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="4ab94-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-138">発信者の URI。</span><span class="sxs-lookup"><span data-stu-id="4ab94-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-139">側</span><span class="sxs-lookup"><span data-stu-id="4ab94-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="4ab94-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="4ab94-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-141">呼び出し先の URI。</span><span class="sxs-lookup"><span data-stu-id="4ab94-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="4ab94-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="4ab94-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4ab94-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-144">発信者のユーザー エージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="4ab94-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="4ab94-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="4ab94-146">smallint</span><span class="sxs-lookup"><span data-stu-id="4ab94-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="4ab94-147">発信者のユーザー エージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="4ab94-147">Type of caller’s user agent.</span></span> <span data-ttu-id="4ab94-148">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ab94-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="4ab94-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="4ab94-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="4ab94-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-151">発信者のユーザー エージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="4ab94-151">Category of caller’s user agent.</span></span> <span data-ttu-id="4ab94-152">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ab94-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="4ab94-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="4ab94-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4ab94-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-155">呼び出し先のユーザー エージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="4ab94-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="4ab94-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="4ab94-157">smallint</span><span class="sxs-lookup"><span data-stu-id="4ab94-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="4ab94-158">呼び出し先のユーザー エージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="4ab94-158">Type of callee’s user agent.</span></span> <span data-ttu-id="4ab94-159">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ab94-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="4ab94-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="4ab94-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="4ab94-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-162">呼び出し先のユーザー エージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="4ab94-162">Category of callee’s user agent.</span></span> <span data-ttu-id="4ab94-163">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ab94-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="4ab94-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="4ab94-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4ab94-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-166">発信者のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="4ab94-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="4ab94-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="4ab94-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4ab94-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-169">呼び出し先のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="4ab94-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-170">CallerOS</span><span class="sxs-lookup"><span data-stu-id="4ab94-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="4ab94-171">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4ab94-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-172">発信者のエンドポイントのオペレーティング システム (OS)。</span><span class="sxs-lookup"><span data-stu-id="4ab94-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="4ab94-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="4ab94-174">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4ab94-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-175">呼び出し先のエンドポイントのオペレーティング システム (OS)。</span><span class="sxs-lookup"><span data-stu-id="4ab94-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-176">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="4ab94-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="4ab94-177">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4ab94-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-178">発信者のエンドポイントの CPU 名。</span><span class="sxs-lookup"><span data-stu-id="4ab94-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="4ab94-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="4ab94-180">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4ab94-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-181">呼び出し先のエンドポイントの CPU 名。</span><span class="sxs-lookup"><span data-stu-id="4ab94-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-182">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="4ab94-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="4ab94-183">smallint</span><span class="sxs-lookup"><span data-stu-id="4ab94-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="4ab94-184">発信者のエンドポイントの CPU コアの数。</span><span class="sxs-lookup"><span data-stu-id="4ab94-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="4ab94-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="4ab94-186">smallint</span><span class="sxs-lookup"><span data-stu-id="4ab94-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="4ab94-187">呼び出し先のエンドポイントの CPU コアの数。</span><span class="sxs-lookup"><span data-stu-id="4ab94-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-188">Callercpu プロセッサ速度</span><span class="sxs-lookup"><span data-stu-id="4ab94-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="4ab94-189">int</span><span class="sxs-lookup"><span data-stu-id="4ab94-189">int</span></span></p></td>
<td><p><span data-ttu-id="4ab94-190">発信者のエンドポイントの CPU プロセッサ速度。</span><span class="sxs-lookup"><span data-stu-id="4ab94-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-191">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="4ab94-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="4ab94-192">int</span><span class="sxs-lookup"><span data-stu-id="4ab94-192">int</span></span></p></td>
<td><p><span data-ttu-id="4ab94-193">呼び出し先のエンドポイントの CPU プロセッサ速度。</span><span class="sxs-lookup"><span data-stu-id="4ab94-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="4ab94-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="4ab94-195">tinyint</span><span class="sxs-lookup"><span data-stu-id="4ab94-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4ab94-196">発信者のシステムが仮想環境で実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4ab94-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="4ab94-197">詳細については、「 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ab94-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="4ab94-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="4ab94-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="4ab94-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4ab94-200">呼び出し先のシステムが仮想環境で実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4ab94-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="4ab94-201">詳細については、「 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ab94-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="4ab94-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="4ab94-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="4ab94-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4ab94-204">メディア パスに関する情報 (直接、リレーなど)。</span><span class="sxs-lookup"><span data-stu-id="4ab94-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="4ab94-205">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ab94-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="4ab94-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="4ab94-207">int</span><span class="sxs-lookup"><span data-stu-id="4ab94-207">int</span></span></p></td>
<td><p><span data-ttu-id="4ab94-p109">発信者のビット フラグに記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ab94-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="4ab94-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="4ab94-211">int</span><span class="sxs-lookup"><span data-stu-id="4ab94-211">int</span></span></p></td>
<td><p><span data-ttu-id="4ab94-p110">呼び出し先のビット フラグに記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ab94-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-214">Transport</span><span class="sxs-lookup"><span data-stu-id="4ab94-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="4ab94-215">int</span><span class="sxs-lookup"><span data-stu-id="4ab94-215">int</span></span></p></td>
<td><p><span data-ttu-id="4ab94-216">トランスポートの種類。0 は UDP、1 は TCP です。</span><span class="sxs-lookup"><span data-stu-id="4ab94-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="4ab94-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4ab94-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="4ab94-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-219">発信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="4ab94-219">IP address of the caller.</span></span> <span data-ttu-id="4ab94-220">IPv4 または IPv6 のアドレスです。</span><span class="sxs-lookup"><span data-stu-id="4ab94-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="4ab94-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="4ab94-222">int</span><span class="sxs-lookup"><span data-stu-id="4ab94-222">int</span></span></p></td>
<td><p><span data-ttu-id="4ab94-223">発信者が使用するポート。</span><span class="sxs-lookup"><span data-stu-id="4ab94-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="4ab94-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="4ab94-225">若干</span><span class="sxs-lookup"><span data-stu-id="4ab94-225">bit</span></span></p></td>
<td><p><span data-ttu-id="4ab94-p112">発信者が組織ネットワーク内にいるかどうかを示します。1 は、発信者がエンタープライズ ネットワーク内に存在することを示し、0 は、発信者がネットワーク外に存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="4ab94-p112">Indicates whether the caller is inside the organization network. 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="4ab94-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4ab94-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="4ab94-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-230">呼び出し先の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="4ab94-230">IP address of the callee.</span></span> <span data-ttu-id="4ab94-231">IPv4 または IPv6 のアドレスです。</span><span class="sxs-lookup"><span data-stu-id="4ab94-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="4ab94-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="4ab94-233">int</span><span class="sxs-lookup"><span data-stu-id="4ab94-233">int</span></span></p></td>
<td><p><span data-ttu-id="4ab94-234">呼び出し先が使用するポート。</span><span class="sxs-lookup"><span data-stu-id="4ab94-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="4ab94-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="4ab94-236">若干</span><span class="sxs-lookup"><span data-stu-id="4ab94-236">bit</span></span></p></td>
<td><p><span data-ttu-id="4ab94-237">呼び出し先が組織ネットワーク内にいるかどうかを示します。1 は、呼び出し先がエンタープライズ ネットワーク内に存在することを示し、0 は、呼び出し先がネットワーク外に存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="4ab94-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="4ab94-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="4ab94-239">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4ab94-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-240">発信者のサイトの名前。</span><span class="sxs-lookup"><span data-stu-id="4ab94-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="4ab94-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="4ab94-242">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4ab94-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-243">発信者のサイトの国/地域の名前。</span><span class="sxs-lookup"><span data-stu-id="4ab94-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="4ab94-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="4ab94-245">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4ab94-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-246">呼び出し先のサイトの名前。</span><span class="sxs-lookup"><span data-stu-id="4ab94-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="4ab94-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="4ab94-248">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4ab94-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-249">呼び出し先のサイトの国/地域の名前。</span><span class="sxs-lookup"><span data-stu-id="4ab94-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="4ab94-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4ab94-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="4ab94-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-252">発信者が使用する音声ビデオ エッジ サービスの IPアドレス。</span><span class="sxs-lookup"><span data-stu-id="4ab94-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="4ab94-253">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ab94-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="4ab94-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="4ab94-255">int</span><span class="sxs-lookup"><span data-stu-id="4ab94-255">int</span></span></p></td>
<td><p><span data-ttu-id="4ab94-256">発信者が使用する音声ビデオ エッジ サービスのポート。</span><span class="sxs-lookup"><span data-stu-id="4ab94-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="4ab94-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4ab94-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="4ab94-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-259">呼び出し先が使用する音声ビデオ エッジ サービスの IPアドレス キー。</span><span class="sxs-lookup"><span data-stu-id="4ab94-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="4ab94-260">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ab94-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="4ab94-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="4ab94-262">int</span><span class="sxs-lookup"><span data-stu-id="4ab94-262">int</span></span></p></td>
<td><p><span data-ttu-id="4ab94-263">呼び出し先が使用する音声ビデオ エッジ サービスのポート。</span><span class="sxs-lookup"><span data-stu-id="4ab94-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="4ab94-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="4ab94-265">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4ab94-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-266">発信者のキャプチャ デバイス名。</span><span class="sxs-lookup"><span data-stu-id="4ab94-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="4ab94-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="4ab94-268">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4ab94-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-269">発信者のレンダー デバイス名。</span><span class="sxs-lookup"><span data-stu-id="4ab94-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="4ab94-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="4ab94-271">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4ab94-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-272">発信者のキャプチャ デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="4ab94-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="4ab94-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="4ab94-274">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4ab94-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-275">発信者のレンダー デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="4ab94-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-276">Calleecapのアーキテクチャ開発</span><span class="sxs-lookup"><span data-stu-id="4ab94-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="4ab94-277">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4ab94-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-278">呼び出し先のキャプチャ デバイス名。</span><span class="sxs-lookup"><span data-stu-id="4ab94-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-279">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="4ab94-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="4ab94-280">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4ab94-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-281">呼び出し先のレンダー デバイス名。</span><span class="sxs-lookup"><span data-stu-id="4ab94-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-282">Callecapん Devdriver</span><span class="sxs-lookup"><span data-stu-id="4ab94-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="4ab94-283">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4ab94-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-284">呼び出し先のキャプチャ デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="4ab94-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="4ab94-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="4ab94-286">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4ab94-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-287">呼び出し先のレンダー デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="4ab94-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="4ab94-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="4ab94-289">tinyint</span><span class="sxs-lookup"><span data-stu-id="4ab94-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4ab94-290">発信者のネットワーク接続の種類。0 は有線、1 はワイヤレスです。</span><span class="sxs-lookup"><span data-stu-id="4ab94-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="4ab94-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="4ab94-292">若干</span><span class="sxs-lookup"><span data-stu-id="4ab94-292">bit</span></span></p></td>
<td><p><span data-ttu-id="4ab94-p116">発信者が仮想プライベート ネットワークで接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="4ab94-p116">Indicates whether or not the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="4ab94-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="4ab94-296">10進数 (18)</span><span class="sxs-lookup"><span data-stu-id="4ab94-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-297">発信者のエンドポイントのネットワーク リンクの速度 (単位 bps)。</span><span class="sxs-lookup"><span data-stu-id="4ab94-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="4ab94-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="4ab94-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="4ab94-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4ab94-300">呼び出し先のネットワーク接続の種類。0 は有線、1 はワイヤレスです。</span><span class="sxs-lookup"><span data-stu-id="4ab94-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="4ab94-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="4ab94-302">若干</span><span class="sxs-lookup"><span data-stu-id="4ab94-302">bit</span></span></p></td>
<td><p><span data-ttu-id="4ab94-p117">呼び出し先が仮想プライベート ネットワークで接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。</span><span class="sxs-lookup"><span data-stu-id="4ab94-p117">Indicates whether or not the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="4ab94-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="4ab94-306">10進数 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="4ab94-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-307">呼び出し先のエンドポイントのネットワーク リンクの速度 (単位 bps)。</span><span class="sxs-lookup"><span data-stu-id="4ab94-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="4ab94-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="4ab94-309">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="4ab94-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-310">音声セッションの Narrowband Conversational MOS (音声ストリームに基づく)。</span><span class="sxs-lookup"><span data-stu-id="4ab94-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="4ab94-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="4ab94-312">int</span><span class="sxs-lookup"><span data-stu-id="4ab94-312">int</span></span></p></td>
<td><p><span data-ttu-id="4ab94-p118">さまざまなポリシー設定 (TURN、API、SDP、ポリシー サーバーなど) が構成された特定の送信側ストリームに適用される実際の帯域幅。この帯域幅を実効帯域幅と見なすことはできません。実効帯域幅は、帯域幅の評価に基づいて実際よりも低くなる可能性があります。これは基本的に、送信ストリームで利用できる最大帯域幅です (帯域幅の評価によって課せられる制限を除く)。</span><span class="sxs-lookup"><span data-stu-id="4ab94-p118">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="4ab94-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="4ab94-317">int</span><span class="sxs-lookup"><span data-stu-id="4ab94-317">int</span></span></p></td>
<td><p><span data-ttu-id="4ab94-318">リアルタイム制御プロトコル (RTCP) 統計情報に基づく平均ネットワーク ジッター。</span><span class="sxs-lookup"><span data-stu-id="4ab94-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="4ab94-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="4ab94-320">int</span><span class="sxs-lookup"><span data-stu-id="4ab94-320">int</span></span></p></td>
<td><p><span data-ttu-id="4ab94-321">通話時の最大ネットワーク ジッター。</span><span class="sxs-lookup"><span data-stu-id="4ab94-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-322">要し</span><span class="sxs-lookup"><span data-stu-id="4ab94-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="4ab94-323">int</span><span class="sxs-lookup"><span data-stu-id="4ab94-323">int</span></span></p></td>
<td><p><span data-ttu-id="4ab94-324">RTCP 統計情報に基づく往復時間。</span><span class="sxs-lookup"><span data-stu-id="4ab94-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="4ab94-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="4ab94-326">int</span><span class="sxs-lookup"><span data-stu-id="4ab94-326">int</span></span></p></td>
<td><p><span data-ttu-id="4ab94-327">音声ストリームの最大往復時間。</span><span class="sxs-lookup"><span data-stu-id="4ab94-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="4ab94-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="4ab94-329">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="4ab94-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-330">通話時の平均パケット損失率。</span><span class="sxs-lookup"><span data-stu-id="4ab94-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="4ab94-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="4ab94-332">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="4ab94-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-333">通話時に観測された最大パケット損失。</span><span class="sxs-lookup"><span data-stu-id="4ab94-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="4ab94-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="4ab94-335">int</span><span class="sxs-lookup"><span data-stu-id="4ab94-335">int</span></span></p></td>
<td><p><span data-ttu-id="4ab94-336">ビデオ ストリームのパケット数 (リアルタイム転送プロトコル、RTP)。</span><span class="sxs-lookup"><span data-stu-id="4ab94-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-337">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="4ab94-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="4ab94-338">int</span><span class="sxs-lookup"><span data-stu-id="4ab94-338">int</span></span></p></td>
<td><p><span data-ttu-id="4ab94-339">音声ストリームの帯域幅の推定。</span><span class="sxs-lookup"><span data-stu-id="4ab94-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="4ab94-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="4ab94-341">int</span><span class="sxs-lookup"><span data-stu-id="4ab94-341">int</span></span></p></td>
<td><p><span data-ttu-id="4ab94-342">通話に使用されるオーディオコーデック。 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 の PayloadDescription テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="4ab94-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-343">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="4ab94-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="4ab94-344">文字 (9)</span><span class="sxs-lookup"><span data-stu-id="4ab94-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-p119">幅×高さで示すビデオの解像度 (単位ピクセル)。文字列で報告されます。</span><span class="sxs-lookup"><span data-stu-id="4ab94-p119">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="4ab94-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="4ab94-348">int</span><span class="sxs-lookup"><span data-stu-id="4ab94-348">int</span></span></p></td>
<td><p><span data-ttu-id="4ab94-349">ビデオ ストリームの平均ビット レート。</span><span class="sxs-lookup"><span data-stu-id="4ab94-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="4ab94-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="4ab94-351">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="4ab94-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-352">ビデオの受信フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="4ab94-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="4ab94-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="4ab94-354">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="4ab94-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-355">ビデオの送信フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="4ab94-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="4ab94-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="4ab94-357">int</span><span class="sxs-lookup"><span data-stu-id="4ab94-357">int</span></span></p></td>
<td><p><span data-ttu-id="4ab94-358">ビデオ セッション時の最大ビデオ ビット レート。</span><span class="sxs-lookup"><span data-stu-id="4ab94-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-359">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="4ab94-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="4ab94-360">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="4ab94-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-361">失われたビデオ パケット数の割合。</span><span class="sxs-lookup"><span data-stu-id="4ab94-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="4ab94-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="4ab94-363">10進法 (9.4)</span><span class="sxs-lookup"><span data-stu-id="4ab94-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-364">失われた合計ビデオ フレーム数の割合。</span><span class="sxs-lookup"><span data-stu-id="4ab94-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="4ab94-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="4ab94-366">若干</span><span class="sxs-lookup"><span data-stu-id="4ab94-366">bit</span></span></p></td>
<td><p><span data-ttu-id="4ab94-367">不使用。</span><span class="sxs-lookup"><span data-stu-id="4ab94-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="4ab94-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="4ab94-369">int</span><span class="sxs-lookup"><span data-stu-id="4ab94-369">int</span></span></p></td>
<td><p><span data-ttu-id="4ab94-370">ビデオに割り当てられた帯域幅の平均。</span><span class="sxs-lookup"><span data-stu-id="4ab94-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ab94-371">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="4ab94-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="4ab94-372">10進法 (9.4)</span><span class="sxs-lookup"><span data-stu-id="4ab94-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="4ab94-373">失われた合計ビデオ フレーム数の割合。</span><span class="sxs-lookup"><span data-stu-id="4ab94-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ab94-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="4ab94-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="4ab94-375">若干</span><span class="sxs-lookup"><span data-stu-id="4ab94-375">bit</span></span></p></td>
<td><p><span data-ttu-id="4ab94-p120">P-Asserted Identity 情報のストリームの方向。1 は、ストリームの方向が発信者から呼び出し先へ向かうことを意味します。0 は、ストリームの方向が呼び出し先から発信者へ向かうことを意味します。</span><span class="sxs-lookup"><span data-stu-id="4ab94-p120">Stream direction for p-asserted identity information. 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

