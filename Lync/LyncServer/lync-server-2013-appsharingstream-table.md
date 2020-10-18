---
title: 'Lync Server 2013: AppSharingStream テーブル'
description: 'Lync Server 2013: AppSharingStream テーブル。'
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
ms.openlocfilehash: b530af5b489e090e5d0d00fbb01b2b950bafbe5a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574723"
---
# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="d48d0-103">Lync Server 2013 の AppSharingStream テーブル</span><span class="sxs-lookup"><span data-stu-id="d48d0-103">AppSharingStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d48d0-104">_**トピックの最終更新日:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="d48d0-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="d48d0-105">AppSharingStream テーブルには、アプリケーション共有のストリームが使用するネットワークの QoE 測定値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d48d0-105">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="d48d0-106">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d48d0-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d48d0-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d48d0-108"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d48d0-109"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d48d0-110"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-112">dateTime</span><span class="sxs-lookup"><span data-stu-id="d48d0-112">dateTime</span></span></p></td>
<td><p><span data-ttu-id="d48d0-113">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="d48d0-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d48d0-114">セッションが開始した日時。</span><span class="sxs-lookup"><span data-stu-id="d48d0-114">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-116">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-116">int</span></span></p></td>
<td><p><span data-ttu-id="d48d0-117">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="d48d0-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d48d0-118">同じ日付に、同時に開始したセッションを区別する順次識別子。</span><span class="sxs-lookup"><span data-stu-id="d48d0-118">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="d48d0-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d48d0-121">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="d48d0-121">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d48d0-p102">通話で使用されたビデオ回線の種類を表します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d48d0-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="d48d0-124">0–音声</span><span class="sxs-lookup"><span data-stu-id="d48d0-124">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="d48d0-125">1–ビデオ</span><span class="sxs-lookup"><span data-stu-id="d48d0-125">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="d48d0-126">2 -- パノラマ ビデオ</span><span class="sxs-lookup"><span data-stu-id="d48d0-126">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="d48d0-127">3–アプリケーション/デスクトップ共有</span><span class="sxs-lookup"><span data-stu-id="d48d0-127">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-128"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-128"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-129">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-129">int</span></span></p></td>
<td><p><span data-ttu-id="d48d0-130">Primary</span><span class="sxs-lookup"><span data-stu-id="d48d0-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="d48d0-131">アプリケーション共有ストリームの一意識別子。</span><span class="sxs-lookup"><span data-stu-id="d48d0-131">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-132"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-132"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-133">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-133">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-134">RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。</span><span class="sxs-lookup"><span data-stu-id="d48d0-134">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="d48d0-135">(ジッターは、通話の過の測定値です &quot; &quot; )。高ジッター値は、通常、混雑または過負荷のメディアサーバーによって発生し、その結果、音声がひずむか失われます。</span><span class="sxs-lookup"><span data-stu-id="d48d0-135">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-136"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-136"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-137">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-138">RTP パケットの着信間に検出された最大ジッター (ジッターとは、通話の "揺れ" の測定値です)。</span><span class="sxs-lookup"><span data-stu-id="d48d0-138">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="d48d0-139">(ジッターは、通話の過の測定値です &quot; &quot; )。高ジッター値は、通常、混雑または過負荷のメディアサーバーによって発生し、その結果、音声がひずむか失われます。</span><span class="sxs-lookup"><span data-stu-id="d48d0-139">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-140"><strong>要し</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-140"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-141">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-141">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-p105">リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する平均時間 (ミリ秒単位)。200 ミリ秒以下の往復時間が許容できる品質と見なされます。</span><span class="sxs-lookup"><span data-stu-id="d48d0-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="d48d0-p106">この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。</span><span class="sxs-lookup"><span data-stu-id="d48d0-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-146"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-146"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-147">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-147">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-p107">リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する最大時間 (ミリ秒単位)。200 ミリ秒以下の往復時間が許容できる品質と見なされます。</span><span class="sxs-lookup"><span data-stu-id="d48d0-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="d48d0-p108">この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。</span><span class="sxs-lookup"><span data-stu-id="d48d0-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-152"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-152"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-153">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-p109">リアルタイム転送プロトコル (RTP) パケット損失の平均レート。(パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを転送するために使われるプロトコルの一種で、パケットが宛先に到達できなかったときに発生します。) この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="d48d0-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-157"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-157"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-158">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-158">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-p110">リアルタイム転送プロトコル (RTP) パケット損失の最大レート。(パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを転送するために使われるプロトコルの一種で、パケットが宛先に到達できなかったときに発生します。) この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="d48d0-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-162"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-162"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-163">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-163">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-164">送信されたパケット数。</span><span class="sxs-lookup"><span data-stu-id="d48d0-164">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-165"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-165"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-166">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-166">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-p111">セッションの最後での、推定された一方向の帯域幅。ビット/秒で報告されます。</span><span class="sxs-lookup"><span data-stu-id="d48d0-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-169"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-169"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-170">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-170">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-171">アプリケーション共有ペイロードの詳細。</span><span class="sxs-lookup"><span data-stu-id="d48d0-171">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-172"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-172"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-173">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-173">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-p112">一方向の遅延の合計時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</span><span class="sxs-lookup"><span data-stu-id="d48d0-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-176"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-176"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-177">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-177">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-p113">一方向の遅延の平均時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</span><span class="sxs-lookup"><span data-stu-id="d48d0-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-180"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-180"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-181">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-181">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-p114">一方向の遅延の最大時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</span><span class="sxs-lookup"><span data-stu-id="d48d0-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-184"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-184"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-185">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-185">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-p115">一方向のバーストの合計発生数。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="d48d0-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-189"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-189"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-190">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-190">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-p116">一方向のバーストの合計密度。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="d48d0-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-194"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-194"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-195">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-195">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-p117">一方向のバーストの合計期間。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="d48d0-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-199"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-199"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-200">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-200">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-p118">一方向のギャップの合計発生数。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="d48d0-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-204"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-204"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-205">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-205">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-p119">一方向のギャップの合計密度。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="d48d0-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-209"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-209"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-210">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-210">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-p120">一方向のギャップの合計期間。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="d48d0-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-214"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-214"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-215">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="d48d0-215">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-216">アプリケーション役割 (共有者または視聴者) とコンテンツ タイプ。</span><span class="sxs-lookup"><span data-stu-id="d48d0-216">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-217"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-217"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-218">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-218">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-p121">リモート デスクトップ プロトコル (RDP) タイルの合計の処理時間。この値が多いことは、表示に遅延が発生していることを示します。</span><span class="sxs-lookup"><span data-stu-id="d48d0-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-221"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-221"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-222">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-222">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-p122">リモート デスクトップ プロトコル (RDP) タイルの平均の処理時間。この値が多いことは、表示に遅延が発生していることを示します。</span><span class="sxs-lookup"><span data-stu-id="d48d0-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-225"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-225"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-226">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-226">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-p123">リモート デスクトップ プロトコル (RDP) タイルの最大の処理時間。この値が多いことは、表示に遅延が発生していることを示します。</span><span class="sxs-lookup"><span data-stu-id="d48d0-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-229"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-229"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-230">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-230">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-p124">リモート デスクトップ プロトコル (RDP) タイルの処理時間でのバースト発生数。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。</span><span class="sxs-lookup"><span data-stu-id="d48d0-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-233"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-233"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-234">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-234">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-p125">リモート デスクトップ プロトコル (RDP) タイルの処理時間でのバースト密度。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。</span><span class="sxs-lookup"><span data-stu-id="d48d0-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-237"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-237"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-238">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-238">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-p126">リモート デスクトップ プロトコル (RDP) タイルの処理時間でのバースト持続時間。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。</span><span class="sxs-lookup"><span data-stu-id="d48d0-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-241"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-241"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-242">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-242">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-243">リモート デスクトップ プロトコル (RDP) タイルの処理時間でのギャップ発生数。</span><span class="sxs-lookup"><span data-stu-id="d48d0-243">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-244"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-244"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-245">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-245">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-p127">リモート デスクトップ プロトコル (RDP) タイルの処理時間でのギャップ密度。ギャップ密度が低いことは、表示エクスペリエンスが良いことを示します。</span><span class="sxs-lookup"><span data-stu-id="d48d0-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-248"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-248"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-249">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-249">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-p128">リモート デスクトップ プロトコル (RDP) タイルの処理時間でのギャップ持続時間。持続時間が短いことは、表示エクスペリエンスが良いことを示します。</span><span class="sxs-lookup"><span data-stu-id="d48d0-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-252"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-252"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-253">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-254">キャプチャされたタイルの合計のレート (タイル/秒)。</span><span class="sxs-lookup"><span data-stu-id="d48d0-254">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-255"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-255"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-256">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-257">キャプチャされたタイルの平均のレート (タイル/秒)。</span><span class="sxs-lookup"><span data-stu-id="d48d0-257">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-258"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-258"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-259">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-259">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-260">キャプチャされたタイルの最大のレート (タイル/秒)。</span><span class="sxs-lookup"><span data-stu-id="d48d0-260">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-261"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-261"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-262">in t</span><span class="sxs-lookup"><span data-stu-id="d48d0-262">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-263">キャプチャされたタイルのレート (タイル/秒) でのバースト発生数。</span><span class="sxs-lookup"><span data-stu-id="d48d0-263">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-264"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-264"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-265">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-265">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-266">キャプチャされたタイルのレート (タイル/秒) でのバースト密度。</span><span class="sxs-lookup"><span data-stu-id="d48d0-266">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-267"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-267"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-268">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-268">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-269">キャプチャされたタイルのレート (タイル/秒) でのバースト持続時間。</span><span class="sxs-lookup"><span data-stu-id="d48d0-269">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-270"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-270"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-271">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-271">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-272">キャプチャされたタイルのレート (タイル/秒) でのギャップ発生数。</span><span class="sxs-lookup"><span data-stu-id="d48d0-272">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-273"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-273"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-274">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-275">キャプチャされたタイルのレート (タイル/秒) でのギャップ密度。</span><span class="sxs-lookup"><span data-stu-id="d48d0-275">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-276"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-276"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-277">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-277">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-278">キャプチャされたタイルのレート (タイル/秒) でのギャップ持続時間。</span><span class="sxs-lookup"><span data-stu-id="d48d0-278">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-279"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-279"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-280">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-281">視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツの合計の割合。</span><span class="sxs-lookup"><span data-stu-id="d48d0-281">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-282"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-282"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-283">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-283">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-284">視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツの平均の割合。</span><span class="sxs-lookup"><span data-stu-id="d48d0-284">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-285"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-285"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-286">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-287">視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツの最大の割合。</span><span class="sxs-lookup"><span data-stu-id="d48d0-287">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-288"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-288"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-289">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-289">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-290">視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツでのバースト発生数。</span><span class="sxs-lookup"><span data-stu-id="d48d0-290">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-291"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-291"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-292">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-293">視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツでのバースト密度。</span><span class="sxs-lookup"><span data-stu-id="d48d0-293">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-294"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-294"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-295">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-295">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-296">視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツでのバースト持続時間。</span><span class="sxs-lookup"><span data-stu-id="d48d0-296">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-297"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-297"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-298">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-298">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-299">視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツでのギャップ発生数。</span><span class="sxs-lookup"><span data-stu-id="d48d0-299">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-300"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-300"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-301">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-302">視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツでのギャップ密度。</span><span class="sxs-lookup"><span data-stu-id="d48d0-302">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-303"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-303"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-304">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-304">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-305">視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツでのギャップ持続時間。</span><span class="sxs-lookup"><span data-stu-id="d48d0-305">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-306"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-306"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-307">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-308">グラフィックス ソースからスクレープされたフレームの合計数。</span><span class="sxs-lookup"><span data-stu-id="d48d0-308">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-309"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-309"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-310">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-310">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-311">グラフィックス ソースからスクレープされたフレームの平均数。</span><span class="sxs-lookup"><span data-stu-id="d48d0-311">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-312"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-312"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-313">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-313">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-314">グラフィックス ソースからスクレープされたフレームの最大数。</span><span class="sxs-lookup"><span data-stu-id="d48d0-314">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-315"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-315"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-316">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-317">グラフィックス ソースからスクレープされたフレームのバースト発生数。</span><span class="sxs-lookup"><span data-stu-id="d48d0-317">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-318"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-318"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-319">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-320">グラフィックス ソースからスクレープされたフレームのバースト密度。</span><span class="sxs-lookup"><span data-stu-id="d48d0-320">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-321"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-321"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-322">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-322">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-323">グラフィックス ソースからスクレープされたフレームのバースト持続時間。</span><span class="sxs-lookup"><span data-stu-id="d48d0-323">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-324"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-324"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-325">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-325">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-326">グラフィックス ソースからスクレープされたフレームのギャップ発生数。</span><span class="sxs-lookup"><span data-stu-id="d48d0-326">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-327"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-327"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-328">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-328">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-329">グラフィックス ソースからスクレープされたフレームのギャップ密度。</span><span class="sxs-lookup"><span data-stu-id="d48d0-329">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-330"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-330"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-331">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-332">グラフィックス ソースからスクレープされたフレームのギャップ持続時間。</span><span class="sxs-lookup"><span data-stu-id="d48d0-332">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-333"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-333"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-334">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-334">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-335">閲覧者が受信するときの合計受信フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="d48d0-335">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-336"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-336"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-337">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-337">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-338">閲覧者が受信するときの平均受信フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="d48d0-338">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-339"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-339"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-340">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-340">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-341">閲覧者が受信するときの最大受信タイル レート。</span><span class="sxs-lookup"><span data-stu-id="d48d0-341">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-342"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-342"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-343">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-343">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-344">閲覧者が受信する受信タイル レートでのバースト発生数。</span><span class="sxs-lookup"><span data-stu-id="d48d0-344">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-345"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-345"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-346">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-346">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-347">閲覧者が受信する受信タイル レートでのバースト密度。</span><span class="sxs-lookup"><span data-stu-id="d48d0-347">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-348"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-348"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-349">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-350">閲覧者が受信する受信タイル レートでのバースト持続時間。</span><span class="sxs-lookup"><span data-stu-id="d48d0-350">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-351"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-351"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-352">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-352">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-353">閲覧者が受信する受信タイル レートでのギャップ発生数。</span><span class="sxs-lookup"><span data-stu-id="d48d0-353">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-354"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-354"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-355">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-355">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-356">閲覧者が受信する受信タイル レートでのギャップ密度。</span><span class="sxs-lookup"><span data-stu-id="d48d0-356">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-357"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-357"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-358">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-358">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-359">閲覧者が受信する受信タイル レートでのギャップ持続時間。</span><span class="sxs-lookup"><span data-stu-id="d48d0-359">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-360"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-360"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-361">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-361">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-362">閲覧者が受信するときの合計受信フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="d48d0-362">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-363"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-363"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-364">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-364">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-365">閲覧者が受信するときの平均受信フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="d48d0-365">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-366"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-366"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-367">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-367">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-368">閲覧者が受信するときの最大受信フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="d48d0-368">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-369"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-369"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-370">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-370">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-371">閲覧者が受信する受信フレーム レートでのバースト発生数。</span><span class="sxs-lookup"><span data-stu-id="d48d0-371">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-372"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-372"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-373">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-374">閲覧者が受信する受信フレーム レートでのバースト密度。</span><span class="sxs-lookup"><span data-stu-id="d48d0-374">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-375"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-375"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-376">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-376">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-377">閲覧者が受信する受信フレーム レートでのバースト持続時間。</span><span class="sxs-lookup"><span data-stu-id="d48d0-377">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-378"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-378"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-379">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-379">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-380">閲覧者が受信する受信フレーム レートでのギャップ発生数。</span><span class="sxs-lookup"><span data-stu-id="d48d0-380">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-381"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-381"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-382">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-382">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-383">閲覧者が受信する受信フレーム レートでのギャップ密度。</span><span class="sxs-lookup"><span data-stu-id="d48d0-383">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-384"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-384"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-385">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-386">閲覧者が受信する受信フレーム レートでのギャップ持続時間。</span><span class="sxs-lookup"><span data-stu-id="d48d0-386">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-387"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-387"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-388">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-388">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-389">送信者の合計の送信タイル レート。</span><span class="sxs-lookup"><span data-stu-id="d48d0-389">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-390"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-390"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-391">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-391">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-392">送信者の平均の送信タイル レート。</span><span class="sxs-lookup"><span data-stu-id="d48d0-392">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-393"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-393"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-394">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-394">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-395">送信者の最大の送信タイル レート。</span><span class="sxs-lookup"><span data-stu-id="d48d0-395">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-396"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-396"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-397">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-397">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-398">送信者の送信タイル レートのバースト発生数。</span><span class="sxs-lookup"><span data-stu-id="d48d0-398">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-399"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-399"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-400">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-400">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-401">送信者の送信タイル レートのバースト密度。</span><span class="sxs-lookup"><span data-stu-id="d48d0-401">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-402"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-402"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-403">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-403">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-404">送信者の送信タイル レートのバースト持続時間。</span><span class="sxs-lookup"><span data-stu-id="d48d0-404">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-405"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-405"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-406">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-406">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-407">送信者の送信タイル レートのギャップ発生数。</span><span class="sxs-lookup"><span data-stu-id="d48d0-407">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-408"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-408"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-409">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-409">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-410">送信者の送信タイル レートのギャップ密度。</span><span class="sxs-lookup"><span data-stu-id="d48d0-410">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-411"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-411"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-412">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-412">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-413">送信者の送信タイル レートのギャップ持続時間。</span><span class="sxs-lookup"><span data-stu-id="d48d0-413">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-414"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-414"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-415">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-415">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-416">送信者の合計の送信フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="d48d0-416">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-417"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-417"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-418">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-418">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-419">送信者の平均の送信フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="d48d0-419">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-420"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-420"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-421">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-421">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-422">送信者の最大の送信フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="d48d0-422">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-423"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-423"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-424">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-424">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-425">送信者の送信フレーム レートのバースト発生数。</span><span class="sxs-lookup"><span data-stu-id="d48d0-425">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-426"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-426"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-427">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-427">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-428">送信者の送信フレーム レートのバースト密度。</span><span class="sxs-lookup"><span data-stu-id="d48d0-428">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-429"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-429"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-430">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-430">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-431">送信者の送信フレーム レートのバースト持続時間。</span><span class="sxs-lookup"><span data-stu-id="d48d0-431">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-432"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-432"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-433">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-433">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-434">送信者の送信フレーム レートのギャップ発生数。</span><span class="sxs-lookup"><span data-stu-id="d48d0-434">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-435"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-435"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-436">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-436">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-437">送信者の送信フレーム レートのギャップ密度。</span><span class="sxs-lookup"><span data-stu-id="d48d0-437">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-438"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-438"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-439">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d48d0-439">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-440">送信者の送信フレーム レートのギャップ持続時間。</span><span class="sxs-lookup"><span data-stu-id="d48d0-440">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-441"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-441"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-442">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-442">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-443">平均のビデオ解像度の高さ (ピクセル)。</span><span class="sxs-lookup"><span data-stu-id="d48d0-443">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-444"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-444"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-445">int</span><span class="sxs-lookup"><span data-stu-id="d48d0-445">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-446">平均のビデオ解像度の幅 (ピクセル)。</span><span class="sxs-lookup"><span data-stu-id="d48d0-446">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-447"><strong>受信</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-447"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-448">若干</span><span class="sxs-lookup"><span data-stu-id="d48d0-448">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-449">着信の平均フレーム レート (フレーム/秒)。</span><span class="sxs-lookup"><span data-stu-id="d48d0-449">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48d0-450"><strong>向き</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-450"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-451">若干</span><span class="sxs-lookup"><span data-stu-id="d48d0-451">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-452">発信の平均フレーム レート (フレーム/秒)。</span><span class="sxs-lookup"><span data-stu-id="d48d0-452">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48d0-453"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="d48d0-453"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="d48d0-454">若干</span><span class="sxs-lookup"><span data-stu-id="d48d0-454">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d48d0-455">1 は、ストリームの方向が発信者から呼び出し先へ向かうことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d48d0-455">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="d48d0-456">0 は、ストリームの方向が呼び出し先から発信者へ向かうことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d48d0-456">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

