---
title: 'Lync Server 2013: モビリティパフォーマンスカウンター'
description: 'Lync Server 2013: モビリティパフォーマンスカウンター。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 922288f6c026f088d651dc61afdcb6ba04fed30a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550533"
---
# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="97d22-103">Lync Server 2013 のモビリティパフォーマンスカウンター</span><span class="sxs-lookup"><span data-stu-id="97d22-103">Mobility performance counters in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97d22-104">_**トピックの最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="97d22-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="97d22-105">次の表に、統合コミュニケーション Web API (UCWA) および Lync Server 2013 Mcx Mobility Service を実行しているサーバーの監視に使用できるパフォーマンスカウンターの名前と説明を示します。</span><span class="sxs-lookup"><span data-stu-id="97d22-105">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="97d22-106">UCWA テーブル内のカウンターのカテゴリ名は、 **LS: WEB – UCWA**です。</span><span class="sxs-lookup"><span data-stu-id="97d22-106">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="97d22-107">Mcx Mobility Service テーブル内のカウンターのカテゴリ名は、 **LS: WEB-Mobile Communication service**です。</span><span class="sxs-lookup"><span data-stu-id="97d22-107">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="97d22-108">UCWA のパフォーマンスカウンター</span><span class="sxs-lookup"><span data-stu-id="97d22-108">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97d22-109">カウンター</span><span class="sxs-lookup"><span data-stu-id="97d22-109">Counter</span></span></th>
<th><span data-ttu-id="97d22-110">説明</span><span class="sxs-lookup"><span data-stu-id="97d22-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97d22-111">アクティブなアプリケーション数</span><span class="sxs-lookup"><span data-stu-id="97d22-111">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="97d22-112">現在のアプリケーション数</span><span class="sxs-lookup"><span data-stu-id="97d22-112">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-113">アクティブなアプリケーション共有のモダリティ数</span><span class="sxs-lookup"><span data-stu-id="97d22-113">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="97d22-114">アプリケーション共有モダリティの現在の数</span><span class="sxs-lookup"><span data-stu-id="97d22-114">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-115">アクティブな音声モダリティ数</span><span class="sxs-lookup"><span data-stu-id="97d22-115">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="97d22-116">現在の音声モダリティ数</span><span class="sxs-lookup"><span data-stu-id="97d22-116">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-117">アクティブデータコラボレーションのモダリティ数</span><span class="sxs-lookup"><span data-stu-id="97d22-117">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="97d22-118">現在のデータコラボレーションモダリティ数</span><span class="sxs-lookup"><span data-stu-id="97d22-118">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-119">Active Directory の写真取得待機時間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="97d22-119">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="97d22-120">このカウンターは、active directory から写真を取得する平均時間 (ミリ秒) を示します。</span><span class="sxs-lookup"><span data-stu-id="97d22-120">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-121">アクティブなメッセージングモダリティ数</span><span class="sxs-lookup"><span data-stu-id="97d22-121">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="97d22-122">現在のメッセージングモダリティ数</span><span class="sxs-lookup"><span data-stu-id="97d22-122">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-123">アクティブなパノラマビデオモダリティ数</span><span class="sxs-lookup"><span data-stu-id="97d22-123">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="97d22-124">現在のパノラマビデオモダリティ数</span><span class="sxs-lookup"><span data-stu-id="97d22-124">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-125">アクティブな保留中の取得数</span><span class="sxs-lookup"><span data-stu-id="97d22-125">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="97d22-126">現在アクティブな保留中の数を取得します。サーバーへの長時間保持接続</span><span class="sxs-lookup"><span data-stu-id="97d22-126">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-127">アクティブなセッション数</span><span class="sxs-lookup"><span data-stu-id="97d22-127">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="97d22-128">アプリケーションごとに UCWA に登録されている現在のエンドポイント数と合計</span><span class="sxs-lookup"><span data-stu-id="97d22-128">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-129">アクティブなユーザーインスタンス数</span><span class="sxs-lookup"><span data-stu-id="97d22-129">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="97d22-130">ユーザーインスタンスの現在の数</span><span class="sxs-lookup"><span data-stu-id="97d22-130">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-131">アプリケーションを使用しないアクティブなユーザーインスタンス</span><span class="sxs-lookup"><span data-stu-id="97d22-131">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="97d22-132">アプリケーションが適用されていない現在のユーザーインスタンス数</span><span class="sxs-lookup"><span data-stu-id="97d22-132">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-133">アクティブなビデオモダリティ数</span><span class="sxs-lookup"><span data-stu-id="97d22-133">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="97d22-134">現在のビデオモダリティ数</span><span class="sxs-lookup"><span data-stu-id="97d22-134">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-135">受信したアプリケーション作成要求の数/秒</span><span class="sxs-lookup"><span data-stu-id="97d22-135">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="97d22-136">受信したアプリケーション作成要求の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="97d22-136">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-137">MCU の参加に失敗した場合</span><span class="sxs-lookup"><span data-stu-id="97d22-137">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="97d22-138">AS MCU 参加エラーの数</span><span class="sxs-lookup"><span data-stu-id="97d22-138">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-139">AV MCU 参加エラー</span><span class="sxs-lookup"><span data-stu-id="97d22-139">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="97d22-140">AV MCU の参加に失敗した回数</span><span class="sxs-lookup"><span data-stu-id="97d22-140">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-141">アプリケーションの平均起動時間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="97d22-141">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="97d22-142">アプリケーションの平均起動時間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="97d22-142">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-143">セッションの平均有効期間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="97d22-143">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="97d22-144">セッションの平均有効期間 (ミリ秒単位)</span><span class="sxs-lookup"><span data-stu-id="97d22-144">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-145">データ MCU の参加エラー</span><span class="sxs-lookup"><span data-stu-id="97d22-145">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="97d22-146">データ MCU の参加に失敗した回数</span><span class="sxs-lookup"><span data-stu-id="97d22-146">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-147">Exchange の連絡先検索の待機時間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="97d22-147">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="97d22-148">このカウンターは、Exchange の連絡先を検索する平均時間 (ミリ秒) を示します。</span><span class="sxs-lookup"><span data-stu-id="97d22-148">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-149">Exchange HD Photo Get 待機時間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="97d22-149">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="97d22-150">このカウンターは、Exchange から写真を取得する平均時間 (ミリ秒) を示します。</span><span class="sxs-lookup"><span data-stu-id="97d22-150">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-151">HTTP 4xx 応答/秒</span><span class="sxs-lookup"><span data-stu-id="97d22-151">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="97d22-152">HTTP 4xx コードでの応答の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="97d22-152">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-153">HTTP 5xx 応答/秒</span><span class="sxs-lookup"><span data-stu-id="97d22-153">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="97d22-154">HTTP 5xx コードでの応答の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="97d22-154">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-155">IM MCU の参加エラー</span><span class="sxs-lookup"><span data-stu-id="97d22-155">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="97d22-156">IM MCU の参加に失敗した回数</span><span class="sxs-lookup"><span data-stu-id="97d22-156">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-157">Active Directory の写真の Get エラー数</span><span class="sxs-lookup"><span data-stu-id="97d22-157">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="97d22-158">Active Directory からの写真の取得に失敗した回数の合計</span><span class="sxs-lookup"><span data-stu-id="97d22-158">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-159">連絡先検索エラー数</span><span class="sxs-lookup"><span data-stu-id="97d22-159">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="97d22-160">Exchange での連絡先の検索に失敗した回数の合計</span><span class="sxs-lookup"><span data-stu-id="97d22-160">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-161">逆シリアル化エラーの数</span><span class="sxs-lookup"><span data-stu-id="97d22-161">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="97d22-162">逆シリアル化エラーの合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-162">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-163">HD Photo Get エラーの数</span><span class="sxs-lookup"><span data-stu-id="97d22-163">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="97d22-164">Exchange からの HD 写真の取得に失敗した回数の合計</span><span class="sxs-lookup"><span data-stu-id="97d22-164">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-165">アプリケーションごとのサブスクリプションの最大数</span><span class="sxs-lookup"><span data-stu-id="97d22-165">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="97d22-166">アプリケーションごとに許容される最大数を超えるサブスクリプション要求の数</span><span class="sxs-lookup"><span data-stu-id="97d22-166">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-167">バッチごとの最大サブスクリプション数</span><span class="sxs-lookup"><span data-stu-id="97d22-167">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="97d22-168">バッチごとに許容される最大数を超えるサブスクリプション要求の数</span><span class="sxs-lookup"><span data-stu-id="97d22-168">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-169">プレゼンスサブスクリプションエラー</span><span class="sxs-lookup"><span data-stu-id="97d22-169">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="97d22-170">プレゼンスをサブスクライブしているエラーの数</span><span class="sxs-lookup"><span data-stu-id="97d22-170">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-171">エンドポイントエラーの登録</span><span class="sxs-lookup"><span data-stu-id="97d22-171">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="97d22-172">エンドポイントの登録に失敗した回数</span><span class="sxs-lookup"><span data-stu-id="97d22-172">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-173">Received/Second 要求数</span><span class="sxs-lookup"><span data-stu-id="97d22-173">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="97d22-174">受信した要求の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="97d22-174">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-175">成功した要求数/秒</span><span class="sxs-lookup"><span data-stu-id="97d22-175">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="97d22-176">成功した要求の1秒あたりの数 (HTTP 2xx/3xx 応答コード)</span><span class="sxs-lookup"><span data-stu-id="97d22-176">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-177">正常に作成したアプリケーション要求/秒</span><span class="sxs-lookup"><span data-stu-id="97d22-177">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="97d22-178">成功したアプリケーション作成要求の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="97d22-178">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-179">タイムアウト保留中の取得数</span><span class="sxs-lookup"><span data-stu-id="97d22-179">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="97d22-180">タイムアウトした保留中の取得の数</span><span class="sxs-lookup"><span data-stu-id="97d22-180">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-181">受信したアプリケーション作成要求の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-181">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="97d22-182">サービスの開始以降に受信されたアプリケーション作成要求の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-182">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-183">HTTP 4xx 応答の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-183">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="97d22-184">HTTP 4xx 応答の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-184">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-185">HTTP 5xx 応答の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-185">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="97d22-186">HTTP 5xx 応答の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-186">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-187">コマンドチャネルで受信した要求の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-187">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="97d22-188">コマンドチャネルで受信した要求の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-188">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-189">成功した要求の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-189">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="97d22-190">成功した要求の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-190">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-191">開始されたセッションの合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-191">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="97d22-192">サービスの開始以降に開始されたセッションの合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-192">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-193">アイドルタイムアウトが原因で終了したセッションの合計</span><span class="sxs-lookup"><span data-stu-id="97d22-193">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="97d22-194">ユーザーのアイドルタイムアウトが原因で終了したセッションの合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-194">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-195">調整されるアプリケーションの合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-195">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="97d22-196">調整されたアプリケーションの数</span><span class="sxs-lookup"><span data-stu-id="97d22-196">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="97d22-197">Mcx Mobility Service のパフォーマンスカウンター</span><span class="sxs-lookup"><span data-stu-id="97d22-197">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97d22-198">カウンター</span><span class="sxs-lookup"><span data-stu-id="97d22-198">Counter</span></span></th>
<th><span data-ttu-id="97d22-199">説明</span><span class="sxs-lookup"><span data-stu-id="97d22-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97d22-200">セッションの平均有効期間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="97d22-200">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="97d22-201">セッションの平均有効期間 (ミリ秒単位)</span><span class="sxs-lookup"><span data-stu-id="97d22-201">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-202">現在のプッシュ通知サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="97d22-202">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="97d22-203">プッシュ通知サブスクリプションの現在の数。</span><span class="sxs-lookup"><span data-stu-id="97d22-203">The current number of push notification subscriptions.</span></span> <span data-ttu-id="97d22-204">この数値は、現在アクティブなセッション数と組み合わせて、Windows Mobile または iPhone デバイス用に登録されている現在アクティブなセッションのサブセットを表します。</span><span class="sxs-lookup"><span data-stu-id="97d22-204">This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-205">現在アクティブなネットワークのタイムアウトポーリング数</span><span class="sxs-lookup"><span data-stu-id="97d22-205">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="97d22-206">タイムアウトしたネットワークポーリングの数</span><span class="sxs-lookup"><span data-stu-id="97d22-206">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-207">現在アクティブなポーリング数</span><span class="sxs-lookup"><span data-stu-id="97d22-207">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="97d22-208">現在アクティブなポーリングの数 (長時間保持されているサーバーへの接続)</span><span class="sxs-lookup"><span data-stu-id="97d22-208">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-209">現在アクティブなセッション数</span><span class="sxs-lookup"><span data-stu-id="97d22-209">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="97d22-210">Mobility Service に登録されている現在のエンドポイント数</span><span class="sxs-lookup"><span data-stu-id="97d22-210">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-211">アクティブなプレゼンスサブスクリプションのある現在アクティブなセッション数</span><span class="sxs-lookup"><span data-stu-id="97d22-211">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="97d22-212">アクティブなプレゼンスサブスクリプションのある現在アクティブなセッションの数</span><span class="sxs-lookup"><span data-stu-id="97d22-212">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-213">プッシュ通知要求が失敗した/秒</span><span class="sxs-lookup"><span data-stu-id="97d22-213">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="97d22-214">失敗したプッシュ通知の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="97d22-214">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-215">1秒あたりに成功したプッシュ通知要求</span><span class="sxs-lookup"><span data-stu-id="97d22-215">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="97d22-216">成功したプッシュ通知の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="97d22-216">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-217">プッシュ通知要求の調整/秒</span><span class="sxs-lookup"><span data-stu-id="97d22-217">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="97d22-218">調整されたプッシュ通知の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="97d22-218">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-219">プッシュ通知要求/秒</span><span class="sxs-lookup"><span data-stu-id="97d22-219">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="97d22-220">送信されたプッシュ通知の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="97d22-220">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-221">失敗した要求数/秒</span><span class="sxs-lookup"><span data-stu-id="97d22-221">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="97d22-222">失敗した要求の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="97d22-222">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-223">Received/Second 要求数</span><span class="sxs-lookup"><span data-stu-id="97d22-223">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="97d22-224">受信した要求の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="97d22-224">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-225">拒否された要求数/秒</span><span class="sxs-lookup"><span data-stu-id="97d22-225">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="97d22-226">拒否された要求の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="97d22-226">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-227">成功した要求数/秒</span><span class="sxs-lookup"><span data-stu-id="97d22-227">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="97d22-228">成功した要求の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="97d22-228">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-229">正常開始セッション要求数/秒</span><span class="sxs-lookup"><span data-stu-id="97d22-229">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="97d22-230">成功した場所の取得要求の1秒あたりの数。</span><span class="sxs-lookup"><span data-stu-id="97d22-230">The per second rate of successful Get Location requests.</span></span> <span data-ttu-id="97d22-231">セッションを開始する要求は、サーバー上で最も CPU を消費します。</span><span class="sxs-lookup"><span data-stu-id="97d22-231">Requests to initiate a session consume the most CPU on the server.</span></span> <span data-ttu-id="97d22-232">サポートされているピーク負荷は 12/秒です。</span><span class="sxs-lookup"><span data-stu-id="97d22-232">Peak supported load is 12/second.</span></span> <span data-ttu-id="97d22-233">持続性は、サーバー上の他の負荷に依存します。</span><span class="sxs-lookup"><span data-stu-id="97d22-233">Sustainability depends on other loads on the server.</span></span> <span data-ttu-id="97d22-234">通常、セッションを開始することは、長期間にわたるサインアウトされたユーザーに対してサインインすることを意味します。</span><span class="sxs-lookup"><span data-stu-id="97d22-234">Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-235">着信音声通話の拒否合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-235">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="97d22-236">拒否された着信音声通話の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-236">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-237">失敗した着信音声通話の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-237">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="97d22-238">失敗した着信音声通話の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-238">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-239">失敗した発信音声通話の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-239">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="97d22-240">失敗した発信音声通話の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-240">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-241">ユーザーが終了したセッションの合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-241">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="97d22-242">ユーザーが終了したセッションの合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-242">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-243">プッシュ通知要求の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-243">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="97d22-244">プッシュ通知要求の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-244">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-245">失敗したプッシュ通知要求の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-245">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="97d22-246">失敗したプッシュ通知要求の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-246">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-247">成功したプッシュ通知要求の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-247">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="97d22-248">成功したプッシュ通知要求の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-248">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-249">調整されるプッシュ通知要求の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-249">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="97d22-250">調整されたプッシュ通知要求の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-250">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-251">失敗した要求の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-251">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="97d22-252">失敗した要求の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-252">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-253">コマンドチャネルで受信した要求の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-253">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="97d22-254">コマンドチャネルで受信した要求の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-254">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-255">拒否された要求の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-255">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="97d22-256">拒否された要求の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-256">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-257">成功した要求の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-257">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="97d22-258">Mobility Service に対して成功した要求の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-258">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-259">セッションが開始した合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-259">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="97d22-260">Mobility Service の開始以降に開始されたセッションの合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-260">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-261">ユーザーのアイドルタイムアウトが原因で終了したセッションの合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-261">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="97d22-262">ユーザーのアイドルタイムアウトが原因で終了したセッションの合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-262">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d22-263">成功した着信音声通話の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-263">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="97d22-264">成功した着信音声通話の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-264">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d22-265">成功した発信音声通話の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-265">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="97d22-266">成功した発信音声通話の合計数</span><span class="sxs-lookup"><span data-stu-id="97d22-266">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

