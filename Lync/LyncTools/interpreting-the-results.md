---
title: 結果の解釈
description: 結果の解釈。
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
ms.openlocfilehash: b8342a1ec1e15e42852fc5293f87342e98587a60
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565343"
---
# <a name="interpreting-the-results"></a><span data-ttu-id="58c99-103">結果の解釈</span><span class="sxs-lookup"><span data-stu-id="58c99-103">Interpreting the Results</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58c99-104">_**トピックの最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="58c99-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="58c99-105">Lync Server 2013 ストレスおよびパフォーマンスツール (LyncPerfTool.exe) には、クライアントの動作と問題が発生しているかどうかを理解するために使用できるカウンターが多数あります。</span><span class="sxs-lookup"><span data-stu-id="58c99-105">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="58c99-106">クライアントカウンター</span><span class="sxs-lookup"><span data-stu-id="58c99-106">Client Counters</span></span>

<span data-ttu-id="58c99-107">実行されている LyncPerfTool.exe の各インスタンスには、カウンターの個別のインスタンスがあります。</span><span class="sxs-lookup"><span data-stu-id="58c99-107">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="58c99-108">各インスタンスには、プロセス ID で名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="58c99-108">Each instance is named by its process ID.</span></span>

<span data-ttu-id="58c99-109">クライアントが過負荷になっている場合は、問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="58c99-109">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="58c99-110">これらの問題を回避するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="58c99-110">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="58c99-111">クライアントコンピューター上の CPU とメモリの使用状況を監視します。</span><span class="sxs-lookup"><span data-stu-id="58c99-111">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="58c99-112">CPU が90% を超えている場合は、ユーザーの数を減らします。</span><span class="sxs-lookup"><span data-stu-id="58c99-112">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="58c99-113">メモリフットプリントが高い場合は、ページファイルのサイズが十分でないと、問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="58c99-113">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="58c99-114">コミットチャージがコンピューターの制限に達していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="58c99-114">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="58c99-115">メモリの制限を使用している場合は、ページファイルのサイズを大きくするか、ユーザーの数を減らすことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="58c99-115">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="58c99-116">次の表に、LyncPerfTool の主要なパフォーマンスカウンターの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="58c99-116">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="58c99-117">**一般的な情報**</span><span class="sxs-lookup"><span data-stu-id="58c99-117">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58c99-118"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="58c99-118"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="58c99-119"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="58c99-119"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58c99-120">所要時間 (分単位)</span><span class="sxs-lookup"><span data-stu-id="58c99-120">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="58c99-121">プロセスが開始されてからの経過時間。</span><span class="sxs-lookup"><span data-stu-id="58c99-121">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58c99-122">アクティブなエンドポイント</span><span class="sxs-lookup"><span data-stu-id="58c99-122">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="58c99-123">サーバーに現在接続されているエンドポイントの数。</span><span class="sxs-lookup"><span data-stu-id="58c99-123">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58c99-124">失敗したログオン</span><span class="sxs-lookup"><span data-stu-id="58c99-124">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="58c99-125">エンドポイントのサインインの失敗の合計数です。</span><span class="sxs-lookup"><span data-stu-id="58c99-125">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58c99-126">ログオン試行</span><span class="sxs-lookup"><span data-stu-id="58c99-126">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="58c99-127">エンドポイントのサインイン試行の合計数です。</span><span class="sxs-lookup"><span data-stu-id="58c99-127">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58c99-128">エンドポイント切断</span><span class="sxs-lookup"><span data-stu-id="58c99-128">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="58c99-129">切断されたエンドポイントの合計数です。</span><span class="sxs-lookup"><span data-stu-id="58c99-129">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="58c99-130">**プレゼンス情報**</span><span class="sxs-lookup"><span data-stu-id="58c99-130">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58c99-131"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="58c99-131"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="58c99-132"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="58c99-132"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58c99-133">SetPresence 呼び出し</span><span class="sxs-lookup"><span data-stu-id="58c99-133">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="58c99-134">プレゼンス変更の試行回数の合計。</span><span class="sxs-lookup"><span data-stu-id="58c99-134">Total number of presence change attempts.</span></span> <span data-ttu-id="58c99-135">プレゼンス変更の種類が異なる場合は、SetPresence (プレゼンスの種類) Calls Performance Counter を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58c99-135">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58c99-136">SetPresence に対する NNN 応答</span><span class="sxs-lookup"><span data-stu-id="58c99-136">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="58c99-137">サーバーから受信した nnn 応答コードの合計数です。</span><span class="sxs-lookup"><span data-stu-id="58c99-137">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58c99-138">GetPresence 呼び出し</span><span class="sxs-lookup"><span data-stu-id="58c99-138">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="58c99-139">プレゼンス要求の取得の試行回数の合計。</span><span class="sxs-lookup"><span data-stu-id="58c99-139">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58c99-140">GetPresence に対する NNN 応答</span><span class="sxs-lookup"><span data-stu-id="58c99-140">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="58c99-141">サーバーから受信した nnn 応答コードの合計数です。</span><span class="sxs-lookup"><span data-stu-id="58c99-141">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="58c99-142">**アドレス帳サービス情報**</span><span class="sxs-lookup"><span data-stu-id="58c99-142">**Address Book service Information**</span></span>

