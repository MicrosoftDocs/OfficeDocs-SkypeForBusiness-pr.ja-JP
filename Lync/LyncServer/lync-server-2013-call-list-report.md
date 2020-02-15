---
title: 'Lync Server 2013: 通話リストレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call List Report
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615020(v=OCS.15)
ms:contentKeyID: 48184921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53b462644e2334f428b8cd9a46c0ca07472f6ee2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-list-report-in-lync-server-2013"></a><span data-ttu-id="d646d-102">Lync Server 2013 の通話リストレポート</span><span class="sxs-lookup"><span data-stu-id="d646d-102">Call List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d646d-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d646d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d646d-104">通話リストレポートでは、組織内で発信および受信された個々の通話の QoE (Quality of Experience) 指標が提供されます。</span><span class="sxs-lookup"><span data-stu-id="d646d-104">The Call List Report provides Quality of Experience (QoE) metrics for individual calls made and received in your organization.</span></span> <span data-ttu-id="d646d-105">報告される実際の指標は、通話リストレポートへのアクセス方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d646d-105">Note that the actual metrics reported will depend on how you access the Call List report.</span></span> <span data-ttu-id="d646d-106">たとえば、 [Lync Server 2013 のデバイスレポート](lync-server-2013-device-report.md)からレポートを開くと、次のようなメトリックが表示されます。これには、デバイスレポートにも報告されるメトリックがあります。</span><span class="sxs-lookup"><span data-stu-id="d646d-106">For example, if you open the report from the [Device Report in Lync Server 2013](lync-server-2013-device-report.md), you'll see metrics such as the following, metrics that are also reported on the Device Report:</span></span>

  - <span data-ttu-id="d646d-107">発信者のマイク</span><span class="sxs-lookup"><span data-stu-id="d646d-107">Caller's microphone</span></span>

  - <span data-ttu-id="d646d-108">発信者のスピーカー</span><span class="sxs-lookup"><span data-stu-id="d646d-108">Caller's speaker</span></span>

  - <span data-ttu-id="d646d-109">呼び出し先のマイク</span><span class="sxs-lookup"><span data-stu-id="d646d-109">Callee's microphone</span></span>

  - <span data-ttu-id="d646d-110">呼び出し先のスピーカー</span><span class="sxs-lookup"><span data-stu-id="d646d-110">Callee's speaker</span></span>

  - <span data-ttu-id="d646d-111">[音声切り替え時間の比率]</span><span class="sxs-lookup"><span data-stu-id="d646d-111">Ratio of voice switch time</span></span>

<span data-ttu-id="d646d-112">ただし、 [Lync Server 2013 の場所レポート](lync-server-2013-location-report.md)から通話リストレポートを開いた場合、これらの指標は表示されません。代わりに、次のような指標が表示します。</span><span class="sxs-lookup"><span data-stu-id="d646d-112">However, if you open the Call List Report from the [Location Report in Lync Server 2013](lync-server-2013-location-report.md), you won't see any of those metrics; instead, you'll see metrics like these:</span></span>

  - <span data-ttu-id="d646d-113">[往復 (ミリ秒)]</span><span class="sxs-lookup"><span data-stu-id="d646d-113">Round trip (ms)</span></span>

  - <span data-ttu-id="d646d-114">[低下 (MOS)]</span><span class="sxs-lookup"><span data-stu-id="d646d-114">Degradation (MOS)</span></span>

  - <span data-ttu-id="d646d-115">[パケット損失]</span><span class="sxs-lookup"><span data-stu-id="d646d-115">Packet loss</span></span>

  - <span data-ttu-id="d646d-116">[往復 (ミリ秒)]</span><span class="sxs-lookup"><span data-stu-id="d646d-116">Jitter (ms)</span></span>

<span data-ttu-id="d646d-117">場所レポートで報告される指標です。</span><span class="sxs-lookup"><span data-stu-id="d646d-117">Those are the metrics reported on the Location Report.</span></span> <span data-ttu-id="d646d-118">ただし、通話リストレポートからは、詳細指標をいつでもクリックして、任意の通話に対して完全な QoE 情報を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="d646d-118">However, from the Call List Report you can always click the Detail metric to provide complete QoE information for any call.</span></span>

