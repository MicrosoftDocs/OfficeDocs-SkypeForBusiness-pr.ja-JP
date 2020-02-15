---
title: 'Lync Server 2013: UCWA イベント'
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
ms.openlocfilehash: 4d42dbd967f90b6e2a905b92558c88fe52ef62d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="72971-102">Lync Server 2013 の UCWA イベント</span><span class="sxs-lookup"><span data-stu-id="72971-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72971-103">_**トピックの最終更新日:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="72971-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="72971-104">Lync Server 2013 は、統合コミュニケーション Web API (UCWA) を使用して、Microsoft Exchange への連絡先検索のアクセスからモバイルクライアントのプレゼンスの更新まで、さまざまな目的で使用します。</span><span class="sxs-lookup"><span data-stu-id="72971-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="72971-105">UCWA は、イベントの種類の情報、警告、およびエラーとして、操作動作の記録を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="72971-105">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="72971-106">次の表では、UCWA コンポーネントによって記述できるイベントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="72971-106">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="72971-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="72971-107">Event ID</span></span></th>
<th><span data-ttu-id="72971-108">イベントの種類</span><span class="sxs-lookup"><span data-stu-id="72971-108">Event Type</span></span></th>
<th><span data-ttu-id="72971-109">概要</span><span class="sxs-lookup"><span data-stu-id="72971-109">Summary</span></span></th>
<th><span data-ttu-id="72971-110">原因と解決策</span><span class="sxs-lookup"><span data-stu-id="72971-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="72971-111">20001</span><span class="sxs-lookup"><span data-stu-id="72971-111">20001</span></span></p></td>
<td><p><span data-ttu-id="72971-112">だけ</span><span class="sxs-lookup"><span data-stu-id="72971-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="72971-113">UCWA の初期化</span><span class="sxs-lookup"><span data-stu-id="72971-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="72971-114">該当なし</span><span class="sxs-lookup"><span data-stu-id="72971-114">N/A</span></span></p>
<p><span data-ttu-id="72971-115">該当なし</span><span class="sxs-lookup"><span data-stu-id="72971-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72971-116">20002</span><span class="sxs-lookup"><span data-stu-id="72971-116">20002</span></span></p></td>
<td><p><span data-ttu-id="72971-117">Error</span><span class="sxs-lookup"><span data-stu-id="72971-117">Error</span></span></p></td>
<td><p><span data-ttu-id="72971-118">UCWA で初期化中に予期しない例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="72971-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="72971-119">初期化中に予期しないエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="72971-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="72971-120">関連付けられたイベントログエントリの例外の詳細を調べて、考えられる原因を特定します。</span><span class="sxs-lookup"><span data-stu-id="72971-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72971-121">20003</span><span class="sxs-lookup"><span data-stu-id="72971-121">20003</span></span></p></td>
<td><p><span data-ttu-id="72971-122">Error</span><span class="sxs-lookup"><span data-stu-id="72971-122">Error</span></span></p></td>
<td><p><span data-ttu-id="72971-123">UCWA で処理不能な例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="72971-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="72971-124">処理不能な例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="72971-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="72971-125">サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="72971-125">Restart the server.</span></span> <span data-ttu-id="72971-126">問題が引き続き発生する場合は、製品サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="72971-126">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72971-127">20004</span><span class="sxs-lookup"><span data-stu-id="72971-127">20004</span></span></p></td>
<td><p><span data-ttu-id="72971-128">Error</span><span class="sxs-lookup"><span data-stu-id="72971-128">Error</span></span></p></td>
<td><p><span data-ttu-id="72971-129">HD photo の Exchange にアクセスできません</span><span class="sxs-lookup"><span data-stu-id="72971-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="72971-130">Exchange への接続は利用できません</span><span class="sxs-lookup"><span data-stu-id="72971-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="72971-131">Exchange への接続が利用可能であることを確認する</span><span class="sxs-lookup"><span data-stu-id="72971-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72971-132">20005</span><span class="sxs-lookup"><span data-stu-id="72971-132">20005</span></span></p></td>
<td><p><span data-ttu-id="72971-133">だけ</span><span class="sxs-lookup"><span data-stu-id="72971-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="72971-134">HD photo の Exchange へのアクセス障害から復旧した</span><span class="sxs-lookup"><span data-stu-id="72971-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="72971-135">該当なし</span><span class="sxs-lookup"><span data-stu-id="72971-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72971-136">20006</span><span class="sxs-lookup"><span data-stu-id="72971-136">20006</span></span></p></td>
<td><p><span data-ttu-id="72971-137">Error</span><span class="sxs-lookup"><span data-stu-id="72971-137">Error</span></span></p></td>
<td><p><span data-ttu-id="72971-138">連絡先検索の Exchange にアクセスできない</span><span class="sxs-lookup"><span data-stu-id="72971-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="72971-139">Exchange への接続は利用できません</span><span class="sxs-lookup"><span data-stu-id="72971-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="72971-140">Exchange への接続が利用可能であることを確認する</span><span class="sxs-lookup"><span data-stu-id="72971-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72971-141">20007</span><span class="sxs-lookup"><span data-stu-id="72971-141">20007</span></span></p></td>
<td><p><span data-ttu-id="72971-142">だけ</span><span class="sxs-lookup"><span data-stu-id="72971-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="72971-143">Exchange の連絡先を検索できない問題から回復した</span><span class="sxs-lookup"><span data-stu-id="72971-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="72971-144">該当なし</span><span class="sxs-lookup"><span data-stu-id="72971-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72971-145">20008</span><span class="sxs-lookup"><span data-stu-id="72971-145">20008</span></span></p></td>
<td><p><span data-ttu-id="72971-146">警告</span><span class="sxs-lookup"><span data-stu-id="72971-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="72971-147">アプリケーションごとに許可されるプレゼンスサブスクリプションを超えるサブスクライブを試行する</span><span class="sxs-lookup"><span data-stu-id="72971-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="72971-148">アプリケーションごとに許可されるプレゼンスサブスクリプションを超えるサブスクライブを試行する</span><span class="sxs-lookup"><span data-stu-id="72971-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="72971-149">クライアントに不要なサブスクリプションがあるかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="72971-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72971-150">20009</span><span class="sxs-lookup"><span data-stu-id="72971-150">20009</span></span></p></td>
<td><p><span data-ttu-id="72971-151">警告</span><span class="sxs-lookup"><span data-stu-id="72971-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="72971-152">バッチごとに許可されるプレゼンスサブスクリプションの数を超えるサブスクライブを試行する</span><span class="sxs-lookup"><span data-stu-id="72971-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="72971-153">バッチごとに許可されるプレゼンスサブスクリプションの数を超えるサブスクライブを試行する</span><span class="sxs-lookup"><span data-stu-id="72971-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="72971-154">クライアントに不要なサブスクリプションがあるかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="72971-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72971-155">20010</span><span class="sxs-lookup"><span data-stu-id="72971-155">20010</span></span></p></td>
<td><p><span data-ttu-id="72971-156">Error</span><span class="sxs-lookup"><span data-stu-id="72971-156">Error</span></span></p></td>
<td><p><span data-ttu-id="72971-157">インバンドデータを取得できません</span><span class="sxs-lookup"><span data-stu-id="72971-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="72971-158">インバンドデータを取得できません</span><span class="sxs-lookup"><span data-stu-id="72971-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="72971-159">問題が引き続き発生する場合は、製品サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="72971-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72971-160">20011</span><span class="sxs-lookup"><span data-stu-id="72971-160">20011</span></span></p></td>
<td><p><span data-ttu-id="72971-161">Error</span><span class="sxs-lookup"><span data-stu-id="72971-161">Error</span></span></p></td>
<td><p><span data-ttu-id="72971-162">プレゼンスをサブスクライブできません</span><span class="sxs-lookup"><span data-stu-id="72971-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="72971-163">プレゼンスをサブスクライブできません</span><span class="sxs-lookup"><span data-stu-id="72971-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="72971-164">問題が引き続き発生する場合は、製品サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="72971-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72971-165">20012</span><span class="sxs-lookup"><span data-stu-id="72971-165">20012</span></span></p></td>
<td><p><span data-ttu-id="72971-166">Error</span><span class="sxs-lookup"><span data-stu-id="72971-166">Error</span></span></p></td>
<td><p><span data-ttu-id="72971-167">エンドポイントの登録に失敗しました</span><span class="sxs-lookup"><span data-stu-id="72971-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="72971-168">エンドポイントの登録に失敗しました</span><span class="sxs-lookup"><span data-stu-id="72971-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="72971-169">問題が引き続き発生する場合は、製品サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="72971-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72971-170">20013</span><span class="sxs-lookup"><span data-stu-id="72971-170">20013</span></span></p></td>
<td><p><span data-ttu-id="72971-171">Error</span><span class="sxs-lookup"><span data-stu-id="72971-171">Error</span></span></p></td>
<td><p><span data-ttu-id="72971-172">IM MCU は使用できません</span><span class="sxs-lookup"><span data-stu-id="72971-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="72971-173">IM MCU は使用できません</span><span class="sxs-lookup"><span data-stu-id="72971-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="72971-174">IM MCU が実行されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="72971-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72971-175">20014</span><span class="sxs-lookup"><span data-stu-id="72971-175">20014</span></span></p></td>
<td><p><span data-ttu-id="72971-176">だけ</span><span class="sxs-lookup"><span data-stu-id="72971-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="72971-177">IM MCU に接続できないエラーから復旧した</span><span class="sxs-lookup"><span data-stu-id="72971-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="72971-178">該当なし</span><span class="sxs-lookup"><span data-stu-id="72971-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72971-179">20015</span><span class="sxs-lookup"><span data-stu-id="72971-179">20015</span></span></p></td>
<td><p><span data-ttu-id="72971-180">Error</span><span class="sxs-lookup"><span data-stu-id="72971-180">Error</span></span></p></td>
<td><p><span data-ttu-id="72971-181">AV MCU は利用できません</span><span class="sxs-lookup"><span data-stu-id="72971-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="72971-182">AV MCU は利用できません</span><span class="sxs-lookup"><span data-stu-id="72971-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="72971-183">AV MCU が実行されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="72971-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72971-184">20016</span><span class="sxs-lookup"><span data-stu-id="72971-184">20016</span></span></p></td>
<td><p><span data-ttu-id="72971-185">だけ</span><span class="sxs-lookup"><span data-stu-id="72971-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="72971-186">AV MCU に接続できないエラーから復旧した</span><span class="sxs-lookup"><span data-stu-id="72971-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="72971-187">該当なし</span><span class="sxs-lookup"><span data-stu-id="72971-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72971-188">20017</span><span class="sxs-lookup"><span data-stu-id="72971-188">20017</span></span></p></td>
<td><p><span data-ttu-id="72971-189">Error</span><span class="sxs-lookup"><span data-stu-id="72971-189">Error</span></span></p></td>
<td><p><span data-ttu-id="72971-190">MCU が利用できない場合</span><span class="sxs-lookup"><span data-stu-id="72971-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="72971-191">MCU が利用できない場合</span><span class="sxs-lookup"><span data-stu-id="72971-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="72971-192">MCU が実行されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="72971-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72971-193">20018</span><span class="sxs-lookup"><span data-stu-id="72971-193">20018</span></span></p></td>
<td><p><span data-ttu-id="72971-194">だけ</span><span class="sxs-lookup"><span data-stu-id="72971-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="72971-195">MCU としての接続エラーから回復した</span><span class="sxs-lookup"><span data-stu-id="72971-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="72971-196">該当なし</span><span class="sxs-lookup"><span data-stu-id="72971-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72971-197">20019</span><span class="sxs-lookup"><span data-stu-id="72971-197">20019</span></span></p></td>
<td><p><span data-ttu-id="72971-198">Error</span><span class="sxs-lookup"><span data-stu-id="72971-198">Error</span></span></p></td>
<td><p><span data-ttu-id="72971-199">データ MCU を使用できません</span><span class="sxs-lookup"><span data-stu-id="72971-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="72971-200">データ MCU を使用できません</span><span class="sxs-lookup"><span data-stu-id="72971-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="72971-201">データ MCU が実行されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="72971-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72971-202">20020</span><span class="sxs-lookup"><span data-stu-id="72971-202">20020</span></span></p></td>
<td><p><span data-ttu-id="72971-203">だけ</span><span class="sxs-lookup"><span data-stu-id="72971-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="72971-204">データ MCU に接続できないエラーから復旧した</span><span class="sxs-lookup"><span data-stu-id="72971-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="72971-205">該当なし</span><span class="sxs-lookup"><span data-stu-id="72971-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72971-206">20021</span><span class="sxs-lookup"><span data-stu-id="72971-206">20021</span></span></p></td>
<td><p><span data-ttu-id="72971-207">Error</span><span class="sxs-lookup"><span data-stu-id="72971-207">Error</span></span></p></td>
<td><p><span data-ttu-id="72971-208">IM MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="72971-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="72971-209">IM MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="72971-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="72971-210">IM MCU が実行されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="72971-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72971-211">20022</span><span class="sxs-lookup"><span data-stu-id="72971-211">20022</span></span></p></td>
<td><p><span data-ttu-id="72971-212">Error</span><span class="sxs-lookup"><span data-stu-id="72971-212">Error</span></span></p></td>
<td><p><span data-ttu-id="72971-213">AV MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="72971-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="72971-214">AV MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="72971-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="72971-215">AV MCU が実行されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="72971-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72971-216">20023</span><span class="sxs-lookup"><span data-stu-id="72971-216">20023</span></span></p></td>
<td><p><span data-ttu-id="72971-217">Error</span><span class="sxs-lookup"><span data-stu-id="72971-217">Error</span></span></p></td>
<td><p><span data-ttu-id="72971-218">MCU として参加できません</span><span class="sxs-lookup"><span data-stu-id="72971-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="72971-219">MCU として参加できません</span><span class="sxs-lookup"><span data-stu-id="72971-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="72971-220">MCU が実行されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="72971-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72971-221">20024</span><span class="sxs-lookup"><span data-stu-id="72971-221">20024</span></span></p></td>
<td><p><span data-ttu-id="72971-222">Error</span><span class="sxs-lookup"><span data-stu-id="72971-222">Error</span></span></p></td>
<td><p><span data-ttu-id="72971-223">データ MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="72971-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="72971-224">データ MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="72971-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="72971-225">データ MCU が実行されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="72971-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72971-226">20025</span><span class="sxs-lookup"><span data-stu-id="72971-226">20025</span></span></p></td>
<td><p><span data-ttu-id="72971-227">Error</span><span class="sxs-lookup"><span data-stu-id="72971-227">Error</span></span></p></td>
<td><p><span data-ttu-id="72971-228">Active directory の写真にアクセスできません</span><span class="sxs-lookup"><span data-stu-id="72971-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="72971-229">Active directory への接続が利用できません</span><span class="sxs-lookup"><span data-stu-id="72971-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="72971-230">Active directory への接続が利用可能であることを確認する</span><span class="sxs-lookup"><span data-stu-id="72971-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72971-231">20026</span><span class="sxs-lookup"><span data-stu-id="72971-231">20026</span></span></p></td>
<td><p><span data-ttu-id="72971-232">だけ</span><span class="sxs-lookup"><span data-stu-id="72971-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="72971-233">Active directory の写真にアクセスできないエラーから復旧した</span><span class="sxs-lookup"><span data-stu-id="72971-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="72971-234">該当なし</span><span class="sxs-lookup"><span data-stu-id="72971-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72971-235">20027</span><span class="sxs-lookup"><span data-stu-id="72971-235">20027</span></span></p></td>
<td><p><span data-ttu-id="72971-236">警告</span><span class="sxs-lookup"><span data-stu-id="72971-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="72971-237">逆シリアル化できません</span><span class="sxs-lookup"><span data-stu-id="72971-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="72971-238">逆シリアル化できません</span><span class="sxs-lookup"><span data-stu-id="72971-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="72971-239">問題が引き続き発生する場合は、製品サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="72971-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

