---
title: 'Lync Server 2013: 通話の詳細レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Detail Report
ms:assetid: 38862e35-3fec-41b9-a035-0b301942d446
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558637(v=OCS.15)
ms:contentKeyID: 48183843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a258a5c228cfe96218c9c694b05055cc5ebd7eb6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-detail-report-in-lync-server-2013"></a><span data-ttu-id="f9c8b-102">Lync Server 2013 の通話詳細レポート</span><span class="sxs-lookup"><span data-stu-id="f9c8b-102">Call Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9c8b-103">_**最終更新日:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="f9c8b-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="f9c8b-104">通話詳細レポートでは、個々の通話の詳細が表示されます。レポートには、次のようなレポートセクションに分類された、Lync Server によって収集されたエクスペリエンスの測度と統計情報のほぼすべてが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-104">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Lync Server, divided into report sections such as:</span></span>

  - <span data-ttu-id="f9c8b-105">通話情報</span><span class="sxs-lookup"><span data-stu-id="f9c8b-105">Call Information</span></span>

  - <span data-ttu-id="f9c8b-106">発信者のデバイスおよび信号指標</span><span class="sxs-lookup"><span data-stu-id="f9c8b-106">Caller Device and Signal Metrics</span></span>

  - <span data-ttu-id="f9c8b-107">呼び出し先のデバイスおよび信号指標</span><span class="sxs-lookup"><span data-stu-id="f9c8b-107">Callee Device and Signal metrics</span></span>

  - <span data-ttu-id="f9c8b-108">発信者クライアント イベント</span><span class="sxs-lookup"><span data-stu-id="f9c8b-108">Caller Client Event</span></span>

  - <span data-ttu-id="f9c8b-109">呼び出し先クライアント イベント</span><span class="sxs-lookup"><span data-stu-id="f9c8b-109">Callee Client Event</span></span>

  - <span data-ttu-id="f9c8b-110">音声ストリーム (発信者から呼び出し先)</span><span class="sxs-lookup"><span data-stu-id="f9c8b-110">Audio Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="f9c8b-111">ビデオ ストリーム (発信者から呼び出し先)</span><span class="sxs-lookup"><span data-stu-id="f9c8b-111">Video Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="f9c8b-112">音声ストリーム (呼び出し先から発信者)</span><span class="sxs-lookup"><span data-stu-id="f9c8b-112">Audio Stream (Callee to Caller)</span></span>

  - <span data-ttu-id="f9c8b-113">ビデオ ストリーム (呼び出し先から発信者)</span><span class="sxs-lookup"><span data-stu-id="f9c8b-113">Video Stream (Callee to Caller)</span></span>

<span data-ttu-id="f9c8b-p101">特定のレポートに表示されるカテゴリと指標は、セッションの種類と、セッションで使用されたエンドポイントの種類に依存します。たとえば、音声のみの通話では、通話にビデオ ストリームがないことにより、ビデオ ストリームの指標は報告されません。同様に、呼び出し先統計はないが、発信者統計を示すレポートがあることがあります。この原因は通常、呼び出し先が SIP 準拠のデバイスを使用していないことです。エンドポイントは通話の終了後に、統計を報告します。しかし、(SIP または SIP 統計を関知しない) 携帯電話は、その種類の情報を報告することはできません。電話の相手先が携帯電話で応答した場合は、通話の終了時に、その携帯電話からのレポートは得られません。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-p101">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session. For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream. Likewise, you might have a report that lists caller statistics but not callee statistics. That's typically because the callee was not using a SIP-compliant device. Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information. If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>

<span data-ttu-id="f9c8b-120">通話の詳細レポートは、特定の通話でメディアの品質の問題が発生した理由を正確に確認するときに最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-120">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>

<div>

## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="f9c8b-121">通話の詳細レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="f9c8b-121">Accessing the Call Detail Report</span></span>