<div>

## <a name="accessing-the-call-list-report"></a><span data-ttu-id="d646d-119">通話リストレポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="d646d-119">Accessing the Call List Report</span></span>

<span data-ttu-id="d646d-120">通話リストレポートには、次のいずれかのレポートからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d646d-120">The Call List Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="d646d-121">[Lync Server 2013 の場所レポート](lync-server-2013-location-report.md)([通話ボリューム] 指標または [低品質通話のパーセンテージ] 指標をクリックする)</span><span class="sxs-lookup"><span data-stu-id="d646d-121">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="d646d-122">[Lync Server 2013 のデバイスレポート](lync-server-2013-device-report.md)([通話ボリューム] 指標または [低品質通話のパーセンテージ] 指標をクリックする)</span><span class="sxs-lookup"><span data-stu-id="d646d-122">The [Device Report in Lync Server 2013](lync-server-2013-device-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="d646d-123">[Lync Server 2013 のメディア品質概要レポート](lync-server-2013-media-quality-summary-report.md)([通話ボリューム] 指標または [低品質通話のパーセンテージ] 指標をクリックする)</span><span class="sxs-lookup"><span data-stu-id="d646d-123">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="d646d-124">[Lync server 2013 のサーバーパフォーマンスレポート](lync-server-2013-server-performance-report.md)([通話ボリューム] または [低品質通話のパーセンテージ] 指標をクリック)</span><span class="sxs-lookup"><span data-stu-id="d646d-124">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

<span data-ttu-id="d646d-125">通話リストレポート内から、詳細指標をクリックして[Lync Server 2013 の通話詳細レポート](lync-server-2013-call-detail-report.md)にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d646d-125">From within the Call List Report you can access the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) by clicking the Detail metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a><span data-ttu-id="d646d-126">通話リストレポートの活用</span><span class="sxs-lookup"><span data-stu-id="d646d-126">Making the Best Use of the Call List Report</span></span>

<span data-ttu-id="d646d-127">通話リストレポートの一部の指標 ([音声切り替え時間の比率] など) が実際に測定される内容を思い出せない場合は、指標ラベルの上にマウスポインターを置きます。ツールヒントが表示され、指標の簡単な説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d646d-127">If you can't remember what some of the Call List Report metrics (such as Ratio voice switch time) actually measure, hold your mouse over the metric label; a tool tip will then appear giving you a brief description of the metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="d646d-128">フィルター</span><span class="sxs-lookup"><span data-stu-id="d646d-128">Filters</span></span>

<span data-ttu-id="d646d-129">なし。</span><span class="sxs-lookup"><span data-stu-id="d646d-129">None.</span></span> <span data-ttu-id="d646d-130">通話リストレポートにフィルターを適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d646d-130">You cannot filter the Call List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="d646d-131">指標</span><span class="sxs-lookup"><span data-stu-id="d646d-131">Metrics</span></span>

<span data-ttu-id="d646d-132">次の表に、通話リストレポートで呼び出しごとに提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="d646d-132">The following table lists the information provided in the Call List Report for each call.</span></span>

