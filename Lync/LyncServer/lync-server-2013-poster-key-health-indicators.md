---
title: 'Lync Server 2013: ポスター: 主要な正常性インジケーター'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 812ce68c84f86250fd25cc646bbcd5faddf0e566
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747447"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="f7b62-102">Lync Server 2013 の主要な正常性インジケーター</span><span class="sxs-lookup"><span data-stu-id="f7b62-102">Key Health Indicators in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7b62-103">_**最終更新日:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="f7b62-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="f7b62-104">この記事では、主要な正常性インジケーターの管理について説明します。これは、ダウンロードセンターからダウンロードできる[正常な Lync server ポスターを保守するための基盤](http://go.microsoft.com/fwlink/?linkid=391838)です。</span><span class="sxs-lookup"><span data-stu-id="f7b62-104">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](http://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="f7b62-105">![KHI データを使ったトラブルシューティングについて説明しているポスター](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "KHI データを使ったトラブルシューティングについて説明しているポスター")</span><span class="sxs-lookup"><span data-stu-id="f7b62-105">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="f7b62-106">このポスターを使って、重要な正常性インジケーター (KHIs) について説明します。パフォーマンスカウンターは、ユーザーエクスペリエンスの問題を明らかにすることを目的としたしきい値を備えています。</span><span class="sxs-lookup"><span data-stu-id="f7b62-106">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="f7b62-107">KHI データの収集は、通常、通話品質の方法 (CQM) を実装するための最初の手順であり、Lync ユーザーの品質オーディオエクスペリエンスを実現することに重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="f7b62-107">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="f7b62-108">CQM の使い方について質問がある場合は、cqmfeedback@microsoft.com に質問を送信できます。</span><span class="sxs-lookup"><span data-stu-id="f7b62-108">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="f7b62-109">このポスターでは、次の領域について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7b62-109">The poster explains the following areas:</span></span>

  - <span data-ttu-id="f7b62-110">主要な正常性インジケーターとは</span><span class="sxs-lookup"><span data-stu-id="f7b62-110">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="f7b62-111">KHI データを収集するには</span><span class="sxs-lookup"><span data-stu-id="f7b62-111">To Collect KHI Data</span></span>

  - <span data-ttu-id="f7b62-112">すべてのサーバーの役割の改善フロー</span><span class="sxs-lookup"><span data-stu-id="f7b62-112">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="f7b62-113">解説</span><span class="sxs-lookup"><span data-stu-id="f7b62-113">Glossary</span></span>

  - <span data-ttu-id="f7b62-114">フロントエンドサーバー</span><span class="sxs-lookup"><span data-stu-id="f7b62-114">Front-end Servers</span></span>

  - <span data-ttu-id="f7b62-115">バックエンドの SQL Server</span><span class="sxs-lookup"><span data-stu-id="f7b62-115">Backend SQL Servers</span></span>

  - <span data-ttu-id="f7b62-116">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="f7b62-116">Mediation Servers</span></span>

  - <span data-ttu-id="f7b62-117">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="f7b62-117">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="f7b62-118">主要な正常性インジケーターとは</span><span class="sxs-lookup"><span data-stu-id="f7b62-118">What are Key Health Indicators?</span></span>

