---
title: 'Lync Server 2013: ポスター: 主要な正常性インジケーター'
description: 'Lync Server 2013: ポスター: 主要な正常性インジケーター。'
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
ms.openlocfilehash: 9962d1764d5d2c664bb8415261344d9b48c81149
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566343"
---
# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="dc6e1-103">Lync Server 2013 の主要な正常性インジケーター</span><span class="sxs-lookup"><span data-stu-id="dc6e1-103">Key Health Indicators in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc6e1-104">_**トピックの最終更新日:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="dc6e1-104">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="dc6e1-105">この記事では、正常な [Lync Servers ポスターを維持するための基礎となる主要な正常性インジケーターについ](https://go.microsoft.com/fwlink/?linkid=391838) て説明します。これは、ダウンロードセンターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-105">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](https://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="dc6e1-106">![KHI データを使用したトラブルシューティングについて説明するポスター](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "KHI データを使用したトラブルシューティングについて説明するポスター")</span><span class="sxs-lookup"><span data-stu-id="dc6e1-106">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="dc6e1-107">このポスターを使用して、主要な正常性インジケーター (KHIs) について説明し、しきい値を使用して、ユーザーの利便性の問題を明らかにすることを目的としたパフォーマンスカウンターを示します。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-107">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="dc6e1-108">通話品質の方法論 (CQM) を実装するための最初の手順は、通常、Lync ユーザー向けの高品質なオーディオ操作を実現することに重点を置いて、KHI データを収集することです。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-108">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="dc6e1-109">CQM の使用方法について質問がある場合は、cqmfeedback@microsoft.com に質問を送信できます。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-109">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="dc6e1-110">ポスターは、以下の領域について説明します。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-110">The poster explains the following areas:</span></span>

  - <span data-ttu-id="dc6e1-111">重要な正常性インジケーターとは</span><span class="sxs-lookup"><span data-stu-id="dc6e1-111">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="dc6e1-112">KHI データを収集するには</span><span class="sxs-lookup"><span data-stu-id="dc6e1-112">To Collect KHI Data</span></span>

  - <span data-ttu-id="dc6e1-113">すべてのサーバーの役割の修復フロー</span><span class="sxs-lookup"><span data-stu-id="dc6e1-113">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="dc6e1-114">用語集</span><span class="sxs-lookup"><span data-stu-id="dc6e1-114">Glossary</span></span>

  - <span data-ttu-id="dc6e1-115">フロントエンドサーバー</span><span class="sxs-lookup"><span data-stu-id="dc6e1-115">Front-end Servers</span></span>

  - <span data-ttu-id="dc6e1-116">バックエンドの SQL サーバー</span><span class="sxs-lookup"><span data-stu-id="dc6e1-116">Backend SQL Servers</span></span>

  - <span data-ttu-id="dc6e1-117">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="dc6e1-117">Mediation Servers</span></span>

  - <span data-ttu-id="dc6e1-118">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="dc6e1-118">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="dc6e1-119">重要な正常性インジケーターとは</span><span class="sxs-lookup"><span data-stu-id="dc6e1-119">What are Key Health Indicators?</span></span>