<span data-ttu-id="f9c8b-122">通話の詳細レポートは、以下の任意のレポートから表示できます。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-122">The Call Detail Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="f9c8b-123">[Lync Server 2013 の位置情報レポート](lync-server-2013-location-report.md)(通話音量または低品質の通話率のメトリックをクリック)</span><span class="sxs-lookup"><span data-stu-id="f9c8b-123">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>

  - <span data-ttu-id="f9c8b-124">[Lync Server 2013 の [メディア品質の概要] レポート](lync-server-2013-media-quality-summary-report.md)(通話音量または [低品質通話率] のいずれかをクリック)</span><span class="sxs-lookup"><span data-stu-id="f9c8b-124">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="f9c8b-125">[Lync server 2013 のメディア品質比較レポート](lync-server-2013-media-quality-comparison-report.md)( [lync Server 2013 の通話リストレポート](lync-server-2013-call-list-report.md)をクリックして、詳細なメトリックをクリックします)。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-125">The [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md) (by clicking the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) and then clicking the Detail metric).</span></span>

  - <span data-ttu-id="f9c8b-126">[Lync server 2013 のサーバーパフォーマンスレポート](lync-server-2013-server-performance-report.md)(通話ボリュームまたは低品質通話パーセンテージメトリックをクリック)</span><span class="sxs-lookup"><span data-stu-id="f9c8b-126">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="f9c8b-127">[Lync Server 2013 の通話リストレポート](lync-server-2013-call-list-report.md)(詳細なメトリックをクリック)</span><span class="sxs-lookup"><span data-stu-id="f9c8b-127">The [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) (by clicking the Detail metric)</span></span>

<span data-ttu-id="f9c8b-128">通話詳細レポート内から、次のメトリックのいずれかをクリックして、 [Lync Server 2013 のデバイスレポート](lync-server-2013-device-report.md)にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-128">From within the Call Detail Report you can access the [Device Report in Lync Server 2013](lync-server-2013-device-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="f9c8b-129">キャプチャ デバイス</span><span class="sxs-lookup"><span data-stu-id="f9c8b-129">Capture device</span></span>

  - <span data-ttu-id="f9c8b-130">[レンダー デバイス]</span><span class="sxs-lookup"><span data-stu-id="f9c8b-130">Render device</span></span>

<span data-ttu-id="f9c8b-131">また、音声ビデオ エッジ サーバー指標をクリックすると、サーバー メディア品質傾向レポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-131">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="f9c8b-132">通話の詳細レポートの活用</span><span class="sxs-lookup"><span data-stu-id="f9c8b-132">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="f9c8b-p102">通話の詳細レポートには、一般的には、マイクのタイムスタンプの誤差、低 SNR 時間、および近端エコー時間の項目のような、250 個以上のさまざまな指標が含まれます。これらの指標の詳細が思い出せない場合は、指標のラベル上にマウス ポインターを置きます。多くの場合は、その指標を説明するツール ヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-p102">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time. If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>

<span data-ttu-id="f9c8b-135">メトリックの検索で問題が発生した場合は、[検索] ボックスにメトリックラベルの一部を入力し、[検索] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-135">If you have problems locating a metric, type part of the metric label in the search box and then click Find.</span></span> <span data-ttu-id="f9c8b-136">たとえば、低い SNR 時間メトリックが見つからない場合は、検索ボックスに「SNR」と入力して、[検索] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-136">For example, if you can't find the Low SNR time metric, type SNR in the search box and then click Find.</span></span>

<span data-ttu-id="f9c8b-p104">レポートは、通話に関する情報を記録するだけです。通話自体は記録されません。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-p104">Note that the report only tracks information about a call. The call itself is not recorded.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="f9c8b-139">フィルター</span><span class="sxs-lookup"><span data-stu-id="f9c8b-139">Filters</span></span>

<span data-ttu-id="f9c8b-p105">なし。通話の詳細レポートにはフィルターを適用できません。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-p105">None. You cannot filter the Call Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="f9c8b-142">指標</span><span class="sxs-lookup"><span data-stu-id="f9c8b-142">Metrics</span></span>

