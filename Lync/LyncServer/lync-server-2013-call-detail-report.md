---
title: 'Lync Server 2013: 通話の詳細レポート'
description: 'Lync Server 2013: 通話の詳細レポート。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Detail Report
ms:assetid: 38862e35-3fec-41b9-a035-0b301942d446
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558637(v=OCS.15)
ms:contentKeyID: 48183843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d72ae6c1c1ec869041eee5b0dc35941c33609710
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561773"
---
# <a name="call-detail-report-in-lync-server-2013"></a><span data-ttu-id="79903-103">Lync Server 2013 の通話の詳細レポート</span><span class="sxs-lookup"><span data-stu-id="79903-103">Call Detail Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79903-104">_**トピックの最終更新日:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="79903-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="79903-105">通話の詳細レポートでは、個々の通話の詳細が表示されます。レポートには、次のようなレポートセクションに分かれた、ほぼすべての qoe 指標と Lync Server によって収集された統計情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="79903-105">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Lync Server, divided into report sections such as:</span></span>

  - <span data-ttu-id="79903-106">通話情報</span><span class="sxs-lookup"><span data-stu-id="79903-106">Call Information</span></span>

  - <span data-ttu-id="79903-107">発信者デバイスと信号測定値</span><span class="sxs-lookup"><span data-stu-id="79903-107">Caller Device and Signal Metrics</span></span>

  - <span data-ttu-id="79903-108">呼び出し先デバイスと信号測定値</span><span class="sxs-lookup"><span data-stu-id="79903-108">Callee Device and Signal metrics</span></span>

  - <span data-ttu-id="79903-109">発信者クライアント イベント</span><span class="sxs-lookup"><span data-stu-id="79903-109">Caller Client Event</span></span>

  - <span data-ttu-id="79903-110">呼び出し先クライアント イベント</span><span class="sxs-lookup"><span data-stu-id="79903-110">Callee Client Event</span></span>

  - <span data-ttu-id="79903-111">音声ストリーム (発信者から呼び出し先)</span><span class="sxs-lookup"><span data-stu-id="79903-111">Audio Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="79903-112">ビデオ ストリーム (発信者から呼び出し先)</span><span class="sxs-lookup"><span data-stu-id="79903-112">Video Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="79903-113">音声ストリーム (呼び出し先から発信者)</span><span class="sxs-lookup"><span data-stu-id="79903-113">Audio Stream (Callee to Caller)</span></span>

  - <span data-ttu-id="79903-114">ビデオ ストリーム (呼び出し先から発信者)</span><span class="sxs-lookup"><span data-stu-id="79903-114">Video Stream (Callee to Caller)</span></span>

<span data-ttu-id="79903-p101">特定のレポートに表示されるカテゴリと測定値は、セッションの種類と、セッションで使用されたエンドポイントの種類に依存します。たとえば、音声のみの通話では、通話にビデオ ストリームがないことにより、ビデオ ストリームの測定値を報告されません。同様に、呼び出し先統計はないが、発信者統計を示すレポートがあることがあります。これは、一般的には、呼び出し先が SIP 準拠のデバイスを使用していなかったことによります。エンドポイントは通話の終了後に、統計を報告します。しかし、(SIP または SIP 統計を関知しない) 携帯電話は、その種類の情報を報告することはできません。だれかに電話して、その人が携帯電話で応答した場合は、通話が終了したときに、その携帯電話からのレポートは得られません。</span><span class="sxs-lookup"><span data-stu-id="79903-p101">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session. For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream. Likewise, you might have a report that lists caller statistics but not callee statistics. That's typically because the callee was not using a SIP-compliant device. Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information. If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>

<span data-ttu-id="79903-121">通話の詳細レポートは、特定の通話でメディアの品質の問題が発生した理由を正確に確認するときに最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="79903-121">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>

<div>

## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="79903-122">通話の詳細レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="79903-122">Accessing the Call Detail Report</span></span>

