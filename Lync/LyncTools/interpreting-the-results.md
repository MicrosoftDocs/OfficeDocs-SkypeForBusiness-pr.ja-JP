---
title: 結果の解釈
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3a15880de861b850d3e0355491e85219ba3579d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499914"
---
# <a name="interpreting-the-results"></a><span data-ttu-id="91123-102">結果の解釈</span><span class="sxs-lookup"><span data-stu-id="91123-102">Interpreting the Results</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91123-103">_**トピックの最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="91123-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="91123-104">Lync Server 2013 ストレスおよびパフォーマンスツール (LyncPerfTool.exe) には、クライアントの動作と問題が発生しているかどうかを理解するために使用できるカウンターが多数あります。</span><span class="sxs-lookup"><span data-stu-id="91123-104">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="91123-105">クライアントカウンター</span><span class="sxs-lookup"><span data-stu-id="91123-105">Client Counters</span></span>

<span data-ttu-id="91123-106">実行されている LyncPerfTool.exe の各インスタンスには、カウンターの個別のインスタンスがあります。</span><span class="sxs-lookup"><span data-stu-id="91123-106">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="91123-107">各インスタンスには、プロセス ID で名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="91123-107">Each instance is named by its process ID.</span></span>

<span data-ttu-id="91123-108">クライアントが過負荷になっている場合は、問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="91123-108">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="91123-109">これらの問題を回避するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="91123-109">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="91123-110">クライアントコンピューター上の CPU とメモリの使用状況を監視します。</span><span class="sxs-lookup"><span data-stu-id="91123-110">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="91123-111">CPU が90% を超えている場合は、ユーザーの数を減らします。</span><span class="sxs-lookup"><span data-stu-id="91123-111">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="91123-112">メモリフットプリントが高い場合は、ページファイルのサイズが十分でないと、問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="91123-112">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="91123-113">コミットチャージがコンピューターの制限に達していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="91123-113">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="91123-114">メモリの制限を使用している場合は、ページファイルのサイズを大きくするか、ユーザーの数を減らすことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="91123-114">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="91123-115">次の表に、LyncPerfTool の主要なパフォーマンスカウンターの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="91123-115">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="91123-116">**一般的な情報**</span><span class="sxs-lookup"><span data-stu-id="91123-116">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91123-117"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="91123-117"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="91123-118"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="91123-118"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91123-119">所要時間 (分単位)</span><span class="sxs-lookup"><span data-stu-id="91123-119">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="91123-120">プロセスが開始されてからの経過時間。</span><span class="sxs-lookup"><span data-stu-id="91123-120">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91123-121">アクティブなエンドポイント</span><span class="sxs-lookup"><span data-stu-id="91123-121">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="91123-122">サーバーに現在接続されているエンドポイントの数。</span><span class="sxs-lookup"><span data-stu-id="91123-122">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91123-123">失敗したログオン</span><span class="sxs-lookup"><span data-stu-id="91123-123">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="91123-124">エンドポイントのサインインの失敗の合計数です。</span><span class="sxs-lookup"><span data-stu-id="91123-124">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91123-125">ログオン試行</span><span class="sxs-lookup"><span data-stu-id="91123-125">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="91123-126">エンドポイントのサインイン試行の合計数です。</span><span class="sxs-lookup"><span data-stu-id="91123-126">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91123-127">エンドポイント切断</span><span class="sxs-lookup"><span data-stu-id="91123-127">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="91123-128">切断されたエンドポイントの合計数です。</span><span class="sxs-lookup"><span data-stu-id="91123-128">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="91123-129">**プレゼンス情報**</span><span class="sxs-lookup"><span data-stu-id="91123-129">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91123-130"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="91123-130"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="91123-131"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="91123-131"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91123-132">SetPresence 呼び出し</span><span class="sxs-lookup"><span data-stu-id="91123-132">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="91123-133">プレゼンス変更の試行回数の合計。</span><span class="sxs-lookup"><span data-stu-id="91123-133">Total number of presence change attempts.</span></span> <span data-ttu-id="91123-134">プレゼンス変更の種類が異なる場合は、SetPresence (プレゼンスの種類) Calls Performance Counter を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91123-134">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91123-135">SetPresence に対する NNN 応答</span><span class="sxs-lookup"><span data-stu-id="91123-135">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="91123-136">サーバーから受信した nnn 応答コードの合計数です。</span><span class="sxs-lookup"><span data-stu-id="91123-136">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91123-137">GetPresence 呼び出し</span><span class="sxs-lookup"><span data-stu-id="91123-137">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="91123-138">プレゼンス要求の取得の試行回数の合計。</span><span class="sxs-lookup"><span data-stu-id="91123-138">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91123-139">GetPresence に対する NNN 応答</span><span class="sxs-lookup"><span data-stu-id="91123-139">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="91123-140">サーバーから受信した nnn 応答コードの合計数です。</span><span class="sxs-lookup"><span data-stu-id="91123-140">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="91123-141">**アドレス帳サービス情報**</span><span class="sxs-lookup"><span data-stu-id="91123-141">**Address Book service Information**</span></span>

