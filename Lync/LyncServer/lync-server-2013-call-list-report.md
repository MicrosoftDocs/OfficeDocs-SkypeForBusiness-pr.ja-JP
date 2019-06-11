---
title: 'Lync Server 2013: 通話リストレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call List Report
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615020(v=OCS.15)
ms:contentKeyID: 48184921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faf330a776f64534c02833a0472cfefea7f0998e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-list-report-in-lync-server-2013"></a><span data-ttu-id="fd54e-102">Lync Server 2013 の通話リストレポート</span><span class="sxs-lookup"><span data-stu-id="fd54e-102">Call List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd54e-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="fd54e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="fd54e-104">通話リストレポートでは、組織内で発信および受信した個々の通話の品質 (QoE) メトリックが提供されます。</span><span class="sxs-lookup"><span data-stu-id="fd54e-104">The Call List Report provides Quality of Experience (QoE) metrics for individual calls made and received in your organization.</span></span> <span data-ttu-id="fd54e-105">実際に報告される指標は、通話リストレポートへのアクセス方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="fd54e-105">Note that the actual metrics reported will depend on how you access the Call List report.</span></span> <span data-ttu-id="fd54e-106">たとえば、 [Lync Server 2013 のデバイスレポート](lync-server-2013-device-report.md)からレポートを開くと、次のようなメトリックが表示されます。これは、デバイスレポートにも報告されます。</span><span class="sxs-lookup"><span data-stu-id="fd54e-106">For example, if you open the report from the [Device Report in Lync Server 2013](lync-server-2013-device-report.md), you'll see metrics such as the following, metrics that are also reported on the Device Report:</span></span>

  - <span data-ttu-id="fd54e-107">発信者のマイク</span><span class="sxs-lookup"><span data-stu-id="fd54e-107">Caller's microphone</span></span>

  - <span data-ttu-id="fd54e-108">発信者のスピーカー</span><span class="sxs-lookup"><span data-stu-id="fd54e-108">Caller's speaker</span></span>

  - <span data-ttu-id="fd54e-109">呼び出し先マイク</span><span class="sxs-lookup"><span data-stu-id="fd54e-109">Callee's microphone</span></span>

  - <span data-ttu-id="fd54e-110">呼び出し先スピーカー</span><span class="sxs-lookup"><span data-stu-id="fd54e-110">Callee's speaker</span></span>

  - <span data-ttu-id="fd54e-111">音声切り替え時間の比率</span><span class="sxs-lookup"><span data-stu-id="fd54e-111">Ratio of voice switch time</span></span>

