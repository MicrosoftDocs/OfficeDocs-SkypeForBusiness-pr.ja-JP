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
ms.openlocfilehash: 5dd289ab5035e8030b161609b69e764995e7f7e4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="d4189-102">Lync Server 2013 のセッションビュー</span><span class="sxs-lookup"><span data-stu-id="d4189-102">Session view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4189-103">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="d4189-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="d4189-104">セッション ビューには、データベースにレコードがあるセッションに関する情報が保存されます。</span><span class="sxs-lookup"><span data-stu-id="d4189-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="d4189-105">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d4189-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4189-106">列</span><span class="sxs-lookup"><span data-stu-id="d4189-106">Column</span></span></th>
<th><span data-ttu-id="d4189-107">データ型</span><span class="sxs-lookup"><span data-stu-id="d4189-107">Data Type</span></span></th>
<th><span data-ttu-id="d4189-108">詳細</span><span class="sxs-lookup"><span data-stu-id="d4189-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4189-109">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="d4189-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="d4189-110">日付型</span><span class="sxs-lookup"><span data-stu-id="d4189-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="d4189-111">MediaLine テーブルから参照されます。</span><span class="sxs-lookup"><span data-stu-id="d4189-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4189-112">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="d4189-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="d4189-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d4189-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d4189-114">これが会議の場合は会議 URI、ピアツーピア セッションの場合は DialogID です。</span><span class="sxs-lookup"><span data-stu-id="d4189-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4189-115">関連付け</span><span class="sxs-lookup"><span data-stu-id="d4189-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="d4189-116">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="d4189-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="d4189-117">セッションの関連付け ID。</span><span class="sxs-lookup"><span data-stu-id="d4189-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4189-118">' このカテゴリ</span><span class="sxs-lookup"><span data-stu-id="d4189-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="d4189-119">若干</span><span class="sxs-lookup"><span data-stu-id="d4189-119">bit</span></span></p></td>
<td><p><span data-ttu-id="d4189-120">ダイアログのカテゴリ。0は Lync Server から仲介サーバーまでです。1は仲介サーバーから PSTN ゲートウェイレグになります。</span><span class="sxs-lookup"><span data-stu-id="d4189-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4189-121">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="d4189-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="d4189-122">若干</span><span class="sxs-lookup"><span data-stu-id="d4189-122">bit</span></span></p></td>
<td><p><span data-ttu-id="d4189-123">通話がバイパスされたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d4189-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4189-124">Mediabypasswarnings フラグ</span><span class="sxs-lookup"><span data-stu-id="d4189-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="d4189-125">int</span><span class="sxs-lookup"><span data-stu-id="d4189-125">int</span></span></p></td>
<td><p><span data-ttu-id="d4189-126">このフィールドは、(存在する場合) バイパス ID が一致したのに通話がバイパスされなかった理由を示します。</span><span class="sxs-lookup"><span data-stu-id="d4189-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="d4189-127">Lync Server の場合は、1つの値のみが定義されます。</span><span class="sxs-lookup"><span data-stu-id="d4189-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="d4189-128">0x0001 - 既定のネットワーク アダプターのバイパス ID が不明です。</span><span class="sxs-lookup"><span data-stu-id="d4189-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4189-129">StartTime</span><span class="sxs-lookup"><span data-stu-id="d4189-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="d4189-130">日付型</span><span class="sxs-lookup"><span data-stu-id="d4189-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="d4189-131">通話の開始時刻。</span><span class="sxs-lookup"><span data-stu-id="d4189-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4189-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="d4189-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="d4189-133">日付型</span><span class="sxs-lookup"><span data-stu-id="d4189-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="d4189-134">通話の終了時刻。</span><span class="sxs-lookup"><span data-stu-id="d4189-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4189-135">CallerPool</span><span class="sxs-lookup"><span data-stu-id="d4189-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="d4189-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4189-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4189-137">発信者プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="d4189-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4189-138">CalleePool</span><span class="sxs-lookup"><span data-stu-id="d4189-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="d4189-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4189-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4189-140">呼び出し先プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="d4189-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4189-141">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="d4189-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="d4189-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d4189-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d4189-143">発信者の P-Asserted-Identity (PAI) URI。</span><span class="sxs-lookup"><span data-stu-id="d4189-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4189-144">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="d4189-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="d4189-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d4189-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d4189-146">呼び出し先の P-Asserted-Identity (PAI) URI。</span><span class="sxs-lookup"><span data-stu-id="d4189-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4189-147">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="d4189-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="d4189-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4189-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4189-149">発信者のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="d4189-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4189-150">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="d4189-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="d4189-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4189-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4189-152">発信者のエンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="d4189-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4189-153">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="d4189-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="d4189-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4189-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4189-155">発信者のユーザー エージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="d4189-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4189-156">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="d4189-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="d4189-157">smallint</span><span class="sxs-lookup"><span data-stu-id="d4189-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="d4189-158">発信者のユーザー エージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="d4189-158">Type of caller’s user agent.</span></span> <span data-ttu-id="d4189-159">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4189-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4189-160">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="d4189-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="d4189-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="d4189-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="d4189-162">発信者のユーザー エージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="d4189-162">Category of caller’s user agent.</span></span> <span data-ttu-id="d4189-163">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4189-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4189-164">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="d4189-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="d4189-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4189-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4189-166">呼び出し先のユーザー エージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="d4189-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4189-167">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="d4189-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="d4189-168">smallint</span><span class="sxs-lookup"><span data-stu-id="d4189-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="d4189-169">呼び出し先のユーザー エージェント タイプ。</span><span class="sxs-lookup"><span data-stu-id="d4189-169">Type of user agent for the callee.</span></span> <span data-ttu-id="d4189-170">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4189-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4189-171">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="d4189-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="d4189-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="d4189-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="d4189-173">呼び出し先のユーザー エージェントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="d4189-173">User agent category for the callee.</span></span> <span data-ttu-id="d4189-174">詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4189-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4189-175">CallerURI</span><span class="sxs-lookup"><span data-stu-id="d4189-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="d4189-176">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d4189-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d4189-177">発信者の URI。</span><span class="sxs-lookup"><span data-stu-id="d4189-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4189-178">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="d4189-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="d4189-179">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d4189-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d4189-180">呼び出し先の URI。</span><span class="sxs-lookup"><span data-stu-id="d4189-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4189-181">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="d4189-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="d4189-182">int</span><span class="sxs-lookup"><span data-stu-id="d4189-182">int</span></span></p></td>
<td><p><span data-ttu-id="d4189-183">通話の優先順位。</span><span class="sxs-lookup"><span data-stu-id="d4189-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

