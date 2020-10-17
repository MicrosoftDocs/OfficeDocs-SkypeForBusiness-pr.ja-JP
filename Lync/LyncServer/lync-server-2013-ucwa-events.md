---
title: 'Lync Server 2013: UCWA イベント'
description: 'Lync Server 2013: UCWA イベント。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8104ce9c7533350f40ce194e1cde205bc3692792
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548853"
---
# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="caf63-103">Lync Server 2013 の UCWA イベント</span><span class="sxs-lookup"><span data-stu-id="caf63-103">UCWA events in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="caf63-104">_**トピックの最終更新日:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="caf63-104">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="caf63-105">Lync Server 2013 は、統合コミュニケーション Web API (UCWA) を使用して、Microsoft Exchange への連絡先検索のアクセスからモバイルクライアントのプレゼンスの更新まで、さまざまな目的で使用します。</span><span class="sxs-lookup"><span data-stu-id="caf63-105">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="caf63-106">UCWA は、イベントの種類の情報、警告、およびエラーとして、操作動作の記録を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="caf63-106">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="caf63-107">次の表では、UCWA コンポーネントによって記述できるイベントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="caf63-107">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="caf63-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="caf63-108">Event ID</span></span></th>
<th><span data-ttu-id="caf63-109">イベントの種類</span><span class="sxs-lookup"><span data-stu-id="caf63-109">Event Type</span></span></th>
<th><span data-ttu-id="caf63-110">要約</span><span class="sxs-lookup"><span data-stu-id="caf63-110">Summary</span></span></th>
<th><span data-ttu-id="caf63-111">原因と解決策</span><span class="sxs-lookup"><span data-stu-id="caf63-111">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="caf63-112">20001</span><span class="sxs-lookup"><span data-stu-id="caf63-112">20001</span></span></p></td>
<td><p><span data-ttu-id="caf63-113">だけ</span><span class="sxs-lookup"><span data-stu-id="caf63-113">Informational</span></span></p></td>
<td><p><span data-ttu-id="caf63-114">UCWA の初期化</span><span class="sxs-lookup"><span data-stu-id="caf63-114">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="caf63-115">該当なし</span><span class="sxs-lookup"><span data-stu-id="caf63-115">N/A</span></span></p>
<p><span data-ttu-id="caf63-116">該当なし</span><span class="sxs-lookup"><span data-stu-id="caf63-116">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="caf63-117">20002</span><span class="sxs-lookup"><span data-stu-id="caf63-117">20002</span></span></p></td>
<td><p><span data-ttu-id="caf63-118">Error</span><span class="sxs-lookup"><span data-stu-id="caf63-118">Error</span></span></p></td>
<td><p><span data-ttu-id="caf63-119">UCWA で初期化中に予期しない例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="caf63-119">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="caf63-120">初期化中に予期しないエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="caf63-120">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="caf63-121">関連付けられたイベントログエントリの例外の詳細を調べて、考えられる原因を特定します。</span><span class="sxs-lookup"><span data-stu-id="caf63-121">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="caf63-122">20003</span><span class="sxs-lookup"><span data-stu-id="caf63-122">20003</span></span></p></td>
<td><p><span data-ttu-id="caf63-123">Error</span><span class="sxs-lookup"><span data-stu-id="caf63-123">Error</span></span></p></td>
<td><p><span data-ttu-id="caf63-124">UCWA で処理不能な例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="caf63-124">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="caf63-125">処理不能な例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="caf63-125">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="caf63-126">サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="caf63-126">Restart the server.</span></span> <span data-ttu-id="caf63-127">問題が引き続き発生する場合は、製品サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="caf63-127">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="caf63-128">20004</span><span class="sxs-lookup"><span data-stu-id="caf63-128">20004</span></span></p></td>
<td><p><span data-ttu-id="caf63-129">Error</span><span class="sxs-lookup"><span data-stu-id="caf63-129">Error</span></span></p></td>
<td><p><span data-ttu-id="caf63-130">HD photo の Exchange にアクセスできません</span><span class="sxs-lookup"><span data-stu-id="caf63-130">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="caf63-131">Exchange への接続は利用できません</span><span class="sxs-lookup"><span data-stu-id="caf63-131">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="caf63-132">Exchange への接続が利用可能であることを確認する</span><span class="sxs-lookup"><span data-stu-id="caf63-132">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="caf63-133">20005</span><span class="sxs-lookup"><span data-stu-id="caf63-133">20005</span></span></p></td>
<td><p><span data-ttu-id="caf63-134">だけ</span><span class="sxs-lookup"><span data-stu-id="caf63-134">Informational</span></span></p></td>
<td><p><span data-ttu-id="caf63-135">HD photo の Exchange へのアクセス障害から復旧した</span><span class="sxs-lookup"><span data-stu-id="caf63-135">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="caf63-136">該当なし</span><span class="sxs-lookup"><span data-stu-id="caf63-136">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="caf63-137">20006</span><span class="sxs-lookup"><span data-stu-id="caf63-137">20006</span></span></p></td>
<td><p><span data-ttu-id="caf63-138">Error</span><span class="sxs-lookup"><span data-stu-id="caf63-138">Error</span></span></p></td>
<td><p><span data-ttu-id="caf63-139">連絡先検索の Exchange にアクセスできない</span><span class="sxs-lookup"><span data-stu-id="caf63-139">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="caf63-140">Exchange への接続は利用できません</span><span class="sxs-lookup"><span data-stu-id="caf63-140">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="caf63-141">Exchange への接続が利用可能であることを確認する</span><span class="sxs-lookup"><span data-stu-id="caf63-141">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="caf63-142">20007</span><span class="sxs-lookup"><span data-stu-id="caf63-142">20007</span></span></p></td>
<td><p><span data-ttu-id="caf63-143">だけ</span><span class="sxs-lookup"><span data-stu-id="caf63-143">Informational</span></span></p></td>
<td><p><span data-ttu-id="caf63-144">Exchange の連絡先を検索できない問題から回復した</span><span class="sxs-lookup"><span data-stu-id="caf63-144">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="caf63-145">該当なし</span><span class="sxs-lookup"><span data-stu-id="caf63-145">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="caf63-146">20008</span><span class="sxs-lookup"><span data-stu-id="caf63-146">20008</span></span></p></td>
<td><p><span data-ttu-id="caf63-147">警告</span><span class="sxs-lookup"><span data-stu-id="caf63-147">Warning</span></span></p></td>
<td><p><span data-ttu-id="caf63-148">アプリケーションごとに許可されるプレゼンスサブスクリプションを超えるサブスクライブを試行する</span><span class="sxs-lookup"><span data-stu-id="caf63-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="caf63-149">アプリケーションごとに許可されるプレゼンスサブスクリプションを超えるサブスクライブを試行する</span><span class="sxs-lookup"><span data-stu-id="caf63-149">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="caf63-150">クライアントに不要なサブスクリプションがあるかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="caf63-150">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="caf63-151">20009</span><span class="sxs-lookup"><span data-stu-id="caf63-151">20009</span></span></p></td>
<td><p><span data-ttu-id="caf63-152">警告</span><span class="sxs-lookup"><span data-stu-id="caf63-152">Warning</span></span></p></td>
<td><p><span data-ttu-id="caf63-153">バッチごとに許可されるプレゼンスサブスクリプションの数を超えるサブスクライブを試行する</span><span class="sxs-lookup"><span data-stu-id="caf63-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="caf63-154">バッチごとに許可されるプレゼンスサブスクリプションの数を超えるサブスクライブを試行する</span><span class="sxs-lookup"><span data-stu-id="caf63-154">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="caf63-155">クライアントに不要なサブスクリプションがあるかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="caf63-155">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="caf63-156">20010</span><span class="sxs-lookup"><span data-stu-id="caf63-156">20010</span></span></p></td>
<td><p><span data-ttu-id="caf63-157">Error</span><span class="sxs-lookup"><span data-stu-id="caf63-157">Error</span></span></p></td>
<td><p><span data-ttu-id="caf63-158">インバンドデータを取得できません</span><span class="sxs-lookup"><span data-stu-id="caf63-158">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="caf63-159">インバンドデータを取得できません</span><span class="sxs-lookup"><span data-stu-id="caf63-159">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="caf63-160">問題が引き続き発生する場合は、製品サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="caf63-160">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="caf63-161">20011</span><span class="sxs-lookup"><span data-stu-id="caf63-161">20011</span></span></p></td>
<td><p><span data-ttu-id="caf63-162">Error</span><span class="sxs-lookup"><span data-stu-id="caf63-162">Error</span></span></p></td>
<td><p><span data-ttu-id="caf63-163">プレゼンスをサブスクライブできません</span><span class="sxs-lookup"><span data-stu-id="caf63-163">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="caf63-164">プレゼンスをサブスクライブできません</span><span class="sxs-lookup"><span data-stu-id="caf63-164">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="caf63-165">問題が引き続き発生する場合は、製品サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="caf63-165">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="caf63-166">20012</span><span class="sxs-lookup"><span data-stu-id="caf63-166">20012</span></span></p></td>
<td><p><span data-ttu-id="caf63-167">Error</span><span class="sxs-lookup"><span data-stu-id="caf63-167">Error</span></span></p></td>
<td><p><span data-ttu-id="caf63-168">エンドポイントの登録に失敗しました</span><span class="sxs-lookup"><span data-stu-id="caf63-168">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="caf63-169">エンドポイントの登録に失敗しました</span><span class="sxs-lookup"><span data-stu-id="caf63-169">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="caf63-170">問題が引き続き発生する場合は、製品サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="caf63-170">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="caf63-171">20013</span><span class="sxs-lookup"><span data-stu-id="caf63-171">20013</span></span></p></td>
<td><p><span data-ttu-id="caf63-172">Error</span><span class="sxs-lookup"><span data-stu-id="caf63-172">Error</span></span></p></td>
<td><p><span data-ttu-id="caf63-173">IM MCU は使用できません</span><span class="sxs-lookup"><span data-stu-id="caf63-173">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="caf63-174">IM MCU は使用できません</span><span class="sxs-lookup"><span data-stu-id="caf63-174">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="caf63-175">IM MCU が実行されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="caf63-175">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="caf63-176">20014</span><span class="sxs-lookup"><span data-stu-id="caf63-176">20014</span></span></p></td>
<td><p><span data-ttu-id="caf63-177">だけ</span><span class="sxs-lookup"><span data-stu-id="caf63-177">Informational</span></span></p></td>
<td><p><span data-ttu-id="caf63-178">IM MCU に接続できないエラーから復旧した</span><span class="sxs-lookup"><span data-stu-id="caf63-178">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="caf63-179">該当なし</span><span class="sxs-lookup"><span data-stu-id="caf63-179">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="caf63-180">20015</span><span class="sxs-lookup"><span data-stu-id="caf63-180">20015</span></span></p></td>
<td><p><span data-ttu-id="caf63-181">Error</span><span class="sxs-lookup"><span data-stu-id="caf63-181">Error</span></span></p></td>
<td><p><span data-ttu-id="caf63-182">AV MCU は利用できません</span><span class="sxs-lookup"><span data-stu-id="caf63-182">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="caf63-183">AV MCU は利用できません</span><span class="sxs-lookup"><span data-stu-id="caf63-183">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="caf63-184">AV MCU が実行されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="caf63-184">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="caf63-185">20016</span><span class="sxs-lookup"><span data-stu-id="caf63-185">20016</span></span></p></td>
<td><p><span data-ttu-id="caf63-186">だけ</span><span class="sxs-lookup"><span data-stu-id="caf63-186">Informational</span></span></p></td>
<td><p><span data-ttu-id="caf63-187">AV MCU に接続できないエラーから復旧した</span><span class="sxs-lookup"><span data-stu-id="caf63-187">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="caf63-188">該当なし</span><span class="sxs-lookup"><span data-stu-id="caf63-188">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="caf63-189">20017</span><span class="sxs-lookup"><span data-stu-id="caf63-189">20017</span></span></p></td>
<td><p><span data-ttu-id="caf63-190">Error</span><span class="sxs-lookup"><span data-stu-id="caf63-190">Error</span></span></p></td>
<td><p><span data-ttu-id="caf63-191">MCU が利用できない場合</span><span class="sxs-lookup"><span data-stu-id="caf63-191">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="caf63-192">MCU が利用できない場合</span><span class="sxs-lookup"><span data-stu-id="caf63-192">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="caf63-193">MCU が実行されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="caf63-193">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="caf63-194">20018</span><span class="sxs-lookup"><span data-stu-id="caf63-194">20018</span></span></p></td>
<td><p><span data-ttu-id="caf63-195">だけ</span><span class="sxs-lookup"><span data-stu-id="caf63-195">Informational</span></span></p></td>
<td><p><span data-ttu-id="caf63-196">MCU としての接続エラーから回復した</span><span class="sxs-lookup"><span data-stu-id="caf63-196">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="caf63-197">該当なし</span><span class="sxs-lookup"><span data-stu-id="caf63-197">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="caf63-198">20019</span><span class="sxs-lookup"><span data-stu-id="caf63-198">20019</span></span></p></td>
<td><p><span data-ttu-id="caf63-199">Error</span><span class="sxs-lookup"><span data-stu-id="caf63-199">Error</span></span></p></td>
<td><p><span data-ttu-id="caf63-200">データ MCU を使用できません</span><span class="sxs-lookup"><span data-stu-id="caf63-200">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="caf63-201">データ MCU を使用できません</span><span class="sxs-lookup"><span data-stu-id="caf63-201">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="caf63-202">データ MCU が実行されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="caf63-202">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="caf63-203">20020</span><span class="sxs-lookup"><span data-stu-id="caf63-203">20020</span></span></p></td>
<td><p><span data-ttu-id="caf63-204">だけ</span><span class="sxs-lookup"><span data-stu-id="caf63-204">Informational</span></span></p></td>
<td><p><span data-ttu-id="caf63-205">データ MCU に接続できないエラーから復旧した</span><span class="sxs-lookup"><span data-stu-id="caf63-205">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="caf63-206">該当なし</span><span class="sxs-lookup"><span data-stu-id="caf63-206">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="caf63-207">20021</span><span class="sxs-lookup"><span data-stu-id="caf63-207">20021</span></span></p></td>
<td><p><span data-ttu-id="caf63-208">Error</span><span class="sxs-lookup"><span data-stu-id="caf63-208">Error</span></span></p></td>
<td><p><span data-ttu-id="caf63-209">IM MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="caf63-209">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="caf63-210">IM MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="caf63-210">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="caf63-211">IM MCU が実行されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="caf63-211">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="caf63-212">20022</span><span class="sxs-lookup"><span data-stu-id="caf63-212">20022</span></span></p></td>
<td><p><span data-ttu-id="caf63-213">Error</span><span class="sxs-lookup"><span data-stu-id="caf63-213">Error</span></span></p></td>
<td><p><span data-ttu-id="caf63-214">AV MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="caf63-214">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="caf63-215">AV MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="caf63-215">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="caf63-216">AV MCU が実行されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="caf63-216">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="caf63-217">20023</span><span class="sxs-lookup"><span data-stu-id="caf63-217">20023</span></span></p></td>
<td><p><span data-ttu-id="caf63-218">Error</span><span class="sxs-lookup"><span data-stu-id="caf63-218">Error</span></span></p></td>
<td><p><span data-ttu-id="caf63-219">MCU として参加できません</span><span class="sxs-lookup"><span data-stu-id="caf63-219">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="caf63-220">MCU として参加できません</span><span class="sxs-lookup"><span data-stu-id="caf63-220">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="caf63-221">MCU が実行されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="caf63-221">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="caf63-222">20024</span><span class="sxs-lookup"><span data-stu-id="caf63-222">20024</span></span></p></td>
<td><p><span data-ttu-id="caf63-223">Error</span><span class="sxs-lookup"><span data-stu-id="caf63-223">Error</span></span></p></td>
<td><p><span data-ttu-id="caf63-224">データ MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="caf63-224">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="caf63-225">データ MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="caf63-225">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="caf63-226">データ MCU が実行されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="caf63-226">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="caf63-227">20025</span><span class="sxs-lookup"><span data-stu-id="caf63-227">20025</span></span></p></td>
<td><p><span data-ttu-id="caf63-228">Error</span><span class="sxs-lookup"><span data-stu-id="caf63-228">Error</span></span></p></td>
<td><p><span data-ttu-id="caf63-229">Active directory の写真にアクセスできません</span><span class="sxs-lookup"><span data-stu-id="caf63-229">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="caf63-230">Active directory への接続が利用できません</span><span class="sxs-lookup"><span data-stu-id="caf63-230">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="caf63-231">Active directory への接続が利用可能であることを確認する</span><span class="sxs-lookup"><span data-stu-id="caf63-231">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="caf63-232">20026</span><span class="sxs-lookup"><span data-stu-id="caf63-232">20026</span></span></p></td>
<td><p><span data-ttu-id="caf63-233">だけ</span><span class="sxs-lookup"><span data-stu-id="caf63-233">Informational</span></span></p></td>
<td><p><span data-ttu-id="caf63-234">Active directory の写真にアクセスできないエラーから復旧した</span><span class="sxs-lookup"><span data-stu-id="caf63-234">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="caf63-235">該当なし</span><span class="sxs-lookup"><span data-stu-id="caf63-235">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="caf63-236">20027</span><span class="sxs-lookup"><span data-stu-id="caf63-236">20027</span></span></p></td>
<td><p><span data-ttu-id="caf63-237">警告</span><span class="sxs-lookup"><span data-stu-id="caf63-237">Warning</span></span></p></td>
<td><p><span data-ttu-id="caf63-238">逆シリアル化できません</span><span class="sxs-lookup"><span data-stu-id="caf63-238">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="caf63-239">逆シリアル化できません</span><span class="sxs-lookup"><span data-stu-id="caf63-239">Cannot deserialize</span></span></p>
<p><span data-ttu-id="caf63-240">問題が引き続き発生する場合は、製品サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="caf63-240">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

