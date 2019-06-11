---
title: 'Lync Server 2013: AudioStreamDetail ビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioStreamDetail view
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49733792
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10992007c76321f8ed3b436b9786cbef840173ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840901"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="6c9d2-102">Lync Server 2013 の AudioStreamDetail ビュー</span><span class="sxs-lookup"><span data-stu-id="6c9d2-102">AudioStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c9d2-103">_**最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="6c9d2-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="6c9d2-104">AudioStreamDetail ビューには、データベース内の各オーディオストリームに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="6c9d2-105">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6c9d2-106">列</span><span class="sxs-lookup"><span data-stu-id="6c9d2-106">Column</span></span></th>
<th><span data-ttu-id="6c9d2-107">データ型</span><span class="sxs-lookup"><span data-stu-id="6c9d2-107">Data Type</span></span></th>
<th><span data-ttu-id="6c9d2-108">詳細</span><span class="sxs-lookup"><span data-stu-id="6c9d2-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-109">セッション時間</span><span class="sxs-lookup"><span data-stu-id="6c9d2-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-110">datetime</span><span class="sxs-lookup"><span data-stu-id="6c9d2-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-111"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="6c9d2-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-113">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-113">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-114"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-115">StreamId</span><span class="sxs-lookup"><span data-stu-id="6c9d2-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-116">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-116">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-117">メディアライン内の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-118">StartTime</span><span class="sxs-lookup"><span data-stu-id="6c9d2-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-119">datetime</span><span class="sxs-lookup"><span data-stu-id="6c9d2-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-120">セッションの開始時刻。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="6c9d2-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-122">datetime</span><span class="sxs-lookup"><span data-stu-id="6c9d2-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-123">セッションの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-124">このカテゴリ</span><span class="sxs-lookup"><span data-stu-id="6c9d2-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-125">bit</span><span class="sxs-lookup"><span data-stu-id="6c9d2-125">bit</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-126">ダイアログカテゴリ: 0 は、仲介サーバー間の Lync サーバーです。1は PSTN ゲートウェイ区間の仲介サーバーです。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-127">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="6c9d2-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-128">bit</span><span class="sxs-lookup"><span data-stu-id="6c9d2-128">bit</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-129">通話がバイパスされたかどうかを示すフラグ。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-130">Mediabypasswarnings フラグ</span><span class="sxs-lookup"><span data-stu-id="6c9d2-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-131">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-131">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-132">存在する場合は、バイパス Id が一致した場合でも、通話がバイパスされなかった理由を示します。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-132">If present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="6c9d2-133">1つの値のみが定義されます。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-133">Only one value is defined:</span></span></p>
<p><span data-ttu-id="6c9d2-134">0x0001 –既定のネットワークアダプターの不明なバイパス ID。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-135">CallPriority</span><span class="sxs-lookup"><span data-stu-id="6c9d2-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-136">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-136">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-137">通話の優先度。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-138">CallerPool</span><span class="sxs-lookup"><span data-stu-id="6c9d2-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-140">発信者番号プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-141">CalleePool</span><span class="sxs-lookup"><span data-stu-id="6c9d2-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-142">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-143">呼び出し元プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-144">[発信者]</span><span class="sxs-lookup"><span data-stu-id="6c9d2-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-146">発信者の URI。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-147">[呼び出し先]</span><span class="sxs-lookup"><span data-stu-id="6c9d2-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-148">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-149">呼び出し先の URI。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-150">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="6c9d2-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-152">呼び出し元のユーザーエージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-153">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="6c9d2-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-154">smallint</span><span class="sxs-lookup"><span data-stu-id="6c9d2-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-155">呼び出し元のユーザーエージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="6c9d2-156">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-157">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="6c9d2-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-158">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-159">発信者のユーザーエージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="6c9d2-160">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-161">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="6c9d2-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-162">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-163">呼び出し先のユーザーエージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-164">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="6c9d2-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-165">smallint</span><span class="sxs-lookup"><span data-stu-id="6c9d2-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-166">呼び出し先のユーザーエージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-166">Type of callee’s user agent.</span></span> <span data-ttu-id="6c9d2-167">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-168">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="6c9d2-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-170">呼び出し先のユーザーエージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-170">Category of callee’s user agent.</span></span> <span data-ttu-id="6c9d2-171">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-172">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="6c9d2-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-173">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-174">発信者のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-175">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="6c9d2-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-176">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-177">呼び出し先のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-178">CallerOS</span><span class="sxs-lookup"><span data-stu-id="6c9d2-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-179">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="6c9d2-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-180">発信者のエンドポイントのオペレーティングシステム (OS)。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-181">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="6c9d2-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-182">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="6c9d2-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-183">呼び出し先のエンドポイントのオペレーティングシステム (OS)。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-184">Caller</span><span class="sxs-lookup"><span data-stu-id="6c9d2-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-185">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="6c9d2-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-186">呼び出し元のエンドポイントの CPU 名。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-187">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="6c9d2-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-188">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="6c9d2-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-189">呼び出し先のエンドポイントの CPU 名。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-190">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="6c9d2-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-191">smallint</span><span class="sxs-lookup"><span data-stu-id="6c9d2-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-192">呼び出し元のエンドポイントの CPU コアの数。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-193">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="6c9d2-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-194">smallint</span><span class="sxs-lookup"><span data-stu-id="6c9d2-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-195">呼び出し先のエンドポイントの CPU コアの数です。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-196">Callerプロセッサーの速度</span><span class="sxs-lookup"><span data-stu-id="6c9d2-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-197">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-197">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-198">発信者のエンドポイントの CPU プロセッサ速度。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-199">Calleecpuプロセッサー速度</span><span class="sxs-lookup"><span data-stu-id="6c9d2-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-200">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-200">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-201">呼び出し先のエンドポイントの CPU プロセッサ速度。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-202">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="6c9d2-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="6c9d2-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-204">呼び出し元のシステムが仮想環境で実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="6c9d2-205">詳細については、「 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-206">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="6c9d2-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-207">tinyint</span><span class="sxs-lookup"><span data-stu-id="6c9d2-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-208">呼び出し先のシステムが仮想環境で実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="6c9d2-209">詳細については、「 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-210">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="6c9d2-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6c9d2-211">相関関係キー。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-211">Correlation key.</span></span> <span data-ttu-id="6c9d2-212"><a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 の Sessioncorrelation テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-213">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="6c9d2-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-214">tinyint</span><span class="sxs-lookup"><span data-stu-id="6c9d2-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-215">メディアパスについての情報 (ダイレクトまたは中継など)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="6c9d2-216">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-217">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="6c9d2-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-218">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-218">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-219">発信者の bits フラグで説明されている対話型接続確立 (ICE) プロセスに関する情報。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-219">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="6c9d2-220">詳細については、「エクスペリエンスの品質監視サーバープロトコルの仕様」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-220">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-221">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="6c9d2-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-222">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-222">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-223">対話式接続確立 (ICE) プロセスについて詳しくは、「呼び出し先のビットフラグ」で説明します。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-223">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="6c9d2-224">詳細については、「エクスペリエンスの品質監視サーバープロトコルの仕様」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-224">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-225">Transport</span><span class="sxs-lookup"><span data-stu-id="6c9d2-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-226">tinyint</span><span class="sxs-lookup"><span data-stu-id="6c9d2-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-227">トランスポートの種類: 0 は UDP、1は TCP です。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-228">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="6c9d2-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-230">発信者の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-230">IP address of the caller.</span></span> <span data-ttu-id="6c9d2-231">これは IPv4 または IPv6 アドレスのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-232">CallerPort</span><span class="sxs-lookup"><span data-stu-id="6c9d2-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-233">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-233">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-234">発信者によって使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-235">CallerInside</span><span class="sxs-lookup"><span data-stu-id="6c9d2-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-236">bit</span><span class="sxs-lookup"><span data-stu-id="6c9d2-236">bit</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-237">発信者が間隔ネットワーク内にあるかどうかを示します。1は、発信者がエンタープライズネットワーク内にあることを意味します。0は、発信者がネットワークの外部にあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-238">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="6c9d2-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-239">var (50)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-240">呼び出し先の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-240">IP address of the callee.</span></span> <span data-ttu-id="6c9d2-241">これは IPv4 または IPv6 アドレスのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-242">CalleePort</span><span class="sxs-lookup"><span data-stu-id="6c9d2-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-243">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-243">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-244">呼び出し先によって使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-245">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="6c9d2-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-246">bit</span><span class="sxs-lookup"><span data-stu-id="6c9d2-246">bit</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-247">呼び出し先が間隔ネットワーク内にあるかどうかを示します。1は、呼び出し先がエンタープライズネットワーク内にあることを意味します。0は、呼び出し先がネットワークの外部にあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-248">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="6c9d2-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-249">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="6c9d2-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-250">発信者のサイトの名前。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-251">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="6c9d2-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-252">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="6c9d2-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-253">発信者のサイトの国/地域の名前です。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-254">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="6c9d2-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-255">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="6c9d2-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-256">呼び出し先のサイトの名前。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-257">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="6c9d2-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-258">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="6c9d2-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-259">呼び出し先のサイトの国/地域の名前です。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-260">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="6c9d2-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-261">var (50)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-262">発信者によって使用される A/V Edge サービスの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="6c9d2-263">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-264">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="6c9d2-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-265">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-265">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-266">発信者が使用する A/V Edge サービスで使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-267">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="6c9d2-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-268">var (50)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-269">呼び出し先によって使用される A/V エッジサービスの IP アドレスキー。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="6c9d2-270">詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-271">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="6c9d2-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-272">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-272">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-273">呼び出し先によって使用される A/V Edge サービスで使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-274">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="6c9d2-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-276">発信者のキャプチャデバイス名。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-277">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="6c9d2-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-279">発信者のレンダーデバイス名。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-280">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="6c9d2-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-282">発信者のキャプチャデバイスドライバー名。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-283">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="6c9d2-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-285">発信者のレンダーデバイスドライバー名。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-286">Calleecapdev</span><span class="sxs-lookup"><span data-stu-id="6c9d2-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-288">呼び出し先のキャプチャデバイス名。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-289">Calle・ Enderdev</span><span class="sxs-lookup"><span data-stu-id="6c9d2-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-290">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-291">呼び出し先のレンダリングデバイス名。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-292">Calleecapdevdriver</span><span class="sxs-lookup"><span data-stu-id="6c9d2-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-293">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-294">呼び出し先のキャプチャデバイスドライバー名。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-295">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="6c9d2-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-296">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-297">呼び出し先のレンダリングデバイスドライバー名。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-298">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="6c9d2-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="6c9d2-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-300">発信者のネットワーク接続の種類: 0 は有線、1はワイヤレス。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-301">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="6c9d2-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-302">bit</span><span class="sxs-lookup"><span data-stu-id="6c9d2-302">bit</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-303">発信者が仮想プライベートネットワーク経由で接続しているかどうかを示します。1は仮想プライベートネットワーク (VPN)、0は VPN 以外。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-304">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="6c9d2-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-305">10進数 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-306">発信者のエンドポイントのネットワークリンク速度 (bps)。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-307">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="6c9d2-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-308">tinyint</span><span class="sxs-lookup"><span data-stu-id="6c9d2-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-309">呼び出し先のネットワーク接続の種類: 0 は有線、1はワイヤレス。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-310">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="6c9d2-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-311">bit</span><span class="sxs-lookup"><span data-stu-id="6c9d2-311">bit</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-312">発信者が仮想プライベートネットワーク経由で接続しているかどうかを示します。1は仮想プライベートネットワーク (VPN)、0は VPN 以外。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-313">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="6c9d2-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-314">10進数 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-315">転送先のエンドポイントのネットワークリンク速度 (bps)。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-316">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="6c9d2-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-317">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-318">オーディオセッションの会話 MOS を Narrowband します (両方のオーディオストリームに基づく)。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-319">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="6c9d2-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-320">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-320">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-321">さまざまなポリシー設定 (TURN、API、SDP、ポリシーサーバーなど) が指定された send side ストリームに適用される実際の帯域幅。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-321">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="6c9d2-322">これは、帯域幅の推定値に基づいて低帯域幅を使用できるため、有効帯域幅と混同しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-322">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="6c9d2-323">これは基本的に最大帯域幅であり、送信ストリームは、帯域幅の推定によって課された制限を受けることができません。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-323">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="6c9d2-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-325">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-325">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-326">リアルタイム制御プロトコル (RTCP) の統計情報からの平均ネットワークジッター。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-327">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="6c9d2-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-328">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-328">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-329">通話中の最大ネットワークジッター。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="6c9d2-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-331">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-332">通話中の平均パケット損失率。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-333">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="6c9d2-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-334">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-335">通話中に発生したパケット損失の上限。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-336">BurstDensity</span><span class="sxs-lookup"><span data-stu-id="6c9d2-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-337">10進数 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-338">通話中に損失が発生した場合のパケット損失の平均密度。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-339">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="6c9d2-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-340">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-340">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-341">通話中に損失が発生したときのパケット損失の平均時間。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-342">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="6c9d2-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-343">10進数 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-344">パケット損失のバースト間のパケット損失の平均密度。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-345">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="6c9d2-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-346">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-346">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-347">パケット損失のバーストの間の平均時間差。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-348">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="6c9d2-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-349">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-349">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-350">オーディオストリームのパケット数。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-351">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="6c9d2-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-352">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-352">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-353">オーディオストリームの帯域幅の推定。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-354">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="6c9d2-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-355">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-356">電話全体のネットワーク MOS が低下します。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-356">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="6c9d2-357">範囲は 0.0 ~ 5.0 です。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-357">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="6c9d2-358">このメトリックは、ジッタとパケット損失によってネットワーク MOS が削減された量を示します。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-358">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="6c9d2-359">許容可能な品質には、0.5 未満の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-359">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-360">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="6c9d2-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-361">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-362">通話中の最大ネットワーク MOS の品質低下。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-363">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="6c9d2-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-364">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-365">ジッターによるネットワーク MOS の低下。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-366">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="6c9d2-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-367">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-368">パケット損失によるネットワーク MOS の低下。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="6c9d2-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-370">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-370">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-371">通話に使用するオーディオコーデック。 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 の PayloadDescription テーブル</a>から参照されています。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-372">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="6c9d2-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-373">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-373">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-374">オーディオストリームのサンプリングレート。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-375">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="6c9d2-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-376">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-376">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-377">発信者が送信したオーディオのアナログゲインの制御オーディオ信号レベル。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-377">Post-Analog Gain Control audio signal level for the audio the caller sent.</span></span> <span data-ttu-id="6c9d2-378">このメトリックの単位は dBmo です。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-378">The unit for this metric is dBmo.</span></span> <span data-ttu-id="6c9d2-379">許容可能な品質を求めるには、少なくとも30個の dBmo を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-379">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="6c9d2-380">このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-380">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-381">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="6c9d2-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-382">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-382">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-383">発信者が受信した音声の音声信号レベル。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-383">Audio signal level for the audio the caller received.</span></span> <span data-ttu-id="6c9d2-384">このメトリックの単位は dBmo です。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-384">The unit for this metric is dBmo.</span></span> <span data-ttu-id="6c9d2-385">許容可能な品質を求めるには、少なくとも30個の dBmo を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-385">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="6c9d2-386">このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-386">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-387">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="6c9d2-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-388">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-388">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-389">発信者が送信したオーディオのアナログゲインのオーディオノイズレベルを制御します。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-389">Post-Analog Gain Control audio noise level for the audio the caller sent.</span></span> <span data-ttu-id="6c9d2-390">このメトリックの単位は dBmo です。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-390">The unit for this metric is dBmo.</span></span> <span data-ttu-id="6c9d2-391">許容される品質には、35 dBmo よりも小さい値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-391">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="6c9d2-392">このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-392">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-393">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="6c9d2-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-394">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-394">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-395">送信者が受信したオーディオのアナログゲインのオーディオノイズレベルを制御します。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-395">Post-Analog Gain Control audio noise level for the audio the caller received.</span></span> <span data-ttu-id="6c9d2-396">このメトリックの単位は dBmo です。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-396">The unit for this metric is dBmo.</span></span> <span data-ttu-id="6c9d2-397">許容される品質には、35 dBmo よりも小さい値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-397">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="6c9d2-398">このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-398">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-399">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="6c9d2-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-400">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-400">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-401">発信者に対する戻り値の損失の強調機能。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-401">Echo Return Loss Enhancement for the caller.</span></span> <span data-ttu-id="6c9d2-402">このメトリックの単位は dB です。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-402">The unit for this metric is dB.</span></span> <span data-ttu-id="6c9d2-403">小さい値は、エコーが少なくなります。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-403">Lower values represent less echo.</span></span> <span data-ttu-id="6c9d2-404">このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-404">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-405">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="6c9d2-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-406">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-406">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-407">発信者のスピーカーレンダリングに対する5分あたりの平均エラー。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-407">Average glitches per five minutes for the caller’s loudspeaker rendering.</span></span> <span data-ttu-id="6c9d2-408">品質を向上させるには、5分未満でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-408">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="6c9d2-409">A/V 会議サーバー、仲介サーバー、または IP 電話によって報告されていません。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-409">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-410">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="6c9d2-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-411">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-411">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-412">発信者のマイクのキャプチャに対する5分あたりの平均エラー。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-412">Average glitches per five minutes for the caller’s microphone capture.</span></span> <span data-ttu-id="6c9d2-413">品質を向上させるには、5分未満の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-413">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="6c9d2-414">A/V 会議サーバー、仲介サーバー、または IP 電話によって報告されていません。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-414">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-415">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="6c9d2-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-416">10進数 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-417">発信者のマイクデバイスクロックドリフトレート。 CPU クロックを基準としています。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-418">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="6c9d2-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-419">10進数 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-420">発信者のスピーカーデバイスクロックドリフトレート。 CPU クロックを基準としています。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-421">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="6c9d2-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-422">10進数 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-423">平均マイクキャプチャストリームタイムスタンプエラー (ミリ秒単位)、通話の最後の20秒。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-424">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="6c9d2-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-425">10進数 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-426">発信者のスピーカーレンダーストリームのタイムスタンプエラーの平均値 (ミリ秒) です。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-427">CallerVsEntryCauses 原因</span><span class="sxs-lookup"><span data-stu-id="6c9d2-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-428">smallint</span><span class="sxs-lookup"><span data-stu-id="6c9d2-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-429">音声スイッチは半二重モードで、中断機能が低減されます。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="6c9d2-430">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-431">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="6c9d2-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-432">tinyint</span><span class="sxs-lookup"><span data-stu-id="6c9d2-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-433">呼び出し元のエコーイベントの原因。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="6c9d2-434">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-435">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="6c9d2-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-436">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-437">呼び出し元のマイクキャプチャストリームでエコーが検出された時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-437">Percentage of time when echo is detected in the caller’s microphone capture stream.</span></span> <span data-ttu-id="6c9d2-438">ヘッドセットを使用する場合は、値を低くする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-438">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-439">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="6c9d2-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-440">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-441">呼び出し元の送信ストリームでエコーが検出された時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-441">Percentage of time when echo is detected in the caller’s sent stream.</span></span> <span data-ttu-id="6c9d2-442">送信ストリームでのエコー率が高いと、エコーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-442">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-443">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="6c9d2-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-444">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-444">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-445">発信者のオーディオのためのゲートウェイからの仲介サーバー上のシグナルレベルを受信しました。これは、仲介サーバーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-445">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="6c9d2-446">このメトリックの単位は dBoV です。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-446">The unit of this metric is dBoV.</span></span> <span data-ttu-id="6c9d2-447">品質を向上させるには、許容範囲は-30 ~-18 dBoV にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-447">For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-448">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="6c9d2-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-449">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-449">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-450">発信者のオーディオのためのゲートウェイからの仲介サーバー上のシグナルレベルを受信しました。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-450">Received signal level on the Mediation Server from the Gateway for the caller’s audio.</span></span> <span data-ttu-id="6c9d2-451">これは、仲介サーバーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-451">This applies only to the Mediation Server.</span></span> <span data-ttu-id="6c9d2-452">このメトリックの単位は dBoV です。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-452">The unit of this metric is dBoV.</span></span> <span data-ttu-id="6c9d2-453">品質を向上させるには、許容範囲として 50 dBoV 未満の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-453">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-454">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="6c9d2-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-455">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-455">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-456">発信者の音声に適用された仲介サーバー側の自動ゲイン制御 (AGC)。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-457">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="6c9d2-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-458">float</span><span class="sxs-lookup"><span data-stu-id="6c9d2-458">float</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-459">通話の最初の30秒間の着信シグナルの発信者への着信シグナルの平方根 (RMS)。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-460">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="6c9d2-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-461">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-461">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-462">呼び出し元が送信したオーディオのアナログゲインコントロールオーディオ信号レベルを表します。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-462">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent.</span></span> <span data-ttu-id="6c9d2-463">このメトリックの単位は dBmo です。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-463">The unit for this metric is dBmo.</span></span> <span data-ttu-id="6c9d2-464">許容可能な品質を求めるには、少なくとも30個の dBmo を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-464">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="6c9d2-465">このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-465">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-466">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="6c9d2-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-467">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-467">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-468">呼び出し側が受信したオーディオの音声信号レベル。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-468">Audio signal level for the audio the callee received.</span></span> <span data-ttu-id="6c9d2-469">このメトリックの単位は dBmo です。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-469">The unit for this metric is dBmo.</span></span> <span data-ttu-id="6c9d2-470">許容可能な品質を求めるには、少なくとも30個の dBmo を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-470">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="6c9d2-471">このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-471">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-472">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="6c9d2-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-473">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-473">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-474">以降のアナログゲインは、呼び出し元が送信したオーディオに対してオーディオノイズレベルを制御します。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-474">Post-Analog Gain Control audio noise level for the audio the callee sent.</span></span> <span data-ttu-id="6c9d2-475">このメトリックの単位は dBmo です。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-475">The unit for this metric is dBmo.</span></span> <span data-ttu-id="6c9d2-476">許容される品質には、35 dBmo よりも小さい値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-476">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="6c9d2-477">このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-477">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-478">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="6c9d2-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-479">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-479">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-480">後からのアナログゲインコントロール呼び出し側が受信したオーディオのオーディオノイズレベルを制御します。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-480">Post-Analog Gain Control audio noise level for the audio the callee received.</span></span> <span data-ttu-id="6c9d2-481">このメトリックの単位は dBmo です。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-481">The unit for this metric is dBmo.</span></span> <span data-ttu-id="6c9d2-482">許容される品質には、35 dBmo よりも小さい値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-482">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="6c9d2-483">このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-483">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-484">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="6c9d2-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-485">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-485">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-486">呼び出し先のエコーリターンロスの強化。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-486">Echo Return Loss Enhancement for the callee.</span></span> <span data-ttu-id="6c9d2-487">このメトリックの単位は dB です。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-487">The unit for this metric is dB.</span></span> <span data-ttu-id="6c9d2-488">小さい値は、エコーが少なくなります。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-488">Lower values represent less echo.</span></span> <span data-ttu-id="6c9d2-489">このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-489">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-490">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="6c9d2-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-491">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-491">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-492">呼び出し先のスピーカーレンダリングに対する5分あたりの平均エラー。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-492">Average glitches per five minutes for the callee’s loudspeaker rendering.</span></span> <span data-ttu-id="6c9d2-493">品質を向上させるには、5分未満でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-493">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="6c9d2-494">A/V 会議サーバー、仲介サーバー、または IP 電話によって報告されていません。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-494">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-495">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="6c9d2-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-496">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-496">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-497">呼び出し先のマイクのキャプチャに対する5分あたりの平均エラー。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-497">Average glitches per five minutes for the callee’s microphone capture.</span></span> <span data-ttu-id="6c9d2-498">品質を向上させるには、5分未満の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-498">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="6c9d2-499">A/V 会議サーバー、仲介サーバー、または IP 電話によって報告されていません。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-499">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-500">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="6c9d2-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-501">10進数 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-502">呼び出し先のマイクデバイスクロックドリフトレート。 CPU クロックを基準としています。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-503">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="6c9d2-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-504">10進数 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-505">呼び出し先のスピーカーデバイスクロックドリフト率。 CPU クロックを基準としています。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-506">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="6c9d2-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-507">10進数 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-508">平均マイクキャプチャストリームタイムスタンプエラー (ミリ秒単位)、通話の最後の20秒。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-509">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="6c9d2-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-510">10進数 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-511">呼び出し側のスピーカーレンダーストリームのタイムスタンプエラーの平均 (ミリ秒) です。これは、通話の最後の20秒を示しています。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-512">Calleevsenの原因</span><span class="sxs-lookup"><span data-stu-id="6c9d2-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-513">smallint</span><span class="sxs-lookup"><span data-stu-id="6c9d2-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-514">音声スイッチは半二重モードで、中断機能が低減されます。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="6c9d2-515">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-516">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="6c9d2-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-517">tinyint</span><span class="sxs-lookup"><span data-stu-id="6c9d2-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-518">呼び出し先のエコーイベントの原因。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="6c9d2-519">詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-520">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="6c9d2-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-521">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-522">呼び出し先のマイクキャプチャストリームでエコーが検出された時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-522">Percentage of time when echo is detected in the callee’s microphone capture stream.</span></span> <span data-ttu-id="6c9d2-523">ヘッドセットを使用する場合は、値を低くする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-523">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-524">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="6c9d2-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-525">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-526">呼び出し元の送信ストリームでエコーが検出された時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-526">Percentage of time when echo is detected in the callee’s sent stream.</span></span> <span data-ttu-id="6c9d2-527">送信ストリームでのエコー率が高いと、エコーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-527">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-528">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="6c9d2-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-529">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-529">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-530">呼び出し元のオーディオのゲートウェイからの、仲介サーバー上の受信したシグナルレベル。これは、仲介サーバーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-530">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="6c9d2-531">このメトリックの単位は dBoV です。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-531">The unit of this metric is dBoV.</span></span> <span data-ttu-id="6c9d2-532">品質を向上させるには、許容範囲は [-30 ~-18] の dBoV にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-532">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-533">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="6c9d2-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-534">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-534">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-535">呼び出し元のオーディオのゲートウェイからの、仲介サーバー上の受信したシグナルレベル。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-535">Received signal level on the Mediation Server from the Gateway for the callee’s audio.</span></span> <span data-ttu-id="6c9d2-536">これは、仲介サーバーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-536">This applies only to the Mediation Server.</span></span> <span data-ttu-id="6c9d2-537">このメトリックの単位は dBoV です。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-537">The unit of this metric is dBoV.</span></span> <span data-ttu-id="6c9d2-538">品質を向上させるには、許容範囲として 50 dBoV 未満の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-538">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-539">お金の獲得</span><span class="sxs-lookup"><span data-stu-id="6c9d2-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-540">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-540">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-541">呼び出し先のオーディオに適用された仲介サーバー側の自動ゲイン制御 (AGC)。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-542">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="6c9d2-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-543">float</span><span class="sxs-lookup"><span data-stu-id="6c9d2-543">float</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-544">呼び出しの最初の30秒間の呼び出し先への着信シグナルのルート平均平方根 (RMS)。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="6c9d2-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-546">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-547">オーディオの修復によって発生した、一般的なサンプルの平均比率。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-548">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="6c9d2-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-549">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-550">オーディオ修復によって生成された、一般的なサンプルの平均比率。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-551">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="6c9d2-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-552">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-553">オーディオの修復によって生成された、一般的なサンプルの圧縮サンプルの平均比率。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-554">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="6c9d2-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-555">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-555">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-556">RTCP の統計情報からのラウンドトリップ時間。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-557">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="6c9d2-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-558">int</span><span class="sxs-lookup"><span data-stu-id="6c9d2-558">int</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-559">オーディオストリームの最大ラウンドトリップ時間。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-560">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="6c9d2-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-561">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-562">通話の平均広帯域ネットワーク MOS。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-562">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="6c9d2-563">このメトリックは、使用されているパケット損失、ジッタ、およびコーデックによって異なります。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-563">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="6c9d2-564">範囲は 1.0 ~ 5.0 です。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-564">Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-565">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="6c9d2-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-566">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-567">通話の最小広帯域ネットワーク MOS。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-568">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="6c9d2-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-569">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-570">平均予測広帯域は、音声のレベル、ノイズレベル、キャプチャデバイスの特性など、送信された音声の MOS スコアを聞き取ります。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-571">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="6c9d2-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-572">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-573">通話の最小 SendListenMOS。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-574">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="6c9d2-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-575">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-576">予測される平均広帯域は、ネットワークから受信した音声 (音声のレベル、ノイズレベル、コーデック、ネットワーク条件、キャプチャデバイスの特性など) を対象としています。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-577">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="6c9d2-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-578">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="6c9d2-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-579">通話の最小 RecvListenMOS。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c9d2-580">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="6c9d2-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-581">bit</span><span class="sxs-lookup"><span data-stu-id="6c9d2-581">bit</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-582">通話にオーディオ FEC が使用されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c9d2-583">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="6c9d2-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-584">bit</span><span class="sxs-lookup"><span data-stu-id="6c9d2-584">bit</span></span></p></td>
<td><p><span data-ttu-id="6c9d2-585">P がアサートされた情報の方向を示します。1は、ストリームの方向を呼び出し元から呼び出し先に転送することを意味します。0は、ストリームの方向を呼び出し元から呼び出し元に転送します。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

