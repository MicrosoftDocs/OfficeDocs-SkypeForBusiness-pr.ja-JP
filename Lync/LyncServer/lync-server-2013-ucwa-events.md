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
ms.openlocfilehash: 1ae71fa6e91c0bc212bc019b1afa85ebcacb4d0d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527794"
---
# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="57271-102">Lync Server 2013 の UCWA イベント</span><span class="sxs-lookup"><span data-stu-id="57271-102">UCWA events in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57271-103">_**トピックの最終更新日:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="57271-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="57271-104">Lync Server 2013 は、統合コミュニケーション Web API (UCWA) を使用して、Microsoft Exchange への連絡先検索のアクセスからモバイルクライアントのプレゼンスの更新まで、さまざまな目的で使用します。</span><span class="sxs-lookup"><span data-stu-id="57271-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="57271-105">UCWA は、イベントの種類の情報、警告、およびエラーとして、操作動作の記録を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="57271-105">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="57271-106">次の表では、UCWA コンポーネントによって記述できるイベントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="57271-106">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57271-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="57271-107">Event ID</span></span></th>
<th><span data-ttu-id="57271-108">イベントの種類</span><span class="sxs-lookup"><span data-stu-id="57271-108">Event Type</span></span></th>
<th><span data-ttu-id="57271-109">要約</span><span class="sxs-lookup"><span data-stu-id="57271-109">Summary</span></span></th>
<th><span data-ttu-id="57271-110">原因と解決策</span><span class="sxs-lookup"><span data-stu-id="57271-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57271-111">20001</span><span class="sxs-lookup"><span data-stu-id="57271-111">20001</span></span></p></td>
<td><p><span data-ttu-id="57271-112">だけ</span><span class="sxs-lookup"><span data-stu-id="57271-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="57271-113">UCWA の初期化</span><span class="sxs-lookup"><span data-stu-id="57271-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="57271-114">該当なし</span><span class="sxs-lookup"><span data-stu-id="57271-114">N/A</span></span></p>
<p><span data-ttu-id="57271-115">該当なし</span><span class="sxs-lookup"><span data-stu-id="57271-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57271-116">20002</span><span class="sxs-lookup"><span data-stu-id="57271-116">20002</span></span></p></td>
<td><p><span data-ttu-id="57271-117">Error</span><span class="sxs-lookup"><span data-stu-id="57271-117">Error</span></span></p></td>
<td><p><span data-ttu-id="57271-118">UCWA で初期化中に予期しない例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="57271-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="57271-119">初期化中に予期しないエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="57271-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="57271-120">関連付けられたイベントログエントリの例外の詳細を調べて、考えられる原因を特定します。</span><span class="sxs-lookup"><span data-stu-id="57271-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57271-121">20003</span><span class="sxs-lookup"><span data-stu-id="57271-121">20003</span></span></p></td>
<td><p><span data-ttu-id="57271-122">Error</span><span class="sxs-lookup"><span data-stu-id="57271-122">Error</span></span></p></td>
<td><p><span data-ttu-id="57271-123">UCWA で処理不能な例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="57271-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="57271-124">処理不能な例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="57271-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="57271-125">サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="57271-125">Restart the server.</span></span> <span data-ttu-id="57271-126">問題が引き続き発生する場合は、製品サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="57271-126">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57271-127">20004</span><span class="sxs-lookup"><span data-stu-id="57271-127">20004</span></span></p></td>
<td><p><span data-ttu-id="57271-128">Error</span><span class="sxs-lookup"><span data-stu-id="57271-128">Error</span></span></p></td>
<td><p><span data-ttu-id="57271-129">HD photo の Exchange にアクセスできません</span><span class="sxs-lookup"><span data-stu-id="57271-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="57271-130">Exchange への接続は利用できません</span><span class="sxs-lookup"><span data-stu-id="57271-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="57271-131">Exchange への接続が利用可能であることを確認する</span><span class="sxs-lookup"><span data-stu-id="57271-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57271-132">20005</span><span class="sxs-lookup"><span data-stu-id="57271-132">20005</span></span></p></td>
<td><p><span data-ttu-id="57271-133">だけ</span><span class="sxs-lookup"><span data-stu-id="57271-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="57271-134">HD photo の Exchange へのアクセス障害から復旧した</span><span class="sxs-lookup"><span data-stu-id="57271-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="57271-135">該当なし</span><span class="sxs-lookup"><span data-stu-id="57271-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57271-136">20006</span><span class="sxs-lookup"><span data-stu-id="57271-136">20006</span></span></p></td>
<td><p><span data-ttu-id="57271-137">Error</span><span class="sxs-lookup"><span data-stu-id="57271-137">Error</span></span></p></td>
<td><p><span data-ttu-id="57271-138">連絡先検索の Exchange にアクセスできない</span><span class="sxs-lookup"><span data-stu-id="57271-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="57271-139">Exchange への接続は利用できません</span><span class="sxs-lookup"><span data-stu-id="57271-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="57271-140">Exchange への接続が利用可能であることを確認する</span><span class="sxs-lookup"><span data-stu-id="57271-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57271-141">20007</span><span class="sxs-lookup"><span data-stu-id="57271-141">20007</span></span></p></td>
<td><p><span data-ttu-id="57271-142">だけ</span><span class="sxs-lookup"><span data-stu-id="57271-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="57271-143">Exchange の連絡先を検索できない問題から回復した</span><span class="sxs-lookup"><span data-stu-id="57271-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="57271-144">該当なし</span><span class="sxs-lookup"><span data-stu-id="57271-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57271-145">20008</span><span class="sxs-lookup"><span data-stu-id="57271-145">20008</span></span></p></td>
<td><p><span data-ttu-id="57271-146">警告</span><span class="sxs-lookup"><span data-stu-id="57271-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="57271-147">アプリケーションごとに許可されるプレゼンスサブスクリプションを超えるサブスクライブを試行する</span><span class="sxs-lookup"><span data-stu-id="57271-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="57271-148">アプリケーションごとに許可されるプレゼンスサブスクリプションを超えるサブスクライブを試行する</span><span class="sxs-lookup"><span data-stu-id="57271-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="57271-149">クライアントに不要なサブスクリプションがあるかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="57271-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57271-150">20009</span><span class="sxs-lookup"><span data-stu-id="57271-150">20009</span></span></p></td>
<td><p><span data-ttu-id="57271-151">警告</span><span class="sxs-lookup"><span data-stu-id="57271-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="57271-152">バッチごとに許可されるプレゼンスサブスクリプションの数を超えるサブスクライブを試行する</span><span class="sxs-lookup"><span data-stu-id="57271-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="57271-153">バッチごとに許可されるプレゼンスサブスクリプションの数を超えるサブスクライブを試行する</span><span class="sxs-lookup"><span data-stu-id="57271-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="57271-154">クライアントに不要なサブスクリプションがあるかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="57271-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57271-155">20010</span><span class="sxs-lookup"><span data-stu-id="57271-155">20010</span></span></p></td>
<td><p><span data-ttu-id="57271-156">Error</span><span class="sxs-lookup"><span data-stu-id="57271-156">Error</span></span></p></td>
<td><p><span data-ttu-id="57271-157">インバンドデータを取得できません</span><span class="sxs-lookup"><span data-stu-id="57271-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="57271-158">インバンドデータを取得できません</span><span class="sxs-lookup"><span data-stu-id="57271-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="57271-159">問題が引き続き発生する場合は、製品サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="57271-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57271-160">20011</span><span class="sxs-lookup"><span data-stu-id="57271-160">20011</span></span></p></td>
<td><p><span data-ttu-id="57271-161">Error</span><span class="sxs-lookup"><span data-stu-id="57271-161">Error</span></span></p></td>
<td><p><span data-ttu-id="57271-162">プレゼンスをサブスクライブできません</span><span class="sxs-lookup"><span data-stu-id="57271-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="57271-163">プレゼンスをサブスクライブできません</span><span class="sxs-lookup"><span data-stu-id="57271-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="57271-164">問題が引き続き発生する場合は、製品サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="57271-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57271-165">20012</span><span class="sxs-lookup"><span data-stu-id="57271-165">20012</span></span></p></td>
<td><p><span data-ttu-id="57271-166">Error</span><span class="sxs-lookup"><span data-stu-id="57271-166">Error</span></span></p></td>
<td><p><span data-ttu-id="57271-167">エンドポイントの登録に失敗しました</span><span class="sxs-lookup"><span data-stu-id="57271-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="57271-168">エンドポイントの登録に失敗しました</span><span class="sxs-lookup"><span data-stu-id="57271-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="57271-169">問題が引き続き発生する場合は、製品サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="57271-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57271-170">20013</span><span class="sxs-lookup"><span data-stu-id="57271-170">20013</span></span></p></td>
<td><p><span data-ttu-id="57271-171">Error</span><span class="sxs-lookup"><span data-stu-id="57271-171">Error</span></span></p></td>
<td><p><span data-ttu-id="57271-172">IM MCU は使用できません</span><span class="sxs-lookup"><span data-stu-id="57271-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="57271-173">IM MCU は使用できません</span><span class="sxs-lookup"><span data-stu-id="57271-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="57271-174">IM MCU が実行されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="57271-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57271-175">20014</span><span class="sxs-lookup"><span data-stu-id="57271-175">20014</span></span></p></td>
<td><p><span data-ttu-id="57271-176">だけ</span><span class="sxs-lookup"><span data-stu-id="57271-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="57271-177">IM MCU に接続できないエラーから復旧した</span><span class="sxs-lookup"><span data-stu-id="57271-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="57271-178">該当なし</span><span class="sxs-lookup"><span data-stu-id="57271-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57271-179">20015</span><span class="sxs-lookup"><span data-stu-id="57271-179">20015</span></span></p></td>
<td><p><span data-ttu-id="57271-180">Error</span><span class="sxs-lookup"><span data-stu-id="57271-180">Error</span></span></p></td>
<td><p><span data-ttu-id="57271-181">AV MCU は利用できません</span><span class="sxs-lookup"><span data-stu-id="57271-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="57271-182">AV MCU は利用できません</span><span class="sxs-lookup"><span data-stu-id="57271-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="57271-183">AV MCU が実行されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="57271-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57271-184">20016</span><span class="sxs-lookup"><span data-stu-id="57271-184">20016</span></span></p></td>
<td><p><span data-ttu-id="57271-185">だけ</span><span class="sxs-lookup"><span data-stu-id="57271-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="57271-186">AV MCU に接続できないエラーから復旧した</span><span class="sxs-lookup"><span data-stu-id="57271-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="57271-187">該当なし</span><span class="sxs-lookup"><span data-stu-id="57271-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57271-188">20017</span><span class="sxs-lookup"><span data-stu-id="57271-188">20017</span></span></p></td>
<td><p><span data-ttu-id="57271-189">Error</span><span class="sxs-lookup"><span data-stu-id="57271-189">Error</span></span></p></td>
<td><p><span data-ttu-id="57271-190">MCU が利用できない場合</span><span class="sxs-lookup"><span data-stu-id="57271-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="57271-191">MCU が利用できない場合</span><span class="sxs-lookup"><span data-stu-id="57271-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="57271-192">MCU が実行されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="57271-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57271-193">20018</span><span class="sxs-lookup"><span data-stu-id="57271-193">20018</span></span></p></td>
<td><p><span data-ttu-id="57271-194">だけ</span><span class="sxs-lookup"><span data-stu-id="57271-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="57271-195">MCU としての接続エラーから回復した</span><span class="sxs-lookup"><span data-stu-id="57271-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="57271-196">該当なし</span><span class="sxs-lookup"><span data-stu-id="57271-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57271-197">20019</span><span class="sxs-lookup"><span data-stu-id="57271-197">20019</span></span></p></td>
<td><p><span data-ttu-id="57271-198">Error</span><span class="sxs-lookup"><span data-stu-id="57271-198">Error</span></span></p></td>
<td><p><span data-ttu-id="57271-199">データ MCU を使用できません</span><span class="sxs-lookup"><span data-stu-id="57271-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="57271-200">データ MCU を使用できません</span><span class="sxs-lookup"><span data-stu-id="57271-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="57271-201">データ MCU が実行されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="57271-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57271-202">20020</span><span class="sxs-lookup"><span data-stu-id="57271-202">20020</span></span></p></td>
<td><p><span data-ttu-id="57271-203">だけ</span><span class="sxs-lookup"><span data-stu-id="57271-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="57271-204">データ MCU に接続できないエラーから復旧した</span><span class="sxs-lookup"><span data-stu-id="57271-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="57271-205">該当なし</span><span class="sxs-lookup"><span data-stu-id="57271-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57271-206">20021</span><span class="sxs-lookup"><span data-stu-id="57271-206">20021</span></span></p></td>
<td><p><span data-ttu-id="57271-207">Error</span><span class="sxs-lookup"><span data-stu-id="57271-207">Error</span></span></p></td>
<td><p><span data-ttu-id="57271-208">IM MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="57271-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="57271-209">IM MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="57271-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="57271-210">IM MCU が実行されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="57271-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57271-211">20022</span><span class="sxs-lookup"><span data-stu-id="57271-211">20022</span></span></p></td>
<td><p><span data-ttu-id="57271-212">Error</span><span class="sxs-lookup"><span data-stu-id="57271-212">Error</span></span></p></td>
<td><p><span data-ttu-id="57271-213">AV MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="57271-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="57271-214">AV MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="57271-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="57271-215">AV MCU が実行されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="57271-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57271-216">20023</span><span class="sxs-lookup"><span data-stu-id="57271-216">20023</span></span></p></td>
<td><p><span data-ttu-id="57271-217">Error</span><span class="sxs-lookup"><span data-stu-id="57271-217">Error</span></span></p></td>
<td><p><span data-ttu-id="57271-218">MCU として参加できません</span><span class="sxs-lookup"><span data-stu-id="57271-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="57271-219">MCU として参加できません</span><span class="sxs-lookup"><span data-stu-id="57271-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="57271-220">MCU が実行されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="57271-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57271-221">20024</span><span class="sxs-lookup"><span data-stu-id="57271-221">20024</span></span></p></td>
<td><p><span data-ttu-id="57271-222">Error</span><span class="sxs-lookup"><span data-stu-id="57271-222">Error</span></span></p></td>
<td><p><span data-ttu-id="57271-223">データ MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="57271-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="57271-224">データ MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="57271-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="57271-225">データ MCU が実行されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="57271-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57271-226">20025</span><span class="sxs-lookup"><span data-stu-id="57271-226">20025</span></span></p></td>
<td><p><span data-ttu-id="57271-227">Error</span><span class="sxs-lookup"><span data-stu-id="57271-227">Error</span></span></p></td>
<td><p><span data-ttu-id="57271-228">Active directory の写真にアクセスできません</span><span class="sxs-lookup"><span data-stu-id="57271-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="57271-229">Active directory への接続が利用できません</span><span class="sxs-lookup"><span data-stu-id="57271-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="57271-230">Active directory への接続が利用可能であることを確認する</span><span class="sxs-lookup"><span data-stu-id="57271-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57271-231">20026</span><span class="sxs-lookup"><span data-stu-id="57271-231">20026</span></span></p></td>
<td><p><span data-ttu-id="57271-232">だけ</span><span class="sxs-lookup"><span data-stu-id="57271-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="57271-233">Active directory の写真にアクセスできないエラーから復旧した</span><span class="sxs-lookup"><span data-stu-id="57271-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="57271-234">該当なし</span><span class="sxs-lookup"><span data-stu-id="57271-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57271-235">20027</span><span class="sxs-lookup"><span data-stu-id="57271-235">20027</span></span></p></td>
<td><p><span data-ttu-id="57271-236">警告</span><span class="sxs-lookup"><span data-stu-id="57271-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="57271-237">逆シリアル化できません</span><span class="sxs-lookup"><span data-stu-id="57271-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="57271-238">逆シリアル化できません</span><span class="sxs-lookup"><span data-stu-id="57271-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="57271-239">問題が引き続き発生する場合は、製品サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="57271-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

