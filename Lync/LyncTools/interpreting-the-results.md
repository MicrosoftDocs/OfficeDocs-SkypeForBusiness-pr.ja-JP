---
title: 結果を解釈する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0a3dc473765a67db2e09f5a56db14b1ea8a41a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a><span data-ttu-id="9a059-102">結果を解釈する</span><span class="sxs-lookup"><span data-stu-id="9a059-102">Interpreting the Results</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a059-103">_**最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="9a059-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="9a059-104">Lync Server 2013 応力/パフォーマンスツール (LyncPerfTool) には、クライアントが何を実行しているのか、問題が発生しているかを理解するために使用できる多くのカウンターがあります。</span><span class="sxs-lookup"><span data-stu-id="9a059-104">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="9a059-105">クライアントカウンター</span><span class="sxs-lookup"><span data-stu-id="9a059-105">Client Counters</span></span>

<span data-ttu-id="9a059-106">実行されている LyncPerfTool の各インスタンスには、カウンターの個別のインスタンスがあります。</span><span class="sxs-lookup"><span data-stu-id="9a059-106">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="9a059-107">各インスタンスには、プロセス ID で名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="9a059-107">Each instance is named by its process ID.</span></span>

<span data-ttu-id="9a059-108">クライアントが過負荷になっていると、問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9a059-108">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="9a059-109">これらの問題を回避するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9a059-109">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="9a059-110">クライアントコンピューターの CPU とメモリ使用量を監視します。</span><span class="sxs-lookup"><span data-stu-id="9a059-110">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="9a059-111">CPU が常に 90% を超えている場合は、ユーザーの数を減らします。</span><span class="sxs-lookup"><span data-stu-id="9a059-111">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="9a059-112">メモリフットプリントが高すぎる場合は、ページファイルが十分でない場合に問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9a059-112">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="9a059-113">コミットチャージがコンピューターの制限に達していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a059-113">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="9a059-114">メモリの制限を使用している場合は、ページファイルのサイズを大きくするか、ユーザーの数を減らすことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="9a059-114">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="9a059-115">次の表では、LyncPerfTool のパフォーマンスカウンターの主要な一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="9a059-115">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="9a059-116">**一般的な情報**</span><span class="sxs-lookup"><span data-stu-id="9a059-116">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9a059-117"><strong>パフォーマンスカウンター</strong></span><span class="sxs-lookup"><span data-stu-id="9a059-117"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="9a059-118"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="9a059-118"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a059-119">分数で費やした時間</span><span class="sxs-lookup"><span data-stu-id="9a059-119">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="9a059-120">プロセスが開始されてから経過した時間。</span><span class="sxs-lookup"><span data-stu-id="9a059-120">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a059-121">アクティブなエンドポイント</span><span class="sxs-lookup"><span data-stu-id="9a059-121">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="9a059-122">現在サーバーに接続されているエンドポイントの数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-122">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a059-123">失敗したログオン</span><span class="sxs-lookup"><span data-stu-id="9a059-123">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="9a059-124">エンドポイントのサインインエラーの合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-124">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a059-125">ログオン試行</span><span class="sxs-lookup"><span data-stu-id="9a059-125">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="9a059-126">エンドポイントのサインイン試行の合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-126">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a059-127">エンドポイントが切断されました</span><span class="sxs-lookup"><span data-stu-id="9a059-127">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="9a059-128">切断されたエンドポイントの合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-128">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9a059-129">**プレゼンス情報**</span><span class="sxs-lookup"><span data-stu-id="9a059-129">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9a059-130"><strong>パフォーマンスカウンター</strong></span><span class="sxs-lookup"><span data-stu-id="9a059-130"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="9a059-131"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="9a059-131"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a059-132">SetPresence 通話</span><span class="sxs-lookup"><span data-stu-id="9a059-132">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="9a059-133">プレゼンス変更の試行回数の合計です。</span><span class="sxs-lookup"><span data-stu-id="9a059-133">Total number of presence change attempts.</span></span> <span data-ttu-id="9a059-134">さまざまな種類のプレゼンス変更については、「SetPresence (プレゼンスの種類) 呼び出しのパフォーマンスカウンター」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a059-134">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a059-135">SetPresence の NNN 応答</span><span class="sxs-lookup"><span data-stu-id="9a059-135">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="9a059-136">サーバーから受信した nnn 応答コードの合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-136">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a059-137">GetPresence 通話</span><span class="sxs-lookup"><span data-stu-id="9a059-137">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="9a059-138">プレゼンス要求の取得試行の合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-138">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a059-139">GetPresence に対する NNN の応答</span><span class="sxs-lookup"><span data-stu-id="9a059-139">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="9a059-140">サーバーから受信した nnn 応答コードの合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-140">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9a059-141">**アドレス帳サービス情報**</span><span class="sxs-lookup"><span data-stu-id="9a059-141">**Address Book service Information**</span></span>