<span data-ttu-id="91123-142">このカテゴリには、アドレス帳サービス (ABS) ファイルのダウンロードとアドレス帳の Web クエリサービス要求を監視するために使用されるカウンターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="91123-142">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91123-143"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="91123-143"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="91123-144"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="91123-144"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91123-145">ABS フル/差分ファイルのダウンロードの試行</span><span class="sxs-lookup"><span data-stu-id="91123-145">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="91123-146">試行された完全または差分ファイルのダウンロード要求の総数。</span><span class="sxs-lookup"><span data-stu-id="91123-146">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91123-147">ABS 完全または差分ファイルのダウンロードに成功しました</span><span class="sxs-lookup"><span data-stu-id="91123-147">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="91123-148">試行された完全または差分ファイルのダウンロード要求の総数。</span><span class="sxs-lookup"><span data-stu-id="91123-148">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91123-149">アドレス帳 Web クエリサービス関連カウンター</span><span class="sxs-lookup"><span data-stu-id="91123-149">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="91123-150">アドレス帳ファイルのダウンロード関連カウンター。</span><span class="sxs-lookup"><span data-stu-id="91123-150">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91123-151">ABS 呼び出しが試行されました</span><span class="sxs-lookup"><span data-stu-id="91123-151">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="91123-152">試行されたアドレス帳 Web クエリサービス要求の合計数。</span><span class="sxs-lookup"><span data-stu-id="91123-152">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91123-153">ABS 呼び出しが成功しました</span><span class="sxs-lookup"><span data-stu-id="91123-153">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="91123-154">成功した応答コードを返したアドレス帳 Web クエリサービス要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="91123-154">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91123-155">ABS 呼び出しに失敗しました</span><span class="sxs-lookup"><span data-stu-id="91123-155">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="91123-156">エラー応答コードを返したアドレス帳 Web クエリサービス要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="91123-156">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="91123-157">**配布リスト (DL) の情報**</span><span class="sxs-lookup"><span data-stu-id="91123-157">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91123-158"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="91123-158"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="91123-159"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="91123-159"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91123-160">呼び出しの試行</span><span class="sxs-lookup"><span data-stu-id="91123-160">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="91123-161">試行された配布リスト展開 (DLX) web サービス要求の合計数。</span><span class="sxs-lookup"><span data-stu-id="91123-161">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91123-162">成功した通話</span><span class="sxs-lookup"><span data-stu-id="91123-162">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="91123-163">成功した応答コードを返した DLX web サービス要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="91123-163">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91123-164">失敗した通話</span><span class="sxs-lookup"><span data-stu-id="91123-164">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="91123-165">エラー応答コードを返した DLX web サービス要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="91123-165">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="91123-166">**VoIP の基本情報**</span><span class="sxs-lookup"><span data-stu-id="91123-166">**VoIP Basic Information**</span></span>