<span data-ttu-id="f7b62-119">主要な正常性インジケーターは、ユーザーエクスペリエンスの問題を明らかにするしきい値を持つパフォーマンスカウンターです。</span><span class="sxs-lookup"><span data-stu-id="f7b62-119">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="f7b62-120">KHI データの収集は、通常、通話品質の方法 (CQM) を実装するための最初の手順であり、Lync ユーザーの品質オーディオエクスペリエンスを実現することに重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="f7b62-120">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="f7b62-121">KHIs は、これらのソリューションではなく、標準の Lync 監視ソリューション (System Center Operations Manager、代理トランザクション、監視サーバーなど) に加えて使用されます。</span><span class="sxs-lookup"><span data-stu-id="f7b62-121">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="f7b62-122">KHI パフォーマンスカウンターを収集し、[ネットワークガイド] に [ネットワークガイド] と表示された、Lync 展開のサーバーの正常性を判断するのに役立つスコアカードを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7b62-122">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="f7b62-123">設定が完了したら、環境の修復について説明し、他の関係者に関する詳しい情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f7b62-123">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="f7b62-124">KHIs を月単位で評価し、展開の進行中の運用プロセスに組み込みます。</span><span class="sxs-lookup"><span data-stu-id="f7b62-124">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="f7b62-125">[Lync Server ネットワークガイド](http://go.microsoft.com/fwlink/p/?linkid=390677)をダウンロードして、khis の一覧を参照し、関連するスプレッドシートを取得してください。</span><span class="sxs-lookup"><span data-stu-id="f7b62-125">Download the [Lync Server Networking Guide](http://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="f7b62-126">KHI データを収集するには</span><span class="sxs-lookup"><span data-stu-id="f7b62-126">To Collect KHI Data</span></span>

1.  <span data-ttu-id="f7b62-127">Lync Server ネットワークガイドに含まれている KHI スクリプトを各 Lync サーバーに実行します。</span><span class="sxs-lookup"><span data-stu-id="f7b62-127">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="f7b62-128">これにより、パフォーマンスモニターの内部にデータコレクターが作成され、その名前に "こんにちは" という名前が付いています。</span><span class="sxs-lookup"><span data-stu-id="f7b62-128">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="f7b62-129">既定では、データは15秒ごとにポーリングされます。</span><span class="sxs-lookup"><span data-stu-id="f7b62-129">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="f7b62-130">会社の就業日の開始前に、各 Lync サーバーに移動し、KHI データコレクターを開始します。</span><span class="sxs-lookup"><span data-stu-id="f7b62-130">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="f7b62-131">その日の最後に、KHI データコレクターを停止し、データを1か所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="f7b62-131">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="f7b62-132">パフォーマンスモニターを使用して、Lync Server ネットワークガイドのダウンロードに含まれている KHI スプレッドシートに入力したら、結果と推奨されるターゲットを比較します。</span><span class="sxs-lookup"><span data-stu-id="f7b62-132">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="f7b62-133">すべてのサーバーの役割の改善フロー</span><span class="sxs-lookup"><span data-stu-id="f7b62-133">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="f7b62-134">Lync の実装の各サーバーについて、サーバーのコンポーネントの正常性とシステムのパフォーマンスが目的のレベル以上であることを確認することから始めます。</span><span class="sxs-lookup"><span data-stu-id="f7b62-134">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="f7b62-135">その後にのみ、Lync の実装でのサーバーの役割に関連するインジケーターを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7b62-135">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="f7b62-136">まず、すべてのサーバーについて KHI のパフォーマンスデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="f7b62-136">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="f7b62-137">システムの各役割 (このドキュメントの後半で説明します) で、基本的なシステムコンポーネントが推奨されるターゲットを満たしているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f7b62-137">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="f7b62-138">そうしない場合は、システムのパフォーマンスを改善し、KHI データを再収集して、Lync の実装でサーバーの役割に固有の基準を確認する前に、システムの正常性を確保します。</span><span class="sxs-lookup"><span data-stu-id="f7b62-138">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="f7b62-139">すべての役割のコンポーネントの正常性は、次のように定義されます。</span><span class="sxs-lookup"><span data-stu-id="f7b62-139">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="f7b62-140">CPU 使用\<率80%</span><span class="sxs-lookup"><span data-stu-id="f7b62-140">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="f7b62-141">平均ディスク書き込み\< 10 ms</span><span class="sxs-lookup"><span data-stu-id="f7b62-141">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="f7b62-142">平均ディスク読み取り\< 10 ms</span><span class="sxs-lookup"><span data-stu-id="f7b62-142">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="f7b62-143">使用可能\>なメモリ20% システム合計 MB</span><span class="sxs-lookup"><span data-stu-id="f7b62-143">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="f7b62-144">ネットワークキューの\<長さ2</span><span class="sxs-lookup"><span data-stu-id="f7b62-144">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="f7b62-145">破棄されたパケット (in/out) = 0</span><span class="sxs-lookup"><span data-stu-id="f7b62-145">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="f7b62-146">解説</span><span class="sxs-lookup"><span data-stu-id="f7b62-146">Glossary</span></span>

<span data-ttu-id="f7b62-147">このポスターでは、次の用語と頭字語が使用されています。</span><span class="sxs-lookup"><span data-stu-id="f7b62-147">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="f7b62-148">MCU = アプリケーション共有マルチポイントコントロールユニット</span><span class="sxs-lookup"><span data-stu-id="f7b62-148">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="f7b62-149">AV MCU = オーディオ/ビデオ MCU</span><span class="sxs-lookup"><span data-stu-id="f7b62-149">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="f7b62-150">IM MCU = インスタントメッセージング MCU</span><span class="sxs-lookup"><span data-stu-id="f7b62-150">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="f7b62-151">UCWA = ユニファイドコミュニケーションの Web API</span><span class="sxs-lookup"><span data-stu-id="f7b62-151">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="f7b62-152">AV Edge = edge 経由の音声/ビデオのトラバーサル</span><span class="sxs-lookup"><span data-stu-id="f7b62-152">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="f7b62-153">AV Auth = 音声/ビデオ認証</span><span class="sxs-lookup"><span data-stu-id="f7b62-153">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="f7b62-154">SIP スタック = Lync のコア SIP の実装が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f7b62-154">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="f7b62-155">データプロキシ = edge 会議に使用</span><span class="sxs-lookup"><span data-stu-id="f7b62-155">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="f7b62-156">I Ss = Lync ストレージサービス</span><span class="sxs-lookup"><span data-stu-id="f7b62-156">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="f7b62-157">フロントエンドサーバー</span><span class="sxs-lookup"><span data-stu-id="f7b62-157">Front-end Servers</span></span>

<span data-ttu-id="f7b62-158">以下の KHI ターゲットは、基本的なコンポーネントの正常性に加えて、フロントエンドサーバーに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="f7b62-158">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7b62-159">機能領域</span><span class="sxs-lookup"><span data-stu-id="f7b62-159">Functional area</span></span></th>
<th><span data-ttu-id="f7b62-160">目標指標</span><span class="sxs-lookup"><span data-stu-id="f7b62-160">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7b62-161">/AV/IM MCU</span><span class="sxs-lookup"><span data-stu-id="f7b62-161">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="f7b62-162">MCU 正常性&lt;状態2</span><span class="sxs-lookup"><span data-stu-id="f7b62-162">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7b62-163">Web コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f7b62-163">Web Components</span></span></p></td>
<td><p><span data-ttu-id="f7b62-164">配布リスト展開広告タイムアウト&lt;0</span><span class="sxs-lookup"><span data-stu-id="f7b62-164">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="f7b62-165">ABWQ エラー = 0</span><span class="sxs-lookup"><span data-stu-id="f7b62-165">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="f7b62-166">LIS のエラー = 0</span><span class="sxs-lookup"><span data-stu-id="f7b62-166">LIS failures = 0</span></span></p>
<p><span data-ttu-id="f7b62-167">認証エラー &lt; 1/秒</span><span class="sxs-lookup"><span data-stu-id="f7b62-167">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="f7b62-168">ASP.NET v4 要求が拒否されました = 0</span><span class="sxs-lookup"><span data-stu-id="f7b62-168">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7b62-169">SIP スタック</span><span class="sxs-lookup"><span data-stu-id="f7b62-169">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="f7b62-170">平均受信メッセージ ( &lt; 1 秒)</span><span class="sxs-lookup"><span data-stu-id="f7b62-170">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="f7b62-171">着信応答の&lt;ドロップ 1/秒の受信&lt;要求 1/秒</span><span class="sxs-lookup"><span data-stu-id="f7b62-171">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="f7b62-172">キュー待機&lt;時間100ミリ秒</span><span class="sxs-lookup"><span data-stu-id="f7b62-172">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="f7b62-173">ストアドプロシージャ&lt;待機時間100ミリ秒</span><span class="sxs-lookup"><span data-stu-id="f7b62-173">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="f7b62-174">調整要求 = 0</span><span class="sxs-lookup"><span data-stu-id="f7b62-174">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="f7b62-175">認証エラー &lt; 1/秒</span><span class="sxs-lookup"><span data-stu-id="f7b62-175">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="f7b62-176">受信メッセージがタイムアウト&lt;しました2</span><span class="sxs-lookup"><span data-stu-id="f7b62-176">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="f7b62-177">平均受信メッセージ1秒&lt;を保持</span><span class="sxs-lookup"><span data-stu-id="f7b62-177">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="f7b62-178">フロー制御接続&lt; 2</span><span class="sxs-lookup"><span data-stu-id="f7b62-178">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="f7b62-179">Avg キューの遅延&lt; 2 秒</span><span class="sxs-lookup"><span data-stu-id="f7b62-179">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7b62-180">一 Ss</span><span class="sxs-lookup"><span data-stu-id="f7b62-180">LySS</span></span></p></td>
<td><p><span data-ttu-id="f7b62-181">Storage Service DB &lt; 80 で使用されている領域の割合</span><span class="sxs-lookup"><span data-stu-id="f7b62-181">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="f7b62-182">#レプリカレプリケーションエラーの数 = 0</span><span class="sxs-lookup"><span data-stu-id="f7b62-182"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="f7b62-183">#データ損失イベントの数 = 0</span><span class="sxs-lookup"><span data-stu-id="f7b62-183"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7b62-184">『</span><span class="sxs-lookup"><span data-stu-id="f7b62-184">SQL</span></span></p></td>
<td><p><span data-ttu-id="f7b62-185">ページ寿命の&gt;予測300秒</span><span class="sxs-lookup"><span data-stu-id="f7b62-185">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="f7b62-186">バッチ要求/秒&lt; 2500</span><span class="sxs-lookup"><span data-stu-id="f7b62-186">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="f7b62-187">バックエンドの SQL Server</span><span class="sxs-lookup"><span data-stu-id="f7b62-187">Backend SQL Servers</span></span>

<span data-ttu-id="f7b62-188">以下の KHI ターゲットは、基本的なコンポーネントの正常性に加えて、SQL server に固有のものです。</span><span class="sxs-lookup"><span data-stu-id="f7b62-188">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7b62-189">機能領域</span><span class="sxs-lookup"><span data-stu-id="f7b62-189">Functional area</span></span></th>
<th><span data-ttu-id="f7b62-190">目標指標</span><span class="sxs-lookup"><span data-stu-id="f7b62-190">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7b62-191">『</span><span class="sxs-lookup"><span data-stu-id="f7b62-191">SQL</span></span></p></td>
<td><p><span data-ttu-id="f7b62-192">ページ寿命の&gt;予測300秒</span><span class="sxs-lookup"><span data-stu-id="f7b62-192">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="f7b62-193">バッチ要求/秒&lt; 2500</span><span class="sxs-lookup"><span data-stu-id="f7b62-193">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="f7b62-194">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="f7b62-194">Mediation Servers</span></span>

<span data-ttu-id="f7b62-195">以下の KHI ターゲットは、基本的なコンポーネントの正常性に加えて、仲介サーバーに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="f7b62-195">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7b62-196">機能領域</span><span class="sxs-lookup"><span data-stu-id="f7b62-196">Functional area</span></span></th>
<th><span data-ttu-id="f7b62-197">目標指標</span><span class="sxs-lookup"><span data-stu-id="f7b62-197">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7b62-198">仲介サーバーサービス</span><span class="sxs-lookup"><span data-stu-id="f7b62-198">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="f7b62-199">通話の読み込みエラーのインデックス = 0</span><span class="sxs-lookup"><span data-stu-id="f7b62-199">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="f7b62-200">プロキシ&lt;10 のために失敗した通話</span><span class="sxs-lookup"><span data-stu-id="f7b62-200">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="f7b62-201">ゲートウェイ&lt;10 のために失敗した通話</span><span class="sxs-lookup"><span data-stu-id="f7b62-201">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="f7b62-202">通話 (in または out) 拒否 = 0</span><span class="sxs-lookup"><span data-stu-id="f7b62-202">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="f7b62-203">メディア候補が見つかりません = 0</span><span class="sxs-lookup"><span data-stu-id="f7b62-203">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="f7b62-204">メディア接続の確認エラー = 0</span><span class="sxs-lookup"><span data-stu-id="f7b62-204">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="f7b62-205">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="f7b62-205">Edge Servers</span></span>

<span data-ttu-id="f7b62-206">以下の KHI ターゲットは、基本的なコンポーネントの正常性に加えて、エッジサーバーに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="f7b62-206">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7b62-207">機能領域</span><span class="sxs-lookup"><span data-stu-id="f7b62-207">Functional area</span></span></th>
<th><span data-ttu-id="f7b62-208">目標指標</span><span class="sxs-lookup"><span data-stu-id="f7b62-208">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7b62-209">AV Auth</span><span class="sxs-lookup"><span data-stu-id="f7b62-209">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="f7b62-210">不正な&lt;リクエスト 20/秒</span><span class="sxs-lookup"><span data-stu-id="f7b62-210">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7b62-211">AV Edge</span><span class="sxs-lookup"><span data-stu-id="f7b62-211">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="f7b62-212">Auth. 失敗&lt;率 20/秒</span><span class="sxs-lookup"><span data-stu-id="f7b62-212">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="f7b62-213">割り当てエラー &lt;20/秒</span><span class="sxs-lookup"><span data-stu-id="f7b62-213">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="f7b62-214">パケットドロップ&lt;300/秒</span><span class="sxs-lookup"><span data-stu-id="f7b62-214">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7b62-215">データプロキシ</span><span class="sxs-lookup"><span data-stu-id="f7b62-215">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="f7b62-216">サーバー接続&lt;の調整3</span><span class="sxs-lookup"><span data-stu-id="f7b62-216">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="f7b62-217">システムの調整&lt;は1</span><span class="sxs-lookup"><span data-stu-id="f7b62-217">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7b62-218">SIP スタック</span><span class="sxs-lookup"><span data-stu-id="f7b62-218">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="f7b62-219">制限を超えた&lt;接続は切断されました1</span><span class="sxs-lookup"><span data-stu-id="f7b62-219">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="f7b62-220">送信タイムアウト&lt;10</span><span class="sxs-lookup"><span data-stu-id="f7b62-220">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="f7b62-221">フロー制御接続&lt;100</span><span class="sxs-lookup"><span data-stu-id="f7b62-221">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="f7b62-222">着信要求が&lt; 1/秒をドロップしました</span><span class="sxs-lookup"><span data-stu-id="f7b62-222">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="f7b62-223">平均メッセージ処理&lt; 3 秒</span><span class="sxs-lookup"><span data-stu-id="f7b62-223">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f7b62-224">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7b62-224">See Also</span></span>


[<span data-ttu-id="f7b62-225">Lync Server ネットワークガイド</span><span class="sxs-lookup"><span data-stu-id="f7b62-225">Lync Server Networking Guide</span></span>](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="f7b62-226">主要な正常性インジケーター: 正常な Lync サーバーを管理するための基盤</span><span class="sxs-lookup"><span data-stu-id="f7b62-226">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](http://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="f7b62-227">Lync 通話品質の方法</span><span class="sxs-lookup"><span data-stu-id="f7b62-227">Lync Call Quality Methodology</span></span>](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

