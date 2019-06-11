---
title: 'Lync Server 2013: UCWA イベント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0671b51e5fbd4b5f072676855d9e8f5201b3e04
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="c183a-102">Lync Server での UCWA 2013</span><span class="sxs-lookup"><span data-stu-id="c183a-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c183a-103">_**最終更新日:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="c183a-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="c183a-104">Lync Server 2013 は、Microsoft Exchange に連絡して、モバイルクライアントのプレゼンスを更新するなど、さまざまな目的で、ユニファイドコミュニケーション Web API (UCWA) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c183a-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="c183a-p101">UCWA は、実行動作の記録を、"情報"、"警告"、および "エラー" のイベントの種類として書き込みます。次の表に、UCWA コンポーネントによって書き込まれる可能性があるイベントを示します。</span><span class="sxs-lookup"><span data-stu-id="c183a-p101">UCWA will write records of operational behavior as event types Informational, Warning, and Error. The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c183a-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c183a-107">Event ID</span></span></th>
<th><span data-ttu-id="c183a-108">イベントの種類</span><span class="sxs-lookup"><span data-stu-id="c183a-108">Event Type</span></span></th>
<th><span data-ttu-id="c183a-109">概要</span><span class="sxs-lookup"><span data-stu-id="c183a-109">Summary</span></span></th>
<th><span data-ttu-id="c183a-110">原因と解決策</span><span class="sxs-lookup"><span data-stu-id="c183a-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c183a-111">20001</span><span class="sxs-lookup"><span data-stu-id="c183a-111">20001</span></span></p></td>
<td><p><span data-ttu-id="c183a-112">情報</span><span class="sxs-lookup"><span data-stu-id="c183a-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="c183a-113">UCWA が初期化されました</span><span class="sxs-lookup"><span data-stu-id="c183a-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="c183a-114">N/A</span><span class="sxs-lookup"><span data-stu-id="c183a-114">N/A</span></span></p>
<p><span data-ttu-id="c183a-115">N/A</span><span class="sxs-lookup"><span data-stu-id="c183a-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c183a-116">20002</span><span class="sxs-lookup"><span data-stu-id="c183a-116">20002</span></span></p></td>
<td><p><span data-ttu-id="c183a-117">エラー</span><span class="sxs-lookup"><span data-stu-id="c183a-117">Error</span></span></p></td>
<td><p><span data-ttu-id="c183a-118">初期化中に UCWA で予期しない例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="c183a-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="c183a-119">初期化中に予期しないエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="c183a-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="c183a-120">関連付けられたイベント ログ エントリで例外の詳細を調査し、可能性のある原因を特定します</span><span class="sxs-lookup"><span data-stu-id="c183a-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c183a-121">20003</span><span class="sxs-lookup"><span data-stu-id="c183a-121">20003</span></span></p></td>
<td><p><span data-ttu-id="c183a-122">エラー</span><span class="sxs-lookup"><span data-stu-id="c183a-122">Error</span></span></p></td>
<td><p><span data-ttu-id="c183a-123">UCWA で処理不能な例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="c183a-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="c183a-124">処理不能な例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="c183a-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="c183a-p102">サーバーを再起動します。問題が解決しない場合は、製品サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="c183a-p102">Restart the server. If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c183a-127">20004</span><span class="sxs-lookup"><span data-stu-id="c183a-127">20004</span></span></p></td>
<td><p><span data-ttu-id="c183a-128">エラー</span><span class="sxs-lookup"><span data-stu-id="c183a-128">Error</span></span></p></td>
<td><p><span data-ttu-id="c183a-129">Exchange の HD 写真にアクセスできません</span><span class="sxs-lookup"><span data-stu-id="c183a-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="c183a-130">Exchange への接続を利用できません</span><span class="sxs-lookup"><span data-stu-id="c183a-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="c183a-131">Exchange への接続が利用できることを確認します</span><span class="sxs-lookup"><span data-stu-id="c183a-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c183a-132">20005</span><span class="sxs-lookup"><span data-stu-id="c183a-132">20005</span></span></p></td>
<td><p><span data-ttu-id="c183a-133">情報</span><span class="sxs-lookup"><span data-stu-id="c183a-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="c183a-134">Exchange の HD 写真にアクセスできないエラーから復旧しました</span><span class="sxs-lookup"><span data-stu-id="c183a-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="c183a-135">N/A</span><span class="sxs-lookup"><span data-stu-id="c183a-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c183a-136">20006</span><span class="sxs-lookup"><span data-stu-id="c183a-136">20006</span></span></p></td>
<td><p><span data-ttu-id="c183a-137">エラー</span><span class="sxs-lookup"><span data-stu-id="c183a-137">Error</span></span></p></td>
<td><p><span data-ttu-id="c183a-138">Exchange の連絡先検索にアクセスできません</span><span class="sxs-lookup"><span data-stu-id="c183a-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="c183a-139">Exchange への接続を利用できません</span><span class="sxs-lookup"><span data-stu-id="c183a-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="c183a-140">Exchange への接続が利用できることを確認します</span><span class="sxs-lookup"><span data-stu-id="c183a-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c183a-141">20007</span><span class="sxs-lookup"><span data-stu-id="c183a-141">20007</span></span></p></td>
<td><p><span data-ttu-id="c183a-142">情報</span><span class="sxs-lookup"><span data-stu-id="c183a-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="c183a-143">Exchange の連絡先を検索できないエラーから復旧しました</span><span class="sxs-lookup"><span data-stu-id="c183a-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="c183a-144">N/A</span><span class="sxs-lookup"><span data-stu-id="c183a-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c183a-145">20008</span><span class="sxs-lookup"><span data-stu-id="c183a-145">20008</span></span></p></td>
<td><p><span data-ttu-id="c183a-146">警告</span><span class="sxs-lookup"><span data-stu-id="c183a-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="c183a-147">アプリケーションごとの許容数を超えるプレゼンス サブスクリプションの登録が試行されました</span><span class="sxs-lookup"><span data-stu-id="c183a-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="c183a-148">アプリケーションごとの許容数を超えるプレゼンス サブスクリプションの登録が試行されました</span><span class="sxs-lookup"><span data-stu-id="c183a-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="c183a-149">クライアントに不要なサブスクリプションがないかどうかを確認します</span><span class="sxs-lookup"><span data-stu-id="c183a-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c183a-150">20009</span><span class="sxs-lookup"><span data-stu-id="c183a-150">20009</span></span></p></td>
<td><p><span data-ttu-id="c183a-151">警告</span><span class="sxs-lookup"><span data-stu-id="c183a-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="c183a-152">バッチごとの許容数を超えるプレゼンス サブスクリプションの登録が試行されました</span><span class="sxs-lookup"><span data-stu-id="c183a-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="c183a-153">バッチごとの許容数を超えるプレゼンス サブスクリプションの登録が試行されました</span><span class="sxs-lookup"><span data-stu-id="c183a-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="c183a-154">クライアントに不要なサブスクリプションがないかどうかを確認します</span><span class="sxs-lookup"><span data-stu-id="c183a-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c183a-155">20010</span><span class="sxs-lookup"><span data-stu-id="c183a-155">20010</span></span></p></td>
<td><p><span data-ttu-id="c183a-156">エラー</span><span class="sxs-lookup"><span data-stu-id="c183a-156">Error</span></span></p></td>
<td><p><span data-ttu-id="c183a-157">インバンド データを取得できません</span><span class="sxs-lookup"><span data-stu-id="c183a-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="c183a-158">インバンド データを取得できません</span><span class="sxs-lookup"><span data-stu-id="c183a-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="c183a-159">問題が解決しない場合は、製品サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="c183a-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c183a-160">20011</span><span class="sxs-lookup"><span data-stu-id="c183a-160">20011</span></span></p></td>
<td><p><span data-ttu-id="c183a-161">エラー</span><span class="sxs-lookup"><span data-stu-id="c183a-161">Error</span></span></p></td>
<td><p><span data-ttu-id="c183a-162">プレゼンスを登録できません</span><span class="sxs-lookup"><span data-stu-id="c183a-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="c183a-163">プレゼンスを登録できません</span><span class="sxs-lookup"><span data-stu-id="c183a-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="c183a-164">問題が解決しない場合は、製品サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="c183a-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c183a-165">20012</span><span class="sxs-lookup"><span data-stu-id="c183a-165">20012</span></span></p></td>
<td><p><span data-ttu-id="c183a-166">エラー</span><span class="sxs-lookup"><span data-stu-id="c183a-166">Error</span></span></p></td>
<td><p><span data-ttu-id="c183a-167">エンドポイントの登録に失敗しました</span><span class="sxs-lookup"><span data-stu-id="c183a-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="c183a-168">エンドポイントの登録に失敗しました</span><span class="sxs-lookup"><span data-stu-id="c183a-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="c183a-169">問題が解決しない場合は、製品サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="c183a-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c183a-170">20013</span><span class="sxs-lookup"><span data-stu-id="c183a-170">20013</span></span></p></td>
<td><p><span data-ttu-id="c183a-171">エラー</span><span class="sxs-lookup"><span data-stu-id="c183a-171">Error</span></span></p></td>
<td><p><span data-ttu-id="c183a-172">IM MCU を利用できません</span><span class="sxs-lookup"><span data-stu-id="c183a-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="c183a-173">IM MCU を利用できません</span><span class="sxs-lookup"><span data-stu-id="c183a-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="c183a-174">IM MCU が実行されているかどうかを確認します</span><span class="sxs-lookup"><span data-stu-id="c183a-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c183a-175">20014</span><span class="sxs-lookup"><span data-stu-id="c183a-175">20014</span></span></p></td>
<td><p><span data-ttu-id="c183a-176">情報</span><span class="sxs-lookup"><span data-stu-id="c183a-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="c183a-177">IM MCU に接続できないエラーから復旧しました</span><span class="sxs-lookup"><span data-stu-id="c183a-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="c183a-178">N/A</span><span class="sxs-lookup"><span data-stu-id="c183a-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c183a-179">20015</span><span class="sxs-lookup"><span data-stu-id="c183a-179">20015</span></span></p></td>
<td><p><span data-ttu-id="c183a-180">エラー</span><span class="sxs-lookup"><span data-stu-id="c183a-180">Error</span></span></p></td>
<td><p><span data-ttu-id="c183a-181">AV MCU を利用できません</span><span class="sxs-lookup"><span data-stu-id="c183a-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="c183a-182">AV MCU を利用できません</span><span class="sxs-lookup"><span data-stu-id="c183a-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="c183a-183">AV MCU が実行されているかどうかを確認します</span><span class="sxs-lookup"><span data-stu-id="c183a-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c183a-184">20016</span><span class="sxs-lookup"><span data-stu-id="c183a-184">20016</span></span></p></td>
<td><p><span data-ttu-id="c183a-185">情報</span><span class="sxs-lookup"><span data-stu-id="c183a-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="c183a-186">AV MCU に接続できないエラーから復旧しました</span><span class="sxs-lookup"><span data-stu-id="c183a-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="c183a-187">N/A</span><span class="sxs-lookup"><span data-stu-id="c183a-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c183a-188">20017</span><span class="sxs-lookup"><span data-stu-id="c183a-188">20017</span></span></p></td>
<td><p><span data-ttu-id="c183a-189">エラー</span><span class="sxs-lookup"><span data-stu-id="c183a-189">Error</span></span></p></td>
<td><p><span data-ttu-id="c183a-190">AS MCU を利用できません</span><span class="sxs-lookup"><span data-stu-id="c183a-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="c183a-191">AS MCU を利用できません</span><span class="sxs-lookup"><span data-stu-id="c183a-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="c183a-192">AS MCU が実行されているかどうかを確認します</span><span class="sxs-lookup"><span data-stu-id="c183a-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c183a-193">20018</span><span class="sxs-lookup"><span data-stu-id="c183a-193">20018</span></span></p></td>
<td><p><span data-ttu-id="c183a-194">情報</span><span class="sxs-lookup"><span data-stu-id="c183a-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="c183a-195">AS MCU に接続できないエラーから復旧しました</span><span class="sxs-lookup"><span data-stu-id="c183a-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="c183a-196">該当なし</span><span class="sxs-lookup"><span data-stu-id="c183a-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c183a-197">20019</span><span class="sxs-lookup"><span data-stu-id="c183a-197">20019</span></span></p></td>
<td><p><span data-ttu-id="c183a-198">エラー</span><span class="sxs-lookup"><span data-stu-id="c183a-198">Error</span></span></p></td>
<td><p><span data-ttu-id="c183a-199">データ MCU を利用できません</span><span class="sxs-lookup"><span data-stu-id="c183a-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="c183a-200">データ MCU を利用できません</span><span class="sxs-lookup"><span data-stu-id="c183a-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="c183a-201">データ MCU が実行されていることを確認します</span><span class="sxs-lookup"><span data-stu-id="c183a-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c183a-202">20020</span><span class="sxs-lookup"><span data-stu-id="c183a-202">20020</span></span></p></td>
<td><p><span data-ttu-id="c183a-203">情報</span><span class="sxs-lookup"><span data-stu-id="c183a-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="c183a-204">データ MCU に接続できないエラーから復旧しました</span><span class="sxs-lookup"><span data-stu-id="c183a-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="c183a-205">N/A</span><span class="sxs-lookup"><span data-stu-id="c183a-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c183a-206">20021</span><span class="sxs-lookup"><span data-stu-id="c183a-206">20021</span></span></p></td>
<td><p><span data-ttu-id="c183a-207">エラー</span><span class="sxs-lookup"><span data-stu-id="c183a-207">Error</span></span></p></td>
<td><p><span data-ttu-id="c183a-208">IM MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="c183a-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="c183a-209">IM MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="c183a-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="c183a-210">IM MCU が実行されているかどうかを確認します</span><span class="sxs-lookup"><span data-stu-id="c183a-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c183a-211">20022</span><span class="sxs-lookup"><span data-stu-id="c183a-211">20022</span></span></p></td>
<td><p><span data-ttu-id="c183a-212">エラー</span><span class="sxs-lookup"><span data-stu-id="c183a-212">Error</span></span></p></td>
<td><p><span data-ttu-id="c183a-213">AV MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="c183a-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="c183a-214">AV MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="c183a-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="c183a-215">AV MCU が実行されているかどうかを確認します</span><span class="sxs-lookup"><span data-stu-id="c183a-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c183a-216">20023</span><span class="sxs-lookup"><span data-stu-id="c183a-216">20023</span></span></p></td>
<td><p><span data-ttu-id="c183a-217">エラー</span><span class="sxs-lookup"><span data-stu-id="c183a-217">Error</span></span></p></td>
<td><p><span data-ttu-id="c183a-218">AS MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="c183a-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="c183a-219">AS MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="c183a-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="c183a-220">AS MCU が実行されているかどうかを確認します</span><span class="sxs-lookup"><span data-stu-id="c183a-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c183a-221">20024</span><span class="sxs-lookup"><span data-stu-id="c183a-221">20024</span></span></p></td>
<td><p><span data-ttu-id="c183a-222">エラー</span><span class="sxs-lookup"><span data-stu-id="c183a-222">Error</span></span></p></td>
<td><p><span data-ttu-id="c183a-223">データ MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="c183a-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="c183a-224">データ MCU に参加できません</span><span class="sxs-lookup"><span data-stu-id="c183a-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="c183a-225">データ MCU が実行されていることを確認します</span><span class="sxs-lookup"><span data-stu-id="c183a-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c183a-226">20025</span><span class="sxs-lookup"><span data-stu-id="c183a-226">20025</span></span></p></td>
<td><p><span data-ttu-id="c183a-227">エラー</span><span class="sxs-lookup"><span data-stu-id="c183a-227">Error</span></span></p></td>
<td><p><span data-ttu-id="c183a-228">Active Directory の写真にアクセスできません</span><span class="sxs-lookup"><span data-stu-id="c183a-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="c183a-229">Active Directory への接続を利用できません</span><span class="sxs-lookup"><span data-stu-id="c183a-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="c183a-230">Active Directory への接続が利用できることを確認します</span><span class="sxs-lookup"><span data-stu-id="c183a-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c183a-231">20026</span><span class="sxs-lookup"><span data-stu-id="c183a-231">20026</span></span></p></td>
<td><p><span data-ttu-id="c183a-232">情報</span><span class="sxs-lookup"><span data-stu-id="c183a-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="c183a-233">Active Directory の写真にアクセスできないエラーから復旧しました</span><span class="sxs-lookup"><span data-stu-id="c183a-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="c183a-234">該当なし</span><span class="sxs-lookup"><span data-stu-id="c183a-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c183a-235">20027</span><span class="sxs-lookup"><span data-stu-id="c183a-235">20027</span></span></p></td>
<td><p><span data-ttu-id="c183a-236">警告</span><span class="sxs-lookup"><span data-stu-id="c183a-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="c183a-237">逆シリアル化できません</span><span class="sxs-lookup"><span data-stu-id="c183a-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="c183a-238">逆シリアル化できません</span><span class="sxs-lookup"><span data-stu-id="c183a-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="c183a-239">問題が解決しない場合は、製品サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="c183a-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