<span data-ttu-id="9a059-142">このカテゴリには、アドレス帳サービス (ABS) ファイルのダウンロードとアドレス帳の Web クエリサービス要求を監視するために使用されるカウンターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9a059-142">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9a059-143"><strong>パフォーマンスカウンター</strong></span><span class="sxs-lookup"><span data-stu-id="9a059-143"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="9a059-144"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="9a059-144"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a059-145">完全なフル/差分ファイルのダウンロードが試行される</span><span class="sxs-lookup"><span data-stu-id="9a059-145">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="9a059-146">試行されたフルまたは差分ファイルのダウンロード要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-146">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a059-147">ABS フル/差分ファイルのダウンロードに成功しました</span><span class="sxs-lookup"><span data-stu-id="9a059-147">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="9a059-148">試行されたフルまたは差分ファイルのダウンロード要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-148">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a059-149">アドレス帳 Web クエリサービスに関連するカウンター</span><span class="sxs-lookup"><span data-stu-id="9a059-149">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="9a059-150">アドレス帳ファイルのダウンロードに関連するカウンター。</span><span class="sxs-lookup"><span data-stu-id="9a059-150">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a059-151">ABS 呼び出しを実行しました</span><span class="sxs-lookup"><span data-stu-id="9a059-151">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="9a059-152">試行されたアドレス帳 Web クエリサービス要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-152">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a059-153">ABS 呼び出しに成功しました</span><span class="sxs-lookup"><span data-stu-id="9a059-153">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="9a059-154">成功応答コードを返した、アドレス帳 Web クエリサービス要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-154">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a059-155">ABS 呼び出しに失敗しました</span><span class="sxs-lookup"><span data-stu-id="9a059-155">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="9a059-156">エラー応答コードを返した、アドレス帳 Web クエリサービス要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-156">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9a059-157">**配布リスト (DL) 情報**</span><span class="sxs-lookup"><span data-stu-id="9a059-157">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9a059-158"><strong>パフォーマンスカウンター</strong></span><span class="sxs-lookup"><span data-stu-id="9a059-158"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="9a059-159"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="9a059-159"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a059-160">通話を発信しました</span><span class="sxs-lookup"><span data-stu-id="9a059-160">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="9a059-161">試みた配布リスト展開 (DLX) web サービス要求の合計数。</span><span class="sxs-lookup"><span data-stu-id="9a059-161">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a059-162">通話成功</span><span class="sxs-lookup"><span data-stu-id="9a059-162">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="9a059-163">成功した応答コードを返した DLX web サービス要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-163">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a059-164">通話失敗</span><span class="sxs-lookup"><span data-stu-id="9a059-164">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="9a059-165">エラー応答コードを返した DLX web サービス要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-165">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9a059-166">**VoIP の基本情報**</span><span class="sxs-lookup"><span data-stu-id="9a059-166">**VoIP Basic Information**</span></span>