<span data-ttu-id="f9c8b-143">次の表に、各通話の通話の詳細レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-143">The following table lists the information provided in the Call Detail Report for each call.</span></span>

### <a name="call-detail-report-metrics"></a><span data-ttu-id="f9c8b-144">通話の詳細レポートの指標</span><span class="sxs-lookup"><span data-stu-id="f9c8b-144">Call Detail Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9c8b-145">名前</span><span class="sxs-lookup"><span data-stu-id="f9c8b-145">Name</span></span></th>
<th><span data-ttu-id="f9c8b-146">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="f9c8b-146">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f9c8b-147">説明</span><span class="sxs-lookup"><span data-stu-id="f9c8b-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9c8b-148"><strong>[発信者 PAI]</strong></span><span class="sxs-lookup"><span data-stu-id="f9c8b-148"><strong>Caller PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="f9c8b-149">いいえ</span><span class="sxs-lookup"><span data-stu-id="f9c8b-149">No</span></span></p></td>
<td><p><span data-ttu-id="f9c8b-p106">呼び出しを開始したユーザーの P-Asserted-Identity。P-Asserted-Identity は、信頼されたネットワーク内でユーザーの証明済み ID を送信するのに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-p106">P-Asserted-Identity of the user who initiated the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9c8b-152"><strong>[発信者 URI]</strong></span><span class="sxs-lookup"><span data-stu-id="f9c8b-152"><strong>Caller URI</strong></span></span></p></td>
<td><p><span data-ttu-id="f9c8b-153">いいえ</span><span class="sxs-lookup"><span data-stu-id="f9c8b-153">No</span></span></p></td>
<td><p><span data-ttu-id="f9c8b-154">呼び出しを開始したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-154">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9c8b-155"><strong>[発信者エンドポイント]</strong></span><span class="sxs-lookup"><span data-stu-id="f9c8b-155"><strong>Caller endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="f9c8b-156">いいえ</span><span class="sxs-lookup"><span data-stu-id="f9c8b-156">No</span></span></p></td>
<td><p><span data-ttu-id="f9c8b-157">呼び出しを実行したデバイス。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-157">Device used to make the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9c8b-158"><strong>[発信者ユーザー エージェント]</strong></span><span class="sxs-lookup"><span data-stu-id="f9c8b-158"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="f9c8b-159">いいえ</span><span class="sxs-lookup"><span data-stu-id="f9c8b-159">No</span></span></p></td>
<td><p><span data-ttu-id="f9c8b-160">呼び出しを実行したデバイスで使用されるソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-160">Software used on the device that made the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9c8b-161"><strong>[通話の開始]</strong></span><span class="sxs-lookup"><span data-stu-id="f9c8b-161"><strong>Call start</strong></span></span></p></td>
<td><p><span data-ttu-id="f9c8b-162">いいえ</span><span class="sxs-lookup"><span data-stu-id="f9c8b-162">No</span></span></p></td>
<td><p><span data-ttu-id="f9c8b-163">呼び出しが最初に開始された日時。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-163">Date and time that the call was initially placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9c8b-164"><strong>[仲介サーバーのバイパス通話]</strong></span><span class="sxs-lookup"><span data-stu-id="f9c8b-164"><strong>Mediation Server bypass call</strong></span></span></p></td>
<td><p><span data-ttu-id="f9c8b-165">いいえ</span><span class="sxs-lookup"><span data-stu-id="f9c8b-165">No</span></span></p></td>
<td><p><span data-ttu-id="f9c8b-166">呼び出しが仲介サーバーを経由せずに PSTN 音声ゲートウェイまたは適切な IP-PBX に接続されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-166">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9c8b-167"><strong>[発信者 OS]</strong></span><span class="sxs-lookup"><span data-stu-id="f9c8b-167"><strong>Caller OS</strong></span></span></p></td>
<td><p><span data-ttu-id="f9c8b-168">いいえ</span><span class="sxs-lookup"><span data-stu-id="f9c8b-168">No</span></span></p></td>
<td><p><span data-ttu-id="f9c8b-169">呼び出し元のコンピューターのオペレーティング システム。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-169">Operating system of the caller's computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9c8b-170"><strong>[発信者 CPU]</strong></span><span class="sxs-lookup"><span data-stu-id="f9c8b-170"><strong>Caller CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="f9c8b-171">いいえ</span><span class="sxs-lookup"><span data-stu-id="f9c8b-171">No</span></span></p></td>
<td><p><span data-ttu-id="f9c8b-172">呼び出しを開始したユーザーのコンピューターに搭載される CPU。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-172">CPU installed in the computer of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9c8b-173"><strong>[発信者 CPU コア番号]</strong></span><span class="sxs-lookup"><span data-stu-id="f9c8b-173"><strong>Caller CPU core number</strong></span></span></p></td>
<td><p><span data-ttu-id="f9c8b-174">いいえ</span><span class="sxs-lookup"><span data-stu-id="f9c8b-174">No</span></span></p></td>
<td><p><span data-ttu-id="f9c8b-175">呼び出しを開始したユーザーが使用するコンピューターのプロセッサ番号。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-175">Processor number in the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9c8b-176"><strong>[発信者 CPU 速度]</strong></span><span class="sxs-lookup"><span data-stu-id="f9c8b-176"><strong>Caller CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="f9c8b-177">いいえ</span><span class="sxs-lookup"><span data-stu-id="f9c8b-177">No</span></span></p></td>
<td><p><span data-ttu-id="f9c8b-178">呼び出しを開始したユーザーが使用するコンピューターの CPU のクロック速度。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-178">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9c8b-179"><strong>[発信者 CPU 仮想化]</strong></span><span class="sxs-lookup"><span data-stu-id="f9c8b-179"><strong>Caller CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="f9c8b-180">いいえ</span><span class="sxs-lookup"><span data-stu-id="f9c8b-180">No</span></span></p></td>
<td><p><span data-ttu-id="f9c8b-181">呼び出しを開始したユーザーが使用するコンピューターでの仮想化 (仮想化されている場合)。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-181">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9c8b-182"><strong>[呼び出し先 PAI]</strong></span><span class="sxs-lookup"><span data-stu-id="f9c8b-182"><strong>Callee PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="f9c8b-183">いいえ</span><span class="sxs-lookup"><span data-stu-id="f9c8b-183">No</span></span></p></td>
<td><p><span data-ttu-id="f9c8b-p107">通話に招待されたユーザーの P-Asserted-Identity。P-Asserted-Identity は、信頼されたネットワーク内でユーザーの証明済み ID を送信するのに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-p107">P-Asserted-Identity of the user who was invited to join the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9c8b-186"><strong>[呼び出し先 URI]</strong></span><span class="sxs-lookup"><span data-stu-id="f9c8b-186"><strong>Callee URI</strong></span></span></p></td>
<td><p><span data-ttu-id="f9c8b-187">いいえ</span><span class="sxs-lookup"><span data-stu-id="f9c8b-187">No</span></span></p></td>
<td><p><span data-ttu-id="f9c8b-188">呼び出し先ユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-188">SIP address of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9c8b-189"><strong>[呼び出し先エンドポイント]</strong></span><span class="sxs-lookup"><span data-stu-id="f9c8b-189"><strong>Callee endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="f9c8b-190">いいえ</span><span class="sxs-lookup"><span data-stu-id="f9c8b-190">No</span></span></p></td>
<td><p><span data-ttu-id="f9c8b-191">呼び出しを受信したデバイス。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-191">Device used to receive the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9c8b-192"><strong>[呼び出し先ユーザー エージェント]</strong></span><span class="sxs-lookup"><span data-stu-id="f9c8b-192"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="f9c8b-193">いいえ</span><span class="sxs-lookup"><span data-stu-id="f9c8b-193">No</span></span></p></td>
<td><p><span data-ttu-id="f9c8b-194">呼び出しを受信したデバイスで使用されるソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-194">Software used on the device that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9c8b-195"><strong>[時間]</strong></span><span class="sxs-lookup"><span data-stu-id="f9c8b-195"><strong>Duration</strong></span></span></p></td>
<td><p><span data-ttu-id="f9c8b-196">いいえ</span><span class="sxs-lookup"><span data-stu-id="f9c8b-196">No</span></span></p></td>
<td><p><span data-ttu-id="f9c8b-197">通話時間。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-197">Length of time for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9c8b-198"><strong>[メディア バイパス警告フラグ]</strong></span><span class="sxs-lookup"><span data-stu-id="f9c8b-198"><strong>Media bypass warning flag</strong></span></span></p></td>
<td><p><span data-ttu-id="f9c8b-199">いいえ</span><span class="sxs-lookup"><span data-stu-id="f9c8b-199">No</span></span></p></td>
<td><p><span data-ttu-id="f9c8b-200">仲介サーバーがバイパスされたときに発行された警告。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-200">Warning issued when the Mediation Server was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9c8b-201"><strong>[呼び出し先 OS]</strong></span><span class="sxs-lookup"><span data-stu-id="f9c8b-201"><strong>Callee OS</strong></span></span></p></td>
<td><p><span data-ttu-id="f9c8b-202">いいえ</span><span class="sxs-lookup"><span data-stu-id="f9c8b-202">No</span></span></p></td>
<td><p><span data-ttu-id="f9c8b-203">呼び出し先ユーザーのコンピューターのオペレーティング システム。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-203">Operating system of the computer for the user who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9c8b-204"><strong>[呼び出し先 CPU]</strong></span><span class="sxs-lookup"><span data-stu-id="f9c8b-204"><strong>Callee CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="f9c8b-205">いいえ</span><span class="sxs-lookup"><span data-stu-id="f9c8b-205">No</span></span></p></td>
<td><p><span data-ttu-id="f9c8b-206">呼び出し先ユーザーのコンピューターに搭載される CPU。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-206">CPU installed in the computer of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9c8b-207"><strong>[呼び出し先コア番号]</strong></span><span class="sxs-lookup"><span data-stu-id="f9c8b-207"><strong>Callee core number</strong></span></span></p></td>
<td><p><span data-ttu-id="f9c8b-208">いいえ</span><span class="sxs-lookup"><span data-stu-id="f9c8b-208">No</span></span></p></td>
<td><p><span data-ttu-id="f9c8b-209">呼び出し先ユーザーが使用するコンピューターのプロセッサ番号。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-209">Processor number in the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9c8b-210"><strong>[呼び出し先 CPU 速度]</strong></span><span class="sxs-lookup"><span data-stu-id="f9c8b-210"><strong>Callee CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="f9c8b-211">いいえ</span><span class="sxs-lookup"><span data-stu-id="f9c8b-211">No</span></span></p></td>
<td><p><span data-ttu-id="f9c8b-212">呼び出し先ユーザーが使用するコンピューターの CPU のクロック速度。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-212">Clock speed of the CPU of the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9c8b-213"><strong>[呼び出し先 CPU 仮想化]</strong></span><span class="sxs-lookup"><span data-stu-id="f9c8b-213"><strong>Callee CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="f9c8b-214">不可</span><span class="sxs-lookup"><span data-stu-id="f9c8b-214">No</span></span></p></td>
<td><p><span data-ttu-id="f9c8b-215">呼び出し先ユーザーが使用するコンピューターでの仮想化 (仮想化されている場合)。</span><span class="sxs-lookup"><span data-stu-id="f9c8b-215">Virtualization (if any) used on the computer used by the person who was called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

