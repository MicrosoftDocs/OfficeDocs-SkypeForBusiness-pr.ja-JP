---
title: 'Lync Server 2013: 場所レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Report
ms:assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615035(v=OCS.15)
ms:contentKeyID: 48185641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e98107d4949a935cbef448e1a533bddb0f7c5dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513794"
---
# <a name="location-report-in-lync-server-2013"></a><span data-ttu-id="f14de-102">Lync Server 2013 の場所レポート</span><span class="sxs-lookup"><span data-stu-id="f14de-102">Location Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f14de-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f14de-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f14de-104">場所レポートは、通話品質指標に関する情報を、ネットワーク上の場所 (つまり、ネットワークサブネット) でグループ化して提供します。</span><span class="sxs-lookup"><span data-stu-id="f14de-104">The Location Report provides information about call quality metrics grouped by network location (that is, by network subnet).</span></span> <span data-ttu-id="f14de-105">ユーザーが呼び出しで問題が発生している場合は、このレポートを参考にして、問題が広範囲にあるか、または特定のネットワークセグメントに限定されているかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="f14de-105">If your users are experiencing problems with their calls, this report can help you determine if those problems are widespread or if they are largely confined to a given network segment.</span></span>

<div>

## <a name="accessing-the-location-report"></a><span data-ttu-id="f14de-106">場所レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="f14de-106">Accessing the Location Report</span></span>

<span data-ttu-id="f14de-107">場所レポートには、監視レポートのホームページからアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f14de-107">The Location Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="f14de-108">次のいずれかの指標クリックしてCall List Reportにドリルダウンできます。</span><span class="sxs-lookup"><span data-stu-id="f14de-108">You can drill down to the Call List Report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="f14de-109">[通話ボリューム]</span><span class="sxs-lookup"><span data-stu-id="f14de-109">Call volume</span></span>

  - <span data-ttu-id="f14de-110">[低品質通話のパーセンテージ]</span><span class="sxs-lookup"><span data-stu-id="f14de-110">Poor call percentage</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="f14de-111">フィルター</span><span class="sxs-lookup"><span data-stu-id="f14de-111">Filters</span></span>

<span data-ttu-id="f14de-112">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。</span><span class="sxs-lookup"><span data-stu-id="f14de-112">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="f14de-113">たとえば、場所レポートを使用すると、通話が発信された場所やワイヤレスまたは有線接続で通話が行われたかどうかなどのフィルター処理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f14de-113">For example, the Location Report enables you to filter on such things as the location where a call was originated or whether the call took place on a wireless or a wired connection.</span></span> <span data-ttu-id="f14de-114">また、データをグループ化する方法を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="f14de-114">You can also choose how data should be grouped.</span></span> <span data-ttu-id="f14de-115">この場合は、通話が、時間、日、週、または月を基準にグループ化されています。</span><span class="sxs-lookup"><span data-stu-id="f14de-115">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="f14de-116">次の表に、場所レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="f14de-116">The following table lists the filters that you can use with the Location Report.</span></span>

