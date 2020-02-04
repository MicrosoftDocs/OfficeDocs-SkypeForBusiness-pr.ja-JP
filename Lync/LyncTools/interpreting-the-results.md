---
title: 結果の解釈
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dcb1d84392cf9f56f2996281eb53e798690ba1e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a><span data-ttu-id="1c2c2-102">結果の解釈</span><span class="sxs-lookup"><span data-stu-id="1c2c2-102">Interpreting the Results</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c2c2-103">_**最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="1c2c2-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="1c2c2-104">Lync Server 2013 応力/パフォーマンスツール (LyncPerfTool) には、クライアントが何を実行しているのか、問題が発生しているかを理解するために使用できる多くのカウンターがあります。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-104">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="1c2c2-105">クライアントのカウンター</span><span class="sxs-lookup"><span data-stu-id="1c2c2-105">Client Counters</span></span>

<span data-ttu-id="1c2c2-106">実行されている LyncPerfTool の各インスタンスには、カウンターの個別のインスタンスがあります。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-106">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="1c2c2-107">それぞれのインスタンスには、そのプロセス ID による名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-107">Each instance is named by its process ID.</span></span>

<span data-ttu-id="1c2c2-108">クライアントが過負荷になっていると、問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-108">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="1c2c2-109">これらの問題を回避するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-109">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="1c2c2-110">クライアントコンピューターの CPU とメモリ使用量を監視します。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-110">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="1c2c2-111">CPU が継続的に 90% 以上になっている場合は、ユーザーの数を減らします。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-111">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="1c2c2-112">メモリフットプリントが高すぎる場合は、ページファイルが十分でない場合に問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-112">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="1c2c2-113">コミット チャージがコンピューターの制限に達していないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-113">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="1c2c2-114">メモリの制限を使用している場合は、ページファイルのサイズを大きくするか、ユーザーの数を減らすことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-114">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="1c2c2-115">次の表では、LyncPerfTool のパフォーマンスカウンターの主要な一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-115">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="1c2c2-116">**一般情報**</span><span class="sxs-lookup"><span data-stu-id="1c2c2-116">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c2c2-117"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="1c2c2-117"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="1c2c2-118"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="1c2c2-118"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-119">Time Spent in Minutes</span><span class="sxs-lookup"><span data-stu-id="1c2c2-119">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-120">プロセスの開始からの経過時間。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-120">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c2c2-121">Active Endpoints</span><span class="sxs-lookup"><span data-stu-id="1c2c2-121">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-122">現在サーバーに接続しているエンドポイントの数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-122">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-123">Failed Logons</span><span class="sxs-lookup"><span data-stu-id="1c2c2-123">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-124">エンドポイント サインインの合計失敗数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-124">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c2c2-125">Logon Attempts</span><span class="sxs-lookup"><span data-stu-id="1c2c2-125">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-126">エンドポイント サインインの合計試行数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-126">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-127">Endpoints Disconnected</span><span class="sxs-lookup"><span data-stu-id="1c2c2-127">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-128">切断されたエンドポイントの合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-128">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1c2c2-129">**プレゼンス情報**</span><span class="sxs-lookup"><span data-stu-id="1c2c2-129">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c2c2-130"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="1c2c2-130"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="1c2c2-131"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="1c2c2-131"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-132">SetPresence Calls</span><span class="sxs-lookup"><span data-stu-id="1c2c2-132">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-133">プレゼンス変更の合計試行数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-133">Total number of presence change attempts.</span></span> <span data-ttu-id="1c2c2-134">プレゼンス変更のさまざまな種類については、SetPresence (プレゼンスの種類) Calls パフォーマンス カウンターを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-134">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c2c2-135">NNN Responses for SetPresence</span><span class="sxs-lookup"><span data-stu-id="1c2c2-135">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-136">サーバーから受信した nnn 応答コードの合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-136">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-137">GetPresence Calls</span><span class="sxs-lookup"><span data-stu-id="1c2c2-137">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-138">プレゼンス取得要求の合計試行数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-138">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c2c2-139">NNN Responses for GetPresence</span><span class="sxs-lookup"><span data-stu-id="1c2c2-139">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-140">サーバーから受信した nnn 応答コードの合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-140">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1c2c2-141">**アドレス帳サービス情報**</span><span class="sxs-lookup"><span data-stu-id="1c2c2-141">**Address Book service Information**</span></span>

