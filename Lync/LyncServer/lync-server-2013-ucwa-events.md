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
ms.openlocfilehash: b5063aca74fe3454569a2b2309be584a4ca11d13
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744857"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="0c5a1-102">Lync Server での UCWA 2013</span><span class="sxs-lookup"><span data-stu-id="0c5a1-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c5a1-103">_**最終更新日:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="0c5a1-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="0c5a1-104">Lync Server 2013 は、Microsoft Exchange に連絡して、モバイルクライアントのプレゼンスを更新するなど、さまざまな目的で、ユニファイドコミュニケーション Web API (UCWA) を使用します。</span><span class="sxs-lookup"><span data-stu-id="0c5a1-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="0c5a1-p101">UCWA は、実行動作の記録を、"情報"、"警告"、および "エラー" のイベントの種類として書き込みます。次の表に、UCWA コンポーネントによって書き込まれる可能性があるイベントを示します。</span><span class="sxs-lookup"><span data-stu-id="0c5a1-p101">UCWA will write records of operational behavior as event types Informational, Warning, and Error. The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c5a1-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0c5a1-107">Event ID</span></span></th>
<th><span data-ttu-id="0c5a1-108">イベントの種類</span><span class="sxs-lookup"><span data-stu-id="0c5a1-108">Event Type</span></span></th>
<th><span data-ttu-id="0c5a1-109">概要</span><span class="sxs-lookup"><span data-stu-id="0c5a1-109">Summary</span></span></th>
<th><span data-ttu-id="0c5a1-110">原因と解決策</span><span class="sxs-lookup"><span data-stu-id="0c5a1-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c5a1-111">20001</span><span class="sxs-lookup"><span data-stu-id="0c5a1-111">20001</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-112">情報</span><span class="sxs-lookup"><span data-stu-id="0c5a1-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-113">UCWA が初期化されました</span><span class="sxs-lookup"><span data-stu-id="0c5a1-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-114">該当なし</span><span class="sxs-lookup"><span data-stu-id="0c5a1-114">N/A</span></span></p>
<p><span data-ttu-id="0c5a1-115">該当なし</span><span class="sxs-lookup"><span data-stu-id="0c5a1-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5a1-116">20002</span><span class="sxs-lookup"><span data-stu-id="0c5a1-116">20002</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-117">エラー</span><span class="sxs-lookup"><span data-stu-id="0c5a1-117">Error</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-118">初期化中に UCWA で予期しない例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="0c5a1-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-119">初期化中に予期しないエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="0c5a1-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="0c5a1-120">関連付けられたイベント ログ エントリで例外の詳細を調査し、可能性のある原因を特定します</span><span class="sxs-lookup"><span data-stu-id="0c5a1-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5a1-121">20003</span><span class="sxs-lookup"><span data-stu-id="0c5a1-121">20003</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-122">エラー</span><span class="sxs-lookup"><span data-stu-id="0c5a1-122">Error</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-123">UCWA で処理不能な例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="0c5a1-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-124">処理不能な例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="0c5a1-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="0c5a1-p102">サーバーを再起動します。問題が解決しない場合は、製品サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="0c5a1-p102">Restart the server. If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5a1-127">20004</span><span class="sxs-lookup"><span data-stu-id="0c5a1-127">20004</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-128">エラー</span><span class="sxs-lookup"><span data-stu-id="0c5a1-128">Error</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-129">Exchange の HD 写真にアクセスできません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-130">Exchange への接続を利用できません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="0c5a1-131">Exchange への接続が利用できることを確認します</span><span class="sxs-lookup"><span data-stu-id="0c5a1-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5a1-132">20005</span><span class="sxs-lookup"><span data-stu-id="0c5a1-132">20005</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-133">情報</span><span class="sxs-lookup"><span data-stu-id="0c5a1-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-134">Exchange の HD 写真にアクセスできないエラーから復旧しました</span><span class="sxs-lookup"><span data-stu-id="0c5a1-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-135">該当なし</span><span class="sxs-lookup"><span data-stu-id="0c5a1-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5a1-136">20006</span><span class="sxs-lookup"><span data-stu-id="0c5a1-136">20006</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-137">エラー</span><span class="sxs-lookup"><span data-stu-id="0c5a1-137">Error</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-138">Exchange の連絡先検索にアクセスできません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-139">Exchange への接続を利用できません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="0c5a1-140">Exchange への接続が利用できることを確認します</span><span class="sxs-lookup"><span data-stu-id="0c5a1-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5a1-141">20007</span><span class="sxs-lookup"><span data-stu-id="0c5a1-141">20007</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-142">情報</span><span class="sxs-lookup"><span data-stu-id="0c5a1-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-143">Exchange の連絡先を検索できないエラーから復旧しました</span><span class="sxs-lookup"><span data-stu-id="0c5a1-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-144">該当なし</span><span class="sxs-lookup"><span data-stu-id="0c5a1-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5a1-145">20008</span><span class="sxs-lookup"><span data-stu-id="0c5a1-145">20008</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-146">警告</span><span class="sxs-lookup"><span data-stu-id="0c5a1-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-147">アプリケーションごとの許容数を超えるプレゼンス サブスクリプションの登録が試行されました</span><span class="sxs-lookup"><span data-stu-id="0c5a1-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-148">アプリケーションごとの許容数を超えるプレゼンス サブスクリプションの登録が試行されました</span><span class="sxs-lookup"><span data-stu-id="0c5a1-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="0c5a1-149">クライアントに不要なサブスクリプションがないかどうかを確認します</span><span class="sxs-lookup"><span data-stu-id="0c5a1-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5a1-150">20009</span><span class="sxs-lookup"><span data-stu-id="0c5a1-150">20009</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-151">警告</span><span class="sxs-lookup"><span data-stu-id="0c5a1-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-152">バッチごとの許容数を超えるプレゼンス サブスクリプションの登録が試行されました</span><span class="sxs-lookup"><span data-stu-id="0c5a1-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-153">バッチごとの許容数を超えるプレゼンス サブスクリプションの登録が試行されました</span><span class="sxs-lookup"><span data-stu-id="0c5a1-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="0c5a1-154">クライアントに不要なサブスクリプションがないかどうかを確認します</span><span class="sxs-lookup"><span data-stu-id="0c5a1-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5a1-155">20010</span><span class="sxs-lookup"><span data-stu-id="0c5a1-155">20010</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-156">エラー</span><span class="sxs-lookup"><span data-stu-id="0c5a1-156">Error</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-157">インバンド データを取得できません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-158">インバンド データを取得できません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="0c5a1-159">問題が解決しない場合は、製品サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="0c5a1-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5a1-160">20011</span><span class="sxs-lookup"><span data-stu-id="0c5a1-160">20011</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-161">エラー</span><span class="sxs-lookup"><span data-stu-id="0c5a1-161">Error</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-162">プレゼンスを登録できません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-163">プレゼンスを登録できません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="0c5a1-164">問題が解決しない場合は、製品サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="0c5a1-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5a1-165">20012</span><span class="sxs-lookup"><span data-stu-id="0c5a1-165">20012</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-166">エラー</span><span class="sxs-lookup"><span data-stu-id="0c5a1-166">Error</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-167">エンドポイントの登録に失敗しました</span><span class="sxs-lookup"><span data-stu-id="0c5a1-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-168">エンドポイントの登録に失敗しました</span><span class="sxs-lookup"><span data-stu-id="0c5a1-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="0c5a1-169">問題が解決しない場合は、製品サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="0c5a1-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5a1-170">20013</span><span class="sxs-lookup"><span data-stu-id="0c5a1-170">20013</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-171">エラー</span><span class="sxs-lookup"><span data-stu-id="0c5a1-171">Error</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-172">IM MCU を利用できません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-173">IM MCU を利用できません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="0c5a1-174">IM MCU が実行されているかどうかを確認します</span><span class="sxs-lookup"><span data-stu-id="0c5a1-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5a1-175">20014</span><span class="sxs-lookup"><span data-stu-id="0c5a1-175">20014</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-176">情報</span><span class="sxs-lookup"><span data-stu-id="0c5a1-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-177">IM MCU に接続できないエラーから復旧しました</span><span class="sxs-lookup"><span data-stu-id="0c5a1-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-178">該当なし</span><span class="sxs-lookup"><span data-stu-id="0c5a1-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5a1-179">20015</span><span class="sxs-lookup"><span data-stu-id="0c5a1-179">20015</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-180">エラー</span><span class="sxs-lookup"><span data-stu-id="0c5a1-180">Error</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-181">AV MCU を利用できません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-182">AV MCU を利用できません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="0c5a1-183">AV MCU が実行されているかどうかを確認します</span><span class="sxs-lookup"><span data-stu-id="0c5a1-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5a1-184">20016</span><span class="sxs-lookup"><span data-stu-id="0c5a1-184">20016</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-185">情報</span><span class="sxs-lookup"><span data-stu-id="0c5a1-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-186">AV MCU に接続できないエラーから復旧しました</span><span class="sxs-lookup"><span data-stu-id="0c5a1-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-187">該当なし</span><span class="sxs-lookup"><span data-stu-id="0c5a1-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5a1-188">20017</span><span class="sxs-lookup"><span data-stu-id="0c5a1-188">20017</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-189">エラー</span><span class="sxs-lookup"><span data-stu-id="0c5a1-189">Error</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-190">AS MCU を利用できません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-191">AS MCU を利用できません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="0c5a1-192">AS MCU が実行されているかどうかを確認します</span><span class="sxs-lookup"><span data-stu-id="0c5a1-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5a1-193">20018</span><span class="sxs-lookup"><span data-stu-id="0c5a1-193">20018</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-194">情報</span><span class="sxs-lookup"><span data-stu-id="0c5a1-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-195">AS MCU に接続できないエラーから復旧しました</span><span class="sxs-lookup"><span data-stu-id="0c5a1-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-196">該当なし</span><span class="sxs-lookup"><span data-stu-id="0c5a1-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5a1-197">20019</span><span class="sxs-lookup"><span data-stu-id="0c5a1-197">20019</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-198">エラー</span><span class="sxs-lookup"><span data-stu-id="0c5a1-198">Error</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-199">データ MCU を利用できません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-200">データ MCU を利用できません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="0c5a1-201">データ MCU が実行されていることを確認します</span><span class="sxs-lookup"><span data-stu-id="0c5a1-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5a1-202">20020</span><span class="sxs-lookup"><span data-stu-id="0c5a1-202">20020</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-203">情報</span><span class="sxs-lookup"><span data-stu-id="0c5a1-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-204">データ MCU に接続できないエラーから復旧しました</span><span class="sxs-lookup"><span data-stu-id="0c5a1-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-205">該当なし</span><span class="sxs-lookup"><span data-stu-id="0c5a1-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5a1-206">20021</span><span class="sxs-lookup"><span data-stu-id="0c5a1-206">20021</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-207">エラー</span><span class="sxs-lookup"><span data-stu-id="0c5a1-207">Error</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-208">IM MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-209">IM MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="0c5a1-210">IM MCU が実行されているかどうかを確認します</span><span class="sxs-lookup"><span data-stu-id="0c5a1-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5a1-211">20022</span><span class="sxs-lookup"><span data-stu-id="0c5a1-211">20022</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-212">エラー</span><span class="sxs-lookup"><span data-stu-id="0c5a1-212">Error</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-213">AV MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-214">AV MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="0c5a1-215">AV MCU が実行されているかどうかを確認します</span><span class="sxs-lookup"><span data-stu-id="0c5a1-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5a1-216">20023</span><span class="sxs-lookup"><span data-stu-id="0c5a1-216">20023</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-217">エラー</span><span class="sxs-lookup"><span data-stu-id="0c5a1-217">Error</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-218">AS MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-219">AS MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="0c5a1-220">AS MCU が実行されているかどうかを確認します</span><span class="sxs-lookup"><span data-stu-id="0c5a1-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5a1-221">20024</span><span class="sxs-lookup"><span data-stu-id="0c5a1-221">20024</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-222">エラー</span><span class="sxs-lookup"><span data-stu-id="0c5a1-222">Error</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-223">データ MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-224">データ MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="0c5a1-225">データ MCU が実行されていることを確認します</span><span class="sxs-lookup"><span data-stu-id="0c5a1-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5a1-226">20025</span><span class="sxs-lookup"><span data-stu-id="0c5a1-226">20025</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-227">エラー</span><span class="sxs-lookup"><span data-stu-id="0c5a1-227">Error</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-228">Active Directory の写真にアクセスできません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-229">Active Directory への接続を利用できません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="0c5a1-230">Active Directory への接続が利用できることを確認します</span><span class="sxs-lookup"><span data-stu-id="0c5a1-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5a1-231">20026</span><span class="sxs-lookup"><span data-stu-id="0c5a1-231">20026</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-232">情報</span><span class="sxs-lookup"><span data-stu-id="0c5a1-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-233">Active Directory の写真にアクセスできないエラーから復旧しました</span><span class="sxs-lookup"><span data-stu-id="0c5a1-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-234">該当なし</span><span class="sxs-lookup"><span data-stu-id="0c5a1-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5a1-235">20027</span><span class="sxs-lookup"><span data-stu-id="0c5a1-235">20027</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-236">警告</span><span class="sxs-lookup"><span data-stu-id="0c5a1-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-237">逆シリアル化できません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="0c5a1-238">逆シリアル化できません</span><span class="sxs-lookup"><span data-stu-id="0c5a1-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="0c5a1-239">問題が解決しない場合は、製品サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="0c5a1-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