<span data-ttu-id="fd54e-112">ただし、 [Lync Server 2013 の場所レポート](lync-server-2013-location-report.md)から通話リストレポートを開くと、これらのメトリックは表示されません。代わりに、次のようなメトリックが表示できます。</span><span class="sxs-lookup"><span data-stu-id="fd54e-112">However, if you open the Call List Report from the [Location Report in Lync Server 2013](lync-server-2013-location-report.md), you won't see any of those metrics; instead, you'll see metrics like these:</span></span>

  - <span data-ttu-id="fd54e-113">往復 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="fd54e-113">Round trip (ms)</span></span>

  - <span data-ttu-id="fd54e-114">低下 (MOS)</span><span class="sxs-lookup"><span data-stu-id="fd54e-114">Degradation (MOS)</span></span>

  - <span data-ttu-id="fd54e-115">パケット損失</span><span class="sxs-lookup"><span data-stu-id="fd54e-115">Packet loss</span></span>

  - <span data-ttu-id="fd54e-116">ジッター (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="fd54e-116">Jitter (ms)</span></span>

<span data-ttu-id="fd54e-p102">これらは場所レポートで報告される指標です。ただし、通話リスト レポートでは、[詳細] 指標をいつでもクリックして、任意の通話のすべての QoE 情報を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="fd54e-p102">Those are the metrics reported on the Location Report. However, from the Call List Report you can always click the Detail metric to provide complete QoE information for any call.</span></span>

<div>

## <a name="accessing-the-call-list-report"></a><span data-ttu-id="fd54e-119">通話リスト レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="fd54e-119">Accessing the Call List Report</span></span>

<span data-ttu-id="fd54e-120">通話リスト レポートには、次のいずれかのレポートからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fd54e-120">The Call List Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="fd54e-121">[Lync Server 2013 の場所レポート](lync-server-2013-location-report.md)(通話ボリュームまたは低通話のパーセンテージメトリックをクリック)</span><span class="sxs-lookup"><span data-stu-id="fd54e-121">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="fd54e-122">[Lync Server 2013 のデバイスレポート](lync-server-2013-device-report.md)(通話ボリュームまたは低通話パーセンテージメトリックをクリック)</span><span class="sxs-lookup"><span data-stu-id="fd54e-122">The [Device Report in Lync Server 2013](lync-server-2013-device-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="fd54e-123">[Lync Server 2013 のメディア品質の概要レポート](lync-server-2013-media-quality-summary-report.md)(通話ボリュームまたは低品質の通話率のメトリックをクリック)</span><span class="sxs-lookup"><span data-stu-id="fd54e-123">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="fd54e-124">[Lync server 2013 のサーバーパフォーマンスレポート](lync-server-2013-server-performance-report.md)(通話ボリュームまたは低通話パーセンテージメトリックをクリック)</span><span class="sxs-lookup"><span data-stu-id="fd54e-124">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

<span data-ttu-id="fd54e-125">通話リストレポート内から、詳細なメトリックをクリックして、 [Lync Server 2013 の通話詳細レポート](lync-server-2013-call-detail-report.md)にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fd54e-125">From within the Call List Report you can access the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) by clicking the Detail metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a><span data-ttu-id="fd54e-126">通話リスト レポートの活用</span><span class="sxs-lookup"><span data-stu-id="fd54e-126">Making the Best Use of the Call List Report</span></span>

<span data-ttu-id="fd54e-127">通話リスト レポートの一部の指標 ([音声切り替え時間の比率] など) で実際に何を測定するのかがわからない場合は、指標ラベルの上にマウス ポインターを置いてください。指標の簡単な説明を示すツール ヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd54e-127">If you can't remember what some of the Call List Report metrics (such as Ratio voice switch time) actually measure, hold your mouse over the metric label; a tool tip will then appear giving you a brief description of the metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="fd54e-128">フィルター</span><span class="sxs-lookup"><span data-stu-id="fd54e-128">Filters</span></span>

<span data-ttu-id="fd54e-p103">なし。通話リスト レポートにフィルターを適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fd54e-p103">None. You cannot filter the Call List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="fd54e-131">指標</span><span class="sxs-lookup"><span data-stu-id="fd54e-131">Metrics</span></span>

<span data-ttu-id="fd54e-132">次の表に、通話リスト レポートで提供される通話ごとの情報を示します。</span><span class="sxs-lookup"><span data-stu-id="fd54e-132">The following table lists the information provided in the Call List Report for each call.</span></span>

### <a name="call-list-report-metrics"></a><span data-ttu-id="fd54e-133">通話リスト レポートの指標</span><span class="sxs-lookup"><span data-stu-id="fd54e-133">Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd54e-134">名前</span><span class="sxs-lookup"><span data-stu-id="fd54e-134">Name</span></span></th>
<th><span data-ttu-id="fd54e-135">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="fd54e-135">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fd54e-136">説明</span><span class="sxs-lookup"><span data-stu-id="fd54e-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd54e-137"><strong>[詳細]</strong></span><span class="sxs-lookup"><span data-stu-id="fd54e-137"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="fd54e-138">不可</span><span class="sxs-lookup"><span data-stu-id="fd54e-138">No</span></span></p></td>
<td><p><span data-ttu-id="fd54e-139">この項目をクリックすると、その通話に関する補足的な情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd54e-139">When you click this item, the report shows additional information on the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd54e-140"><strong>[発信者]</strong></span><span class="sxs-lookup"><span data-stu-id="fd54e-140"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="fd54e-141">はい</span><span class="sxs-lookup"><span data-stu-id="fd54e-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="fd54e-142">通話の発信者の SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="fd54e-142">SIP address of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd54e-143"><strong>[呼び出し先]</strong></span><span class="sxs-lookup"><span data-stu-id="fd54e-143"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="fd54e-144">はい</span><span class="sxs-lookup"><span data-stu-id="fd54e-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="fd54e-145">通話の着信者の SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="fd54e-145">SIP address of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd54e-146"><strong>[開始時刻]</strong></span><span class="sxs-lookup"><span data-stu-id="fd54e-146"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="fd54e-147">はい</span><span class="sxs-lookup"><span data-stu-id="fd54e-147">Yes</span></span></p></td>
<td><p><span data-ttu-id="fd54e-148">通話が開始された日時。</span><span class="sxs-lookup"><span data-stu-id="fd54e-148">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd54e-149"><strong>[終了時刻]</strong></span><span class="sxs-lookup"><span data-stu-id="fd54e-149"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="fd54e-150">はい</span><span class="sxs-lookup"><span data-stu-id="fd54e-150">Yes</span></span></p></td>
<td><p><span data-ttu-id="fd54e-151">通話が終了した日時。</span><span class="sxs-lookup"><span data-stu-id="fd54e-151">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd54e-152"><strong>[発信者ユーザー エージェント]</strong></span><span class="sxs-lookup"><span data-stu-id="fd54e-152"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="fd54e-153">はい</span><span class="sxs-lookup"><span data-stu-id="fd54e-153">Yes</span></span></p></td>
<td><p><span data-ttu-id="fd54e-154">通話の発信者のエンドポイントで使われているソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="fd54e-154">Software used by the endpoint of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd54e-155"><strong>[呼び出し先ユーザー エージェント]</strong></span><span class="sxs-lookup"><span data-stu-id="fd54e-155"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="fd54e-156">はい</span><span class="sxs-lookup"><span data-stu-id="fd54e-156">Yes</span></span></p></td>
<td><p><span data-ttu-id="fd54e-157">通話の着信者のエンドポイントで使われているソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="fd54e-157">Software used by the endpoint of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd54e-158"><strong>[往復 (ミリ秒)]</strong></span><span class="sxs-lookup"><span data-stu-id="fd54e-158"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="fd54e-159">はい</span><span class="sxs-lookup"><span data-stu-id="fd54e-159">Yes</span></span></p></td>
<td><p><span data-ttu-id="fd54e-p104">リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する平均時間 (ミリ秒単位)。100 ミリ秒以下の往復時間が許容できる品質と見なされます。</span><span class="sxs-lookup"><span data-stu-id="fd54e-p104">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="fd54e-p105">この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。</span><span class="sxs-lookup"><span data-stu-id="fd54e-p105">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd54e-164"><strong>低下 (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="fd54e-164"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="fd54e-165">はい</span><span class="sxs-lookup"><span data-stu-id="fd54e-165">Yes</span></span></p></td>
<td><p><span data-ttu-id="fd54e-166">通話時に発生した平均オピニオン値 (MOS) 低下の平均値。</span><span class="sxs-lookup"><span data-stu-id="fd54e-166">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="fd54e-167">低下の値範囲は、最低 0.0 から最高 5.0 までとなります。</span><span class="sxs-lookup"><span data-stu-id="fd54e-167">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="fd54e-168">0.5 以下の値は、許容される低下を表します。</span><span class="sxs-lookup"><span data-stu-id="fd54e-168">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="fd54e-169">従来、平均オピニオン値は、ユーザーが通話の品質を 1 から 5 の範囲で評価することによって計算されていました。</span><span class="sxs-lookup"><span data-stu-id="fd54e-169">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="fd54e-170">Lync server では、Lync Server で一連のアルゴリズムを使って、ユーザーが通話を評価した方法を予測します。</span><span class="sxs-lookup"><span data-stu-id="fd54e-170">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="fd54e-p107">この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーやエンドポイントの過負荷などの原因が考えられます。その結果、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="fd54e-p107">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd54e-173"><strong>パケット損失</strong></span><span class="sxs-lookup"><span data-stu-id="fd54e-173"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="fd54e-174">はい</span><span class="sxs-lookup"><span data-stu-id="fd54e-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="fd54e-p108">RTP パケットの平均損失率 (パケット損失は、RTP パケット (音声およびビデオをインターネット上で転送する場合に使用されるプロトコル) が宛先に到達できなかった場合に発生します)。通常、この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。その結果、一般に音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="fd54e-p108">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd54e-178"><strong>ジッター</strong></span><span class="sxs-lookup"><span data-stu-id="fd54e-178"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="fd54e-179">はい</span><span class="sxs-lookup"><span data-stu-id="fd54e-179">Yes</span></span></p></td>
<td><p><span data-ttu-id="fd54e-180">RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。</span><span class="sxs-lookup"><span data-stu-id="fd54e-180">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="fd54e-181">(ジッタは、通話の&quot;shakiness&quot;の尺度です)。通常、高ジッターの値は、輻輳または過負荷のメディアサーバーによって発生し、音声が歪むか、失われる原因となります。</span><span class="sxs-lookup"><span data-stu-id="fd54e-181">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd54e-182"><strong>ヒーラー隠し比率</strong></span><span class="sxs-lookup"><span data-stu-id="fd54e-182"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="fd54e-183">はい</span><span class="sxs-lookup"><span data-stu-id="fd54e-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="fd54e-p110">サンプルの合計数に対する隠しオーディオ サンプルの平均比率 (隠しオーディオ サンプルとは、突然遷移を取り除くために使用される手法です。突然遷移は、通常、ネットワーク パケットの削除が原因で発生します)。この値が高い場合は、パケット損失やジッターのために高いレベルで損失の隠蔽が適用されています。その結果、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="fd54e-p110">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd54e-186"><strong>ヒーラー引き伸ばし比率</strong></span><span class="sxs-lookup"><span data-stu-id="fd54e-186"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="fd54e-187">はい</span><span class="sxs-lookup"><span data-stu-id="fd54e-187">Yes</span></span></p></td>
<td><p><span data-ttu-id="fd54e-p111">サンプルの合計数に対する引き伸ばされたオーディオ サンプルの平均比率 (引き伸ばされたオーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように拡張されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの引き伸ばしが行われています。その結果、音声が機械のように聞こえたりひずんで聞こえたりします。</span><span class="sxs-lookup"><span data-stu-id="fd54e-p111">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd54e-190"><strong>ヒーラー圧縮比率</strong></span><span class="sxs-lookup"><span data-stu-id="fd54e-190"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="fd54e-191">はい</span><span class="sxs-lookup"><span data-stu-id="fd54e-191">Yes</span></span></p></td>
<td><p><span data-ttu-id="fd54e-p112">サンプルの合計数に対する圧縮オーディオ サンプルの平均比率 (圧縮オーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように圧縮されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの圧縮が行われています。その結果、音声が早送りされたように聞こえたりひずんで聞こえたりします。</span><span class="sxs-lookup"><span data-stu-id="fd54e-p112">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd54e-194"><strong>[接続]</strong></span><span class="sxs-lookup"><span data-stu-id="fd54e-194"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="fd54e-195">可</span><span class="sxs-lookup"><span data-stu-id="fd54e-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="fd54e-p113">ワイヤレス通信リンクの種類。通常、これは次のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="fd54e-p113">Type of wireless communication link. Typically, this is one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fd54e-198">リレー</span><span class="sxs-lookup"><span data-stu-id="fd54e-198">Relay</span></span></p></li>
<li><p><span data-ttu-id="fd54e-199">直接</span><span class="sxs-lookup"><span data-stu-id="fd54e-199">Direct</span></span></p></li>
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