<span data-ttu-id="1c2c2-142">このカテゴリには、アドレス帳サービス (ABS) のファイル ダウンロードとアドレス帳 Web クエリ サービスの要求を監視するために使用するカウンターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-142">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c2c2-143"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="1c2c2-143"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="1c2c2-144"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="1c2c2-144"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-145">ABS Full/Delta File Downloads Attempted</span><span class="sxs-lookup"><span data-stu-id="1c2c2-145">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-146">試行された完全または差分ファイル ダウンロード要求の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-146">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c2c2-147">ABS Full/Delta File Downloads Succeeded</span><span class="sxs-lookup"><span data-stu-id="1c2c2-147">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-148">試行された完全または差分ファイル ダウンロード要求の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-148">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-149">アドレス帳 Web クエリ サービスに関連するカウンター</span><span class="sxs-lookup"><span data-stu-id="1c2c2-149">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-150">アドレス帳ファイルのダウンロードに関連するカウンター。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-150">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c2c2-151">ABS WS Calls attempted</span><span class="sxs-lookup"><span data-stu-id="1c2c2-151">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-152">試行したアドレス帳 Web クエリ サービス要求の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-152">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-153">ABS WS Calls Succeeded</span><span class="sxs-lookup"><span data-stu-id="1c2c2-153">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-154">成功応答コードを返したアドレス帳 Web クエリ サービス要求の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-154">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c2c2-155">ABS WS Calls Failed</span><span class="sxs-lookup"><span data-stu-id="1c2c2-155">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-156">エラー応答コードを返したアドレス帳 Web クエリ サービスの合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-156">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1c2c2-157">**配布リスト (DL) の情報**</span><span class="sxs-lookup"><span data-stu-id="1c2c2-157">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c2c2-158"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="1c2c2-158"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="1c2c2-159"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="1c2c2-159"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-160">Calls Attempted</span><span class="sxs-lookup"><span data-stu-id="1c2c2-160">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-161">試行した配布リスト展開 (DLX) Web サービス要求の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-161">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c2c2-162">Calls Succeeded</span><span class="sxs-lookup"><span data-stu-id="1c2c2-162">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-163">成功応答コードを返した DLX Web サービス要求の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-163">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-164">Calls Failed</span><span class="sxs-lookup"><span data-stu-id="1c2c2-164">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-165">エラー応答コードを返した DLX Web サービス要求の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-165">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1c2c2-166">**VoIP の基本情報**</span><span class="sxs-lookup"><span data-stu-id="1c2c2-166">**VoIP Basic Information**</span></span>