<span data-ttu-id="91123-167">以下のパフォーマンスカウンターは、これらのシナリオが有効になっている場合に、仲介サーバー、音声ビデオ会議サーバー、エッジサーバー、応答グループアプリケーション、および会議の自動応答の呼び出しを含む、すべてのボイスオーバー IP (VoIP) 呼び出しの番号を報告します。</span><span class="sxs-lookup"><span data-stu-id="91123-167">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91123-168"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="91123-168"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="91123-169"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="91123-169"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91123-170">アクティブな通話</span><span class="sxs-lookup"><span data-stu-id="91123-170">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="91123-171">現在実行中の着信/発信音声通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="91123-171">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91123-172">通話の終了</span><span class="sxs-lookup"><span data-stu-id="91123-172">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="91123-173">着信/発信音声呼び出しの合計数が既に終了しています。</span><span class="sxs-lookup"><span data-stu-id="91123-173">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91123-174">拒否した通話</span><span class="sxs-lookup"><span data-stu-id="91123-174">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="91123-175">辞退した着信音声通話の合計数です。</span><span class="sxs-lookup"><span data-stu-id="91123-175">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91123-176">着信/発信呼び出しの試行</span><span class="sxs-lookup"><span data-stu-id="91123-176">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="91123-177">試行された着信/発信音声通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="91123-177">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91123-178">確立された着信/発信呼び出し</span><span class="sxs-lookup"><span data-stu-id="91123-178">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="91123-179">確立された着信/発信音声通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="91123-179">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91123-180">着信受信 NNN</span><span class="sxs-lookup"><span data-stu-id="91123-180">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="91123-181">サーバーから受信した nnn 応答コードの合計数です。</span><span class="sxs-lookup"><span data-stu-id="91123-181">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91123-182">VoIP パススルー率 (%)</span><span class="sxs-lookup"><span data-stu-id="91123-182">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="91123-183">試行された合計通話数/合計試行回数。</span><span class="sxs-lookup"><span data-stu-id="91123-183">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="91123-184">**応答グループサービスの呼び出し情報**</span><span class="sxs-lookup"><span data-stu-id="91123-184">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91123-185"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="91123-185"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="91123-186"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="91123-186"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91123-187">アクティブな通話</span><span class="sxs-lookup"><span data-stu-id="91123-187">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="91123-188">応答グループアプリケーションへのアクティブな呼び出しの合計数。</span><span class="sxs-lookup"><span data-stu-id="91123-188">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91123-189">呼び出しの試行</span><span class="sxs-lookup"><span data-stu-id="91123-189">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="91123-190">試行された通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="91123-190">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="91123-191">**インスタントメッセージング (IM) の呼び出し情報**</span><span class="sxs-lookup"><span data-stu-id="91123-191">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91123-192"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="91123-192"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="91123-193"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="91123-193"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91123-194">アクティブな通話</span><span class="sxs-lookup"><span data-stu-id="91123-194">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="91123-195">進行中の着信/発信インスタントメッセージング呼び出しの総数です。</span><span class="sxs-lookup"><span data-stu-id="91123-195">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91123-196">通話の終了</span><span class="sxs-lookup"><span data-stu-id="91123-196">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="91123-197">受信/送信されたインスタントメッセージング呼び出しの合計数が既に終了しています。</span><span class="sxs-lookup"><span data-stu-id="91123-197">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91123-198">着信受信 NNN</span><span class="sxs-lookup"><span data-stu-id="91123-198">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="91123-199">サーバーから受信した nnn 応答コードの合計数です。</span><span class="sxs-lookup"><span data-stu-id="91123-199">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91123-200">受信/送信された IM メッセージ</span><span class="sxs-lookup"><span data-stu-id="91123-200">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="91123-201">すべてのセッションで受信または送信されたメッセージの合計数。</span><span class="sxs-lookup"><span data-stu-id="91123-201">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91123-202">着信/発信呼び出しの試行</span><span class="sxs-lookup"><span data-stu-id="91123-202">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="91123-203">試行された着信/発信インスタントメッセージ呼び出しの合計数です。</span><span class="sxs-lookup"><span data-stu-id="91123-203">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91123-204">確立された着信/発信呼び出し</span><span class="sxs-lookup"><span data-stu-id="91123-204">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="91123-205">確立された着信/発信インスタントメッセージ呼び出しの合計数です。</span><span class="sxs-lookup"><span data-stu-id="91123-205">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="91123-206">**アプリ共有の呼び出し情報**</span><span class="sxs-lookup"><span data-stu-id="91123-206">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91123-207"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="91123-207"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="91123-208"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="91123-208"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91123-209">アクティブな通話</span><span class="sxs-lookup"><span data-stu-id="91123-209">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="91123-210">進行中または送信中のアプリケーション共有通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="91123-210">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91123-211">通話の終了</span><span class="sxs-lookup"><span data-stu-id="91123-211">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="91123-212">受信/送信アプリケーション共有呼び出しの合計数が既に終了しています。</span><span class="sxs-lookup"><span data-stu-id="91123-212">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91123-213">着信受信 NNN</span><span class="sxs-lookup"><span data-stu-id="91123-213">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="91123-214">サーバーから受信した nnn 応答コードの合計数です。</span><span class="sxs-lookup"><span data-stu-id="91123-214">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91123-215">着信/発信呼び出しの試行</span><span class="sxs-lookup"><span data-stu-id="91123-215">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="91123-216">試行された着信/送信アプリケーション共有の通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="91123-216">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91123-217">確立された着信/発信呼び出し</span><span class="sxs-lookup"><span data-stu-id="91123-217">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="91123-218">確立された着信/送信アプリケーション共有の呼び出しの合計数です。</span><span class="sxs-lookup"><span data-stu-id="91123-218">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="91123-219">**CAA の呼び出し情報**</span><span class="sxs-lookup"><span data-stu-id="91123-219">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91123-220"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="91123-220"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="91123-221"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="91123-221"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91123-222">アクティブな通話</span><span class="sxs-lookup"><span data-stu-id="91123-222">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="91123-223">現在進行中の着信/発信公衆交換電話網 (PSTN) 通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="91123-223">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91123-224">通話の終了</span><span class="sxs-lookup"><span data-stu-id="91123-224">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="91123-225">既に終了した着信/発信 PSTN 通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="91123-225">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91123-226">着信/発信呼び出しの試行</span><span class="sxs-lookup"><span data-stu-id="91123-226">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="91123-227">試行された着信/発信 PSTN 通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="91123-227">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91123-228">確立された着信/発信呼び出し</span><span class="sxs-lookup"><span data-stu-id="91123-228">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="91123-229">確立された着信/発信 PSTN 呼び出しの合計数です。</span><span class="sxs-lookup"><span data-stu-id="91123-229">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="91123-230">**会議情報**</span><span class="sxs-lookup"><span data-stu-id="91123-230">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91123-231"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="91123-231"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="91123-232"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="91123-232"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91123-233">アクティブなインスタントメッセージング会議</span><span class="sxs-lookup"><span data-stu-id="91123-233">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="91123-234">進行中のインスタントメッセージ会議の合計数。</span><span class="sxs-lookup"><span data-stu-id="91123-234">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91123-235">アクティブな音声ビデオ会議</span><span class="sxs-lookup"><span data-stu-id="91123-235">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="91123-236">進行中の音声ビデオ (A/V) 会議の合計数。</span><span class="sxs-lookup"><span data-stu-id="91123-236">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91123-237">アクティブなアプリケーション共有会議</span><span class="sxs-lookup"><span data-stu-id="91123-237">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="91123-238">進行中のアプリケーション共有会議の合計数。</span><span class="sxs-lookup"><span data-stu-id="91123-238">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91123-239">参加者数</span><span class="sxs-lookup"><span data-stu-id="91123-239">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="91123-240">現在、電話会議に接続している参加者の総数です。</span><span class="sxs-lookup"><span data-stu-id="91123-240">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91123-241">会議のスケジュールエラー</span><span class="sxs-lookup"><span data-stu-id="91123-241">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="91123-242">会議を計画しているときに失敗した回数の合計。</span><span class="sxs-lookup"><span data-stu-id="91123-242">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91123-243">会議の参加エラー</span><span class="sxs-lookup"><span data-stu-id="91123-243">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="91123-244">電話会議に接続しようとしたときに発生したエラーの合計数です。</span><span class="sxs-lookup"><span data-stu-id="91123-244">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="91123-245">**UCWA クライアントカウンター**</span><span class="sxs-lookup"><span data-stu-id="91123-245">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91123-246"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="91123-246"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="91123-247"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="91123-247"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91123-248">成功した IMMCU の結合の合計数</span><span class="sxs-lookup"><span data-stu-id="91123-248">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="91123-249">参加したインスタントメッセージ会議の合計数。</span><span class="sxs-lookup"><span data-stu-id="91123-249">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91123-250">成功した DMCU 結合の合計数</span><span class="sxs-lookup"><span data-stu-id="91123-250">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="91123-251">参加した音声ビデオ会議の合計数。</span><span class="sxs-lookup"><span data-stu-id="91123-251">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