<span data-ttu-id="79903-123">通話の詳細レポートは、以下の任意のレポートから表示できます。</span><span class="sxs-lookup"><span data-stu-id="79903-123">The Call Detail Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="79903-124">[Lync Server 2013 の場所レポート](lync-server-2013-location-report.md)([通話ボリューム] または [低品質通話のパーセンテージ] のどちらかをクリック)</span><span class="sxs-lookup"><span data-stu-id="79903-124">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>

  - <span data-ttu-id="79903-125">[Lync Server 2013 のメディア品質概要レポート](lync-server-2013-media-quality-summary-report.md)([通話ボリューム] または [低品質通話のパーセンテージ] のどちらかをクリック)</span><span class="sxs-lookup"><span data-stu-id="79903-125">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="79903-126">[Lync server 2013 のメディア品質比較レポート](lync-server-2013-media-quality-comparison-report.md)( [lync Server 2013 の通話リストレポート](lync-server-2013-call-list-report.md)をクリックしてから、詳細指標をクリック)。</span><span class="sxs-lookup"><span data-stu-id="79903-126">The [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md) (by clicking the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) and then clicking the Detail metric).</span></span>

  - <span data-ttu-id="79903-127">[Lync server 2013 のサーバーパフォーマンスレポート](lync-server-2013-server-performance-report.md)([通話ボリューム] または [低品質通話のパーセンテージ] のどちらかをクリック)</span><span class="sxs-lookup"><span data-stu-id="79903-127">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="79903-128">[Lync Server 2013 の通話リストレポート](lync-server-2013-call-list-report.md)(詳細指標をクリック)</span><span class="sxs-lookup"><span data-stu-id="79903-128">The [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) (by clicking the Detail metric)</span></span>

