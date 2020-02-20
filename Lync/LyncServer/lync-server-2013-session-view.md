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
ms.openlocfilehash: 80b9c7c9b54deb28b70c8ee2386359bec37d5a69
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="8a41a-102">Lync Server 2013 のセッションビュー</span><span class="sxs-lookup"><span data-stu-id="8a41a-102">Session view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a41a-103">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="8a41a-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="8a41a-104">セッション ビューには、データベースにレコードがあるセッションに関する情報が保存されます。</span><span class="sxs-lookup"><span data-stu-id="8a41a-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="8a41a-105">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="8a41a-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8a41a-106">列</span><span class="sxs-lookup"><span data-stu-id="8a41a-106">Column</span></span></th>
<th><span data-ttu-id="8a41a-107">データ型</span><span class="sxs-lookup"><span data-stu-id="8a41a-107">Data Type</span></span></th>
<th><span data-ttu-id="8a41a-108">詳細</span><span class="sxs-lookup"><span data-stu-id="8a41a-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a41a-109">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="8a41a-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="8a41a-110">日付型</span><span class="sxs-lookup"><span data-stu-id="8a41a-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="8a41a-111">MediaLine テーブルから参照されます。</span><span class="sxs-lookup"><span data-stu-id="8a41a-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a41a-112">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="8a41a-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="8a41a-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8a41a-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8a41a-114">これが会議の場合は会議 URI、ピアツーピア セッションの場合は DialogID です。</span><span class="sxs-lookup"><span data-stu-id="8a41a-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a41a-115">関連付け</span><span class="sxs-lookup"><span data-stu-id="8a41a-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="8a41a-116">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="8a41a-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="8a41a-117">セッションの関連付け ID。</span><span class="sxs-lookup"><span data-stu-id="8a41a-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a41a-118">' このカテゴリ</span><span class="sxs-lookup"><span data-stu-id="8a41a-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="8a41a-119">若干</span><span class="sxs-lookup"><span data-stu-id="8a41a-119">bit</span></span></p></td>
<td><p><span data-ttu-id="8a41a-120">ダイアログのカテゴリ。0は Lync Server から仲介サーバーまでです。1は仲介サーバーから PSTN ゲートウェイレグになります。</span><span class="sxs-lookup"><span data-stu-id="8a41a-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a41a-121">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="8a41a-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="8a41a-122">若干</span><span class="sxs-lookup"><span data-stu-id="8a41a-122">bit</span></span></p></td>
<td><p><span data-ttu-id="8a41a-123">通話がバイパスされたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="8a41a-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a41a-124">Mediabypasswarnings フラグ</span><span class="sxs-lookup"><span data-stu-id="8a41a-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="8a41a-125">int</span><span class="sxs-lookup"><span data-stu-id="8a41a-125">int</span></span></p></td>
<td><p><span data-ttu-id="8a41a-126">このフィールドは、(存在する場合) バイパス ID が一致したのに通話がバイパスされなかった理由を示します。</span><span class="sxs-lookup"><span data-stu-id="8a41a-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="8a41a-127">Lync Server の場合は、1つの値のみが定義されます。</span><span class="sxs-lookup"><span data-stu-id="8a41a-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="8a41a-128">0x0001 - 既定のネットワーク アダプターのバイパス ID が不明です。</span><span class="sxs-lookup"><span data-stu-id="8a41a-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a41a-129">StartTime</span><span class="sxs-lookup"><span data-stu-id="8a41a-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="8a41a-130">日付型</span><span class="sxs-lookup"><span data-stu-id="8a41a-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="8a41a-131">通話の開始時刻。</span><span class="sxs-lookup"><span data-stu-id="8a41a-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a41a-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="8a41a-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="8a41a-133">日付型</span><span class="sxs-lookup"><span data-stu-id="8a41a-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="8a41a-134">通話の終了時刻。</span><span class="sxs-lookup"><span data-stu-id="8a41a-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a41a-135">CallerPool</span><span class="sxs-lookup"><span data-stu-id="8a41a-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="8a41a-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8a41a-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8a41a-137">発信者プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="8a41a-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a41a-138">CalleePool</span><span class="sxs-lookup"><span data-stu-id="8a41a-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="8a41a-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8a41a-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8a41a-140">呼び出し先プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="8a41a-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a41a-141">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="8a41a-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="8a41a-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8a41a-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8a41a-143">発信者の P-Asserted-Identity (PAI) URI。</span><span class="sxs-lookup"><span data-stu-id="8a41a-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a41a-144">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="8a41a-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="8a41a-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8a41a-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8a41a-146">呼び出し先の P-Asserted-Identity (PAI) URI。</span><span class="sxs-lookup"><span data-stu-id="8a41a-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a41a-147">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="8a41a-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="8a41a-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8a41a-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8a41a-149">発信者のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="8a41a-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a41a-150">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="8a41a-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="8a41a-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8a41a-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8a41a-152">発信者のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="8a41a-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a41a-153">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="8a41a-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="8a41a-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8a41a-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8a41a-155">発信者のユーザー エージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="8a41a-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a41a-156">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="8a41a-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="8a41a-157">smallint</span><span class="sxs-lookup"><span data-stu-id="8a41a-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="8a41a-158">発信者のユーザー エージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="8a41a-158">Type of caller’s user agent.</span></span> <span data-ttu-id="8a41a-159">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a41a-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a41a-160">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="8a41a-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="8a41a-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="8a41a-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="8a41a-162">発信者のユーザー エージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="8a41a-162">Category of caller’s user agent.</span></span> <span data-ttu-id="8a41a-163">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a41a-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a41a-164">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="8a41a-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="8a41a-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8a41a-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8a41a-166">呼び出し先のユーザー エージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="8a41a-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a41a-167">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="8a41a-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="8a41a-168">smallint</span><span class="sxs-lookup"><span data-stu-id="8a41a-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="8a41a-169">呼び出し先のユーザー エージェント タイプ。</span><span class="sxs-lookup"><span data-stu-id="8a41a-169">Type of user agent for the callee.</span></span> <span data-ttu-id="8a41a-170">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a41a-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a41a-171">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="8a41a-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="8a41a-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="8a41a-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="8a41a-173">呼び出し先のユーザー エージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="8a41a-173">User agent category for the callee.</span></span> <span data-ttu-id="8a41a-174">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a41a-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a41a-175">CallerURI</span><span class="sxs-lookup"><span data-stu-id="8a41a-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="8a41a-176">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8a41a-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8a41a-177">発信者の URI。</span><span class="sxs-lookup"><span data-stu-id="8a41a-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a41a-178">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="8a41a-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="8a41a-179">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8a41a-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8a41a-180">呼び出し先の URI。</span><span class="sxs-lookup"><span data-stu-id="8a41a-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a41a-181">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="8a41a-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="8a41a-182">int</span><span class="sxs-lookup"><span data-stu-id="8a41a-182">int</span></span></p></td>
<td><p><span data-ttu-id="8a41a-183">通話の優先順位。</span><span class="sxs-lookup"><span data-stu-id="8a41a-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