<span data-ttu-id="58c99-143">このカテゴリには、アドレス帳サービス (ABS) ファイルのダウンロードとアドレス帳の Web クエリサービス要求を監視するために使用されるカウンターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="58c99-143">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58c99-144"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="58c99-144"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="58c99-145"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="58c99-145"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58c99-146">ABS フル/差分ファイルのダウンロードの試行</span><span class="sxs-lookup"><span data-stu-id="58c99-146">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="58c99-147">試行された完全または差分ファイルのダウンロード要求の総数。</span><span class="sxs-lookup"><span data-stu-id="58c99-147">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58c99-148">ABS 完全または差分ファイルのダウンロードに成功しました</span><span class="sxs-lookup"><span data-stu-id="58c99-148">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="58c99-149">試行された完全または差分ファイルのダウンロード要求の総数。</span><span class="sxs-lookup"><span data-stu-id="58c99-149">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58c99-150">アドレス帳 Web クエリサービス関連カウンター</span><span class="sxs-lookup"><span data-stu-id="58c99-150">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="58c99-151">アドレス帳ファイルのダウンロード関連カウンター。</span><span class="sxs-lookup"><span data-stu-id="58c99-151">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58c99-152">ABS 呼び出しが試行されました</span><span class="sxs-lookup"><span data-stu-id="58c99-152">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="58c99-153">試行されたアドレス帳 Web クエリサービス要求の合計数。</span><span class="sxs-lookup"><span data-stu-id="58c99-153">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58c99-154">ABS 呼び出しが成功しました</span><span class="sxs-lookup"><span data-stu-id="58c99-154">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="58c99-155">成功した応答コードを返したアドレス帳 Web クエリサービス要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="58c99-155">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58c99-156">ABS 呼び出しに失敗しました</span><span class="sxs-lookup"><span data-stu-id="58c99-156">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="58c99-157">エラー応答コードを返したアドレス帳 Web クエリサービス要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="58c99-157">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="58c99-158">**配布リスト (DL) の情報**</span><span class="sxs-lookup"><span data-stu-id="58c99-158">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58c99-159"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="58c99-159"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="58c99-160"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="58c99-160"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58c99-161">呼び出しの試行</span><span class="sxs-lookup"><span data-stu-id="58c99-161">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="58c99-162">試行された配布リスト展開 (DLX) web サービス要求の合計数。</span><span class="sxs-lookup"><span data-stu-id="58c99-162">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58c99-163">成功した通話</span><span class="sxs-lookup"><span data-stu-id="58c99-163">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="58c99-164">成功した応答コードを返した DLX web サービス要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="58c99-164">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58c99-165">失敗した通話</span><span class="sxs-lookup"><span data-stu-id="58c99-165">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="58c99-166">エラー応答コードを返した DLX web サービス要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="58c99-166">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="58c99-167">**VoIP の基本情報**</span><span class="sxs-lookup"><span data-stu-id="58c99-167">**VoIP Basic Information**</span></span>

