---
title: 'Lync Server 2013: AppSharingStream テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingStream table
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48183852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c00a606981ab09d370d5aac390aa244a31063f24
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="bed90-102">Lync Server 2013 の AppSharingStream テーブル</span><span class="sxs-lookup"><span data-stu-id="bed90-102">AppSharingStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bed90-103">_**最終更新日:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="bed90-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="bed90-104">AppSharingStream テーブルには、アプリケーション共有に使用されるネットワークストリームのエクスペリエンスのメトリックの質が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bed90-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="bed90-105">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="bed90-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bed90-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="bed90-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="bed90-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="bed90-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bed90-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-111">dateTime</span><span class="sxs-lookup"><span data-stu-id="bed90-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="bed90-112">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="bed90-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="bed90-113">セッションが開始された日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="bed90-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-115">int</span><span class="sxs-lookup"><span data-stu-id="bed90-115">int</span></span></p></td>
<td><p><span data-ttu-id="bed90-116">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="bed90-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="bed90-117">同じ日付と同時に開始したセッションを区別するために使用されるシーケンシャル識別子。</span><span class="sxs-lookup"><span data-stu-id="bed90-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="bed90-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bed90-120">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="bed90-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="bed90-121">通話で使用されるビデオラインの種類を表します。</span><span class="sxs-lookup"><span data-stu-id="bed90-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="bed90-122">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bed90-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed90-123">0–音声</span><span class="sxs-lookup"><span data-stu-id="bed90-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="bed90-124">1-ビデオ</span><span class="sxs-lookup"><span data-stu-id="bed90-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="bed90-125">2-パノラマビデオ</span><span class="sxs-lookup"><span data-stu-id="bed90-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="bed90-126">3-アプリケーション/デスクトップ共有</span><span class="sxs-lookup"><span data-stu-id="bed90-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-127"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-128">int</span><span class="sxs-lookup"><span data-stu-id="bed90-128">int</span></span></p></td>
<td><p><span data-ttu-id="bed90-129">Primary</span><span class="sxs-lookup"><span data-stu-id="bed90-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="bed90-130">アプリケーション共有ストリームの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="bed90-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-132">int</span><span class="sxs-lookup"><span data-stu-id="bed90-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-133">RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。</span><span class="sxs-lookup"><span data-stu-id="bed90-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="bed90-134">(ジッタは、通話の&quot;shakiness&quot;の尺度です)。通常、高ジッターの値は、輻輳または過負荷のメディアサーバーによって発生し、音声が歪むか、失われる原因となります。</span><span class="sxs-lookup"><span data-stu-id="bed90-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-136">int</span><span class="sxs-lookup"><span data-stu-id="bed90-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-137">RTP パケット着信の間の最大ジッターが検出されました。</span><span class="sxs-lookup"><span data-stu-id="bed90-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="bed90-138">(ジッタは、通話の&quot;shakiness&quot;の尺度です)。通常、高ジッターの値は、輻輳または過負荷のメディアサーバーによって発生し、音声が歪むか、失われる原因となります。</span><span class="sxs-lookup"><span data-stu-id="bed90-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-139"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-140">int</span><span class="sxs-lookup"><span data-stu-id="bed90-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-p105">リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する平均時間 (ミリ秒単位)。200 ミリ秒以下の往復時間が許容できる品質と見なされます。</span><span class="sxs-lookup"><span data-stu-id="bed90-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="bed90-p106">この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。</span><span class="sxs-lookup"><span data-stu-id="bed90-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-146">int</span><span class="sxs-lookup"><span data-stu-id="bed90-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-147">リアルタイムトランスポートプロトコルパケットが別のエンドポイントに移動してから戻るために必要な最大 (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="bed90-147">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="bed90-148">200 ミリ秒以下の往復時間が許容できる品質と見なされます。</span><span class="sxs-lookup"><span data-stu-id="bed90-148">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="bed90-p108">この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。</span><span class="sxs-lookup"><span data-stu-id="bed90-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-152">float</span><span class="sxs-lookup"><span data-stu-id="bed90-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-p109">リアルタイム転送プロトコル (RTP) パケット損失の平均レート。(パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを転送するために使われるプロトコルの一種で、パケットが宛先に到達できなかったときに発生します)。この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="bed90-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-157">float</span><span class="sxs-lookup"><span data-stu-id="bed90-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-158">リアルタイムトランスポートプロトコル (RTP) パケット損失の最大速度。</span><span class="sxs-lookup"><span data-stu-id="bed90-158">Maximum rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="bed90-159">(パケットの損失は、RTP パケット、インターネット上でのオーディオとビデオの伝送に使用されるプロトコル)、宛先への到達に失敗した場合に発生します。)通常、高損失率は輻輳が原因で発生します。帯域幅の不足。ワイヤレスの輻輳または妨害または、オーバーロードされたメディアサーバー。</span><span class="sxs-lookup"><span data-stu-id="bed90-159">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="bed90-160">パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="bed90-160">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-162">int</span><span class="sxs-lookup"><span data-stu-id="bed90-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-163">送信されたパケットの数です。</span><span class="sxs-lookup"><span data-stu-id="bed90-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-164"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-165">int</span><span class="sxs-lookup"><span data-stu-id="bed90-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-166">セッションの終了時に提供される推定される一方向の帯域幅。</span><span class="sxs-lookup"><span data-stu-id="bed90-166">Estimated one-way bandwidth available at the end of the session.</span></span> <span data-ttu-id="bed90-167">1秒あたりのビット数で報告されます。</span><span class="sxs-lookup"><span data-stu-id="bed90-167">Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-169">int</span><span class="sxs-lookup"><span data-stu-id="bed90-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-170">アプリケーション共有ペイロードの説明。</span><span class="sxs-lookup"><span data-stu-id="bed90-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-172">float</span><span class="sxs-lookup"><span data-stu-id="bed90-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-173">一方向の待機時間の合計。</span><span class="sxs-lookup"><span data-stu-id="bed90-173">Total amount of one-way latency.</span></span> <span data-ttu-id="bed90-174">相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。</span><span class="sxs-lookup"><span data-stu-id="bed90-174">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-176">float</span><span class="sxs-lookup"><span data-stu-id="bed90-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-177">一方向の待ち時間の平均値。</span><span class="sxs-lookup"><span data-stu-id="bed90-177">Average amount of one-way latency.</span></span> <span data-ttu-id="bed90-178">相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。</span><span class="sxs-lookup"><span data-stu-id="bed90-178">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-180">float</span><span class="sxs-lookup"><span data-stu-id="bed90-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-181">一方向の待機時間の上限。</span><span class="sxs-lookup"><span data-stu-id="bed90-181">Maximum amount of one-way latency.</span></span> <span data-ttu-id="bed90-182">相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。</span><span class="sxs-lookup"><span data-stu-id="bed90-182">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-184">int</span><span class="sxs-lookup"><span data-stu-id="bed90-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-185">1方向のバースト発生の合計。</span><span class="sxs-lookup"><span data-stu-id="bed90-185">Total one-way burst occurrences.</span></span> <span data-ttu-id="bed90-186">"Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。</span><span class="sxs-lookup"><span data-stu-id="bed90-186">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="bed90-187">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="bed90-187">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-189">float</span><span class="sxs-lookup"><span data-stu-id="bed90-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-190">全体的な1方向バースト密度。</span><span class="sxs-lookup"><span data-stu-id="bed90-190">Total one-way burst density.</span></span> <span data-ttu-id="bed90-191">"Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。</span><span class="sxs-lookup"><span data-stu-id="bed90-191">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="bed90-192">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="bed90-192">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-194">float</span><span class="sxs-lookup"><span data-stu-id="bed90-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-195">一方向のバースト期間の合計。</span><span class="sxs-lookup"><span data-stu-id="bed90-195">Total one-way burst duration.</span></span> <span data-ttu-id="bed90-196">"Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。</span><span class="sxs-lookup"><span data-stu-id="bed90-196">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="bed90-197">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="bed90-197">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-199">int</span><span class="sxs-lookup"><span data-stu-id="bed90-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-200">一方向のギャップ出現の合計。</span><span class="sxs-lookup"><span data-stu-id="bed90-200">Total one-way gap occurrences.</span></span> <span data-ttu-id="bed90-201">"Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。</span><span class="sxs-lookup"><span data-stu-id="bed90-201">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="bed90-202">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="bed90-202">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-204">float</span><span class="sxs-lookup"><span data-stu-id="bed90-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-205">一方向のギャップの密度の合計。</span><span class="sxs-lookup"><span data-stu-id="bed90-205">Total one-way gap density.</span></span> <span data-ttu-id="bed90-206">"Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。</span><span class="sxs-lookup"><span data-stu-id="bed90-206">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="bed90-207">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="bed90-207">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-209">float</span><span class="sxs-lookup"><span data-stu-id="bed90-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-210">一方向のギャップ期間の合計。</span><span class="sxs-lookup"><span data-stu-id="bed90-210">Total one-way gap duration.</span></span> <span data-ttu-id="bed90-211">"Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。</span><span class="sxs-lookup"><span data-stu-id="bed90-211">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="bed90-212">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="bed90-212">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="bed90-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-215">アプリケーションロール (共有先またはビューアー) とコンテンツタイプ。</span><span class="sxs-lookup"><span data-stu-id="bed90-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-217">float</span><span class="sxs-lookup"><span data-stu-id="bed90-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-218">リモートデスクトッププロトコル (RDP) タイルの合計処理時間。</span><span class="sxs-lookup"><span data-stu-id="bed90-218">Total processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="bed90-219">表示環境では、合計の遅延が長くなります。</span><span class="sxs-lookup"><span data-stu-id="bed90-219">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-220"><strong>Rdp タイル処理</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-221">float</span><span class="sxs-lookup"><span data-stu-id="bed90-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-222">リモートデスクトッププロトコル (RDP) タイルの平均処理時間。</span><span class="sxs-lookup"><span data-stu-id="bed90-222">Average processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="bed90-223">表示環境では、合計の遅延が長くなります。</span><span class="sxs-lookup"><span data-stu-id="bed90-223">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-225">float</span><span class="sxs-lookup"><span data-stu-id="bed90-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-226">リモートデスクトッププロトコル (RDP) タイルの最大処理時間。</span><span class="sxs-lookup"><span data-stu-id="bed90-226">Maximum processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="bed90-227">表示環境では、合計の遅延が長くなります。</span><span class="sxs-lookup"><span data-stu-id="bed90-227">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-229">int</span><span class="sxs-lookup"><span data-stu-id="bed90-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-230">リモートデスクトッププロトコル (RDP) タイルの処理時間でのバースト発生。</span><span class="sxs-lookup"><span data-stu-id="bed90-230">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="bed90-231">"Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。</span><span class="sxs-lookup"><span data-stu-id="bed90-231">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-233">float</span><span class="sxs-lookup"><span data-stu-id="bed90-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-234">リモートデスクトッププロトコル (RDP) タイルの処理時間のバースト密度。</span><span class="sxs-lookup"><span data-stu-id="bed90-234">Burst density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="bed90-235">"Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。</span><span class="sxs-lookup"><span data-stu-id="bed90-235">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-237">float</span><span class="sxs-lookup"><span data-stu-id="bed90-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-238">リモートデスクトッププロトコル (RDP) タイルの処理時間のバースト時間。</span><span class="sxs-lookup"><span data-stu-id="bed90-238">Burst duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="bed90-239">"Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。</span><span class="sxs-lookup"><span data-stu-id="bed90-239">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-241">int</span><span class="sxs-lookup"><span data-stu-id="bed90-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-242">リモートデスクトッププロトコル (RDP) タイルの処理時間のギャップの出現回数。</span><span class="sxs-lookup"><span data-stu-id="bed90-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-244">float</span><span class="sxs-lookup"><span data-stu-id="bed90-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-245">リモートデスクトッププロトコル (RDP) タイルの処理時間のギャップの密度。</span><span class="sxs-lookup"><span data-stu-id="bed90-245">Gap density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="bed90-246">隙間が小さいほど、表示エクスペリエンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="bed90-246">Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-248">float</span><span class="sxs-lookup"><span data-stu-id="bed90-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-249">リモートデスクトッププロトコル (RDP) タイルの処理時間の間隔。</span><span class="sxs-lookup"><span data-stu-id="bed90-249">Gap duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="bed90-250">短い間隔の期間は、表示感が向上するようになります。</span><span class="sxs-lookup"><span data-stu-id="bed90-250">Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-252">float</span><span class="sxs-lookup"><span data-stu-id="bed90-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-253">キャプチャされたタイルの合計レート (1 秒あたりのタイル数)</span><span class="sxs-lookup"><span data-stu-id="bed90-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-255">float</span><span class="sxs-lookup"><span data-stu-id="bed90-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-256">キャプチャされたタイルの平均速度 (1 秒あたりのタイル数)。</span><span class="sxs-lookup"><span data-stu-id="bed90-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-258">float</span><span class="sxs-lookup"><span data-stu-id="bed90-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-259">キャプチャされたタイルの最大速度 (1 秒あたりのタイル数)</span><span class="sxs-lookup"><span data-stu-id="bed90-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-261">t</span><span class="sxs-lookup"><span data-stu-id="bed90-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-262">キャプチャされたタイルの速度 (1 秒あたりのタイル) でバーストが発生します。</span><span class="sxs-lookup"><span data-stu-id="bed90-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-264">float</span><span class="sxs-lookup"><span data-stu-id="bed90-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-265">キャプチャされたタイルの速度 (1 秒あたりのタイル数) のバースト密度。</span><span class="sxs-lookup"><span data-stu-id="bed90-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-267">float</span><span class="sxs-lookup"><span data-stu-id="bed90-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-268">キャプチャされたタイルの割合でのバースト時間 (1 秒あたりのタイル数)。</span><span class="sxs-lookup"><span data-stu-id="bed90-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-270">int</span><span class="sxs-lookup"><span data-stu-id="bed90-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-271">キャプチャされたタイルの比率 (1 秒あたりのタイル数) でのギャップ出現回数。</span><span class="sxs-lookup"><span data-stu-id="bed90-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-273">float</span><span class="sxs-lookup"><span data-stu-id="bed90-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-274">キャプチャされたタイル (1 秒あたりのタイル数) の間隔の間隔。</span><span class="sxs-lookup"><span data-stu-id="bed90-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-276">float</span><span class="sxs-lookup"><span data-stu-id="bed90-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-277">キャプチャされたタイルの割合の間隔 (1 秒あたりのタイル数)</span><span class="sxs-lookup"><span data-stu-id="bed90-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-278"><strong>損失タイル</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-279">float</span><span class="sxs-lookup"><span data-stu-id="bed90-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-280">閲覧者に届かなかったが、破棄され、最新のコンテンツによって上書きされたコンテンツの割合の合計。</span><span class="sxs-lookup"><span data-stu-id="bed90-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-282">float</span><span class="sxs-lookup"><span data-stu-id="bed90-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-283">閲覧者に届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツの平均割合。</span><span class="sxs-lookup"><span data-stu-id="bed90-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-285">float</span><span class="sxs-lookup"><span data-stu-id="bed90-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-286">閲覧者に届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツの最大パーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="bed90-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-288">int</span><span class="sxs-lookup"><span data-stu-id="bed90-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-289">閲覧者に届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツのバースト発生。</span><span class="sxs-lookup"><span data-stu-id="bed90-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-291">float</span><span class="sxs-lookup"><span data-stu-id="bed90-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-292">ビューアーに届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツのバースト密度。</span><span class="sxs-lookup"><span data-stu-id="bed90-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-294">float</span><span class="sxs-lookup"><span data-stu-id="bed90-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-295">ビューアーに届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツのバースト時間。</span><span class="sxs-lookup"><span data-stu-id="bed90-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-297">int</span><span class="sxs-lookup"><span data-stu-id="bed90-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-298">閲覧者に届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツの Gap オカレンス。</span><span class="sxs-lookup"><span data-stu-id="bed90-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-300">float</span><span class="sxs-lookup"><span data-stu-id="bed90-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-301">ビューアーに届かなかったが、新しいコンテンツで破棄されて上書きされたコンテンツの Gap 濃度。</span><span class="sxs-lookup"><span data-stu-id="bed90-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-303">float</span><span class="sxs-lookup"><span data-stu-id="bed90-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-304">ビューアーに届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツの間隔の期間。</span><span class="sxs-lookup"><span data-stu-id="bed90-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-306">float</span><span class="sxs-lookup"><span data-stu-id="bed90-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-307">グラフィックスソースから scraped フレームの合計数です。</span><span class="sxs-lookup"><span data-stu-id="bed90-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-309">float</span><span class="sxs-lookup"><span data-stu-id="bed90-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-310">グラフィックスソースから scraped フレームの平均数。</span><span class="sxs-lookup"><span data-stu-id="bed90-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-312">float</span><span class="sxs-lookup"><span data-stu-id="bed90-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-313">グラフィックスソースから scraped フレームの最大数。</span><span class="sxs-lookup"><span data-stu-id="bed90-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-315">int</span><span class="sxs-lookup"><span data-stu-id="bed90-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-316">グラフィックソースからフレームの scraped が発生します。</span><span class="sxs-lookup"><span data-stu-id="bed90-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-318">float</span><span class="sxs-lookup"><span data-stu-id="bed90-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-319">グラフィックスソースからのフレーム scraped のバースト密度。</span><span class="sxs-lookup"><span data-stu-id="bed90-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-321">float</span><span class="sxs-lookup"><span data-stu-id="bed90-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-322">グラフィックスソースからのフレーム scraped のバースト時間。</span><span class="sxs-lookup"><span data-stu-id="bed90-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-324">int</span><span class="sxs-lookup"><span data-stu-id="bed90-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-325">グラフィックソースから、フレーム内の Gap オカレンスが scraped ます。</span><span class="sxs-lookup"><span data-stu-id="bed90-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-327">float</span><span class="sxs-lookup"><span data-stu-id="bed90-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-328">グラフィックスソースから scraped フレームの間隔の濃度。</span><span class="sxs-lookup"><span data-stu-id="bed90-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-330">float</span><span class="sxs-lookup"><span data-stu-id="bed90-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-331">グラフィックスソースから scraped フレームの間隔を指定します。</span><span class="sxs-lookup"><span data-stu-id="bed90-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-333">float</span><span class="sxs-lookup"><span data-stu-id="bed90-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-334">視聴者が受信したフレームの合計料金。</span><span class="sxs-lookup"><span data-stu-id="bed90-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-336">float</span><span class="sxs-lookup"><span data-stu-id="bed90-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-337">視聴者が受信したフレームの平均速度。</span><span class="sxs-lookup"><span data-stu-id="bed90-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-339">float</span><span class="sxs-lookup"><span data-stu-id="bed90-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-340">視聴者が受信した最大受信タイルレート。</span><span class="sxs-lookup"><span data-stu-id="bed90-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-342">int</span><span class="sxs-lookup"><span data-stu-id="bed90-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-343">視聴者が受信したタイルレートでのバースト発生</span><span class="sxs-lookup"><span data-stu-id="bed90-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-345">float</span><span class="sxs-lookup"><span data-stu-id="bed90-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-346">視聴者が受信したタイルレートのバースト密度。</span><span class="sxs-lookup"><span data-stu-id="bed90-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-348">float</span><span class="sxs-lookup"><span data-stu-id="bed90-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-349">閲覧者が受信した受信タイルレートのバースト時間。</span><span class="sxs-lookup"><span data-stu-id="bed90-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-351">int</span><span class="sxs-lookup"><span data-stu-id="bed90-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-352">閲覧者が受信したタイルレートのギャップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bed90-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-354">float</span><span class="sxs-lookup"><span data-stu-id="bed90-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-355">閲覧者によって受信された、受信タイルレートのギャップの密度。</span><span class="sxs-lookup"><span data-stu-id="bed90-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-357">float</span><span class="sxs-lookup"><span data-stu-id="bed90-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-358">視聴者が受信したタイルレートの間隔。</span><span class="sxs-lookup"><span data-stu-id="bed90-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-360">float</span><span class="sxs-lookup"><span data-stu-id="bed90-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-361">視聴者が受信したフレームの合計料金。</span><span class="sxs-lookup"><span data-stu-id="bed90-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-363">float</span><span class="sxs-lookup"><span data-stu-id="bed90-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-364">視聴者が受信したフレームの平均速度。</span><span class="sxs-lookup"><span data-stu-id="bed90-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-366">float</span><span class="sxs-lookup"><span data-stu-id="bed90-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-367">視聴者が受信した受信フレームレートの上限。</span><span class="sxs-lookup"><span data-stu-id="bed90-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-369">int</span><span class="sxs-lookup"><span data-stu-id="bed90-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-370">視聴者が受信したフレームレートのバーストが発生します。</span><span class="sxs-lookup"><span data-stu-id="bed90-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-372">float</span><span class="sxs-lookup"><span data-stu-id="bed90-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-373">視聴者が受信したフレームレートのバースト密度。</span><span class="sxs-lookup"><span data-stu-id="bed90-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-375">float</span><span class="sxs-lookup"><span data-stu-id="bed90-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-376">ビューアーで受信した受信フレームレートのバースト時間。</span><span class="sxs-lookup"><span data-stu-id="bed90-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-378">int</span><span class="sxs-lookup"><span data-stu-id="bed90-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-379">閲覧者が受信したフレームレートのギャップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bed90-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-381">float</span><span class="sxs-lookup"><span data-stu-id="bed90-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-382">視聴者が受信したフレームレートの間隔。</span><span class="sxs-lookup"><span data-stu-id="bed90-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-384">float</span><span class="sxs-lookup"><span data-stu-id="bed90-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-385">視聴者が受信したフレームレートの間隔。</span><span class="sxs-lookup"><span data-stu-id="bed90-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-387">float</span><span class="sxs-lookup"><span data-stu-id="bed90-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-388">送信者の合計送信タイルレート。</span><span class="sxs-lookup"><span data-stu-id="bed90-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-390">float</span><span class="sxs-lookup"><span data-stu-id="bed90-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-391">送信者の平均送信タイルレート。</span><span class="sxs-lookup"><span data-stu-id="bed90-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-393">float</span><span class="sxs-lookup"><span data-stu-id="bed90-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-394">送信者の最大送信タイルレート。</span><span class="sxs-lookup"><span data-stu-id="bed90-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-396">int</span><span class="sxs-lookup"><span data-stu-id="bed90-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-397">送信者の送信タイルレートのバーストが発生します。</span><span class="sxs-lookup"><span data-stu-id="bed90-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-399">float</span><span class="sxs-lookup"><span data-stu-id="bed90-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-400">送信者の送信タイルレートのバースト密度。</span><span class="sxs-lookup"><span data-stu-id="bed90-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-402">float</span><span class="sxs-lookup"><span data-stu-id="bed90-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-403">送信者の送信タイルレートのバースト時間。</span><span class="sxs-lookup"><span data-stu-id="bed90-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-405">int</span><span class="sxs-lookup"><span data-stu-id="bed90-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-406">送信者に対して、送信タイルレートのギャップが発生します。</span><span class="sxs-lookup"><span data-stu-id="bed90-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-408">float</span><span class="sxs-lookup"><span data-stu-id="bed90-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-409">送信者の送信タイルレートの間隔。</span><span class="sxs-lookup"><span data-stu-id="bed90-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-411">float</span><span class="sxs-lookup"><span data-stu-id="bed90-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-412">送信者の送信タイルレートの間隔。</span><span class="sxs-lookup"><span data-stu-id="bed90-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-414">float</span><span class="sxs-lookup"><span data-stu-id="bed90-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-415">送信者の総送信フレームレート。</span><span class="sxs-lookup"><span data-stu-id="bed90-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-417">float</span><span class="sxs-lookup"><span data-stu-id="bed90-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-418">送信者の平均送信フレームレート。</span><span class="sxs-lookup"><span data-stu-id="bed90-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-420">float</span><span class="sxs-lookup"><span data-stu-id="bed90-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-421">送信者の最大送信フレームレート。</span><span class="sxs-lookup"><span data-stu-id="bed90-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-423">int</span><span class="sxs-lookup"><span data-stu-id="bed90-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-424">送信者の送信フレームレートでのバースト発生。</span><span class="sxs-lookup"><span data-stu-id="bed90-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-426">float</span><span class="sxs-lookup"><span data-stu-id="bed90-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-427">送信者の送信フレームレートのバースト密度。</span><span class="sxs-lookup"><span data-stu-id="bed90-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-429">float</span><span class="sxs-lookup"><span data-stu-id="bed90-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-430">送信者の送信フレームレートのバースト時間。</span><span class="sxs-lookup"><span data-stu-id="bed90-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-432">int</span><span class="sxs-lookup"><span data-stu-id="bed90-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-433">送信者に対して送信されるフレームレートのギャップ。</span><span class="sxs-lookup"><span data-stu-id="bed90-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-435">float</span><span class="sxs-lookup"><span data-stu-id="bed90-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-436">送信者の発信フレームレートのギャップの密度。</span><span class="sxs-lookup"><span data-stu-id="bed90-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-438">float</span><span class="sxs-lookup"><span data-stu-id="bed90-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-439">送信者の発信フレームレートの間隔。</span><span class="sxs-lookup"><span data-stu-id="bed90-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-441">int</span><span class="sxs-lookup"><span data-stu-id="bed90-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-442">平均ビデオ解像度の高さ (ピクセル単位)。</span><span class="sxs-lookup"><span data-stu-id="bed90-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-444">int</span><span class="sxs-lookup"><span data-stu-id="bed90-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-445">平均ビデオ解像度の幅 (ピクセル単位)。</span><span class="sxs-lookup"><span data-stu-id="bed90-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-446"><strong>トラフィック</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-447">bit</span><span class="sxs-lookup"><span data-stu-id="bed90-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-448">受信伝送の平均フレームレート (1 秒あたりのフレーム数)。</span><span class="sxs-lookup"><span data-stu-id="bed90-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed90-449"><strong>発信</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-450">bit</span><span class="sxs-lookup"><span data-stu-id="bed90-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-451">送信時の平均フレームレート (1 秒あたりのフレーム数)。</span><span class="sxs-lookup"><span data-stu-id="bed90-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed90-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="bed90-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="bed90-453">bit</span><span class="sxs-lookup"><span data-stu-id="bed90-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bed90-454">1ストリームの方向は、呼び出し元から呼び出し先へとなります。</span><span class="sxs-lookup"><span data-stu-id="bed90-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="bed90-455">0は、ストリームの方向を呼び出し元から呼び出し元に転送します。</span><span class="sxs-lookup"><span data-stu-id="bed90-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