<span data-ttu-id="9a059-167">以下のパフォーマンスカウンターには、これらのシナリオが有効な場合に、仲介サーバー、A/V 会議サーバー、エッジサーバー、応答グループアプリケーション、会議の自動応答など、すべてのボイスオーバー IP (VoIP) 通話の番号が報告されます。</span><span class="sxs-lookup"><span data-stu-id="9a059-167">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9a059-168"><strong>パフォーマンスカウンター</strong></span><span class="sxs-lookup"><span data-stu-id="9a059-168"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="9a059-169"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="9a059-169"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a059-170">アクティブな通話</span><span class="sxs-lookup"><span data-stu-id="9a059-170">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="9a059-171">現在進行中の着信/発信音声通話の合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-171">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a059-172">通話終了</span><span class="sxs-lookup"><span data-stu-id="9a059-172">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="9a059-173">着信/発信の音声通話の合計数は既に終了しています。</span><span class="sxs-lookup"><span data-stu-id="9a059-173">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a059-174">通話拒否</span><span class="sxs-lookup"><span data-stu-id="9a059-174">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="9a059-175">拒否された音声通話の合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-175">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a059-176">着信/発信通話を発信しました</span><span class="sxs-lookup"><span data-stu-id="9a059-176">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="9a059-177">発信した音声通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="9a059-177">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a059-178">確立された着信/発信通話</span><span class="sxs-lookup"><span data-stu-id="9a059-178">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="9a059-179">送受信された音声通話の合計数が設定されました。</span><span class="sxs-lookup"><span data-stu-id="9a059-179">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a059-180">通話受信 NNN</span><span class="sxs-lookup"><span data-stu-id="9a059-180">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="9a059-181">サーバーから受信した nnn 応答コードの合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-181">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a059-182">VoIP パスレート (%)</span><span class="sxs-lookup"><span data-stu-id="9a059-182">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="9a059-183">発信された通話合計発信/合計通話が完了しました。</span><span class="sxs-lookup"><span data-stu-id="9a059-183">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9a059-184">**応答グループサービスの通話情報**</span><span class="sxs-lookup"><span data-stu-id="9a059-184">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9a059-185"><strong>パフォーマンスカウンター</strong></span><span class="sxs-lookup"><span data-stu-id="9a059-185"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="9a059-186"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="9a059-186"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a059-187">アクティブな通話</span><span class="sxs-lookup"><span data-stu-id="9a059-187">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="9a059-188">応答グループアプリケーションへのアクティブな通話の合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-188">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a059-189">通話を発信しました</span><span class="sxs-lookup"><span data-stu-id="9a059-189">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="9a059-190">試行された通話の合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-190">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9a059-191">**インスタントメッセージング (IM) 通話情報**</span><span class="sxs-lookup"><span data-stu-id="9a059-191">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9a059-192"><strong>パフォーマンスカウンター</strong></span><span class="sxs-lookup"><span data-stu-id="9a059-192"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="9a059-193"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="9a059-193"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a059-194">アクティブな通話</span><span class="sxs-lookup"><span data-stu-id="9a059-194">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="9a059-195">進行中の着信/発信インスタントメッセージ通話の合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-195">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a059-196">通話終了</span><span class="sxs-lookup"><span data-stu-id="9a059-196">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="9a059-197">受信/送信されたインスタントメッセージの通話の合計数が既に終了しています。</span><span class="sxs-lookup"><span data-stu-id="9a059-197">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a059-198">通話受信 NNN</span><span class="sxs-lookup"><span data-stu-id="9a059-198">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="9a059-199">サーバーから受信した nnn 応答コードの合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-199">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a059-200">受信/送信された IM メッセージ</span><span class="sxs-lookup"><span data-stu-id="9a059-200">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="9a059-201">すべてのセッションで受信または送信されたメッセージの合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-201">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a059-202">着信/発信通話を発信しました</span><span class="sxs-lookup"><span data-stu-id="9a059-202">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="9a059-203">発信したインスタントメッセージ通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="9a059-203">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a059-204">確立された着信/発信通話</span><span class="sxs-lookup"><span data-stu-id="9a059-204">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="9a059-205">確立された受信/送信インスタントメッセージの合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-205">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9a059-206">**アプリ共有の通話情報**</span><span class="sxs-lookup"><span data-stu-id="9a059-206">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9a059-207"><strong>パフォーマンスカウンター</strong></span><span class="sxs-lookup"><span data-stu-id="9a059-207"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="9a059-208"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="9a059-208"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a059-209">アクティブな通話</span><span class="sxs-lookup"><span data-stu-id="9a059-209">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="9a059-210">進行中の着信/送信アプリケーション共有通話の合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-210">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a059-211">通話終了</span><span class="sxs-lookup"><span data-stu-id="9a059-211">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="9a059-212">受信/送信アプリケーション共有通話の合計数が既に終了しています。</span><span class="sxs-lookup"><span data-stu-id="9a059-212">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a059-213">通話受信 NNN</span><span class="sxs-lookup"><span data-stu-id="9a059-213">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="9a059-214">サーバーから受信した nnn 応答コードの合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-214">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a059-215">着信/発信通話を発信しました</span><span class="sxs-lookup"><span data-stu-id="9a059-215">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="9a059-216">試行された受信/送信アプリケーション共有通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="9a059-216">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a059-217">確立された着信/発信通話</span><span class="sxs-lookup"><span data-stu-id="9a059-217">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="9a059-218">確立された受信/送信アプリケーション共有通話の合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-218">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9a059-219">**CAA を通話情報**</span><span class="sxs-lookup"><span data-stu-id="9a059-219">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9a059-220"><strong>パフォーマンスカウンター</strong></span><span class="sxs-lookup"><span data-stu-id="9a059-220"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="9a059-221"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="9a059-221"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a059-222">アクティブな通話</span><span class="sxs-lookup"><span data-stu-id="9a059-222">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="9a059-223">現在進行中の着信/発信公衆交換電話網 (PSTN) 通話の合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-223">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a059-224">通話終了</span><span class="sxs-lookup"><span data-stu-id="9a059-224">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="9a059-225">着信/発信された PSTN 通話の合計数は既に終了しています。</span><span class="sxs-lookup"><span data-stu-id="9a059-225">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a059-226">着信/発信通話を発信しました</span><span class="sxs-lookup"><span data-stu-id="9a059-226">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="9a059-227">試行された着信/発信の PSTN 通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="9a059-227">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a059-228">確立された着信/発信通話</span><span class="sxs-lookup"><span data-stu-id="9a059-228">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="9a059-229">確立された着信/発信 PSTN 通話の合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-229">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9a059-230">**会議情報**</span><span class="sxs-lookup"><span data-stu-id="9a059-230">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9a059-231"><strong>パフォーマンスカウンター</strong></span><span class="sxs-lookup"><span data-stu-id="9a059-231"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="9a059-232"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="9a059-232"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a059-233">アクティブなインスタントメッセージ会議</span><span class="sxs-lookup"><span data-stu-id="9a059-233">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="9a059-234">進行中のインスタントメッセージ会議の合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-234">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a059-235">アクティブな音声/ビデオ会議</span><span class="sxs-lookup"><span data-stu-id="9a059-235">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="9a059-236">進行中の音声/ビデオ (A/V) 会議の合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-236">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a059-237">アクティブなアプリケーション共有会議</span><span class="sxs-lookup"><span data-stu-id="9a059-237">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="9a059-238">進行中のアプリケーション共有会議の合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-238">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a059-239">参加者の数</span><span class="sxs-lookup"><span data-stu-id="9a059-239">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="9a059-240">現在会議に接続されている参加者の合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-240">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a059-241">会議のスケジュールエラー</span><span class="sxs-lookup"><span data-stu-id="9a059-241">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="9a059-242">会議をスケジュールしようとしたときに発生したエラーの合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-242">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a059-243">電話会議に参加できない</span><span class="sxs-lookup"><span data-stu-id="9a059-243">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="9a059-244">会議に接続しようとしているときに発生したエラーの合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-244">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9a059-245">**UCWA クライアントカウンター**</span><span class="sxs-lookup"><span data-stu-id="9a059-245">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9a059-246"><strong>パフォーマンスカウンター</strong></span><span class="sxs-lookup"><span data-stu-id="9a059-246"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="9a059-247"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="9a059-247"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a059-248">成功した IMMCU の結合の合計数</span><span class="sxs-lookup"><span data-stu-id="9a059-248">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="9a059-249">参加したインスタントメッセージ会議の合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-249">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a059-250">成功した DMCU 結合の合計数</span><span class="sxs-lookup"><span data-stu-id="9a059-250">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="9a059-251">参加した A/V 会議の合計数です。</span><span class="sxs-lookup"><span data-stu-id="9a059-251">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

