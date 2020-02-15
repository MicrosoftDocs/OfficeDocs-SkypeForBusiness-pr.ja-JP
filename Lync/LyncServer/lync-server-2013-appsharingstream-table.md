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
ms.openlocfilehash: 31a75ddd223816c57a69bd0c9e88b48845d4374e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029308"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="e28ae-102">Lync Server 2013 の AppSharingStream テーブル</span><span class="sxs-lookup"><span data-stu-id="e28ae-102">AppSharingStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e28ae-103">_**トピックの最終更新日:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="e28ae-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="e28ae-104">AppSharingStream テーブルには、アプリケーション共有のストリームが使用するネットワークの QoE 測定値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e28ae-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="e28ae-105">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e28ae-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e28ae-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e28ae-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e28ae-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e28ae-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-111">dateTime</span><span class="sxs-lookup"><span data-stu-id="e28ae-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="e28ae-112">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="e28ae-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e28ae-113">セッションが開始した日時。</span><span class="sxs-lookup"><span data-stu-id="e28ae-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-115">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-115">int</span></span></p></td>
<td><p><span data-ttu-id="e28ae-116">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="e28ae-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e28ae-117">同じ日付に、同時に開始したセッションを区別する順次識別子。</span><span class="sxs-lookup"><span data-stu-id="e28ae-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="e28ae-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e28ae-120">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="e28ae-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e28ae-p102">通話で使用されたビデオ回線の種類を表します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e28ae-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="e28ae-123">0–音声</span><span class="sxs-lookup"><span data-stu-id="e28ae-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="e28ae-124">1–ビデオ</span><span class="sxs-lookup"><span data-stu-id="e28ae-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="e28ae-125">2 -- パノラマ ビデオ</span><span class="sxs-lookup"><span data-stu-id="e28ae-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="e28ae-126">3–アプリケーション/デスクトップ共有</span><span class="sxs-lookup"><span data-stu-id="e28ae-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-127"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-128">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-128">int</span></span></p></td>
<td><p><span data-ttu-id="e28ae-129">Primary</span><span class="sxs-lookup"><span data-stu-id="e28ae-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="e28ae-130">アプリケーション共有ストリームの一意識別子。</span><span class="sxs-lookup"><span data-stu-id="e28ae-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-132">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-133">RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。</span><span class="sxs-lookup"><span data-stu-id="e28ae-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="e28ae-134">(ジッターは、通話の&quot;過&quot;の測定値です)。高ジッター値は、通常、混雑または過負荷のメディアサーバーによって発生し、その結果、音声がひずむか失われます。</span><span class="sxs-lookup"><span data-stu-id="e28ae-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-136">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-137">RTP パケットの着信間に検出された最大ジッター (ジッターとは、通話の "揺れ" の測定値です)。</span><span class="sxs-lookup"><span data-stu-id="e28ae-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="e28ae-138">(ジッターは、通話の&quot;過&quot;の測定値です)。高ジッター値は、通常、混雑または過負荷のメディアサーバーによって発生し、その結果、音声がひずむか失われます。</span><span class="sxs-lookup"><span data-stu-id="e28ae-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-139"><strong>要し</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-140">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-p105">リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する平均時間 (ミリ秒単位)。200 ミリ秒以下の往復時間が許容できる品質と見なされます。</span><span class="sxs-lookup"><span data-stu-id="e28ae-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="e28ae-p106">この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。</span><span class="sxs-lookup"><span data-stu-id="e28ae-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-146">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-p107">リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する最大時間 (ミリ秒単位)。200 ミリ秒以下の往復時間が許容できる品質と見なされます。</span><span class="sxs-lookup"><span data-stu-id="e28ae-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="e28ae-p108">この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。</span><span class="sxs-lookup"><span data-stu-id="e28ae-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-152">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-p109">リアルタイム転送プロトコル (RTP) パケット損失の平均レート。(パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを転送するために使われるプロトコルの一種で、パケットが宛先に到達できなかったときに発生します。) この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="e28ae-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-157">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-p110">リアルタイム転送プロトコル (RTP) パケット損失の最大レート。(パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを転送するために使われるプロトコルの一種で、パケットが宛先に到達できなかったときに発生します。) この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="e28ae-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-162">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-163">送信されたパケット数。</span><span class="sxs-lookup"><span data-stu-id="e28ae-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-164"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-165">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-p111">セッションの最後での、推定された一方向の帯域幅。ビット/秒で報告されます。</span><span class="sxs-lookup"><span data-stu-id="e28ae-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-169">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-170">アプリケーション共有ペイロードの詳細。</span><span class="sxs-lookup"><span data-stu-id="e28ae-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-172">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-p112">一方向の遅延の合計時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</span><span class="sxs-lookup"><span data-stu-id="e28ae-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-176">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-p113">一方向の遅延の平均時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</span><span class="sxs-lookup"><span data-stu-id="e28ae-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-180">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-p114">一方向の遅延の最大時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</span><span class="sxs-lookup"><span data-stu-id="e28ae-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-184">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-p115">一方向のバーストの合計発生数。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="e28ae-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-189">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-p116">一方向のバーストの合計密度。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="e28ae-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-194">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-p117">一方向のバーストの合計期間。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="e28ae-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-199">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-p118">一方向のギャップの合計発生数。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="e28ae-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-204">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-p119">一方向のギャップの合計密度。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="e28ae-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-209">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-p120">一方向のギャップの合計期間。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="e28ae-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="e28ae-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-215">アプリケーション役割 (共有者または視聴者) とコンテンツ タイプ。</span><span class="sxs-lookup"><span data-stu-id="e28ae-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-217">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-p121">リモート デスクトップ プロトコル (RDP) タイルの合計の処理時間。この値が多いことは、表示に遅延が発生していることを示します。</span><span class="sxs-lookup"><span data-stu-id="e28ae-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-220"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-221">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-p122">リモート デスクトップ プロトコル (RDP) タイルの平均の処理時間。この値が多いことは、表示に遅延が発生していることを示します。</span><span class="sxs-lookup"><span data-stu-id="e28ae-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-225">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-p123">リモート デスクトップ プロトコル (RDP) タイルの最大の処理時間。この値が多いことは、表示に遅延が発生していることを示します。</span><span class="sxs-lookup"><span data-stu-id="e28ae-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-229">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-p124">リモート デスクトップ プロトコル (RDP) タイルの処理時間でのバースト発生数。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。</span><span class="sxs-lookup"><span data-stu-id="e28ae-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-233">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-p125">リモート デスクトップ プロトコル (RDP) タイルの処理時間でのバースト密度。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。</span><span class="sxs-lookup"><span data-stu-id="e28ae-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-237">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-p126">リモート デスクトップ プロトコル (RDP) タイルの処理時間でのバースト持続時間。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。</span><span class="sxs-lookup"><span data-stu-id="e28ae-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-241">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-242">リモート デスクトップ プロトコル (RDP) タイルの処理時間でのギャップ発生数。</span><span class="sxs-lookup"><span data-stu-id="e28ae-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-244">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-p127">リモート デスクトップ プロトコル (RDP) タイルの処理時間でのギャップ密度。ギャップ密度が低いことは、表示エクスペリエンスが良いことを示します。</span><span class="sxs-lookup"><span data-stu-id="e28ae-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-248">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-p128">リモート デスクトップ プロトコル (RDP) タイルの処理時間でのギャップ持続時間。持続時間が短いことは、表示エクスペリエンスが良いことを示します。</span><span class="sxs-lookup"><span data-stu-id="e28ae-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-252">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-253">キャプチャされたタイルの合計のレート (タイル/秒)。</span><span class="sxs-lookup"><span data-stu-id="e28ae-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-255">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-256">キャプチャされたタイルの平均のレート (タイル/秒)。</span><span class="sxs-lookup"><span data-stu-id="e28ae-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-258">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-259">キャプチャされたタイルの最大のレート (タイル/秒)。</span><span class="sxs-lookup"><span data-stu-id="e28ae-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-261">in t</span><span class="sxs-lookup"><span data-stu-id="e28ae-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-262">キャプチャされたタイルのレート (タイル/秒) でのバースト発生数。</span><span class="sxs-lookup"><span data-stu-id="e28ae-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-264">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-265">キャプチャされたタイルのレート (タイル/秒) でのバースト密度。</span><span class="sxs-lookup"><span data-stu-id="e28ae-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-267">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-268">キャプチャされたタイルのレート (タイル/秒) でのバースト持続時間。</span><span class="sxs-lookup"><span data-stu-id="e28ae-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-270">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-271">キャプチャされたタイルのレート (タイル/秒) でのギャップ発生数。</span><span class="sxs-lookup"><span data-stu-id="e28ae-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-273">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-274">キャプチャされたタイルのレート (タイル/秒) でのギャップ密度。</span><span class="sxs-lookup"><span data-stu-id="e28ae-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-276">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-277">キャプチャされたタイルのレート (タイル/秒) でのギャップ持続時間。</span><span class="sxs-lookup"><span data-stu-id="e28ae-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-278"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-279">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-280">視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツの合計の割合。</span><span class="sxs-lookup"><span data-stu-id="e28ae-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-282">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-283">視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツの平均の割合。</span><span class="sxs-lookup"><span data-stu-id="e28ae-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-285">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-286">視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツの最大の割合。</span><span class="sxs-lookup"><span data-stu-id="e28ae-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-288">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-289">視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツでのバースト発生数。</span><span class="sxs-lookup"><span data-stu-id="e28ae-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-291">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-292">視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツでのバースト密度。</span><span class="sxs-lookup"><span data-stu-id="e28ae-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-294">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-295">視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツでのバースト持続時間。</span><span class="sxs-lookup"><span data-stu-id="e28ae-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-297">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-298">視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツでのギャップ発生数。</span><span class="sxs-lookup"><span data-stu-id="e28ae-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-300">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-301">視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツでのギャップ密度。</span><span class="sxs-lookup"><span data-stu-id="e28ae-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-303">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-304">視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツでのギャップ持続時間。</span><span class="sxs-lookup"><span data-stu-id="e28ae-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-306">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-307">グラフィックス ソースからスクレープされたフレームの合計数。</span><span class="sxs-lookup"><span data-stu-id="e28ae-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-309">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-310">グラフィックス ソースからスクレープされたフレームの平均数。</span><span class="sxs-lookup"><span data-stu-id="e28ae-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-312">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-313">グラフィックス ソースからスクレープされたフレームの最大数。</span><span class="sxs-lookup"><span data-stu-id="e28ae-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-315">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-316">グラフィックス ソースからスクレープされたフレームのバースト発生数。</span><span class="sxs-lookup"><span data-stu-id="e28ae-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-318">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-319">グラフィックス ソースからスクレープされたフレームのバースト密度。</span><span class="sxs-lookup"><span data-stu-id="e28ae-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-321">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-322">グラフィックス ソースからスクレープされたフレームのバースト持続時間。</span><span class="sxs-lookup"><span data-stu-id="e28ae-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-324">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-325">グラフィックス ソースからスクレープされたフレームのギャップ発生数。</span><span class="sxs-lookup"><span data-stu-id="e28ae-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-327">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-328">グラフィックス ソースからスクレープされたフレームのギャップ密度。</span><span class="sxs-lookup"><span data-stu-id="e28ae-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-330">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-331">グラフィックス ソースからスクレープされたフレームのギャップ持続時間。</span><span class="sxs-lookup"><span data-stu-id="e28ae-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-333">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-334">閲覧者が受信するときの合計受信フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="e28ae-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-336">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-337">閲覧者が受信するときの平均受信フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="e28ae-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-339">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-340">閲覧者が受信するときの最大受信タイル レート。</span><span class="sxs-lookup"><span data-stu-id="e28ae-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-342">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-343">閲覧者が受信する受信タイル レートでのバースト発生数。</span><span class="sxs-lookup"><span data-stu-id="e28ae-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-345">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-346">閲覧者が受信する受信タイル レートでのバースト密度。</span><span class="sxs-lookup"><span data-stu-id="e28ae-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-348">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-349">閲覧者が受信する受信タイル レートでのバースト持続時間。</span><span class="sxs-lookup"><span data-stu-id="e28ae-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-351">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-352">閲覧者が受信する受信タイル レートでのギャップ発生数。</span><span class="sxs-lookup"><span data-stu-id="e28ae-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-354">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-355">閲覧者が受信する受信タイル レートでのギャップ密度。</span><span class="sxs-lookup"><span data-stu-id="e28ae-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-357">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-358">閲覧者が受信する受信タイル レートでのギャップ持続時間。</span><span class="sxs-lookup"><span data-stu-id="e28ae-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-360">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-361">閲覧者が受信するときの合計受信フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="e28ae-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-363">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-364">閲覧者が受信するときの平均受信フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="e28ae-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-366">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-367">閲覧者が受信するときの最大受信フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="e28ae-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-369">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-370">閲覧者が受信する受信フレーム レートでのバースト発生数。</span><span class="sxs-lookup"><span data-stu-id="e28ae-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-372">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-373">閲覧者が受信する受信フレーム レートでのバースト密度。</span><span class="sxs-lookup"><span data-stu-id="e28ae-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-375">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-376">閲覧者が受信する受信フレーム レートでのバースト持続時間。</span><span class="sxs-lookup"><span data-stu-id="e28ae-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-378">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-379">閲覧者が受信する受信フレーム レートでのギャップ発生数。</span><span class="sxs-lookup"><span data-stu-id="e28ae-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-381">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-382">閲覧者が受信する受信フレーム レートでのギャップ密度。</span><span class="sxs-lookup"><span data-stu-id="e28ae-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-384">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-385">閲覧者が受信する受信フレーム レートでのギャップ持続時間。</span><span class="sxs-lookup"><span data-stu-id="e28ae-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-387">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-388">送信者の合計の送信タイル レート。</span><span class="sxs-lookup"><span data-stu-id="e28ae-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-390">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-391">送信者の平均の送信タイル レート。</span><span class="sxs-lookup"><span data-stu-id="e28ae-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-393">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-394">送信者の最大の送信タイル レート。</span><span class="sxs-lookup"><span data-stu-id="e28ae-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-396">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-397">送信者の送信タイル レートのバースト発生数。</span><span class="sxs-lookup"><span data-stu-id="e28ae-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-399">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-400">送信者の送信タイル レートのバースト密度。</span><span class="sxs-lookup"><span data-stu-id="e28ae-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-402">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-403">送信者の送信タイル レートのバースト持続時間。</span><span class="sxs-lookup"><span data-stu-id="e28ae-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-405">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-406">送信者の送信タイル レートのギャップ発生数。</span><span class="sxs-lookup"><span data-stu-id="e28ae-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-408">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-409">送信者の送信タイル レートのギャップ密度。</span><span class="sxs-lookup"><span data-stu-id="e28ae-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-411">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-412">送信者の送信タイル レートのギャップ持続時間。</span><span class="sxs-lookup"><span data-stu-id="e28ae-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-414">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-415">送信者の合計の送信フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="e28ae-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-417">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-418">送信者の平均の送信フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="e28ae-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-420">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-421">送信者の最大の送信フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="e28ae-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-423">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-424">送信者の送信フレーム レートのバースト発生数。</span><span class="sxs-lookup"><span data-stu-id="e28ae-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-426">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-427">送信者の送信フレーム レートのバースト密度。</span><span class="sxs-lookup"><span data-stu-id="e28ae-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-429">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-430">送信者の送信フレーム レートのバースト持続時間。</span><span class="sxs-lookup"><span data-stu-id="e28ae-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-432">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-433">送信者の送信フレーム レートのギャップ発生数。</span><span class="sxs-lookup"><span data-stu-id="e28ae-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-435">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-436">送信者の送信フレーム レートのギャップ密度。</span><span class="sxs-lookup"><span data-stu-id="e28ae-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-438">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e28ae-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-439">送信者の送信フレーム レートのギャップ持続時間。</span><span class="sxs-lookup"><span data-stu-id="e28ae-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-441">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-442">平均のビデオ解像度の高さ (ピクセル)。</span><span class="sxs-lookup"><span data-stu-id="e28ae-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-444">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-445">平均のビデオ解像度の幅 (ピクセル)。</span><span class="sxs-lookup"><span data-stu-id="e28ae-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-446"><strong>受信</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-447">若干</span><span class="sxs-lookup"><span data-stu-id="e28ae-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-448">着信の平均フレーム レート (フレーム/秒)。</span><span class="sxs-lookup"><span data-stu-id="e28ae-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-449"><strong>送信</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-450">若干</span><span class="sxs-lookup"><span data-stu-id="e28ae-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-451">発信の平均フレーム レート (フレーム/秒)。</span><span class="sxs-lookup"><span data-stu-id="e28ae-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-453">若干</span><span class="sxs-lookup"><span data-stu-id="e28ae-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e28ae-454">1 は、ストリームの方向が発信者から呼び出し先へ向かうことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e28ae-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="e28ae-455">0 は、ストリームの方向が呼び出し先から発信者へ向かうことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e28ae-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