<span data-ttu-id="1c2c2-167">次に示す各パフォーマンス カウンターは、すべての Voice over IP (VoIP) の通話数を報告します。これには、仲介サーバー、音声ビデオ会議サーバー、エッジ サーバー、応答グループ アプリケーション、および電話会議自動応答に対する通話が含まれます (これらのシナリオが有効な場合)。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-167">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c2c2-168"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="1c2c2-168"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="1c2c2-169"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="1c2c2-169"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-170">Calls Active</span><span class="sxs-lookup"><span data-stu-id="1c2c2-170">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-171">現在進行中の着信/発信音声通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-171">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c2c2-172">Calls Terminated</span><span class="sxs-lookup"><span data-stu-id="1c2c2-172">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-173">既に終了している着信/発信音声通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-173">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-174">Calls Declined</span><span class="sxs-lookup"><span data-stu-id="1c2c2-174">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-175">拒否した着信音声通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-175">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c2c2-176">Incoming/Outgoing Calls Attempted</span><span class="sxs-lookup"><span data-stu-id="1c2c2-176">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-177">試行した着信/発信音声通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-177">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-178">Incoming/Outgoing Calls Established</span><span class="sxs-lookup"><span data-stu-id="1c2c2-178">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-179">成立した着信/発信音声通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-179">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c2c2-180">Calls Received NNN</span><span class="sxs-lookup"><span data-stu-id="1c2c2-180">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-181">サーバーから受信した nnn 応答コードの合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-181">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-182">VoIP Pass Rate (%)</span><span class="sxs-lookup"><span data-stu-id="1c2c2-182">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-183">成立した通話の合計/試行した通話の合計。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-183">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1c2c2-184">**応答グループ サービス通話の情報**</span><span class="sxs-lookup"><span data-stu-id="1c2c2-184">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c2c2-185"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="1c2c2-185"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="1c2c2-186"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="1c2c2-186"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-187">Calls Active</span><span class="sxs-lookup"><span data-stu-id="1c2c2-187">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-188">応答グループ アプリケーションへのアクティブな通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-188">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c2c2-189">Calls Attempted</span><span class="sxs-lookup"><span data-stu-id="1c2c2-189">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-190">試行した通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-190">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1c2c2-191">**インスタント メッセージング (IM) 通話の情報**</span><span class="sxs-lookup"><span data-stu-id="1c2c2-191">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c2c2-192"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="1c2c2-192"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="1c2c2-193"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="1c2c2-193"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-194">Calls Active</span><span class="sxs-lookup"><span data-stu-id="1c2c2-194">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-195">進行中の着信/発信インスタント メッセージング通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-195">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c2c2-196">Calls Terminated</span><span class="sxs-lookup"><span data-stu-id="1c2c2-196">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-197">既に終了している着信/発信インスタント メッセージング通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-197">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-198">Calls Received NNN</span><span class="sxs-lookup"><span data-stu-id="1c2c2-198">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-199">サーバーから受信した nnn 応答コードの合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-199">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c2c2-200">IM Messages Received/Sent</span><span class="sxs-lookup"><span data-stu-id="1c2c2-200">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-201">すべてのセッションで受信または送信したメッセージの合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-201">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-202">Incoming/Outgoing Calls Attempted</span><span class="sxs-lookup"><span data-stu-id="1c2c2-202">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-203">試行した着信/発信インスタント メッセージング通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-203">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c2c2-204">Incoming/Outgoing Calls Established</span><span class="sxs-lookup"><span data-stu-id="1c2c2-204">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-205">成立した着信/発信インスタント メッセージ通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-205">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1c2c2-206">**アプリケーション共有通話の情報**</span><span class="sxs-lookup"><span data-stu-id="1c2c2-206">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c2c2-207"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="1c2c2-207"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="1c2c2-208"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="1c2c2-208"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-209">Calls Active</span><span class="sxs-lookup"><span data-stu-id="1c2c2-209">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-210">進行中の着信/発信アプリケーション共有通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-210">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c2c2-211">Calls Terminated</span><span class="sxs-lookup"><span data-stu-id="1c2c2-211">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-212">既に終了している着信/発信アプリケーション共有通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-212">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-213">Calls Received NNN</span><span class="sxs-lookup"><span data-stu-id="1c2c2-213">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-214">サーバーから受信した nnn 応答コードの合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-214">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c2c2-215">Incoming/Outgoing Calls Attempted</span><span class="sxs-lookup"><span data-stu-id="1c2c2-215">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-216">試行した着信/発信アプリケーション共有通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-216">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-217">Incoming/Outgoing Calls Established</span><span class="sxs-lookup"><span data-stu-id="1c2c2-217">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-218">成立した着信/発信アプリケーション共有通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-218">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1c2c2-219">**CAA 通話の情報**</span><span class="sxs-lookup"><span data-stu-id="1c2c2-219">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c2c2-220"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="1c2c2-220"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="1c2c2-221"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="1c2c2-221"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-222">Calls Active</span><span class="sxs-lookup"><span data-stu-id="1c2c2-222">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-223">現在進行中の着信/発信公衆交換電話網 (PSTN) 通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-223">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c2c2-224">Calls Terminated</span><span class="sxs-lookup"><span data-stu-id="1c2c2-224">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-225">既に終了している着信/発信 PSTN 通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-225">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-226">Incoming/Outgoing Calls Attempted</span><span class="sxs-lookup"><span data-stu-id="1c2c2-226">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-227">試行した着信/発信 PSTN 通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-227">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c2c2-228">Incoming/Outgoing Calls Established</span><span class="sxs-lookup"><span data-stu-id="1c2c2-228">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-229">成立した着信/発信 PSTN 通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-229">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1c2c2-230">**会議通話の情報**</span><span class="sxs-lookup"><span data-stu-id="1c2c2-230">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c2c2-231"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="1c2c2-231"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="1c2c2-232"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="1c2c2-232"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-233">Active Instant Messaging Conferences</span><span class="sxs-lookup"><span data-stu-id="1c2c2-233">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-234">進行中のインスタント メッセージング会議通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-234">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c2c2-235">Active Audio/Video Conferences</span><span class="sxs-lookup"><span data-stu-id="1c2c2-235">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-236">進行中の音声ビデオ (A/V) 会議通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-236">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-237">Active Application Sharing Conferences</span><span class="sxs-lookup"><span data-stu-id="1c2c2-237">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-238">進行中のアプリケーション共有会議通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-238">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c2c2-239">Number of Participants</span><span class="sxs-lookup"><span data-stu-id="1c2c2-239">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-240">会議通話に現在接続している参加者の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-240">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-241">Conference Schedule Failure</span><span class="sxs-lookup"><span data-stu-id="1c2c2-241">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-242">会議通話のスケジュールに失敗した合計回数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-242">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c2c2-243">Join Conference Failure</span><span class="sxs-lookup"><span data-stu-id="1c2c2-243">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-244">会議通話への接続に失敗した合計回数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-244">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1c2c2-245">**UCWA クライアントのカウンター**</span><span class="sxs-lookup"><span data-stu-id="1c2c2-245">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c2c2-246"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="1c2c2-246"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="1c2c2-247"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="1c2c2-247"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c2c2-248">Total Number of IMMCU Joins Succeeded</span><span class="sxs-lookup"><span data-stu-id="1c2c2-248">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-249">参加したインスタント メッセージング会議通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-249">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c2c2-250">Total Number of DMCU Joins Succeeded</span><span class="sxs-lookup"><span data-stu-id="1c2c2-250">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="1c2c2-251">参加した音声ビデオ会議通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="1c2c2-251">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