<span data-ttu-id="79903-129">通話の詳細レポートから、次のいずれかの指標をクリックすることによって、 [Lync Server 2013 のデバイスレポート](lync-server-2013-device-report.md) にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="79903-129">From within the Call Detail Report you can access the [Device Report in Lync Server 2013](lync-server-2013-device-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="79903-130">キャプチャ デバイス</span><span class="sxs-lookup"><span data-stu-id="79903-130">Capture device</span></span>

  - <span data-ttu-id="79903-131">レンダー デバイス</span><span class="sxs-lookup"><span data-stu-id="79903-131">Render device</span></span>

<span data-ttu-id="79903-132">また、音声ビデオ エッジ サーバー測定値をクリックすることによってサーバーメディア品質傾向レポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="79903-132">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="79903-133">通話の詳細レポートの活用</span><span class="sxs-lookup"><span data-stu-id="79903-133">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="79903-p102">通話の詳細レポートには、一般的には、マイクのタイムスタンプの誤差、低 SNR 時間、および近端エコー時間の項目のような、250 以上のさまざまな測定値が含まれます。これらの測定値の詳細が思い出せない場合は、測定値のラベル上にマウス ポインターを置きます。多くの場合は、その測定値を説明するツール ヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="79903-p102">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time. If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>

<span data-ttu-id="79903-p103">特定の測定値が見つからない場合は、検索ボックスに測定値ラベルの一部を入力して、次に [検索] をクリックします。たとえば、低 SNR 時間測定値が見つからない場合は、検索ボックスに "SNR" と入力して、次に [検索] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79903-p103">If you have problems locating a metric, type part of the metric label in the search box and then click Find. For example, if you can't find the Low SNR time metric, type SNR in the search box and then click Find.</span></span>

<span data-ttu-id="79903-138">レポートでは、通話に関する情報のみが追跡されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="79903-138">Note that the report only tracks information about a call.</span></span> <span data-ttu-id="79903-139">通話自体は記録されません。</span><span class="sxs-lookup"><span data-stu-id="79903-139">The call itself is not recorded.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="79903-140">フィルター</span><span class="sxs-lookup"><span data-stu-id="79903-140">Filters</span></span>

<span data-ttu-id="79903-p105">なし。通話の詳細レポートにはフィルターを適用できません。</span><span class="sxs-lookup"><span data-stu-id="79903-p105">None. You cannot filter the Call Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="79903-143">指標</span><span class="sxs-lookup"><span data-stu-id="79903-143">Metrics</span></span>

<span data-ttu-id="79903-144">次の表に、各通話の通話の詳細レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="79903-144">The following table lists the information provided in the Call Detail Report for each call.</span></span>

### <a name="call-detail-report-metrics"></a><span data-ttu-id="79903-145">通話の詳細レポートの指標</span><span class="sxs-lookup"><span data-stu-id="79903-145">Call Detail Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79903-146">名前</span><span class="sxs-lookup"><span data-stu-id="79903-146">Name</span></span></th>
<th><span data-ttu-id="79903-147">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="79903-147">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="79903-148">説明</span><span class="sxs-lookup"><span data-stu-id="79903-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79903-149">[<strong>発信者 PAI</strong>]</span><span class="sxs-lookup"><span data-stu-id="79903-149"><strong>Caller PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="79903-150">いいえ</span><span class="sxs-lookup"><span data-stu-id="79903-150">No</span></span></p></td>
<td><p><span data-ttu-id="79903-p106">呼び出しを開始したユーザーの P-Asserted-Identity。P-Asserted-Identity は、信頼されたネットワーク内でユーザーの証明済み ID を送信するのに使用されます。</span><span class="sxs-lookup"><span data-stu-id="79903-p106">P-Asserted-Identity of the user who initiated the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79903-153">[<strong>発信者 URI</strong>]</span><span class="sxs-lookup"><span data-stu-id="79903-153"><strong>Caller URI</strong></span></span></p></td>
<td><p><span data-ttu-id="79903-154">いいえ</span><span class="sxs-lookup"><span data-stu-id="79903-154">No</span></span></p></td>
<td><p><span data-ttu-id="79903-155">呼び出しを開始したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="79903-155">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79903-156">[<strong>発信者エンドポイント</strong>]</span><span class="sxs-lookup"><span data-stu-id="79903-156"><strong>Caller endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="79903-157">いいえ</span><span class="sxs-lookup"><span data-stu-id="79903-157">No</span></span></p></td>
<td><p><span data-ttu-id="79903-158">呼び出しを実行したデバイス。</span><span class="sxs-lookup"><span data-stu-id="79903-158">Device used to make the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79903-159">[<strong>発信者ユーザー エージェント</strong>]</span><span class="sxs-lookup"><span data-stu-id="79903-159"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="79903-160">いいえ</span><span class="sxs-lookup"><span data-stu-id="79903-160">No</span></span></p></td>
<td><p><span data-ttu-id="79903-161">呼び出しを実行したデバイスで使用されるソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="79903-161">Software used on the device that made the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79903-162">[<strong>通話の開始</strong>]</span><span class="sxs-lookup"><span data-stu-id="79903-162"><strong>Call start</strong></span></span></p></td>
<td><p><span data-ttu-id="79903-163">いいえ</span><span class="sxs-lookup"><span data-stu-id="79903-163">No</span></span></p></td>
<td><p><span data-ttu-id="79903-164">呼び出しが最初に開始された日時。</span><span class="sxs-lookup"><span data-stu-id="79903-164">Date and time that the call was initially placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79903-165">[<strong>仲介サーバーのバイパス通話</strong>]</span><span class="sxs-lookup"><span data-stu-id="79903-165"><strong>Mediation Server bypass call</strong></span></span></p></td>
<td><p><span data-ttu-id="79903-166">いいえ</span><span class="sxs-lookup"><span data-stu-id="79903-166">No</span></span></p></td>
<td><p><span data-ttu-id="79903-167">呼び出しが仲介サーバーを経由せずに PSTN 音声ゲートウェイまたは適切な IP-PBX に接続されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="79903-167">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79903-168">[<strong>発信者 OS</strong>]</span><span class="sxs-lookup"><span data-stu-id="79903-168"><strong>Caller OS</strong></span></span></p></td>
<td><p><span data-ttu-id="79903-169">いいえ</span><span class="sxs-lookup"><span data-stu-id="79903-169">No</span></span></p></td>
<td><p><span data-ttu-id="79903-170">呼び出し元のコンピューターのオペレーティング システム。</span><span class="sxs-lookup"><span data-stu-id="79903-170">Operating system of the caller's computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79903-171">[<strong>発信者 CPU</strong>]</span><span class="sxs-lookup"><span data-stu-id="79903-171"><strong>Caller CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="79903-172">いいえ</span><span class="sxs-lookup"><span data-stu-id="79903-172">No</span></span></p></td>
<td><p><span data-ttu-id="79903-173">呼び出しを開始したユーザーのコンピューターに搭載される CPU。</span><span class="sxs-lookup"><span data-stu-id="79903-173">CPU installed in the computer of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79903-174">[<strong>発信者 CPU コア番号</strong>]</span><span class="sxs-lookup"><span data-stu-id="79903-174"><strong>Caller CPU core number</strong></span></span></p></td>
<td><p><span data-ttu-id="79903-175">いいえ</span><span class="sxs-lookup"><span data-stu-id="79903-175">No</span></span></p></td>
<td><p><span data-ttu-id="79903-176">呼び出しを開始したユーザーが使用するコンピューターのプロセッサ番号。</span><span class="sxs-lookup"><span data-stu-id="79903-176">Processor number in the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79903-177">[<strong>発信者 CPU 速度</strong>]</span><span class="sxs-lookup"><span data-stu-id="79903-177"><strong>Caller CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="79903-178">いいえ</span><span class="sxs-lookup"><span data-stu-id="79903-178">No</span></span></p></td>
<td><p><span data-ttu-id="79903-179">呼び出しを開始したユーザーが使用するコンピューターの CPU のクロック速度。</span><span class="sxs-lookup"><span data-stu-id="79903-179">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79903-180">[<strong>発信者 CPU 仮想化</strong>]</span><span class="sxs-lookup"><span data-stu-id="79903-180"><strong>Caller CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="79903-181">いいえ</span><span class="sxs-lookup"><span data-stu-id="79903-181">No</span></span></p></td>
<td><p><span data-ttu-id="79903-182">呼び出しを開始したユーザーが使用するコンピューターでの仮想化 (仮想化されている場合)。</span><span class="sxs-lookup"><span data-stu-id="79903-182">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79903-183">[<strong>呼び出し先 PAI</strong>]</span><span class="sxs-lookup"><span data-stu-id="79903-183"><strong>Callee PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="79903-184">いいえ</span><span class="sxs-lookup"><span data-stu-id="79903-184">No</span></span></p></td>
<td><p><span data-ttu-id="79903-p107">通話に招待されたユーザーの P-Asserted-Identity。P-Asserted-Identity は、信頼されたネットワーク内でユーザーの証明済み ID を送信するのに使用されます。</span><span class="sxs-lookup"><span data-stu-id="79903-p107">P-Asserted-Identity of the user who was invited to join the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79903-187">[<strong>呼び出し先 URI</strong>]</span><span class="sxs-lookup"><span data-stu-id="79903-187"><strong>Callee URI</strong></span></span></p></td>
<td><p><span data-ttu-id="79903-188">いいえ</span><span class="sxs-lookup"><span data-stu-id="79903-188">No</span></span></p></td>
<td><p><span data-ttu-id="79903-189">呼び出し先ユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="79903-189">SIP address of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79903-190">[<strong>呼び出し先エンドポイント</strong>]</span><span class="sxs-lookup"><span data-stu-id="79903-190"><strong>Callee endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="79903-191">いいえ</span><span class="sxs-lookup"><span data-stu-id="79903-191">No</span></span></p></td>
<td><p><span data-ttu-id="79903-192">呼び出しを受信したデバイス。</span><span class="sxs-lookup"><span data-stu-id="79903-192">Device used to receive the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79903-193">[<strong>呼び出し先ユーザー エージェント</strong>]</span><span class="sxs-lookup"><span data-stu-id="79903-193"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="79903-194">いいえ</span><span class="sxs-lookup"><span data-stu-id="79903-194">No</span></span></p></td>
<td><p><span data-ttu-id="79903-195">呼び出しを受信したデバイスで使用されるソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="79903-195">Software used on the device that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79903-196"><strong>Duration</strong></span><span class="sxs-lookup"><span data-stu-id="79903-196"><strong>Duration</strong></span></span></p></td>
<td><p><span data-ttu-id="79903-197">いいえ</span><span class="sxs-lookup"><span data-stu-id="79903-197">No</span></span></p></td>
<td><p><span data-ttu-id="79903-198">通話時間。</span><span class="sxs-lookup"><span data-stu-id="79903-198">Length of time for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79903-199">[<strong>メディア バイパス警告フラグ</strong>]</span><span class="sxs-lookup"><span data-stu-id="79903-199"><strong>Media bypass warning flag</strong></span></span></p></td>
<td><p><span data-ttu-id="79903-200">いいえ</span><span class="sxs-lookup"><span data-stu-id="79903-200">No</span></span></p></td>
<td><p><span data-ttu-id="79903-201">仲介サーバーがバイパスされたときに発行された警告。</span><span class="sxs-lookup"><span data-stu-id="79903-201">Warning issued when the Mediation Server was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79903-202">[<strong>呼び出し先 OS</strong>]</span><span class="sxs-lookup"><span data-stu-id="79903-202"><strong>Callee OS</strong></span></span></p></td>
<td><p><span data-ttu-id="79903-203">いいえ</span><span class="sxs-lookup"><span data-stu-id="79903-203">No</span></span></p></td>
<td><p><span data-ttu-id="79903-204">呼び出し先ユーザーのコンピューターのオペレーティング システム。</span><span class="sxs-lookup"><span data-stu-id="79903-204">Operating system of the computer for the user who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79903-205">[<strong>呼び出し先 CPU</strong>]</span><span class="sxs-lookup"><span data-stu-id="79903-205"><strong>Callee CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="79903-206">いいえ</span><span class="sxs-lookup"><span data-stu-id="79903-206">No</span></span></p></td>
<td><p><span data-ttu-id="79903-207">呼び出し先ユーザーのコンピューターに搭載される CPU。</span><span class="sxs-lookup"><span data-stu-id="79903-207">CPU installed in the computer of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79903-208">[<strong>呼び出し先コア番号</strong>]</span><span class="sxs-lookup"><span data-stu-id="79903-208"><strong>Callee core number</strong></span></span></p></td>
<td><p><span data-ttu-id="79903-209">いいえ</span><span class="sxs-lookup"><span data-stu-id="79903-209">No</span></span></p></td>
<td><p><span data-ttu-id="79903-210">呼び出し先ユーザーが使用するコンピューターのプロセッサ番号。</span><span class="sxs-lookup"><span data-stu-id="79903-210">Processor number in the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79903-211">[<strong>呼び出し先 CPU 速度</strong>]</span><span class="sxs-lookup"><span data-stu-id="79903-211"><strong>Callee CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="79903-212">いいえ</span><span class="sxs-lookup"><span data-stu-id="79903-212">No</span></span></p></td>
<td><p><span data-ttu-id="79903-213">呼び出し先ユーザーが使用するコンピューターの CPU のクロック速度。</span><span class="sxs-lookup"><span data-stu-id="79903-213">Clock speed of the CPU of the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79903-214">[<strong>呼び出し先 CPU 仮想化</strong>]</span><span class="sxs-lookup"><span data-stu-id="79903-214"><strong>Callee CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="79903-215">いいえ</span><span class="sxs-lookup"><span data-stu-id="79903-215">No</span></span></p></td>
<td><p><span data-ttu-id="79903-216">呼び出し先ユーザーが使用するコンピューターでの仮想化 (仮想化されている場合)。</span><span class="sxs-lookup"><span data-stu-id="79903-216">Virtualization (if any) used on the computer used by the person who was called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

