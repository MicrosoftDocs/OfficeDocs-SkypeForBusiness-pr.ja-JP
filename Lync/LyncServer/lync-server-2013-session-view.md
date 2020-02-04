---
title: 'Lync Server 2013: セッションビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a153899fd484da861088a8e7672a69707e46a59
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="19333-102">Lync Server 2013 のセッションビュー</span><span class="sxs-lookup"><span data-stu-id="19333-102">Session view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19333-103">_**最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="19333-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="19333-104">セッションビューには、データベース内にレコードがあるセッションに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="19333-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="19333-105">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="19333-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="19333-106">列</span><span class="sxs-lookup"><span data-stu-id="19333-106">Column</span></span></th>
<th><span data-ttu-id="19333-107">データ型</span><span class="sxs-lookup"><span data-stu-id="19333-107">Data Type</span></span></th>
<th><span data-ttu-id="19333-108">詳細</span><span class="sxs-lookup"><span data-stu-id="19333-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19333-109">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="19333-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="19333-110">datetime</span><span class="sxs-lookup"><span data-stu-id="19333-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="19333-111">MediaLine テーブルから参照されます。</span><span class="sxs-lookup"><span data-stu-id="19333-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19333-112">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="19333-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="19333-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="19333-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="19333-114">会議の URI (会議の場合) または [この Id がピアツーピアセッションの場合] です。</span><span class="sxs-lookup"><span data-stu-id="19333-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19333-115">関連性</span><span class="sxs-lookup"><span data-stu-id="19333-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="19333-116">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="19333-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="19333-117">セッションの関連付け ID。</span><span class="sxs-lookup"><span data-stu-id="19333-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19333-118">このカテゴリ</span><span class="sxs-lookup"><span data-stu-id="19333-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="19333-119">bit</span><span class="sxs-lookup"><span data-stu-id="19333-119">bit</span></span></p></td>
<td><p><span data-ttu-id="19333-120">ダイアログカテゴリ0は Lync Server、仲介サーバーの区間、1は、PSTN ゲートウェイ区間への仲介サーバーです。</span><span class="sxs-lookup"><span data-stu-id="19333-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19333-121">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="19333-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="19333-122">bit</span><span class="sxs-lookup"><span data-stu-id="19333-122">bit</span></span></p></td>
<td><p><span data-ttu-id="19333-123">通話がバイパスされたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="19333-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19333-124">Mediabypasswarnings フラグ</span><span class="sxs-lookup"><span data-stu-id="19333-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="19333-125">int</span><span class="sxs-lookup"><span data-stu-id="19333-125">int</span></span></p></td>
<td><p><span data-ttu-id="19333-126">このフィールドは、バイパス Id が一致した場合でも、着信がバイパスされなかった理由を示します (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="19333-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="19333-127">Lync Server の場合は、1つの値のみが定義されます。</span><span class="sxs-lookup"><span data-stu-id="19333-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="19333-128">0x0001 –既定のネットワークアダプターの不明なバイパス ID</span><span class="sxs-lookup"><span data-stu-id="19333-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19333-129">StartTime</span><span class="sxs-lookup"><span data-stu-id="19333-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="19333-130">datetime</span><span class="sxs-lookup"><span data-stu-id="19333-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="19333-131">通話開始時刻。</span><span class="sxs-lookup"><span data-stu-id="19333-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19333-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="19333-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="19333-133">datetime</span><span class="sxs-lookup"><span data-stu-id="19333-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="19333-134">通話終了時刻。</span><span class="sxs-lookup"><span data-stu-id="19333-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19333-135">CallerPool</span><span class="sxs-lookup"><span data-stu-id="19333-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="19333-136">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="19333-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="19333-137">発信者番号プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="19333-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19333-138">CalleePool</span><span class="sxs-lookup"><span data-stu-id="19333-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="19333-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="19333-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="19333-140">呼び出し元プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="19333-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19333-141">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="19333-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="19333-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="19333-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="19333-143">呼び出し元の p がアサートされた id URI。</span><span class="sxs-lookup"><span data-stu-id="19333-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19333-144">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="19333-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="19333-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="19333-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="19333-146">呼び出し先の p-アサートされた id URI。</span><span class="sxs-lookup"><span data-stu-id="19333-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19333-147">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="19333-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="19333-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="19333-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="19333-149">発信者のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="19333-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19333-150">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="19333-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="19333-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="19333-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="19333-152">発信者のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="19333-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19333-153">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="19333-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="19333-154">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="19333-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="19333-155">呼び出し元のユーザーエージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="19333-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19333-156">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="19333-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="19333-157">smallint</span><span class="sxs-lookup"><span data-stu-id="19333-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="19333-158">呼び出し元のユーザーエージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="19333-158">Type of caller’s user agent.</span></span> <span data-ttu-id="19333-159">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19333-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19333-160">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="19333-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="19333-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="19333-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="19333-162">呼び出し元のユーザーエージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="19333-162">Category of caller’s user agent.</span></span> <span data-ttu-id="19333-163">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19333-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19333-164">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="19333-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="19333-165">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="19333-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="19333-166">呼び出し先のユーザーエージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="19333-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19333-167">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="19333-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="19333-168">smallint</span><span class="sxs-lookup"><span data-stu-id="19333-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="19333-169">呼び出し先のユーザーエージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="19333-169">Type of user agent for the callee.</span></span> <span data-ttu-id="19333-170">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19333-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19333-171">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="19333-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="19333-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="19333-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="19333-173">呼び出し先のユーザーエージェントカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="19333-173">User agent category for the callee.</span></span> <span data-ttu-id="19333-174">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19333-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19333-175">CallerURI</span><span class="sxs-lookup"><span data-stu-id="19333-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="19333-176">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="19333-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="19333-177">発信者の URI。</span><span class="sxs-lookup"><span data-stu-id="19333-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19333-178">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="19333-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="19333-179">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="19333-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="19333-180">呼び出し先の URI。</span><span class="sxs-lookup"><span data-stu-id="19333-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19333-181">通話</span><span class="sxs-lookup"><span data-stu-id="19333-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="19333-182">int</span><span class="sxs-lookup"><span data-stu-id="19333-182">int</span></span></p></td>
<td><p><span data-ttu-id="19333-183">通話の優先度。</span><span class="sxs-lookup"><span data-stu-id="19333-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