<span data-ttu-id="dc6e1-120">キー正常性インジケーターは、パフォーマンスカウンターのしきい値によって、ユーザーの作業環境の問題を明らかにします。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-120">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="dc6e1-121">通話品質の方法論 (CQM) を実装するための最初の手順は、通常、Lync ユーザー向けの高品質なオーディオ操作を実現することに重点を置いて、KHI データを収集することです。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-121">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="dc6e1-122">KHIs は、標準的な Lync 監視ソリューション (System Center Operations Manager、代理トランザクション、監視サーバーなど) に加えて、これらのソリューションの代わりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-122">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="dc6e1-123">KHI パフォーマンスカウンターを収集し、ネットワークガイドに付属する KHI スプレッドシートに、Lync 展開のサーバーの状態を判断するのに役立つスコアカードを作成します。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-123">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="dc6e1-124">情報を入力すると、環境を修復して、他の関係者に対してさらに洞察を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-124">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="dc6e1-125">KHIs を月単位で評価し、展開の継続的な運用プロセスに組み込みます。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-125">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="dc6e1-126">[Lync Server ネットワークガイド](https://go.microsoft.com/fwlink/p/?linkid=390677)をダウンロードして、khis の完全なリストを確認し、関連するスプレッドシートを取得します。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-126">Download the [Lync Server Networking Guide](https://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="dc6e1-127">KHI データを収集するには</span><span class="sxs-lookup"><span data-stu-id="dc6e1-127">To Collect KHI Data</span></span>

1.  <span data-ttu-id="dc6e1-128">各 Lync Server で Lync Server ネットワークガイドに含まれている KHI スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-128">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="dc6e1-129">これにより、パフォーマンスモニターの内部にデータコレクターが作成され、KHI という名前になります。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-129">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="dc6e1-130">既定では、データは15秒ごとにポーリングされます。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-130">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="dc6e1-131">会社の就業日の開始前に、各 Lync Server に移動し、KHI データコレクターを開始します。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-131">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="dc6e1-132">その日の最後に、KHI Data コレクターを停止し、データを1か所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-132">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="dc6e1-133">パフォーマンスモニターを使用して Lync Server ネットワークガイドのダウンロードに含まれている KHI スプレッドシートにデータを入力した後、結果を推奨されるターゲットと比較します。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-133">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="dc6e1-134">すべてのサーバーの役割の修復フロー</span><span class="sxs-lookup"><span data-stu-id="dc6e1-134">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="dc6e1-135">Lync 実装の各サーバーについては、まず、サーバーのコンポーネントの正常性とシステムのパフォーマンスが目的のレベル以上であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-135">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="dc6e1-136">その後、Lync の実装全体におけるサーバーの役割に関連する指標を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-136">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="dc6e1-137">まず、すべてのサーバーの KHI パフォーマンスデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-137">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="dc6e1-138">各システムの役割 (このドキュメントで後述します) について、基本的なシステムコンポーネントが推奨されるターゲットを満たしているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-138">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="dc6e1-139">そうでない場合は、Lync の実装でのサーバーの役割に固有の指標を確認する前に、システムのパフォーマンスを修復し、KHI データを再度収集して、システムの正常性を確保します。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-139">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="dc6e1-140">すべての役割のコンポーネントの正常性は次のように定義されます。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-140">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="dc6e1-141">CPU 使用率 \< 80%</span><span class="sxs-lookup"><span data-stu-id="dc6e1-141">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="dc6e1-142">平均ディスク書き込み \< 10 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="dc6e1-142">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="dc6e1-143">平均ディスク読み取り \< 10 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="dc6e1-143">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="dc6e1-144">使用可能なメモリ \> 20% システムの合計 MB</span><span class="sxs-lookup"><span data-stu-id="dc6e1-144">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="dc6e1-145">ネットワークキューの長さ \< 2</span><span class="sxs-lookup"><span data-stu-id="dc6e1-145">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="dc6e1-146">破棄されたパケット (入力/出力) = 0</span><span class="sxs-lookup"><span data-stu-id="dc6e1-146">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="dc6e1-147">用語集</span><span class="sxs-lookup"><span data-stu-id="dc6e1-147">Glossary</span></span>

<span data-ttu-id="dc6e1-148">このポスターでは、次の用語と略語を使用しています。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-148">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="dc6e1-149">MCU として = アプリケーション共有マルチポイントコントロールユニット</span><span class="sxs-lookup"><span data-stu-id="dc6e1-149">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="dc6e1-150">AV MCU = 音声/ビデオ MCU</span><span class="sxs-lookup"><span data-stu-id="dc6e1-150">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="dc6e1-151">IM MCU = インスタントメッセージング MCU</span><span class="sxs-lookup"><span data-stu-id="dc6e1-151">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="dc6e1-152">UCWA = 統合コミュニケーション Web API</span><span class="sxs-lookup"><span data-stu-id="dc6e1-152">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="dc6e1-153">AV Edge = エッジ経由の音声/ビデオのトラバース</span><span class="sxs-lookup"><span data-stu-id="dc6e1-153">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="dc6e1-154">AV Auth = 音声/ビデオ認証</span><span class="sxs-lookup"><span data-stu-id="dc6e1-154">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="dc6e1-155">SIP スタック = Lync のコア SIP 実装が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-155">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="dc6e1-156">データプロキシ = エッジ会議に使用</span><span class="sxs-lookup"><span data-stu-id="dc6e1-156">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="dc6e1-157">その他の Ss = Lync Storage Service</span><span class="sxs-lookup"><span data-stu-id="dc6e1-157">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="dc6e1-158">フロントエンドサーバー</span><span class="sxs-lookup"><span data-stu-id="dc6e1-158">Front-end Servers</span></span>

<span data-ttu-id="dc6e1-159">次の KHI ターゲットは、基本コンポーネントの正常性に加えて、フロントエンドサーバーに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-159">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc6e1-160">機能領域</span><span class="sxs-lookup"><span data-stu-id="dc6e1-160">Functional area</span></span></th>
<th><span data-ttu-id="dc6e1-161">ターゲット指標</span><span class="sxs-lookup"><span data-stu-id="dc6e1-161">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc6e1-162">AS/AV/IM MCU</span><span class="sxs-lookup"><span data-stu-id="dc6e1-162">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="dc6e1-163">MCU 正常性状態 &lt; 2</span><span class="sxs-lookup"><span data-stu-id="dc6e1-163">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc6e1-164">Web Components</span><span class="sxs-lookup"><span data-stu-id="dc6e1-164">Web Components</span></span></p></td>
<td><p><span data-ttu-id="dc6e1-165">配布リスト展開 AD タイムアウト &lt; 0</span><span class="sxs-lookup"><span data-stu-id="dc6e1-165">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="dc6e1-166">ABWQ の失敗 = 0</span><span class="sxs-lookup"><span data-stu-id="dc6e1-166">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="dc6e1-167">LIS のエラー = 0</span><span class="sxs-lookup"><span data-stu-id="dc6e1-167">LIS failures = 0</span></span></p>
<p><span data-ttu-id="dc6e1-168">認証エラー &lt; 1/秒</span><span class="sxs-lookup"><span data-stu-id="dc6e1-168">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="dc6e1-169">ASP.NET v4 要求が拒否されました = 0</span><span class="sxs-lookup"><span data-stu-id="dc6e1-169">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc6e1-170">SIP スタック</span><span class="sxs-lookup"><span data-stu-id="dc6e1-170">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="dc6e1-171">1秒あたりの平均受信メッセージ処理 &lt;</span><span class="sxs-lookup"><span data-stu-id="dc6e1-171">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="dc6e1-172">着信応答ドロップされた &lt; 1/Sec 受信要求ドロップ &lt; 1/秒</span><span class="sxs-lookup"><span data-stu-id="dc6e1-172">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="dc6e1-173">キュー待機時間 &lt; 100 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="dc6e1-173">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="dc6e1-174">ストアドプロシージャ待機時間 &lt; 100 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="dc6e1-174">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="dc6e1-175">調整される要求 = 0</span><span class="sxs-lookup"><span data-stu-id="dc6e1-175">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="dc6e1-176">認証エラー &lt; 1/秒</span><span class="sxs-lookup"><span data-stu-id="dc6e1-176">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="dc6e1-177">受信メッセージがタイムアウトになりました &lt; 2</span><span class="sxs-lookup"><span data-stu-id="dc6e1-177">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="dc6e1-178">受信メッセージの平均保持時間 &lt; 1 秒</span><span class="sxs-lookup"><span data-stu-id="dc6e1-178">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="dc6e1-179">フロー制御された接続 &lt; 2</span><span class="sxs-lookup"><span data-stu-id="dc6e1-179">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="dc6e1-180">平均アウトキュー遅延 &lt; 2 秒</span><span class="sxs-lookup"><span data-stu-id="dc6e1-180">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc6e1-181">LySS</span><span class="sxs-lookup"><span data-stu-id="dc6e1-181">LySS</span></span></p></td>
<td><p><span data-ttu-id="dc6e1-182">Storage Service DB 80 で使用される領域の割合 (%) &lt;</span><span class="sxs-lookup"><span data-stu-id="dc6e1-182">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="dc6e1-183"># レプリカレプリケーションエラーの数 = 0</span><span class="sxs-lookup"><span data-stu-id="dc6e1-183"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="dc6e1-184"># データ損失イベントの数 = 0</span><span class="sxs-lookup"><span data-stu-id="dc6e1-184"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc6e1-185">SQL</span><span class="sxs-lookup"><span data-stu-id="dc6e1-185">SQL</span></span></p></td>
<td><p><span data-ttu-id="dc6e1-186">ページ寿命 &gt; の予測300秒。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-186">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="dc6e1-187">Batch requests/sec &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="dc6e1-187">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="dc6e1-188">バックエンドの SQL サーバー</span><span class="sxs-lookup"><span data-stu-id="dc6e1-188">Backend SQL Servers</span></span>

<span data-ttu-id="dc6e1-189">次の KHI ターゲットは、基本的なコンポーネントの正常性に加えて、SQL server に固有のものです。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-189">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc6e1-190">機能領域</span><span class="sxs-lookup"><span data-stu-id="dc6e1-190">Functional area</span></span></th>
<th><span data-ttu-id="dc6e1-191">ターゲット指標</span><span class="sxs-lookup"><span data-stu-id="dc6e1-191">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc6e1-192">SQL</span><span class="sxs-lookup"><span data-stu-id="dc6e1-192">SQL</span></span></p></td>
<td><p><span data-ttu-id="dc6e1-193">ページ寿命 &gt; の予測300秒。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-193">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="dc6e1-194">Batch requests/sec &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="dc6e1-194">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="dc6e1-195">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="dc6e1-195">Mediation Servers</span></span>

<span data-ttu-id="dc6e1-196">次の KHI ターゲットは、基本的なコンポーネントの正常性に加えて、仲介サーバーに固有です。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-196">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc6e1-197">機能領域</span><span class="sxs-lookup"><span data-stu-id="dc6e1-197">Functional area</span></span></th>
<th><span data-ttu-id="dc6e1-198">ターゲット指標</span><span class="sxs-lookup"><span data-stu-id="dc6e1-198">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc6e1-199">仲介サーバーサービス</span><span class="sxs-lookup"><span data-stu-id="dc6e1-199">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="dc6e1-200">読み込み呼び出しエラーのインデックス = 0</span><span class="sxs-lookup"><span data-stu-id="dc6e1-200">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="dc6e1-201">プロキシ10のために失敗した通話 &lt;</span><span class="sxs-lookup"><span data-stu-id="dc6e1-201">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="dc6e1-202">ゲートウェイ10が原因で失敗した通話 &lt;</span><span class="sxs-lookup"><span data-stu-id="dc6e1-202">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="dc6e1-203">拒否された呼び出し (in または out) = 0</span><span class="sxs-lookup"><span data-stu-id="dc6e1-203">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="dc6e1-204">メディア候補がありません = 0</span><span class="sxs-lookup"><span data-stu-id="dc6e1-204">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="dc6e1-205">メディア接続チェックの失敗 = 0</span><span class="sxs-lookup"><span data-stu-id="dc6e1-205">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="dc6e1-206">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="dc6e1-206">Edge Servers</span></span>

<span data-ttu-id="dc6e1-207">基本的なコンポーネントの正常性に加えて、エッジサーバーに固有の以下の KHI ターゲットが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-207">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc6e1-208">機能領域</span><span class="sxs-lookup"><span data-stu-id="dc6e1-208">Functional area</span></span></th>
<th><span data-ttu-id="dc6e1-209">ターゲット指標</span><span class="sxs-lookup"><span data-stu-id="dc6e1-209">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc6e1-210">AV 認証</span><span class="sxs-lookup"><span data-stu-id="dc6e1-210">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="dc6e1-211">無効な要求数 &lt; 20/秒</span><span class="sxs-lookup"><span data-stu-id="dc6e1-211">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc6e1-212">AV エッジ</span><span class="sxs-lookup"><span data-stu-id="dc6e1-212">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="dc6e1-213">Auth. 失敗回数 &lt; 20/秒</span><span class="sxs-lookup"><span data-stu-id="dc6e1-213">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="dc6e1-214">割り当てエラー数 &lt; 20/秒</span><span class="sxs-lookup"><span data-stu-id="dc6e1-214">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="dc6e1-215">削除されたパケット数 &lt; 300/秒</span><span class="sxs-lookup"><span data-stu-id="dc6e1-215">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc6e1-216">データプロキシ</span><span class="sxs-lookup"><span data-stu-id="dc6e1-216">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="dc6e1-217">サーバー接続の調整 &lt; 3</span><span class="sxs-lookup"><span data-stu-id="dc6e1-217">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="dc6e1-218">システムが調整 &lt; 1</span><span class="sxs-lookup"><span data-stu-id="dc6e1-218">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc6e1-219">SIP スタック</span><span class="sxs-lookup"><span data-stu-id="dc6e1-219">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="dc6e1-220">制限を超えた接続の削除 &lt; 1</span><span class="sxs-lookup"><span data-stu-id="dc6e1-220">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="dc6e1-221">送信タイムアウト &lt; 10</span><span class="sxs-lookup"><span data-stu-id="dc6e1-221">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="dc6e1-222">フロー制御された接続 &lt; 100</span><span class="sxs-lookup"><span data-stu-id="dc6e1-222">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="dc6e1-223">1/sec がドロップした着信要求 &lt;</span><span class="sxs-lookup"><span data-stu-id="dc6e1-223">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="dc6e1-224">平均メッセージ処理時間 &lt; 3 秒</span><span class="sxs-lookup"><span data-stu-id="dc6e1-224">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dc6e1-225">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc6e1-225">See Also</span></span>


[<span data-ttu-id="dc6e1-226">Lync Server ネットワークガイド</span><span class="sxs-lookup"><span data-stu-id="dc6e1-226">Lync Server Networking Guide</span></span>](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="dc6e1-227">主要な正常性インジケーター: 正常な Lync Server を維持するための基礎</span><span class="sxs-lookup"><span data-stu-id="dc6e1-227">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](https://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="dc6e1-228">Lync 通話品質の方法論</span><span class="sxs-lookup"><span data-stu-id="dc6e1-228">Lync Call Quality Methodology</span></span>](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

