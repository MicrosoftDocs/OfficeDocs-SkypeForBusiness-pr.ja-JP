---
title: 'Lync Server 2013: モビリティーパフォーマンスカウンター'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c0759ccd6a9203dfac87f0ec55f555d49d19ccc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="526fd-102">Lync Server 2013 のモバイルパフォーマンスカウンター</span><span class="sxs-lookup"><span data-stu-id="526fd-102">Mobility performance counters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="526fd-103">_**最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="526fd-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="526fd-104">次の表は、ユニファイドコミュニケーション Web API (UCWA) および Lync Server 2013 Mcx Mobility Service を実行しているサーバーを監視するために使用できるパフォーマンスカウンターの名前と説明を示しています。</span><span class="sxs-lookup"><span data-stu-id="526fd-104">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="526fd-105">UCWA の表のカウンターのカテゴリ名は、**LS:WEB - UCWA** です。</span><span class="sxs-lookup"><span data-stu-id="526fd-105">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="526fd-106">Mcx Mobility Service の表のカウンターのカテゴリ名は、**LS:WEB - Mobile Communication Service** です。</span><span class="sxs-lookup"><span data-stu-id="526fd-106">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="526fd-107">UCWA のパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="526fd-107">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="526fd-108">カウンター</span><span class="sxs-lookup"><span data-stu-id="526fd-108">Counter</span></span></th>
<th><span data-ttu-id="526fd-109">説明</span><span class="sxs-lookup"><span data-stu-id="526fd-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="526fd-110">Active Application Count</span><span class="sxs-lookup"><span data-stu-id="526fd-110">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="526fd-111">現在のアプリケーション数</span><span class="sxs-lookup"><span data-stu-id="526fd-111">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-112">Active Application Sharing Modality Count</span><span class="sxs-lookup"><span data-stu-id="526fd-112">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="526fd-113">現在のアプリケーション共有モダリティ数</span><span class="sxs-lookup"><span data-stu-id="526fd-113">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-114">Active Audio Modality Count</span><span class="sxs-lookup"><span data-stu-id="526fd-114">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="526fd-115">現在の音声モダリティ数</span><span class="sxs-lookup"><span data-stu-id="526fd-115">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-116">Active Data Collaboration Modality Count</span><span class="sxs-lookup"><span data-stu-id="526fd-116">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="526fd-117">現在のデータの共同作業モダリティ数</span><span class="sxs-lookup"><span data-stu-id="526fd-117">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-118">Active Directory Photo Get Latency (ms)</span><span class="sxs-lookup"><span data-stu-id="526fd-118">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="526fd-119">このカウンターは、Active Directory から写真を取得する平均時間 (ミリ秒) を示します</span><span class="sxs-lookup"><span data-stu-id="526fd-119">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-120">Active Messaging Modality Count</span><span class="sxs-lookup"><span data-stu-id="526fd-120">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="526fd-121">現在のメッセージング モダリティ数</span><span class="sxs-lookup"><span data-stu-id="526fd-121">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-122">Active Panoramic Video Modality Count</span><span class="sxs-lookup"><span data-stu-id="526fd-122">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="526fd-123">現在のパノラマ ビデオ モダリティ数</span><span class="sxs-lookup"><span data-stu-id="526fd-123">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-124">Active Pending Get Count</span><span class="sxs-lookup"><span data-stu-id="526fd-124">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="526fd-125">現在アクティブな保留中の取得数。サーバーへの接続は長時間維持されます</span><span class="sxs-lookup"><span data-stu-id="526fd-125">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-126">Active Session Count</span><span class="sxs-lookup"><span data-stu-id="526fd-126">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="526fd-127">アプリケーションごとに UCWA に登録されている現在のエンドポイント数と合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-127">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-128">Active User Instance Count</span><span class="sxs-lookup"><span data-stu-id="526fd-128">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="526fd-129">現在のユーザー インスタンス数</span><span class="sxs-lookup"><span data-stu-id="526fd-129">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-130">Active User Instances without Application</span><span class="sxs-lookup"><span data-stu-id="526fd-130">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="526fd-131">現在のユーザー インスタンス数 (アプリケーションを含まない)</span><span class="sxs-lookup"><span data-stu-id="526fd-131">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-132">Active Video Modality Count</span><span class="sxs-lookup"><span data-stu-id="526fd-132">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="526fd-133">現在のビデオ モダリティ数</span><span class="sxs-lookup"><span data-stu-id="526fd-133">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-134">Application Creation Requests Received/Second</span><span class="sxs-lookup"><span data-stu-id="526fd-134">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="526fd-135">受信したアプリケーション作成要求の 1 秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="526fd-135">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-136">AS MCU Join Failures</span><span class="sxs-lookup"><span data-stu-id="526fd-136">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="526fd-137">AS MCU 参加に失敗した数</span><span class="sxs-lookup"><span data-stu-id="526fd-137">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-138">AV MCU Join Failures</span><span class="sxs-lookup"><span data-stu-id="526fd-138">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="526fd-139">AV MCU 参加に失敗した数</span><span class="sxs-lookup"><span data-stu-id="526fd-139">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-140">Average Application Startup Time (ms)</span><span class="sxs-lookup"><span data-stu-id="526fd-140">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="526fd-141">アプリケーションの平均起動時間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="526fd-141">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-142">Average Lifetime for Session (ms)</span><span class="sxs-lookup"><span data-stu-id="526fd-142">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="526fd-143">セッションの平均存続期間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="526fd-143">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-144">Data MCU Join Failures</span><span class="sxs-lookup"><span data-stu-id="526fd-144">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="526fd-145">Data MCU 参加に失敗した数</span><span class="sxs-lookup"><span data-stu-id="526fd-145">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-146">Exchange Contact Search Latency (ms)</span><span class="sxs-lookup"><span data-stu-id="526fd-146">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="526fd-147">このカウンターは、Exchange 内の連絡先を検索する平均時間 (ミリ秒) を示します</span><span class="sxs-lookup"><span data-stu-id="526fd-147">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-148">Exchange HD Photo Get Latency (ms)</span><span class="sxs-lookup"><span data-stu-id="526fd-148">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="526fd-149">このカウンターは、Exchange から写真を取得する平均時間 (ミリ秒) を示します</span><span class="sxs-lookup"><span data-stu-id="526fd-149">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-150">HTTP 4xx Responses/Second</span><span class="sxs-lookup"><span data-stu-id="526fd-150">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="526fd-151">HTTP 4xx コードでの応答の 1 秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="526fd-151">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-152">HTTP 5xx Responses/Second</span><span class="sxs-lookup"><span data-stu-id="526fd-152">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="526fd-153">HTTP 5xx コードでの応答の 1 秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="526fd-153">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-154">IM MCU Join Failures</span><span class="sxs-lookup"><span data-stu-id="526fd-154">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="526fd-155">IM MCU 参加に失敗した数</span><span class="sxs-lookup"><span data-stu-id="526fd-155">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-156">Number of Active Directory Photo Get Failures</span><span class="sxs-lookup"><span data-stu-id="526fd-156">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="526fd-157">Active Directory からの写真の取得に失敗した合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-157">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-158">Number of Contact Search failures</span><span class="sxs-lookup"><span data-stu-id="526fd-158">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="526fd-159">Exchange の連絡先の検索に失敗した合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-159">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-160">Number of Deserialization Failures</span><span class="sxs-lookup"><span data-stu-id="526fd-160">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="526fd-161">シリアル化解除が失敗した合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-161">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-162">HD Photo Get エラーの数</span><span class="sxs-lookup"><span data-stu-id="526fd-162">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="526fd-163">Exchange からの HD 写真の取得に失敗した合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-163">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-164">Over The Maximum Subscriptions Per Application</span><span class="sxs-lookup"><span data-stu-id="526fd-164">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="526fd-165">アプリケーションごとに許可された最大値を超えるサブスクリプション要求の数</span><span class="sxs-lookup"><span data-stu-id="526fd-165">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-166">Over The Maximum Subscriptions Per Batch</span><span class="sxs-lookup"><span data-stu-id="526fd-166">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="526fd-167">バッチごとに許可された最大値を超えるサブスクリプション要求の数</span><span class="sxs-lookup"><span data-stu-id="526fd-167">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-168">Presence Subscription Failures</span><span class="sxs-lookup"><span data-stu-id="526fd-168">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="526fd-169">プレゼンスの登録に失敗した数</span><span class="sxs-lookup"><span data-stu-id="526fd-169">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-170">Registering Endpoint Failures</span><span class="sxs-lookup"><span data-stu-id="526fd-170">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="526fd-171">エンドポイントの登録に失敗した数</span><span class="sxs-lookup"><span data-stu-id="526fd-171">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-172">Requests Received/Second</span><span class="sxs-lookup"><span data-stu-id="526fd-172">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="526fd-173">受信した要求の 1 秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="526fd-173">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-174">Requests Succeeded/Second</span><span class="sxs-lookup"><span data-stu-id="526fd-174">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="526fd-175">成功した要求 (HTTP 2xx/3xx 応答コード) の 1 秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="526fd-175">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-176">Succeeded Create Application Requests/Second</span><span class="sxs-lookup"><span data-stu-id="526fd-176">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="526fd-177">成功したアプリケーション作成要求の 1 秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="526fd-177">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-178">Timed Out Pending Get Count</span><span class="sxs-lookup"><span data-stu-id="526fd-178">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="526fd-179">タイムアウトした保留中の取得の数</span><span class="sxs-lookup"><span data-stu-id="526fd-179">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-180">Total Application Creation Requests Received</span><span class="sxs-lookup"><span data-stu-id="526fd-180">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="526fd-181">サービスの開始以降に受信したアプリケーション作成要求の合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-181">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-182">Total HTTP 4xx Responses</span><span class="sxs-lookup"><span data-stu-id="526fd-182">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="526fd-183">HTTP 4xx 応答の合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-183">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-184">Total HTTP 5xx Responses</span><span class="sxs-lookup"><span data-stu-id="526fd-184">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="526fd-185">HTTP 5xx 応答の合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-185">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-186">Total Requests Received on the Command Channel</span><span class="sxs-lookup"><span data-stu-id="526fd-186">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="526fd-187">コマンド チャネルで受信した要求の合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-187">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-188">Total Requests Succeeded</span><span class="sxs-lookup"><span data-stu-id="526fd-188">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="526fd-189">成功した要求の合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-189">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-190">Total Sessions Initiated</span><span class="sxs-lookup"><span data-stu-id="526fd-190">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="526fd-191">サービスが開始されてから起動されたセッションの合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-191">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-192">Total Sessions Terminated Because of Idle Timeout</span><span class="sxs-lookup"><span data-stu-id="526fd-192">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="526fd-193">ユーザーのアイドル タイムアウトが原因で終了したセッションの合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-193">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-194">Total Throttled Applications</span><span class="sxs-lookup"><span data-stu-id="526fd-194">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="526fd-195">制限されたアプリケーションの数</span><span class="sxs-lookup"><span data-stu-id="526fd-195">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="526fd-196">Mcx Mobility Service のパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="526fd-196">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="526fd-197">カウンター</span><span class="sxs-lookup"><span data-stu-id="526fd-197">Counter</span></span></th>
<th><span data-ttu-id="526fd-198">説明</span><span class="sxs-lookup"><span data-stu-id="526fd-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="526fd-199">Average Lifetime for a Session in Milliseconds</span><span class="sxs-lookup"><span data-stu-id="526fd-199">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="526fd-200">セッションの平均存続期間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="526fd-200">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-201">Current Push Notification Subscriptions</span><span class="sxs-lookup"><span data-stu-id="526fd-201">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="526fd-p101">プッシュ通知サブスクリプションの現在の数。この数は、Currently Active Session Count と連携して、Windows Mobile または iPhone のデバイスに登録された現在アクティブなセッションのサブセットを表します。</span><span class="sxs-lookup"><span data-stu-id="526fd-p101">The current number of push notification subscriptions. This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-204">Currently Active Network Timeout Poll Count</span><span class="sxs-lookup"><span data-stu-id="526fd-204">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="526fd-205">タイムアウトしたネットワーク ポーリングの数</span><span class="sxs-lookup"><span data-stu-id="526fd-205">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-206">Currently Active Poll Count</span><span class="sxs-lookup"><span data-stu-id="526fd-206">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="526fd-207">現在アクティブなポーリングの数 (長時間維持されるサーバーとの接続)</span><span class="sxs-lookup"><span data-stu-id="526fd-207">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-208">Currently Active Session Count</span><span class="sxs-lookup"><span data-stu-id="526fd-208">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="526fd-209">Mobility Service に登録されたエンドポイントの現在の数</span><span class="sxs-lookup"><span data-stu-id="526fd-209">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-210">Currently Active Session Count with Active Presence Subscriptions</span><span class="sxs-lookup"><span data-stu-id="526fd-210">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="526fd-211">アクティブなプレゼンス サブスクリプションのある現在アクティブなセッションの数</span><span class="sxs-lookup"><span data-stu-id="526fd-211">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-212">Push Notification Requests Failed/Second</span><span class="sxs-lookup"><span data-stu-id="526fd-212">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="526fd-213">失敗したプッシュ通知の 1 秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="526fd-213">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-214">Push Notification Requests Succeeded/Second</span><span class="sxs-lookup"><span data-stu-id="526fd-214">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="526fd-215">成功したプッシュ通知の 1 秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="526fd-215">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-216">Push Notification Requests Throttled/Second</span><span class="sxs-lookup"><span data-stu-id="526fd-216">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="526fd-217">調整済みのプッシュ通知の 1 秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="526fd-217">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-218">Push Notification Requests/Second</span><span class="sxs-lookup"><span data-stu-id="526fd-218">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="526fd-219">送信されたプッシュ通知の 1 秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="526fd-219">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-220">Requests Failed/Second</span><span class="sxs-lookup"><span data-stu-id="526fd-220">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="526fd-221">失敗した要求の 1 秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="526fd-221">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-222">Requests Received/Second</span><span class="sxs-lookup"><span data-stu-id="526fd-222">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="526fd-223">受信した要求の 1 秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="526fd-223">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-224">Requests Rejected/Second</span><span class="sxs-lookup"><span data-stu-id="526fd-224">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="526fd-225">拒否された要求の 1 秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="526fd-225">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-226">Requests Succeeded/Second</span><span class="sxs-lookup"><span data-stu-id="526fd-226">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="526fd-227">成功した要求の 1 秒あたりの数</span><span class="sxs-lookup"><span data-stu-id="526fd-227">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-228">Succeeded Initiate Session Requests/Second</span><span class="sxs-lookup"><span data-stu-id="526fd-228">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="526fd-p102">成功した Get Location 要求の 1 秒あたりの数。セッションを開始する要求は、サーバー上の大部分の CPU を消費します。ピーク時にサポートされるロードは 12/秒です。持続可能性は、サーバー上の他のロードによって異なります。セッションの開始は、通常、長時間サインアウトしていたユーザーのサインインを意味します。</span><span class="sxs-lookup"><span data-stu-id="526fd-p102">The per second rate of successful Get Location requests. Requests to initiate a session consume the most CPU on the server. Peak supported load is 12/second. Sustainability depends on other loads on the server. Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-234">Total Declined Inbound Voice Calls</span><span class="sxs-lookup"><span data-stu-id="526fd-234">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="526fd-235">拒否された着信音声通話の合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-235">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-236">Total Failed Inbound Voice Calls</span><span class="sxs-lookup"><span data-stu-id="526fd-236">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="526fd-237">失敗した着信音声通話の合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-237">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-238">Total Failed Outbound Voice Calls</span><span class="sxs-lookup"><span data-stu-id="526fd-238">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="526fd-239">失敗した発信音声通話の合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-239">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-240">Total number of sessions terminated by user</span><span class="sxs-lookup"><span data-stu-id="526fd-240">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="526fd-241">ユーザーが終了したセッションの合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-241">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-242">Total Push Notification Requests</span><span class="sxs-lookup"><span data-stu-id="526fd-242">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="526fd-243">プッシュ通知要求の合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-243">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-244">Total Push Notification Requests Failed</span><span class="sxs-lookup"><span data-stu-id="526fd-244">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="526fd-245">失敗したプッシュ通知要求の合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-245">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-246">Total Push Notification Requests Succeeded</span><span class="sxs-lookup"><span data-stu-id="526fd-246">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="526fd-247">成功したプッシュ通知要求の合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-247">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-248">Total Push Notification Requests Throttled</span><span class="sxs-lookup"><span data-stu-id="526fd-248">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="526fd-249">調整済みのプッシュ通知要求の合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-249">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-250">Total Requests Failed</span><span class="sxs-lookup"><span data-stu-id="526fd-250">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="526fd-251">失敗した要求の合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-251">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-252">Total Requests received on the Command Channel</span><span class="sxs-lookup"><span data-stu-id="526fd-252">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="526fd-253">コマンド チャネルで受信した要求の合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-253">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-254">Total Requests Rejected</span><span class="sxs-lookup"><span data-stu-id="526fd-254">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="526fd-255">拒否された要求の合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-255">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-256">Total Requests Succeeded</span><span class="sxs-lookup"><span data-stu-id="526fd-256">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="526fd-257">Mobility Service に対する成功した要求の合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-257">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-258">Total Session Initiated Count</span><span class="sxs-lookup"><span data-stu-id="526fd-258">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="526fd-259">Mobility Service が開始されてから起動されたセッションの合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-259">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-260">Total Sessions Terminated Because of User Idle Timeout</span><span class="sxs-lookup"><span data-stu-id="526fd-260">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="526fd-261">ユーザーのアイドル タイムアウトが原因で終了したセッションの合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-261">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526fd-262">Total Successful Inbound Voice Calls</span><span class="sxs-lookup"><span data-stu-id="526fd-262">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="526fd-263">成功した着信音声通話の合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-263">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526fd-264">Total Successful Outbound Voice Calls</span><span class="sxs-lookup"><span data-stu-id="526fd-264">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="526fd-265">成功した発信音声通話の合計数</span><span class="sxs-lookup"><span data-stu-id="526fd-265">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