<span data-ttu-id="58c99-168">以下のパフォーマンスカウンターは、これらのシナリオが有効になっている場合に、仲介サーバー、音声ビデオ会議サーバー、エッジサーバー、応答グループアプリケーション、および会議の自動応答の呼び出しを含む、すべてのボイスオーバー IP (VoIP) 呼び出しの番号を報告します。</span><span class="sxs-lookup"><span data-stu-id="58c99-168">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58c99-169"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="58c99-169"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="58c99-170"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="58c99-170"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58c99-171">アクティブな通話</span><span class="sxs-lookup"><span data-stu-id="58c99-171">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="58c99-172">現在実行中の着信/発信音声通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="58c99-172">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58c99-173">通話の終了</span><span class="sxs-lookup"><span data-stu-id="58c99-173">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="58c99-174">着信/発信音声呼び出しの合計数が既に終了しています。</span><span class="sxs-lookup"><span data-stu-id="58c99-174">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58c99-175">拒否した通話</span><span class="sxs-lookup"><span data-stu-id="58c99-175">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="58c99-176">辞退した着信音声通話の合計数です。</span><span class="sxs-lookup"><span data-stu-id="58c99-176">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58c99-177">着信/発信呼び出しの試行</span><span class="sxs-lookup"><span data-stu-id="58c99-177">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="58c99-178">試行された着信/発信音声通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="58c99-178">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58c99-179">確立された着信/発信呼び出し</span><span class="sxs-lookup"><span data-stu-id="58c99-179">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="58c99-180">確立された着信/発信音声通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="58c99-180">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58c99-181">着信受信 NNN</span><span class="sxs-lookup"><span data-stu-id="58c99-181">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="58c99-182">サーバーから受信した nnn 応答コードの合計数です。</span><span class="sxs-lookup"><span data-stu-id="58c99-182">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58c99-183">VoIP パススルー率 (%)</span><span class="sxs-lookup"><span data-stu-id="58c99-183">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="58c99-184">試行された合計通話数/合計試行回数。</span><span class="sxs-lookup"><span data-stu-id="58c99-184">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="58c99-185">**応答グループサービスの呼び出し情報**</span><span class="sxs-lookup"><span data-stu-id="58c99-185">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58c99-186"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="58c99-186"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="58c99-187"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="58c99-187"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58c99-188">アクティブな通話</span><span class="sxs-lookup"><span data-stu-id="58c99-188">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="58c99-189">応答グループアプリケーションへのアクティブな呼び出しの合計数。</span><span class="sxs-lookup"><span data-stu-id="58c99-189">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58c99-190">呼び出しの試行</span><span class="sxs-lookup"><span data-stu-id="58c99-190">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="58c99-191">試行された通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="58c99-191">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="58c99-192">**インスタントメッセージング (IM) の呼び出し情報**</span><span class="sxs-lookup"><span data-stu-id="58c99-192">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58c99-193"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="58c99-193"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="58c99-194"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="58c99-194"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58c99-195">アクティブな通話</span><span class="sxs-lookup"><span data-stu-id="58c99-195">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="58c99-196">進行中の着信/発信インスタントメッセージング呼び出しの総数です。</span><span class="sxs-lookup"><span data-stu-id="58c99-196">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58c99-197">通話の終了</span><span class="sxs-lookup"><span data-stu-id="58c99-197">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="58c99-198">受信/送信されたインスタントメッセージング呼び出しの合計数が既に終了しています。</span><span class="sxs-lookup"><span data-stu-id="58c99-198">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58c99-199">着信受信 NNN</span><span class="sxs-lookup"><span data-stu-id="58c99-199">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="58c99-200">サーバーから受信した nnn 応答コードの合計数です。</span><span class="sxs-lookup"><span data-stu-id="58c99-200">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58c99-201">受信/送信された IM メッセージ</span><span class="sxs-lookup"><span data-stu-id="58c99-201">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="58c99-202">すべてのセッションで受信または送信されたメッセージの合計数。</span><span class="sxs-lookup"><span data-stu-id="58c99-202">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58c99-203">着信/発信呼び出しの試行</span><span class="sxs-lookup"><span data-stu-id="58c99-203">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="58c99-204">試行された着信/発信インスタントメッセージ呼び出しの合計数です。</span><span class="sxs-lookup"><span data-stu-id="58c99-204">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58c99-205">確立された着信/発信呼び出し</span><span class="sxs-lookup"><span data-stu-id="58c99-205">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="58c99-206">確立された着信/発信インスタントメッセージ呼び出しの合計数です。</span><span class="sxs-lookup"><span data-stu-id="58c99-206">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="58c99-207">**アプリ共有の呼び出し情報**</span><span class="sxs-lookup"><span data-stu-id="58c99-207">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58c99-208"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="58c99-208"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="58c99-209"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="58c99-209"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58c99-210">アクティブな通話</span><span class="sxs-lookup"><span data-stu-id="58c99-210">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="58c99-211">進行中または送信中のアプリケーション共有通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="58c99-211">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58c99-212">通話の終了</span><span class="sxs-lookup"><span data-stu-id="58c99-212">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="58c99-213">受信/送信アプリケーション共有呼び出しの合計数が既に終了しています。</span><span class="sxs-lookup"><span data-stu-id="58c99-213">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58c99-214">着信受信 NNN</span><span class="sxs-lookup"><span data-stu-id="58c99-214">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="58c99-215">サーバーから受信した nnn 応答コードの合計数です。</span><span class="sxs-lookup"><span data-stu-id="58c99-215">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58c99-216">着信/発信呼び出しの試行</span><span class="sxs-lookup"><span data-stu-id="58c99-216">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="58c99-217">試行された着信/送信アプリケーション共有の通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="58c99-217">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58c99-218">確立された着信/発信呼び出し</span><span class="sxs-lookup"><span data-stu-id="58c99-218">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="58c99-219">確立された着信/送信アプリケーション共有の呼び出しの合計数です。</span><span class="sxs-lookup"><span data-stu-id="58c99-219">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="58c99-220">**CAA の呼び出し情報**</span><span class="sxs-lookup"><span data-stu-id="58c99-220">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58c99-221"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="58c99-221"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="58c99-222"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="58c99-222"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58c99-223">アクティブな通話</span><span class="sxs-lookup"><span data-stu-id="58c99-223">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="58c99-224">現在進行中の着信/発信公衆交換電話網 (PSTN) 通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="58c99-224">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58c99-225">通話の終了</span><span class="sxs-lookup"><span data-stu-id="58c99-225">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="58c99-226">既に終了した着信/発信 PSTN 通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="58c99-226">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58c99-227">着信/発信呼び出しの試行</span><span class="sxs-lookup"><span data-stu-id="58c99-227">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="58c99-228">試行された着信/発信 PSTN 通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="58c99-228">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58c99-229">確立された着信/発信呼び出し</span><span class="sxs-lookup"><span data-stu-id="58c99-229">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="58c99-230">確立された着信/発信 PSTN 呼び出しの合計数です。</span><span class="sxs-lookup"><span data-stu-id="58c99-230">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="58c99-231">**会議情報**</span><span class="sxs-lookup"><span data-stu-id="58c99-231">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58c99-232"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="58c99-232"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="58c99-233"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="58c99-233"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58c99-234">アクティブなインスタントメッセージング会議</span><span class="sxs-lookup"><span data-stu-id="58c99-234">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="58c99-235">進行中のインスタントメッセージ会議の合計数。</span><span class="sxs-lookup"><span data-stu-id="58c99-235">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58c99-236">アクティブな音声ビデオ会議</span><span class="sxs-lookup"><span data-stu-id="58c99-236">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="58c99-237">進行中の音声ビデオ (A/V) 会議の合計数。</span><span class="sxs-lookup"><span data-stu-id="58c99-237">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58c99-238">アクティブなアプリケーション共有会議</span><span class="sxs-lookup"><span data-stu-id="58c99-238">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="58c99-239">進行中のアプリケーション共有会議の合計数。</span><span class="sxs-lookup"><span data-stu-id="58c99-239">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58c99-240">参加者数</span><span class="sxs-lookup"><span data-stu-id="58c99-240">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="58c99-241">現在、電話会議に接続している参加者の総数です。</span><span class="sxs-lookup"><span data-stu-id="58c99-241">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58c99-242">会議のスケジュールエラー</span><span class="sxs-lookup"><span data-stu-id="58c99-242">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="58c99-243">会議を計画しているときに失敗した回数の合計。</span><span class="sxs-lookup"><span data-stu-id="58c99-243">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58c99-244">会議の参加エラー</span><span class="sxs-lookup"><span data-stu-id="58c99-244">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="58c99-245">電話会議に接続しようとしたときに発生したエラーの合計数です。</span><span class="sxs-lookup"><span data-stu-id="58c99-245">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="58c99-246">**UCWA クライアントカウンター**</span><span class="sxs-lookup"><span data-stu-id="58c99-246">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58c99-247"><strong>パフォーマンス カウンター</strong></span><span class="sxs-lookup"><span data-stu-id="58c99-247"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="58c99-248"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="58c99-248"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58c99-249">成功した IMMCU の結合の合計数</span><span class="sxs-lookup"><span data-stu-id="58c99-249">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="58c99-250">参加したインスタントメッセージ会議の合計数。</span><span class="sxs-lookup"><span data-stu-id="58c99-250">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58c99-251">成功した DMCU 結合の合計数</span><span class="sxs-lookup"><span data-stu-id="58c99-251">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="58c99-252">参加した音声ビデオ会議の合計数。</span><span class="sxs-lookup"><span data-stu-id="58c99-252">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

