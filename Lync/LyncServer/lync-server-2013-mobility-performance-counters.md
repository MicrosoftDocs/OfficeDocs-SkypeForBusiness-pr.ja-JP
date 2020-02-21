---
title: 'Lync Server 2013: モビリティパフォーマンスカウンター'
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
ms.openlocfilehash: a0f0d9170b4526c443b88c9227af8f2c55dae4b8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="44e03-102">Lync Server 2013 のモビリティパフォーマンスカウンター</span><span class="sxs-lookup"><span data-stu-id="44e03-102">Mobility performance counters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44e03-103">_**トピックの最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="44e03-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="44e03-104">次の表に、統合コミュニケーション Web API (UCWA) および Lync Server 2013 Mcx Mobility Service を実行しているサーバーの監視に使用できるパフォーマンスカウンターの名前と説明を示します。</span><span class="sxs-lookup"><span data-stu-id="44e03-104">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="44e03-105">UCWA テーブル内のカウンターのカテゴリ名は、 **LS: WEB – UCWA**です。</span><span class="sxs-lookup"><span data-stu-id="44e03-105">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="44e03-106">Mcx Mobility Service テーブル内のカウンターのカテゴリ名は、 **LS: WEB-Mobile Communication service**です。</span><span class="sxs-lookup"><span data-stu-id="44e03-106">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="44e03-107">UCWA のパフォーマンスカウンター</span><span class="sxs-lookup"><span data-stu-id="44e03-107">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44e03-108">カウンター</span><span class="sxs-lookup"><span data-stu-id="44e03-108">Counter</span></span></th>
<th><span data-ttu-id="44e03-109">説明</span><span class="sxs-lookup"><span data-stu-id="44e03-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44e03-110">アクティブなアプリケーション数</span><span class="sxs-lookup"><span data-stu-id="44e03-110">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="44e03-111">現在のアプリケーション数</span><span class="sxs-lookup"><span data-stu-id="44e03-111">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-112">アクティブなアプリケーション共有のモダリティ数</span><span class="sxs-lookup"><span data-stu-id="44e03-112">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="44e03-113">アプリケーション共有モダリティの現在の数</span><span class="sxs-lookup"><span data-stu-id="44e03-113">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-114">アクティブな音声モダリティ数</span><span class="sxs-lookup"><span data-stu-id="44e03-114">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="44e03-115">現在の音声モダリティ数</span><span class="sxs-lookup"><span data-stu-id="44e03-115">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-116">アクティブデータコラボレーションのモダリティ数</span><span class="sxs-lookup"><span data-stu-id="44e03-116">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="44e03-117">現在のデータコラボレーションモダリティ数</span><span class="sxs-lookup"><span data-stu-id="44e03-117">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-118">Active Directory の写真取得待機時間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="44e03-118">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="44e03-119">このカウンターは、active directory から写真を取得する平均時間 (ミリ秒) を示します。</span><span class="sxs-lookup"><span data-stu-id="44e03-119">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-120">アクティブなメッセージングモダリティ数</span><span class="sxs-lookup"><span data-stu-id="44e03-120">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="44e03-121">現在のメッセージングモダリティ数</span><span class="sxs-lookup"><span data-stu-id="44e03-121">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-122">アクティブなパノラマビデオモダリティ数</span><span class="sxs-lookup"><span data-stu-id="44e03-122">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="44e03-123">現在のパノラマビデオモダリティ数</span><span class="sxs-lookup"><span data-stu-id="44e03-123">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-124">アクティブな保留中の取得数</span><span class="sxs-lookup"><span data-stu-id="44e03-124">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="44e03-125">現在アクティブな保留中の数を取得します。サーバーへの長時間保持接続</span><span class="sxs-lookup"><span data-stu-id="44e03-125">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-126">アクティブなセッション数</span><span class="sxs-lookup"><span data-stu-id="44e03-126">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="44e03-127">アプリケーションごとに UCWA に登録されている現在のエンドポイント数と合計</span><span class="sxs-lookup"><span data-stu-id="44e03-127">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-128">アクティブなユーザーインスタンス数</span><span class="sxs-lookup"><span data-stu-id="44e03-128">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="44e03-129">ユーザーインスタンスの現在の数</span><span class="sxs-lookup"><span data-stu-id="44e03-129">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-130">アプリケーションを使用しないアクティブなユーザーインスタンス</span><span class="sxs-lookup"><span data-stu-id="44e03-130">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="44e03-131">アプリケーションが適用されていない現在のユーザーインスタンス数</span><span class="sxs-lookup"><span data-stu-id="44e03-131">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-132">アクティブなビデオモダリティ数</span><span class="sxs-lookup"><span data-stu-id="44e03-132">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="44e03-133">現在のビデオモダリティ数</span><span class="sxs-lookup"><span data-stu-id="44e03-133">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-134">受信したアプリケーション作成要求の数/秒</span><span class="sxs-lookup"><span data-stu-id="44e03-134">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="44e03-135">受信したアプリケーション作成要求の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="44e03-135">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-136">MCU の参加に失敗した場合</span><span class="sxs-lookup"><span data-stu-id="44e03-136">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="44e03-137">AS MCU 参加エラーの数</span><span class="sxs-lookup"><span data-stu-id="44e03-137">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-138">AV MCU 参加エラー</span><span class="sxs-lookup"><span data-stu-id="44e03-138">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="44e03-139">AV MCU の参加に失敗した回数</span><span class="sxs-lookup"><span data-stu-id="44e03-139">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-140">アプリケーションの平均起動時間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="44e03-140">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="44e03-141">アプリケーションの平均起動時間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="44e03-141">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-142">セッションの平均有効期間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="44e03-142">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="44e03-143">セッションの平均有効期間 (ミリ秒単位)</span><span class="sxs-lookup"><span data-stu-id="44e03-143">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-144">データ MCU の参加エラー</span><span class="sxs-lookup"><span data-stu-id="44e03-144">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="44e03-145">データ MCU の参加に失敗した回数</span><span class="sxs-lookup"><span data-stu-id="44e03-145">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-146">Exchange の連絡先検索の待機時間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="44e03-146">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="44e03-147">このカウンターは、Exchange の連絡先を検索する平均時間 (ミリ秒) を示します。</span><span class="sxs-lookup"><span data-stu-id="44e03-147">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-148">Exchange HD Photo Get 待機時間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="44e03-148">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="44e03-149">このカウンターは、Exchange から写真を取得する平均時間 (ミリ秒) を示します。</span><span class="sxs-lookup"><span data-stu-id="44e03-149">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-150">HTTP 4xx 応答/秒</span><span class="sxs-lookup"><span data-stu-id="44e03-150">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="44e03-151">HTTP 4xx コードでの応答の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="44e03-151">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-152">HTTP 5xx 応答/秒</span><span class="sxs-lookup"><span data-stu-id="44e03-152">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="44e03-153">HTTP 5xx コードでの応答の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="44e03-153">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-154">IM MCU の参加エラー</span><span class="sxs-lookup"><span data-stu-id="44e03-154">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="44e03-155">IM MCU の参加に失敗した回数</span><span class="sxs-lookup"><span data-stu-id="44e03-155">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-156">Active Directory の写真の Get エラー数</span><span class="sxs-lookup"><span data-stu-id="44e03-156">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="44e03-157">Active Directory からの写真の取得に失敗した回数の合計</span><span class="sxs-lookup"><span data-stu-id="44e03-157">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-158">連絡先検索エラー数</span><span class="sxs-lookup"><span data-stu-id="44e03-158">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="44e03-159">Exchange での連絡先の検索に失敗した回数の合計</span><span class="sxs-lookup"><span data-stu-id="44e03-159">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-160">逆シリアル化エラーの数</span><span class="sxs-lookup"><span data-stu-id="44e03-160">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="44e03-161">逆シリアル化エラーの合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-161">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-162">HD Photo Get エラーの数</span><span class="sxs-lookup"><span data-stu-id="44e03-162">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="44e03-163">Exchange からの HD 写真の取得に失敗した回数の合計</span><span class="sxs-lookup"><span data-stu-id="44e03-163">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-164">アプリケーションごとのサブスクリプションの最大数</span><span class="sxs-lookup"><span data-stu-id="44e03-164">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="44e03-165">アプリケーションごとに許容される最大数を超えるサブスクリプション要求の数</span><span class="sxs-lookup"><span data-stu-id="44e03-165">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-166">バッチごとの最大サブスクリプション数</span><span class="sxs-lookup"><span data-stu-id="44e03-166">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="44e03-167">バッチごとに許容される最大数を超えるサブスクリプション要求の数</span><span class="sxs-lookup"><span data-stu-id="44e03-167">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-168">プレゼンスサブスクリプションエラー</span><span class="sxs-lookup"><span data-stu-id="44e03-168">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="44e03-169">プレゼンスをサブスクライブしているエラーの数</span><span class="sxs-lookup"><span data-stu-id="44e03-169">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-170">エンドポイントエラーの登録</span><span class="sxs-lookup"><span data-stu-id="44e03-170">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="44e03-171">エンドポイントの登録に失敗した回数</span><span class="sxs-lookup"><span data-stu-id="44e03-171">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-172">Received/Second 要求数</span><span class="sxs-lookup"><span data-stu-id="44e03-172">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="44e03-173">受信した要求の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="44e03-173">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-174">成功した要求数/秒</span><span class="sxs-lookup"><span data-stu-id="44e03-174">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="44e03-175">成功した要求の1秒あたりの数 (HTTP 2xx/3xx 応答コード)</span><span class="sxs-lookup"><span data-stu-id="44e03-175">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-176">正常に作成したアプリケーション要求/秒</span><span class="sxs-lookup"><span data-stu-id="44e03-176">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="44e03-177">成功したアプリケーション作成要求の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="44e03-177">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-178">タイムアウト保留中の取得数</span><span class="sxs-lookup"><span data-stu-id="44e03-178">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="44e03-179">タイムアウトした保留中の取得の数</span><span class="sxs-lookup"><span data-stu-id="44e03-179">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-180">受信したアプリケーション作成要求の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-180">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="44e03-181">サービスの開始以降に受信されたアプリケーション作成要求の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-181">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-182">HTTP 4xx 応答の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-182">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="44e03-183">HTTP 4xx 応答の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-183">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-184">HTTP 5xx 応答の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-184">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="44e03-185">HTTP 5xx 応答の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-185">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-186">コマンドチャネルで受信した要求の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-186">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="44e03-187">コマンドチャネルで受信した要求の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-187">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-188">成功した要求の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-188">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="44e03-189">成功した要求の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-189">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-190">開始されたセッションの合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-190">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="44e03-191">サービスの開始以降に開始されたセッションの合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-191">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-192">アイドルタイムアウトが原因で終了したセッションの合計</span><span class="sxs-lookup"><span data-stu-id="44e03-192">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="44e03-193">ユーザーのアイドルタイムアウトが原因で終了したセッションの合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-193">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-194">調整されるアプリケーションの合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-194">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="44e03-195">調整されたアプリケーションの数</span><span class="sxs-lookup"><span data-stu-id="44e03-195">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="44e03-196">Mcx Mobility Service のパフォーマンスカウンター</span><span class="sxs-lookup"><span data-stu-id="44e03-196">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44e03-197">カウンター</span><span class="sxs-lookup"><span data-stu-id="44e03-197">Counter</span></span></th>
<th><span data-ttu-id="44e03-198">説明</span><span class="sxs-lookup"><span data-stu-id="44e03-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44e03-199">セッションの平均有効期間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="44e03-199">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="44e03-200">セッションの平均有効期間 (ミリ秒単位)</span><span class="sxs-lookup"><span data-stu-id="44e03-200">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-201">現在のプッシュ通知サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="44e03-201">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="44e03-202">プッシュ通知サブスクリプションの現在の数。</span><span class="sxs-lookup"><span data-stu-id="44e03-202">The current number of push notification subscriptions.</span></span> <span data-ttu-id="44e03-203">この数値は、現在アクティブなセッション数と組み合わせて、Windows Mobile または iPhone デバイス用に登録されている現在アクティブなセッションのサブセットを表します。</span><span class="sxs-lookup"><span data-stu-id="44e03-203">This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-204">現在アクティブなネットワークのタイムアウトポーリング数</span><span class="sxs-lookup"><span data-stu-id="44e03-204">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="44e03-205">タイムアウトしたネットワークポーリングの数</span><span class="sxs-lookup"><span data-stu-id="44e03-205">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-206">現在アクティブなポーリング数</span><span class="sxs-lookup"><span data-stu-id="44e03-206">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="44e03-207">現在アクティブなポーリングの数 (長時間保持されているサーバーへの接続)</span><span class="sxs-lookup"><span data-stu-id="44e03-207">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-208">現在アクティブなセッション数</span><span class="sxs-lookup"><span data-stu-id="44e03-208">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="44e03-209">Mobility Service に登録されている現在のエンドポイント数</span><span class="sxs-lookup"><span data-stu-id="44e03-209">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-210">アクティブなプレゼンスサブスクリプションのある現在アクティブなセッション数</span><span class="sxs-lookup"><span data-stu-id="44e03-210">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="44e03-211">アクティブなプレゼンスサブスクリプションのある現在アクティブなセッションの数</span><span class="sxs-lookup"><span data-stu-id="44e03-211">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-212">プッシュ通知要求が失敗した/秒</span><span class="sxs-lookup"><span data-stu-id="44e03-212">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="44e03-213">失敗したプッシュ通知の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="44e03-213">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-214">1秒あたりに成功したプッシュ通知要求</span><span class="sxs-lookup"><span data-stu-id="44e03-214">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="44e03-215">成功したプッシュ通知の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="44e03-215">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-216">プッシュ通知要求の調整/秒</span><span class="sxs-lookup"><span data-stu-id="44e03-216">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="44e03-217">調整されたプッシュ通知の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="44e03-217">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-218">プッシュ通知要求/秒</span><span class="sxs-lookup"><span data-stu-id="44e03-218">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="44e03-219">送信されたプッシュ通知の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="44e03-219">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-220">失敗した要求数/秒</span><span class="sxs-lookup"><span data-stu-id="44e03-220">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="44e03-221">失敗した要求の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="44e03-221">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-222">Received/Second 要求数</span><span class="sxs-lookup"><span data-stu-id="44e03-222">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="44e03-223">受信した要求の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="44e03-223">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-224">拒否された要求数/秒</span><span class="sxs-lookup"><span data-stu-id="44e03-224">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="44e03-225">拒否された要求の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="44e03-225">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-226">成功した要求数/秒</span><span class="sxs-lookup"><span data-stu-id="44e03-226">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="44e03-227">成功した要求の1秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="44e03-227">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-228">正常開始セッション要求数/秒</span><span class="sxs-lookup"><span data-stu-id="44e03-228">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="44e03-229">成功した場所の取得要求の1秒あたりの数。</span><span class="sxs-lookup"><span data-stu-id="44e03-229">The per second rate of successful Get Location requests.</span></span> <span data-ttu-id="44e03-230">セッションを開始する要求は、サーバー上で最も CPU を消費します。</span><span class="sxs-lookup"><span data-stu-id="44e03-230">Requests to initiate a session consume the most CPU on the server.</span></span> <span data-ttu-id="44e03-231">サポートされているピーク負荷は 12/秒です。</span><span class="sxs-lookup"><span data-stu-id="44e03-231">Peak supported load is 12/second.</span></span> <span data-ttu-id="44e03-232">持続性は、サーバー上の他の負荷に依存します。</span><span class="sxs-lookup"><span data-stu-id="44e03-232">Sustainability depends on other loads on the server.</span></span> <span data-ttu-id="44e03-233">通常、セッションを開始することは、長期間にわたるサインアウトされたユーザーに対してサインインすることを意味します。</span><span class="sxs-lookup"><span data-stu-id="44e03-233">Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-234">着信音声通話の拒否合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-234">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="44e03-235">拒否された着信音声通話の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-235">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-236">失敗した着信音声通話の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-236">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="44e03-237">失敗した着信音声通話の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-237">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-238">失敗した発信音声通話の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-238">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="44e03-239">失敗した発信音声通話の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-239">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-240">ユーザーが終了したセッションの合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-240">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="44e03-241">ユーザーが終了したセッションの合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-241">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-242">プッシュ通知要求の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-242">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="44e03-243">プッシュ通知要求の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-243">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-244">失敗したプッシュ通知要求の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-244">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="44e03-245">失敗したプッシュ通知要求の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-245">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-246">成功したプッシュ通知要求の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-246">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="44e03-247">成功したプッシュ通知要求の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-247">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-248">調整されるプッシュ通知要求の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-248">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="44e03-249">調整されたプッシュ通知要求の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-249">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-250">失敗した要求の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-250">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="44e03-251">失敗した要求の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-251">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-252">コマンドチャネルで受信した要求の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-252">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="44e03-253">コマンドチャネルで受信した要求の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-253">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-254">拒否された要求の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-254">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="44e03-255">拒否された要求の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-255">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-256">成功した要求の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-256">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="44e03-257">Mobility Service に対して成功した要求の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-257">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-258">セッションが開始した合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-258">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="44e03-259">Mobility Service の開始以降に開始されたセッションの合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-259">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-260">ユーザーのアイドルタイムアウトが原因で終了したセッションの合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-260">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="44e03-261">ユーザーのアイドルタイムアウトが原因で終了したセッションの合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-261">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e03-262">成功した着信音声通話の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-262">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="44e03-263">成功した着信音声通話の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-263">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e03-264">成功した発信音声通話の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-264">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="44e03-265">成功した発信音声通話の合計数</span><span class="sxs-lookup"><span data-stu-id="44e03-265">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

