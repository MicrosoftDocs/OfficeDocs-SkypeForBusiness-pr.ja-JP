---
title: 'Lync Server 2013: セッションビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a90d6a3f066caccb20b141daa485cabea29e2352
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="9fb07-102">Lync Server 2013 のセッションビュー</span><span class="sxs-lookup"><span data-stu-id="9fb07-102">Session view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9fb07-103">_**最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="9fb07-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="9fb07-104">セッションビューには、データベース内にレコードがあるセッションに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="9fb07-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="9fb07-105">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="9fb07-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9fb07-106">列</span><span class="sxs-lookup"><span data-stu-id="9fb07-106">Column</span></span></th>
<th><span data-ttu-id="9fb07-107">データ型</span><span class="sxs-lookup"><span data-stu-id="9fb07-107">Data Type</span></span></th>
<th><span data-ttu-id="9fb07-108">詳細</span><span class="sxs-lookup"><span data-stu-id="9fb07-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9fb07-109">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="9fb07-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="9fb07-110">datetime</span><span class="sxs-lookup"><span data-stu-id="9fb07-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="9fb07-111">MediaLine テーブルから参照されます。</span><span class="sxs-lookup"><span data-stu-id="9fb07-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb07-112">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="9fb07-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="9fb07-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9fb07-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9fb07-114">会議の URI (会議の場合) または [この Id がピアツーピアセッションの場合] です。</span><span class="sxs-lookup"><span data-stu-id="9fb07-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb07-115">関連性</span><span class="sxs-lookup"><span data-stu-id="9fb07-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="9fb07-116">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="9fb07-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="9fb07-117">セッションの関連付け ID。</span><span class="sxs-lookup"><span data-stu-id="9fb07-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb07-118">このカテゴリ</span><span class="sxs-lookup"><span data-stu-id="9fb07-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="9fb07-119">bit</span><span class="sxs-lookup"><span data-stu-id="9fb07-119">bit</span></span></p></td>
<td><p><span data-ttu-id="9fb07-120">ダイアログカテゴリ0は Lync Server、仲介サーバーの区間、1は、PSTN ゲートウェイ区間への仲介サーバーです。</span><span class="sxs-lookup"><span data-stu-id="9fb07-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb07-121">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="9fb07-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="9fb07-122">bit</span><span class="sxs-lookup"><span data-stu-id="9fb07-122">bit</span></span></p></td>
<td><p><span data-ttu-id="9fb07-123">通話がバイパスされたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="9fb07-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb07-124">Mediabypasswarnings フラグ</span><span class="sxs-lookup"><span data-stu-id="9fb07-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="9fb07-125">int</span><span class="sxs-lookup"><span data-stu-id="9fb07-125">int</span></span></p></td>
<td><p><span data-ttu-id="9fb07-126">このフィールドは、バイパス Id が一致した場合でも、着信がバイパスされなかった理由を示します (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="9fb07-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="9fb07-127">Lync Server の場合は、1つの値のみが定義されます。</span><span class="sxs-lookup"><span data-stu-id="9fb07-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="9fb07-128">0x0001 –既定のネットワークアダプターの不明なバイパス ID</span><span class="sxs-lookup"><span data-stu-id="9fb07-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb07-129">StartTime</span><span class="sxs-lookup"><span data-stu-id="9fb07-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="9fb07-130">datetime</span><span class="sxs-lookup"><span data-stu-id="9fb07-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="9fb07-131">通話開始時刻。</span><span class="sxs-lookup"><span data-stu-id="9fb07-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb07-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="9fb07-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="9fb07-133">datetime</span><span class="sxs-lookup"><span data-stu-id="9fb07-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="9fb07-134">通話終了時刻。</span><span class="sxs-lookup"><span data-stu-id="9fb07-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb07-135">CallerPool</span><span class="sxs-lookup"><span data-stu-id="9fb07-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="9fb07-136">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9fb07-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9fb07-137">発信者番号プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="9fb07-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb07-138">CalleePool</span><span class="sxs-lookup"><span data-stu-id="9fb07-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="9fb07-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9fb07-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9fb07-140">呼び出し元プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="9fb07-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb07-141">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="9fb07-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="9fb07-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9fb07-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9fb07-143">呼び出し元の p がアサートされた id URI。</span><span class="sxs-lookup"><span data-stu-id="9fb07-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb07-144">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="9fb07-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="9fb07-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9fb07-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9fb07-146">呼び出し先の p-アサートされた id URI。</span><span class="sxs-lookup"><span data-stu-id="9fb07-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb07-147">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="9fb07-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="9fb07-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9fb07-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9fb07-149">発信者のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="9fb07-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb07-150">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="9fb07-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="9fb07-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9fb07-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9fb07-152">発信者のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="9fb07-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb07-153">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="9fb07-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="9fb07-154">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9fb07-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9fb07-155">呼び出し元のユーザーエージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="9fb07-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb07-156">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="9fb07-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="9fb07-157">smallint</span><span class="sxs-lookup"><span data-stu-id="9fb07-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="9fb07-158">呼び出し元のユーザーエージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="9fb07-158">Type of caller’s user agent.</span></span> <span data-ttu-id="9fb07-159">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fb07-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb07-160">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="9fb07-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="9fb07-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="9fb07-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="9fb07-162">呼び出し元のユーザーエージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="9fb07-162">Category of caller’s user agent.</span></span> <span data-ttu-id="9fb07-163">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fb07-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb07-164">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="9fb07-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="9fb07-165">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9fb07-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9fb07-166">呼び出し先のユーザーエージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="9fb07-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb07-167">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="9fb07-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="9fb07-168">smallint</span><span class="sxs-lookup"><span data-stu-id="9fb07-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="9fb07-169">呼び出し先のユーザーエージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="9fb07-169">Type of user agent for the callee.</span></span> <span data-ttu-id="9fb07-170">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fb07-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb07-171">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="9fb07-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="9fb07-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="9fb07-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="9fb07-173">呼び出し先のユーザーエージェントカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="9fb07-173">User agent category for the callee.</span></span> <span data-ttu-id="9fb07-174">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fb07-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb07-175">CallerURI</span><span class="sxs-lookup"><span data-stu-id="9fb07-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="9fb07-176">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9fb07-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9fb07-177">発信者の URI。</span><span class="sxs-lookup"><span data-stu-id="9fb07-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb07-178">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="9fb07-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="9fb07-179">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9fb07-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9fb07-180">呼び出し先の URI。</span><span class="sxs-lookup"><span data-stu-id="9fb07-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb07-181">通話</span><span class="sxs-lookup"><span data-stu-id="9fb07-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="9fb07-182">int</span><span class="sxs-lookup"><span data-stu-id="9fb07-182">int</span></span></p></td>
<td><p><span data-ttu-id="9fb07-183">通話の優先度。</span><span class="sxs-lookup"><span data-stu-id="9fb07-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