### <a name="location-report-filters"></a><span data-ttu-id="f14de-117">場所レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="f14de-117">Location Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f14de-118">名前</span><span class="sxs-lookup"><span data-stu-id="f14de-118">Name</span></span></th>
<th><span data-ttu-id="f14de-119">説明</span><span class="sxs-lookup"><span data-stu-id="f14de-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f14de-120"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="f14de-120"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="f14de-p104">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="f14de-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="f14de-123">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="f14de-123">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f14de-p105">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="f14de-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f14de-126">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f14de-126">7/7/2012</span></span></p>
<p><span data-ttu-id="f14de-127">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="f14de-127">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f14de-128">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f14de-128">7/3/2012</span></span></p>
<p><span data-ttu-id="f14de-129">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="f14de-129">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f14de-130"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="f14de-130"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="f14de-p106">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="f14de-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="f14de-133">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="f14de-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f14de-p107">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="f14de-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f14de-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f14de-136">7/7/2012</span></span></p>
<p><span data-ttu-id="f14de-137">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="f14de-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f14de-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f14de-138">7/3/2012</span></span></p>
<p><span data-ttu-id="f14de-139">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="f14de-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f14de-140"><strong>発信者の場所</strong></span><span class="sxs-lookup"><span data-stu-id="f14de-140"><strong>Caller location</strong></span></span></p></td>
<td><p><span data-ttu-id="f14de-141">通話を発信したユーザーの IP サブネット。</span><span class="sxs-lookup"><span data-stu-id="f14de-141">IP subnet of the user who placed the call.</span></span> <span data-ttu-id="f14de-142"><strong>[All]</strong>のみを選択して、すべてのサブネットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f14de-142">You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f14de-143"><strong>呼び出し先の場所</strong></span><span class="sxs-lookup"><span data-stu-id="f14de-143"><strong>Callee location</strong></span></span></p></td>
<td><p><span data-ttu-id="f14de-144">通話を受信したユーザーの IP サブネット。</span><span class="sxs-lookup"><span data-stu-id="f14de-144">IP subnet of the user who received the call.</span></span> <span data-ttu-id="f14de-145"><strong>[All]</strong>のみを選択して、すべてのサブネットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f14de-145">You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f14de-146">[<strong>ネットワークの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="f14de-146"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="f14de-p110">通話時にクライアントが接続したネットワークの種類を示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="f14de-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="f14de-149">[All]</span><span class="sxs-lookup"><span data-stu-id="f14de-149">[All]</span></span></p></li>
<li><p><span data-ttu-id="f14de-150">有線</span><span class="sxs-lookup"><span data-stu-id="f14de-150">Wired</span></span></p></li>
<li><p><span data-ttu-id="f14de-151">通信</span><span class="sxs-lookup"><span data-stu-id="f14de-151">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f14de-152"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="f14de-152"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="f14de-p111">通話時に外部クライアントが仮想プライベート ネットワーク (VPN) 接続を使用したかどうかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="f14de-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="f14de-155">[All]</span><span class="sxs-lookup"><span data-stu-id="f14de-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="f14de-156">VPN</span><span class="sxs-lookup"><span data-stu-id="f14de-156">VPN</span></span></p></li>
<li><p><span data-ttu-id="f14de-157">非 VPN</span><span class="sxs-lookup"><span data-stu-id="f14de-157">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="f14de-158">指標</span><span class="sxs-lookup"><span data-stu-id="f14de-158">Metrics</span></span>

<span data-ttu-id="f14de-159">次の表に、場所レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="f14de-159">The following table lists the information provided in the Location Report.</span></span>

### <a name="location-report-metrics"></a><span data-ttu-id="f14de-160">場所レポートの指標</span><span class="sxs-lookup"><span data-stu-id="f14de-160">Location Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f14de-161">名前</span><span class="sxs-lookup"><span data-stu-id="f14de-161">Name</span></span></th>
<th><span data-ttu-id="f14de-162">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="f14de-162">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f14de-163">説明</span><span class="sxs-lookup"><span data-stu-id="f14de-163">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f14de-164"><strong>発信者サブネット</strong></span><span class="sxs-lookup"><span data-stu-id="f14de-164"><strong>Caller subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="f14de-165">いいえ</span><span class="sxs-lookup"><span data-stu-id="f14de-165">No</span></span></p></td>
<td><p><span data-ttu-id="f14de-166">通話を発信したユーザーの IP サブネット。</span><span class="sxs-lookup"><span data-stu-id="f14de-166">IP subnet of the user who placed the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f14de-167"><strong>呼び出し先サブネット</strong></span><span class="sxs-lookup"><span data-stu-id="f14de-167"><strong>Callee subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="f14de-168">いいえ</span><span class="sxs-lookup"><span data-stu-id="f14de-168">No</span></span></p></td>
<td><p><span data-ttu-id="f14de-169">通話を受信したユーザーの IP サブネット。</span><span class="sxs-lookup"><span data-stu-id="f14de-169">IP subnet of the user who received the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f14de-170">[<strong>通話ボリューム</strong>]</span><span class="sxs-lookup"><span data-stu-id="f14de-170"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="f14de-171">必要</span><span class="sxs-lookup"><span data-stu-id="f14de-171">Yes</span></span></p></td>
<td><p><span data-ttu-id="f14de-172">発信された通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="f14de-172">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f14de-173">[<strong>低品質通話のパーセンテージ</strong>]</span><span class="sxs-lookup"><span data-stu-id="f14de-173"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="f14de-174">必要</span><span class="sxs-lookup"><span data-stu-id="f14de-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="f14de-175">低品質通話として分類された通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="f14de-175">Percentage of calls classified as poor calls.</span></span> <span data-ttu-id="f14de-176">低品質通話とは、少なくとも 1 つの測定指標が許容値を超えている通話 (たとえば、過剰なジッターが発生した通話) のことです。</span><span class="sxs-lookup"><span data-stu-id="f14de-176">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f14de-177">[<strong>往復 (ミリ秒)</strong>]</span><span class="sxs-lookup"><span data-stu-id="f14de-177"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="f14de-178">必要</span><span class="sxs-lookup"><span data-stu-id="f14de-178">Yes</span></span></p></td>
<td><p><span data-ttu-id="f14de-p113">リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する平均時間 (ミリ秒単位)。100 ミリ秒以下の往復時間が許容できる品質と見なされます。</span><span class="sxs-lookup"><span data-stu-id="f14de-p113">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="f14de-p114">この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が困難になります。</span><span class="sxs-lookup"><span data-stu-id="f14de-p114">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f14de-183">[<strong>低下 (MOS)</strong>]</span><span class="sxs-lookup"><span data-stu-id="f14de-183"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="f14de-184">必要</span><span class="sxs-lookup"><span data-stu-id="f14de-184">Yes</span></span></p></td>
<td><p><span data-ttu-id="f14de-185">通話時に発生した平均オピニオン値 (MOS) 低下の平均値。</span><span class="sxs-lookup"><span data-stu-id="f14de-185">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="f14de-186">低下の値範囲は、最低 0.0 から最高 5.0 までとなります。</span><span class="sxs-lookup"><span data-stu-id="f14de-186">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="f14de-187">0.5 以下の値は、許容される低下を表します。</span><span class="sxs-lookup"><span data-stu-id="f14de-187">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="f14de-188">従来、平均オピニオン値は、ユーザーが通話の品質を 1 から 5 の範囲で評価することによって計算されていました。</span><span class="sxs-lookup"><span data-stu-id="f14de-188">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="f14de-189">Lync Server では、Lync Server は一連のアルゴリズムを使用して、ユーザーが通話を評価する方法を予測します。</span><span class="sxs-lookup"><span data-stu-id="f14de-189">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="f14de-p116">この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーやエンドポイントの過負荷などの原因が考えられます。その結果、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="f14de-p116">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f14de-192">[<strong>パケット損失</strong>]</span><span class="sxs-lookup"><span data-stu-id="f14de-192"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="f14de-193">必要</span><span class="sxs-lookup"><span data-stu-id="f14de-193">Yes</span></span></p></td>
<td><p><span data-ttu-id="f14de-p117">RTP パケットの平均損失率 (パケット損失は、RTP パケット (音声およびビデオをインターネット上で転送する場合に使用されるプロトコル) が宛先に到達できなかった場合に発生します)。通常、この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。その結果、一般に音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="f14de-p117">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f14de-197"><strong>ずれ</strong></span><span class="sxs-lookup"><span data-stu-id="f14de-197"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="f14de-198">必要</span><span class="sxs-lookup"><span data-stu-id="f14de-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="f14de-199">RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。</span><span class="sxs-lookup"><span data-stu-id="f14de-199">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="f14de-200">(ジッターは、通話の過の測定値です &quot; &quot; )。高ジッター値は、通常、混雑または過負荷のメディアサーバーによって発生し、その結果、音声がひずむか失われます。</span><span class="sxs-lookup"><span data-stu-id="f14de-200">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f14de-201">[<strong>ヒーラー隠し比率</strong>]</span><span class="sxs-lookup"><span data-stu-id="f14de-201"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="f14de-202">必要</span><span class="sxs-lookup"><span data-stu-id="f14de-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="f14de-p119">サンプルの合計数に対する隠しオーディオ サンプルの平均比率 (隠しオーディオ サンプルとは、突然遷移を取り除くために使用される手法です。突然遷移は、通常、ネットワーク パケットの削除が原因で発生します)。この値が高い場合は、パケット損失やジッターのために高いレベルで損失の隠蔽が適用されています。その結果、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="f14de-p119">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f14de-205">[<strong>ヒーラー引き伸ばし比率</strong>]</span><span class="sxs-lookup"><span data-stu-id="f14de-205"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="f14de-206">必要</span><span class="sxs-lookup"><span data-stu-id="f14de-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="f14de-p120">サンプルの合計数に対する引き伸ばされたオーディオ サンプルの平均比率 (引き伸ばされたオーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように拡張されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの引き伸ばしが行われています。その結果、音声が機械のように聞こえたりひずんで聞こえたりします。</span><span class="sxs-lookup"><span data-stu-id="f14de-p120">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f14de-209">[<strong>ヒーラー圧縮比率</strong>]</span><span class="sxs-lookup"><span data-stu-id="f14de-209"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="f14de-210">必要</span><span class="sxs-lookup"><span data-stu-id="f14de-210">Yes</span></span></p></td>
<td><p><span data-ttu-id="f14de-p121">サンプルの合計数に対する圧縮オーディオ サンプルの平均比率 (圧縮オーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように圧縮されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの圧縮が行われています。その結果、音声が早送りされたように聞こえたりひずんで聞こえたりします。</span><span class="sxs-lookup"><span data-stu-id="f14de-p121">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

