---
title: 'Lync Server 2013: AppSharingStream テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AppSharingStream table
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48183852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56f23e214ffcffad8613d413924a53ffe571883d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="41729-102">Lync Server 2013 の AppSharingStream テーブル</span><span class="sxs-lookup"><span data-stu-id="41729-102">AppSharingStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41729-103">_**最終更新日:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="41729-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="41729-104">AppSharingStream テーブルには、アプリケーション共有に使用されるネットワークストリームのエクスペリエンスのメトリックの質が含まれています。</span><span class="sxs-lookup"><span data-stu-id="41729-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="41729-105">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="41729-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41729-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="41729-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="41729-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="41729-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="41729-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="41729-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="41729-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="41729-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41729-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="41729-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-111">dateTime</span><span class="sxs-lookup"><span data-stu-id="41729-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="41729-112">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="41729-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="41729-113">セッションが開始された日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="41729-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="41729-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-115">int</span><span class="sxs-lookup"><span data-stu-id="41729-115">int</span></span></p></td>
<td><p><span data-ttu-id="41729-116">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="41729-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="41729-117">同じ日付と同時に開始したセッションを区別するために使用されるシーケンシャル識別子。</span><span class="sxs-lookup"><span data-stu-id="41729-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="41729-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="41729-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="41729-120">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="41729-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="41729-121">通話で使用されるビデオラインの種類を表します。</span><span class="sxs-lookup"><span data-stu-id="41729-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="41729-122">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="41729-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="41729-123">0–音声</span><span class="sxs-lookup"><span data-stu-id="41729-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="41729-124">1-ビデオ</span><span class="sxs-lookup"><span data-stu-id="41729-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="41729-125">2-パノラマビデオ</span><span class="sxs-lookup"><span data-stu-id="41729-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="41729-126">3-アプリケーション/デスクトップ共有</span><span class="sxs-lookup"><span data-stu-id="41729-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-127"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="41729-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-128">int</span><span class="sxs-lookup"><span data-stu-id="41729-128">int</span></span></p></td>
<td><p><span data-ttu-id="41729-129">Primary</span><span class="sxs-lookup"><span data-stu-id="41729-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="41729-130">アプリケーション共有ストリームの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="41729-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="41729-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-132">int</span><span class="sxs-lookup"><span data-stu-id="41729-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-133">RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。</span><span class="sxs-lookup"><span data-stu-id="41729-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="41729-134">(ジッタは、通話の&quot;shakiness&quot;の尺度です)。通常、高ジッターの値は、輻輳または過負荷のメディアサーバーによって発生し、音声が歪むか、失われる原因となります。</span><span class="sxs-lookup"><span data-stu-id="41729-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="41729-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-136">int</span><span class="sxs-lookup"><span data-stu-id="41729-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-137">RTP パケット着信の間の最大ジッターが検出されました。</span><span class="sxs-lookup"><span data-stu-id="41729-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="41729-138">(ジッタは、通話の&quot;shakiness&quot;の尺度です)。通常、高ジッターの値は、輻輳または過負荷のメディアサーバーによって発生し、音声が歪むか、失われる原因となります。</span><span class="sxs-lookup"><span data-stu-id="41729-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-139"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="41729-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-140">int</span><span class="sxs-lookup"><span data-stu-id="41729-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-p105">リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する平均時間 (ミリ秒単位)。200 ミリ秒以下の往復時間が許容できる品質と見なされます。</span><span class="sxs-lookup"><span data-stu-id="41729-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="41729-p106">この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。</span><span class="sxs-lookup"><span data-stu-id="41729-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="41729-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-146">int</span><span class="sxs-lookup"><span data-stu-id="41729-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-147">リアルタイムトランスポートプロトコルパケットが別のエンドポイントに移動してから戻るために必要な最大 (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="41729-147">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="41729-148">200 ミリ秒以下の往復時間が許容できる品質と見なされます。</span><span class="sxs-lookup"><span data-stu-id="41729-148">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="41729-p108">この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。</span><span class="sxs-lookup"><span data-stu-id="41729-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="41729-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-152">float</span><span class="sxs-lookup"><span data-stu-id="41729-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-p109">リアルタイム転送プロトコル (RTP) パケット損失の平均レート。(パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを転送するために使われるプロトコルの一種で、パケットが宛先に到達できなかったときに発生します)。この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="41729-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="41729-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-157">float</span><span class="sxs-lookup"><span data-stu-id="41729-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-158">リアルタイムトランスポートプロトコル (RTP) パケット損失の最大速度。</span><span class="sxs-lookup"><span data-stu-id="41729-158">Maximum rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="41729-159">(パケットの損失は、RTP パケット、インターネット上でのオーディオとビデオの伝送に使用されるプロトコル)、宛先への到達に失敗した場合に発生します。)通常、高損失率は輻輳が原因で発生します。帯域幅の不足。ワイヤレスの輻輳または妨害または、オーバーロードされたメディアサーバー。</span><span class="sxs-lookup"><span data-stu-id="41729-159">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="41729-160">パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="41729-160">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="41729-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-162">int</span><span class="sxs-lookup"><span data-stu-id="41729-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-163">送信されたパケットの数です。</span><span class="sxs-lookup"><span data-stu-id="41729-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-164"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="41729-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-165">int</span><span class="sxs-lookup"><span data-stu-id="41729-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-166">セッションの終了時に提供される推定される一方向の帯域幅。</span><span class="sxs-lookup"><span data-stu-id="41729-166">Estimated one-way bandwidth available at the end of the session.</span></span> <span data-ttu-id="41729-167">1秒あたりのビット数で報告されます。</span><span class="sxs-lookup"><span data-stu-id="41729-167">Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="41729-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-169">int</span><span class="sxs-lookup"><span data-stu-id="41729-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-170">アプリケーション共有ペイロードの説明。</span><span class="sxs-lookup"><span data-stu-id="41729-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="41729-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-172">float</span><span class="sxs-lookup"><span data-stu-id="41729-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-173">一方向の待機時間の合計。</span><span class="sxs-lookup"><span data-stu-id="41729-173">Total amount of one-way latency.</span></span> <span data-ttu-id="41729-174">相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。</span><span class="sxs-lookup"><span data-stu-id="41729-174">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="41729-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-176">float</span><span class="sxs-lookup"><span data-stu-id="41729-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-177">一方向の待ち時間の平均値。</span><span class="sxs-lookup"><span data-stu-id="41729-177">Average amount of one-way latency.</span></span> <span data-ttu-id="41729-178">相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。</span><span class="sxs-lookup"><span data-stu-id="41729-178">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="41729-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-180">float</span><span class="sxs-lookup"><span data-stu-id="41729-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-181">一方向の待機時間の上限。</span><span class="sxs-lookup"><span data-stu-id="41729-181">Maximum amount of one-way latency.</span></span> <span data-ttu-id="41729-182">相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。</span><span class="sxs-lookup"><span data-stu-id="41729-182">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41729-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-184">int</span><span class="sxs-lookup"><span data-stu-id="41729-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-185">1方向のバースト発生の合計。</span><span class="sxs-lookup"><span data-stu-id="41729-185">Total one-way burst occurrences.</span></span> <span data-ttu-id="41729-186">"Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。</span><span class="sxs-lookup"><span data-stu-id="41729-186">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="41729-187">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="41729-187">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41729-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-189">float</span><span class="sxs-lookup"><span data-stu-id="41729-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-190">全体的な1方向バースト密度。</span><span class="sxs-lookup"><span data-stu-id="41729-190">Total one-way burst density.</span></span> <span data-ttu-id="41729-191">"Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。</span><span class="sxs-lookup"><span data-stu-id="41729-191">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="41729-192">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="41729-192">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41729-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-194">float</span><span class="sxs-lookup"><span data-stu-id="41729-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-195">一方向のバースト期間の合計。</span><span class="sxs-lookup"><span data-stu-id="41729-195">Total one-way burst duration.</span></span> <span data-ttu-id="41729-196">"Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。</span><span class="sxs-lookup"><span data-stu-id="41729-196">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="41729-197">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="41729-197">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41729-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-199">int</span><span class="sxs-lookup"><span data-stu-id="41729-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-200">一方向のギャップ出現の合計。</span><span class="sxs-lookup"><span data-stu-id="41729-200">Total one-way gap occurrences.</span></span> <span data-ttu-id="41729-201">"Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。</span><span class="sxs-lookup"><span data-stu-id="41729-201">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="41729-202">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="41729-202">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41729-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-204">float</span><span class="sxs-lookup"><span data-stu-id="41729-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-205">一方向のギャップの密度の合計。</span><span class="sxs-lookup"><span data-stu-id="41729-205">Total one-way gap density.</span></span> <span data-ttu-id="41729-206">"Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。</span><span class="sxs-lookup"><span data-stu-id="41729-206">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="41729-207">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="41729-207">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41729-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-209">float</span><span class="sxs-lookup"><span data-stu-id="41729-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-210">一方向のギャップ期間の合計。</span><span class="sxs-lookup"><span data-stu-id="41729-210">Total one-way gap duration.</span></span> <span data-ttu-id="41729-211">"Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。</span><span class="sxs-lookup"><span data-stu-id="41729-211">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="41729-212">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="41729-212">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="41729-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="41729-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-215">アプリケーションロール (共有先またはビューアー) とコンテンツタイプ。</span><span class="sxs-lookup"><span data-stu-id="41729-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="41729-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-217">float</span><span class="sxs-lookup"><span data-stu-id="41729-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-218">リモートデスクトッププロトコル (RDP) タイルの合計処理時間。</span><span class="sxs-lookup"><span data-stu-id="41729-218">Total processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="41729-219">表示環境では、合計の遅延が長くなります。</span><span class="sxs-lookup"><span data-stu-id="41729-219">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-220"><strong>Rdp タイル処理</strong></span><span class="sxs-lookup"><span data-stu-id="41729-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-221">float</span><span class="sxs-lookup"><span data-stu-id="41729-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-222">リモートデスクトッププロトコル (RDP) タイルの平均処理時間。</span><span class="sxs-lookup"><span data-stu-id="41729-222">Average processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="41729-223">表示環境では、合計の遅延が長くなります。</span><span class="sxs-lookup"><span data-stu-id="41729-223">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="41729-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-225">float</span><span class="sxs-lookup"><span data-stu-id="41729-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-226">リモートデスクトッププロトコル (RDP) タイルの最大処理時間。</span><span class="sxs-lookup"><span data-stu-id="41729-226">Maximum processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="41729-227">表示環境では、合計の遅延が長くなります。</span><span class="sxs-lookup"><span data-stu-id="41729-227">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41729-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-229">int</span><span class="sxs-lookup"><span data-stu-id="41729-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-230">リモートデスクトッププロトコル (RDP) タイルの処理時間でのバースト発生。</span><span class="sxs-lookup"><span data-stu-id="41729-230">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="41729-231">"Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。</span><span class="sxs-lookup"><span data-stu-id="41729-231">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41729-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-233">float</span><span class="sxs-lookup"><span data-stu-id="41729-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-234">リモートデスクトッププロトコル (RDP) タイルの処理時間のバースト密度。</span><span class="sxs-lookup"><span data-stu-id="41729-234">Burst density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="41729-235">"Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。</span><span class="sxs-lookup"><span data-stu-id="41729-235">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41729-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-237">float</span><span class="sxs-lookup"><span data-stu-id="41729-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-238">リモートデスクトッププロトコル (RDP) タイルの処理時間のバースト時間。</span><span class="sxs-lookup"><span data-stu-id="41729-238">Burst duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="41729-239">"Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。</span><span class="sxs-lookup"><span data-stu-id="41729-239">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41729-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-241">int</span><span class="sxs-lookup"><span data-stu-id="41729-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-242">リモートデスクトッププロトコル (RDP) タイルの処理時間のギャップの出現回数。</span><span class="sxs-lookup"><span data-stu-id="41729-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41729-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-244">float</span><span class="sxs-lookup"><span data-stu-id="41729-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-245">リモートデスクトッププロトコル (RDP) タイルの処理時間のギャップの密度。</span><span class="sxs-lookup"><span data-stu-id="41729-245">Gap density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="41729-246">隙間が小さいほど、表示エクスペリエンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="41729-246">Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41729-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-248">float</span><span class="sxs-lookup"><span data-stu-id="41729-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-249">リモートデスクトッププロトコル (RDP) タイルの処理時間の間隔。</span><span class="sxs-lookup"><span data-stu-id="41729-249">Gap duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="41729-250">短い間隔の期間は、表示感が向上するようになります。</span><span class="sxs-lookup"><span data-stu-id="41729-250">Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="41729-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-252">float</span><span class="sxs-lookup"><span data-stu-id="41729-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-253">キャプチャされたタイルの合計レート (1 秒あたりのタイル数)</span><span class="sxs-lookup"><span data-stu-id="41729-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="41729-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-255">float</span><span class="sxs-lookup"><span data-stu-id="41729-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-256">キャプチャされたタイルの平均速度 (1 秒あたりのタイル数)。</span><span class="sxs-lookup"><span data-stu-id="41729-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="41729-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-258">float</span><span class="sxs-lookup"><span data-stu-id="41729-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-259">キャプチャされたタイルの最大速度 (1 秒あたりのタイル数)</span><span class="sxs-lookup"><span data-stu-id="41729-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41729-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-261">t</span><span class="sxs-lookup"><span data-stu-id="41729-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-262">キャプチャされたタイルの速度 (1 秒あたりのタイル) でバーストが発生します。</span><span class="sxs-lookup"><span data-stu-id="41729-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41729-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-264">float</span><span class="sxs-lookup"><span data-stu-id="41729-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-265">キャプチャされたタイルの速度 (1 秒あたりのタイル数) のバースト密度。</span><span class="sxs-lookup"><span data-stu-id="41729-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41729-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-267">float</span><span class="sxs-lookup"><span data-stu-id="41729-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-268">キャプチャされたタイルの割合でのバースト時間 (1 秒あたりのタイル数)。</span><span class="sxs-lookup"><span data-stu-id="41729-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41729-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-270">int</span><span class="sxs-lookup"><span data-stu-id="41729-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-271">キャプチャされたタイルの比率 (1 秒あたりのタイル数) でのギャップ出現回数。</span><span class="sxs-lookup"><span data-stu-id="41729-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41729-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-273">float</span><span class="sxs-lookup"><span data-stu-id="41729-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-274">キャプチャされたタイル (1 秒あたりのタイル数) の間隔の間隔。</span><span class="sxs-lookup"><span data-stu-id="41729-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41729-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-276">float</span><span class="sxs-lookup"><span data-stu-id="41729-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-277">キャプチャされたタイルの割合の間隔 (1 秒あたりのタイル数)</span><span class="sxs-lookup"><span data-stu-id="41729-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-278"><strong>損失タイル</strong></span><span class="sxs-lookup"><span data-stu-id="41729-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-279">float</span><span class="sxs-lookup"><span data-stu-id="41729-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-280">閲覧者に届かなかったが、破棄され、最新のコンテンツによって上書きされたコンテンツの割合の合計。</span><span class="sxs-lookup"><span data-stu-id="41729-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="41729-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-282">float</span><span class="sxs-lookup"><span data-stu-id="41729-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-283">閲覧者に届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツの平均割合。</span><span class="sxs-lookup"><span data-stu-id="41729-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="41729-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-285">float</span><span class="sxs-lookup"><span data-stu-id="41729-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-286">閲覧者に届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツの最大パーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="41729-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41729-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-288">int</span><span class="sxs-lookup"><span data-stu-id="41729-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-289">閲覧者に届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツのバースト発生。</span><span class="sxs-lookup"><span data-stu-id="41729-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41729-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-291">float</span><span class="sxs-lookup"><span data-stu-id="41729-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-292">ビューアーに届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツのバースト密度。</span><span class="sxs-lookup"><span data-stu-id="41729-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41729-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-294">float</span><span class="sxs-lookup"><span data-stu-id="41729-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-295">ビューアーに届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツのバースト時間。</span><span class="sxs-lookup"><span data-stu-id="41729-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41729-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-297">int</span><span class="sxs-lookup"><span data-stu-id="41729-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-298">閲覧者に届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツの Gap オカレンス。</span><span class="sxs-lookup"><span data-stu-id="41729-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41729-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-300">float</span><span class="sxs-lookup"><span data-stu-id="41729-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-301">ビューアーに届かなかったが、新しいコンテンツで破棄されて上書きされたコンテンツの Gap 濃度。</span><span class="sxs-lookup"><span data-stu-id="41729-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41729-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-303">float</span><span class="sxs-lookup"><span data-stu-id="41729-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-304">ビューアーに届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツの間隔の期間。</span><span class="sxs-lookup"><span data-stu-id="41729-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="41729-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-306">float</span><span class="sxs-lookup"><span data-stu-id="41729-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-307">グラフィックスソースから scraped フレームの合計数です。</span><span class="sxs-lookup"><span data-stu-id="41729-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="41729-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-309">float</span><span class="sxs-lookup"><span data-stu-id="41729-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-310">グラフィックスソースから scraped フレームの平均数。</span><span class="sxs-lookup"><span data-stu-id="41729-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="41729-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-312">float</span><span class="sxs-lookup"><span data-stu-id="41729-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-313">グラフィックスソースから scraped フレームの最大数。</span><span class="sxs-lookup"><span data-stu-id="41729-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41729-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-315">int</span><span class="sxs-lookup"><span data-stu-id="41729-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-316">グラフィックソースからフレームの scraped が発生します。</span><span class="sxs-lookup"><span data-stu-id="41729-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41729-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-318">float</span><span class="sxs-lookup"><span data-stu-id="41729-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-319">グラフィックスソースからのフレーム scraped のバースト密度。</span><span class="sxs-lookup"><span data-stu-id="41729-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41729-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-321">float</span><span class="sxs-lookup"><span data-stu-id="41729-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-322">グラフィックスソースからのフレーム scraped のバースト時間。</span><span class="sxs-lookup"><span data-stu-id="41729-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41729-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-324">int</span><span class="sxs-lookup"><span data-stu-id="41729-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-325">グラフィックソースから、フレーム内の Gap オカレンスが scraped ます。</span><span class="sxs-lookup"><span data-stu-id="41729-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41729-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-327">float</span><span class="sxs-lookup"><span data-stu-id="41729-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-328">グラフィックスソースから scraped フレームの間隔の濃度。</span><span class="sxs-lookup"><span data-stu-id="41729-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41729-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-330">float</span><span class="sxs-lookup"><span data-stu-id="41729-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-331">グラフィックスソースから scraped フレームの間隔を指定します。</span><span class="sxs-lookup"><span data-stu-id="41729-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="41729-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-333">float</span><span class="sxs-lookup"><span data-stu-id="41729-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-334">視聴者が受信したフレームの合計料金。</span><span class="sxs-lookup"><span data-stu-id="41729-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="41729-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-336">float</span><span class="sxs-lookup"><span data-stu-id="41729-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-337">視聴者が受信したフレームの平均速度。</span><span class="sxs-lookup"><span data-stu-id="41729-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="41729-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-339">float</span><span class="sxs-lookup"><span data-stu-id="41729-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-340">視聴者が受信した最大受信タイルレート。</span><span class="sxs-lookup"><span data-stu-id="41729-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41729-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-342">int</span><span class="sxs-lookup"><span data-stu-id="41729-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-343">視聴者が受信したタイルレートでのバースト発生</span><span class="sxs-lookup"><span data-stu-id="41729-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41729-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-345">float</span><span class="sxs-lookup"><span data-stu-id="41729-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-346">視聴者が受信したタイルレートのバースト密度。</span><span class="sxs-lookup"><span data-stu-id="41729-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41729-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-348">float</span><span class="sxs-lookup"><span data-stu-id="41729-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-349">閲覧者が受信した受信タイルレートのバースト時間。</span><span class="sxs-lookup"><span data-stu-id="41729-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41729-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-351">int</span><span class="sxs-lookup"><span data-stu-id="41729-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-352">閲覧者が受信したタイルレートのギャップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="41729-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41729-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-354">float</span><span class="sxs-lookup"><span data-stu-id="41729-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-355">閲覧者によって受信された、受信タイルレートのギャップの密度。</span><span class="sxs-lookup"><span data-stu-id="41729-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41729-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-357">float</span><span class="sxs-lookup"><span data-stu-id="41729-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-358">視聴者が受信したタイルレートの間隔。</span><span class="sxs-lookup"><span data-stu-id="41729-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="41729-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-360">float</span><span class="sxs-lookup"><span data-stu-id="41729-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-361">視聴者が受信したフレームの合計料金。</span><span class="sxs-lookup"><span data-stu-id="41729-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="41729-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-363">float</span><span class="sxs-lookup"><span data-stu-id="41729-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-364">視聴者が受信したフレームの平均速度。</span><span class="sxs-lookup"><span data-stu-id="41729-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="41729-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-366">float</span><span class="sxs-lookup"><span data-stu-id="41729-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-367">視聴者が受信した受信フレームレートの上限。</span><span class="sxs-lookup"><span data-stu-id="41729-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41729-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-369">int</span><span class="sxs-lookup"><span data-stu-id="41729-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-370">視聴者が受信したフレームレートのバーストが発生します。</span><span class="sxs-lookup"><span data-stu-id="41729-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41729-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-372">float</span><span class="sxs-lookup"><span data-stu-id="41729-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-373">視聴者が受信したフレームレートのバースト密度。</span><span class="sxs-lookup"><span data-stu-id="41729-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41729-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-375">float</span><span class="sxs-lookup"><span data-stu-id="41729-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-376">ビューアーで受信した受信フレームレートのバースト時間。</span><span class="sxs-lookup"><span data-stu-id="41729-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41729-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-378">int</span><span class="sxs-lookup"><span data-stu-id="41729-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-379">閲覧者が受信したフレームレートのギャップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="41729-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41729-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-381">float</span><span class="sxs-lookup"><span data-stu-id="41729-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-382">視聴者が受信したフレームレートの間隔。</span><span class="sxs-lookup"><span data-stu-id="41729-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41729-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-384">float</span><span class="sxs-lookup"><span data-stu-id="41729-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-385">視聴者が受信したフレームレートの間隔。</span><span class="sxs-lookup"><span data-stu-id="41729-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="41729-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-387">float</span><span class="sxs-lookup"><span data-stu-id="41729-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-388">送信者の合計送信タイルレート。</span><span class="sxs-lookup"><span data-stu-id="41729-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="41729-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-390">float</span><span class="sxs-lookup"><span data-stu-id="41729-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-391">送信者の平均送信タイルレート。</span><span class="sxs-lookup"><span data-stu-id="41729-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="41729-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-393">float</span><span class="sxs-lookup"><span data-stu-id="41729-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-394">送信者の最大送信タイルレート。</span><span class="sxs-lookup"><span data-stu-id="41729-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41729-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-396">int</span><span class="sxs-lookup"><span data-stu-id="41729-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-397">送信者の送信タイルレートのバーストが発生します。</span><span class="sxs-lookup"><span data-stu-id="41729-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41729-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-399">float</span><span class="sxs-lookup"><span data-stu-id="41729-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-400">送信者の送信タイルレートのバースト密度。</span><span class="sxs-lookup"><span data-stu-id="41729-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41729-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-402">float</span><span class="sxs-lookup"><span data-stu-id="41729-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-403">送信者の送信タイルレートのバースト時間。</span><span class="sxs-lookup"><span data-stu-id="41729-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41729-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-405">int</span><span class="sxs-lookup"><span data-stu-id="41729-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-406">送信者に対して、送信タイルレートのギャップが発生します。</span><span class="sxs-lookup"><span data-stu-id="41729-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41729-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-408">float</span><span class="sxs-lookup"><span data-stu-id="41729-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-409">送信者の送信タイルレートの間隔。</span><span class="sxs-lookup"><span data-stu-id="41729-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41729-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-411">float</span><span class="sxs-lookup"><span data-stu-id="41729-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-412">送信者の送信タイルレートの間隔。</span><span class="sxs-lookup"><span data-stu-id="41729-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="41729-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-414">float</span><span class="sxs-lookup"><span data-stu-id="41729-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-415">送信者の総送信フレームレート。</span><span class="sxs-lookup"><span data-stu-id="41729-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="41729-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-417">float</span><span class="sxs-lookup"><span data-stu-id="41729-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-418">送信者の平均送信フレームレート。</span><span class="sxs-lookup"><span data-stu-id="41729-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="41729-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-420">float</span><span class="sxs-lookup"><span data-stu-id="41729-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-421">送信者の最大送信フレームレート。</span><span class="sxs-lookup"><span data-stu-id="41729-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41729-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-423">int</span><span class="sxs-lookup"><span data-stu-id="41729-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-424">送信者の送信フレームレートでのバースト発生。</span><span class="sxs-lookup"><span data-stu-id="41729-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41729-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-426">float</span><span class="sxs-lookup"><span data-stu-id="41729-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-427">送信者の送信フレームレートのバースト密度。</span><span class="sxs-lookup"><span data-stu-id="41729-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41729-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-429">float</span><span class="sxs-lookup"><span data-stu-id="41729-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-430">送信者の送信フレームレートのバースト時間。</span><span class="sxs-lookup"><span data-stu-id="41729-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41729-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-432">int</span><span class="sxs-lookup"><span data-stu-id="41729-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-433">送信者に対して送信されるフレームレートのギャップ。</span><span class="sxs-lookup"><span data-stu-id="41729-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41729-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-435">float</span><span class="sxs-lookup"><span data-stu-id="41729-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-436">送信者の発信フレームレートのギャップの密度。</span><span class="sxs-lookup"><span data-stu-id="41729-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41729-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-438">float</span><span class="sxs-lookup"><span data-stu-id="41729-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-439">送信者の発信フレームレートの間隔。</span><span class="sxs-lookup"><span data-stu-id="41729-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="41729-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-441">int</span><span class="sxs-lookup"><span data-stu-id="41729-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-442">平均ビデオ解像度の高さ (ピクセル単位)。</span><span class="sxs-lookup"><span data-stu-id="41729-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="41729-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-444">int</span><span class="sxs-lookup"><span data-stu-id="41729-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-445">平均ビデオ解像度の幅 (ピクセル単位)。</span><span class="sxs-lookup"><span data-stu-id="41729-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-446"><strong>トラフィック</strong></span><span class="sxs-lookup"><span data-stu-id="41729-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-447">bit</span><span class="sxs-lookup"><span data-stu-id="41729-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-448">受信伝送の平均フレームレート (1 秒あたりのフレーム数)。</span><span class="sxs-lookup"><span data-stu-id="41729-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41729-449"><strong>発信</strong></span><span class="sxs-lookup"><span data-stu-id="41729-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-450">bit</span><span class="sxs-lookup"><span data-stu-id="41729-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-451">送信時の平均フレームレート (1 秒あたりのフレーム数)。</span><span class="sxs-lookup"><span data-stu-id="41729-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41729-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="41729-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="41729-453">bit</span><span class="sxs-lookup"><span data-stu-id="41729-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41729-454">1ストリームの方向は、呼び出し元から呼び出し先へとなります。</span><span class="sxs-lookup"><span data-stu-id="41729-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="41729-455">0は、ストリームの方向を呼び出し元から呼び出し元に転送します。</span><span class="sxs-lookup"><span data-stu-id="41729-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