### <a name="call-list-report-metrics"></a><span data-ttu-id="d646d-133">通話リストレポートの指標</span><span class="sxs-lookup"><span data-stu-id="d646d-133">Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d646d-134">名前</span><span class="sxs-lookup"><span data-stu-id="d646d-134">Name</span></span></th>
<th><span data-ttu-id="d646d-135">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="d646d-135">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d646d-136">説明</span><span class="sxs-lookup"><span data-stu-id="d646d-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d646d-137"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="d646d-137"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="d646d-138">いいえ</span><span class="sxs-lookup"><span data-stu-id="d646d-138">No</span></span></p></td>
<td><p><span data-ttu-id="d646d-139">この項目をクリックすると、その通話に関する追加情報がレポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d646d-139">When you click this item, the report shows additional information on the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d646d-140"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="d646d-140"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="d646d-141">はい</span><span class="sxs-lookup"><span data-stu-id="d646d-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="d646d-142">呼び出しを開始したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="d646d-142">SIP address of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d646d-143"><strong>側</strong></span><span class="sxs-lookup"><span data-stu-id="d646d-143"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="d646d-144">はい</span><span class="sxs-lookup"><span data-stu-id="d646d-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="d646d-145">呼び出し先ユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="d646d-145">SIP address of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d646d-146">[<strong>開始時刻</strong>]</span><span class="sxs-lookup"><span data-stu-id="d646d-146"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="d646d-147">はい</span><span class="sxs-lookup"><span data-stu-id="d646d-147">Yes</span></span></p></td>
<td><p><span data-ttu-id="d646d-148">通話が開始された日時。</span><span class="sxs-lookup"><span data-stu-id="d646d-148">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d646d-149">[<strong>終了時刻</strong>]</span><span class="sxs-lookup"><span data-stu-id="d646d-149"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="d646d-150">はい</span><span class="sxs-lookup"><span data-stu-id="d646d-150">Yes</span></span></p></td>
<td><p><span data-ttu-id="d646d-151">通話が終了した日時。</span><span class="sxs-lookup"><span data-stu-id="d646d-151">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d646d-152">[<strong>発信者ユーザー エージェント</strong>]</span><span class="sxs-lookup"><span data-stu-id="d646d-152"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="d646d-153">はい</span><span class="sxs-lookup"><span data-stu-id="d646d-153">Yes</span></span></p></td>
<td><p><span data-ttu-id="d646d-154">呼び出しを開始したユーザーのエンドポイントによって使用されるソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="d646d-154">Software used by the endpoint of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d646d-155">[<strong>呼び出し先ユーザー エージェント</strong>]</span><span class="sxs-lookup"><span data-stu-id="d646d-155"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="d646d-156">はい</span><span class="sxs-lookup"><span data-stu-id="d646d-156">Yes</span></span></p></td>
<td><p><span data-ttu-id="d646d-157">呼び出し先のユーザーのエンドポイントで使用されているソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="d646d-157">Software used by the endpoint of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d646d-158">[<strong>往復 (ミリ秒)</strong>]</span><span class="sxs-lookup"><span data-stu-id="d646d-158"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="d646d-159">はい</span><span class="sxs-lookup"><span data-stu-id="d646d-159">Yes</span></span></p></td>
<td><p><span data-ttu-id="d646d-p104">リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する平均時間 (ミリ秒単位)。100 ミリ秒以下の往復時間が許容できる品質と見なされます。</span><span class="sxs-lookup"><span data-stu-id="d646d-p104">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="d646d-p105">この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が困難になります。</span><span class="sxs-lookup"><span data-stu-id="d646d-p105">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d646d-164">[<strong>低下 (MOS)</strong>]</span><span class="sxs-lookup"><span data-stu-id="d646d-164"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="d646d-165">はい</span><span class="sxs-lookup"><span data-stu-id="d646d-165">Yes</span></span></p></td>
<td><p><span data-ttu-id="d646d-166">通話時に発生した平均オピニオン値 (MOS) 低下の平均値。</span><span class="sxs-lookup"><span data-stu-id="d646d-166">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="d646d-167">低下の値範囲は、最低 0.0 から最高 5.0 までとなります。</span><span class="sxs-lookup"><span data-stu-id="d646d-167">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="d646d-168">0.5 以下の値は、許容される低下を表します。</span><span class="sxs-lookup"><span data-stu-id="d646d-168">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="d646d-169">従来、平均オピニオン値は、ユーザーが通話の品質を 1 から 5 の範囲で評価することによって計算されていました。</span><span class="sxs-lookup"><span data-stu-id="d646d-169">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="d646d-170">Lync Server では、Lync Server は一連のアルゴリズムを使用して、ユーザーが通話を評価する方法を予測します。</span><span class="sxs-lookup"><span data-stu-id="d646d-170">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="d646d-p107">この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーやエンドポイントの過負荷などの原因が考えられます。その結果、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="d646d-p107">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d646d-173">[<strong>パケット損失</strong>]</span><span class="sxs-lookup"><span data-stu-id="d646d-173"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="d646d-174">はい</span><span class="sxs-lookup"><span data-stu-id="d646d-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="d646d-p108">RTP パケットの平均損失率 (パケット損失は、RTP パケット (音声およびビデオをインターネット上で転送する場合に使用されるプロトコル) が宛先に到達できなかった場合に発生します)。通常、この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。その結果、一般に音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="d646d-p108">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d646d-178"><strong>ずれ</strong></span><span class="sxs-lookup"><span data-stu-id="d646d-178"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="d646d-179">はい</span><span class="sxs-lookup"><span data-stu-id="d646d-179">Yes</span></span></p></td>
<td><p><span data-ttu-id="d646d-180">RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。</span><span class="sxs-lookup"><span data-stu-id="d646d-180">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="d646d-181">(ジッターは、通話の&quot;過&quot;の測定値です)。高ジッター値は、通常、混雑または過負荷のメディアサーバーによって発生し、その結果、音声がひずむか失われます。</span><span class="sxs-lookup"><span data-stu-id="d646d-181">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d646d-182">[<strong>ヒーラー隠し比率</strong>]</span><span class="sxs-lookup"><span data-stu-id="d646d-182"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="d646d-183">はい</span><span class="sxs-lookup"><span data-stu-id="d646d-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="d646d-p110">サンプルの合計数に対する隠しオーディオ サンプルの平均比率 (隠しオーディオ サンプルとは、突然遷移を取り除くために使用される手法です。突然遷移は、通常、ネットワーク パケットの削除が原因で発生します)。この値が高い場合は、パケット損失やジッターのために高いレベルで損失の隠蔽が適用されています。その結果、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="d646d-p110">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d646d-186">[<strong>ヒーラー引き伸ばし比率</strong>]</span><span class="sxs-lookup"><span data-stu-id="d646d-186"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="d646d-187">はい</span><span class="sxs-lookup"><span data-stu-id="d646d-187">Yes</span></span></p></td>
<td><p><span data-ttu-id="d646d-p111">サンプルの合計数に対する引き伸ばされたオーディオ サンプルの平均比率 (引き伸ばされたオーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように拡張されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの引き伸ばしが行われています。その結果、音声が機械のように聞こえたりひずんで聞こえたりします。</span><span class="sxs-lookup"><span data-stu-id="d646d-p111">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d646d-190">[<strong>ヒーラー圧縮比率</strong>]</span><span class="sxs-lookup"><span data-stu-id="d646d-190"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="d646d-191">はい</span><span class="sxs-lookup"><span data-stu-id="d646d-191">Yes</span></span></p></td>
<td><p><span data-ttu-id="d646d-p112">サンプルの合計数に対する圧縮オーディオ サンプルの平均比率 (圧縮オーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように圧縮されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの圧縮が行われています。その結果、音声が早送りされたように聞こえたりひずんで聞こえたりします。</span><span class="sxs-lookup"><span data-stu-id="d646d-p112">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d646d-194"><strong>接続</strong></span><span class="sxs-lookup"><span data-stu-id="d646d-194"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="d646d-195">はい</span><span class="sxs-lookup"><span data-stu-id="d646d-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="d646d-196">ワイヤレス通信リンクの種類。</span><span class="sxs-lookup"><span data-stu-id="d646d-196">Type of wireless communication link.</span></span> <span data-ttu-id="d646d-197">通常、これは次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="d646d-197">Typically, this is one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d646d-198">中継</span><span class="sxs-lookup"><span data-stu-id="d646d-198">Relay</span></span></p></li>
<li><p><span data-ttu-id="d646d-199">直接</span><span class="sxs-lookup"><span data-stu-id="d646d-199">Direct</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

