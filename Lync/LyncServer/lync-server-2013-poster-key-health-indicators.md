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
ms.openlocfilehash: 2710e85eced76241f4946ef2746e544d07be941f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="aa0f7-102">Lync Server 2013 の主要な正常性インジケーター</span><span class="sxs-lookup"><span data-stu-id="aa0f7-102">Key Health Indicators in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa0f7-103">_**トピックの最終更新日:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="aa0f7-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="aa0f7-104">この記事では、正常な[Lync Servers ポスターを維持するための基礎となる主要な正常性インジケーターについ](https://go.microsoft.com/fwlink/?linkid=391838)て説明します。これは、ダウンロードセンターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-104">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](https://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="aa0f7-105">![KHI データを使用したトラブルシューティングについて説明するポスター](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "KHI データを使用したトラブルシューティングについて説明するポスター")</span><span class="sxs-lookup"><span data-stu-id="aa0f7-105">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="aa0f7-106">このポスターを使用して、主要な正常性インジケーター (KHIs) について説明し、しきい値を使用して、ユーザーの利便性の問題を明らかにすることを目的としたパフォーマンスカウンターを示します。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-106">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="aa0f7-107">通話品質の方法論 (CQM) を実装するための最初の手順は、通常、Lync ユーザー向けの高品質なオーディオ操作を実現することに重点を置いて、KHI データを収集することです。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-107">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="aa0f7-108">CQM の使用方法について質問がある場合は、cqmfeedback@microsoft.com に質問を送信できます。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-108">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="aa0f7-109">ポスターは、以下の領域について説明します。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-109">The poster explains the following areas:</span></span>

  - <span data-ttu-id="aa0f7-110">重要な正常性インジケーターとは</span><span class="sxs-lookup"><span data-stu-id="aa0f7-110">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="aa0f7-111">KHI データを収集するには</span><span class="sxs-lookup"><span data-stu-id="aa0f7-111">To Collect KHI Data</span></span>

  - <span data-ttu-id="aa0f7-112">すべてのサーバーの役割の修復フロー</span><span class="sxs-lookup"><span data-stu-id="aa0f7-112">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="aa0f7-113">用語集</span><span class="sxs-lookup"><span data-stu-id="aa0f7-113">Glossary</span></span>

  - <span data-ttu-id="aa0f7-114">フロントエンドサーバー</span><span class="sxs-lookup"><span data-stu-id="aa0f7-114">Front-end Servers</span></span>

  - <span data-ttu-id="aa0f7-115">バックエンドの SQL サーバー</span><span class="sxs-lookup"><span data-stu-id="aa0f7-115">Backend SQL Servers</span></span>

  - <span data-ttu-id="aa0f7-116">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="aa0f7-116">Mediation Servers</span></span>

  - <span data-ttu-id="aa0f7-117">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="aa0f7-117">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="aa0f7-118">重要な正常性インジケーターとは</span><span class="sxs-lookup"><span data-stu-id="aa0f7-118">What are Key Health Indicators?</span></span>

<span data-ttu-id="aa0f7-119">キー正常性インジケーターは、パフォーマンスカウンターのしきい値によって、ユーザーの作業環境の問題を明らかにします。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-119">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="aa0f7-120">通話品質の方法論 (CQM) を実装するための最初の手順は、通常、Lync ユーザー向けの高品質なオーディオ操作を実現することに重点を置いて、KHI データを収集することです。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-120">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="aa0f7-121">KHIs は、標準的な Lync 監視ソリューション (System Center Operations Manager、代理トランザクション、監視サーバーなど) に加えて、これらのソリューションの代わりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-121">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="aa0f7-122">KHI パフォーマンスカウンターを収集し、ネットワークガイドに付属する KHI スプレッドシートに、Lync 展開のサーバーの状態を判断するのに役立つスコアカードを作成します。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-122">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="aa0f7-123">情報を入力すると、環境を修復して、他の関係者に対してさらに洞察を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-123">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="aa0f7-124">KHIs を月単位で評価し、展開の継続的な運用プロセスに組み込みます。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-124">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="aa0f7-125">[Lync Server ネットワークガイド](https://go.microsoft.com/fwlink/p/?linkid=390677)をダウンロードして、khis の完全なリストを確認し、関連するスプレッドシートを取得します。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-125">Download the [Lync Server Networking Guide](https://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="aa0f7-126">KHI データを収集するには</span><span class="sxs-lookup"><span data-stu-id="aa0f7-126">To Collect KHI Data</span></span>

1.  <span data-ttu-id="aa0f7-127">各 Lync Server で Lync Server ネットワークガイドに含まれている KHI スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-127">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="aa0f7-128">これにより、パフォーマンスモニターの内部にデータコレクターが作成され、KHI という名前になります。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-128">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="aa0f7-129">既定では、データは15秒ごとにポーリングされます。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-129">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="aa0f7-130">会社の就業日の開始前に、各 Lync Server に移動し、KHI データコレクターを開始します。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-130">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="aa0f7-131">その日の最後に、KHI Data コレクターを停止し、データを1か所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-131">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="aa0f7-132">パフォーマンスモニターを使用して Lync Server ネットワークガイドのダウンロードに含まれている KHI スプレッドシートにデータを入力した後、結果を推奨されるターゲットと比較します。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-132">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="aa0f7-133">すべてのサーバーの役割の修復フロー</span><span class="sxs-lookup"><span data-stu-id="aa0f7-133">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="aa0f7-134">Lync 実装の各サーバーについては、まず、サーバーのコンポーネントの正常性とシステムのパフォーマンスが目的のレベル以上であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-134">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="aa0f7-135">その後、Lync の実装全体におけるサーバーの役割に関連する指標を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-135">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="aa0f7-136">まず、すべてのサーバーの KHI パフォーマンスデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-136">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="aa0f7-137">各システムの役割 (このドキュメントで後述します) について、基本的なシステムコンポーネントが推奨されるターゲットを満たしているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-137">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="aa0f7-138">そうでない場合は、Lync の実装でのサーバーの役割に固有の指標を確認する前に、システムのパフォーマンスを修復し、KHI データを再度収集して、システムの正常性を確保します。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-138">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="aa0f7-139">すべての役割のコンポーネントの正常性は次のように定義されます。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-139">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="aa0f7-140">CPU 使用\<率80%</span><span class="sxs-lookup"><span data-stu-id="aa0f7-140">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="aa0f7-141">平均ディスク書き込み\< 10 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="aa0f7-141">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="aa0f7-142">平均ディスク読み取り\< 10 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="aa0f7-142">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="aa0f7-143">使用可能\>なメモリ20% システムの合計 MB</span><span class="sxs-lookup"><span data-stu-id="aa0f7-143">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="aa0f7-144">ネットワークキューの\<長さ2</span><span class="sxs-lookup"><span data-stu-id="aa0f7-144">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="aa0f7-145">破棄されたパケット (入力/出力) = 0</span><span class="sxs-lookup"><span data-stu-id="aa0f7-145">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="aa0f7-146">用語集</span><span class="sxs-lookup"><span data-stu-id="aa0f7-146">Glossary</span></span>

<span data-ttu-id="aa0f7-147">このポスターでは、次の用語と略語を使用しています。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-147">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="aa0f7-148">MCU として = アプリケーション共有マルチポイントコントロールユニット</span><span class="sxs-lookup"><span data-stu-id="aa0f7-148">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="aa0f7-149">AV MCU = 音声/ビデオ MCU</span><span class="sxs-lookup"><span data-stu-id="aa0f7-149">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="aa0f7-150">IM MCU = インスタントメッセージング MCU</span><span class="sxs-lookup"><span data-stu-id="aa0f7-150">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="aa0f7-151">UCWA = 統合コミュニケーション Web API</span><span class="sxs-lookup"><span data-stu-id="aa0f7-151">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="aa0f7-152">AV Edge = エッジ経由の音声/ビデオのトラバース</span><span class="sxs-lookup"><span data-stu-id="aa0f7-152">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="aa0f7-153">AV Auth = 音声/ビデオ認証</span><span class="sxs-lookup"><span data-stu-id="aa0f7-153">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="aa0f7-154">SIP スタック = Lync のコア SIP 実装が含まれています。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-154">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="aa0f7-155">データプロキシ = エッジ会議に使用</span><span class="sxs-lookup"><span data-stu-id="aa0f7-155">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="aa0f7-156">その他の Ss = Lync Storage Service</span><span class="sxs-lookup"><span data-stu-id="aa0f7-156">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="aa0f7-157">フロントエンドサーバー</span><span class="sxs-lookup"><span data-stu-id="aa0f7-157">Front-end Servers</span></span>

<span data-ttu-id="aa0f7-158">次の KHI ターゲットは、基本コンポーネントの正常性に加えて、フロントエンドサーバーに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-158">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa0f7-159">機能領域</span><span class="sxs-lookup"><span data-stu-id="aa0f7-159">Functional area</span></span></th>
<th><span data-ttu-id="aa0f7-160">ターゲット指標</span><span class="sxs-lookup"><span data-stu-id="aa0f7-160">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa0f7-161">AS/AV/IM MCU</span><span class="sxs-lookup"><span data-stu-id="aa0f7-161">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="aa0f7-162">MCU 正常性&lt;状態2</span><span class="sxs-lookup"><span data-stu-id="aa0f7-162">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0f7-163">Web コンポーネント</span><span class="sxs-lookup"><span data-stu-id="aa0f7-163">Web Components</span></span></p></td>
<td><p><span data-ttu-id="aa0f7-164">配布リスト展開 AD タイムアウト&lt;0</span><span class="sxs-lookup"><span data-stu-id="aa0f7-164">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="aa0f7-165">ABWQ の失敗 = 0</span><span class="sxs-lookup"><span data-stu-id="aa0f7-165">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="aa0f7-166">LIS のエラー = 0</span><span class="sxs-lookup"><span data-stu-id="aa0f7-166">LIS failures = 0</span></span></p>
<p><span data-ttu-id="aa0f7-167">認証エラー &lt; 1/秒</span><span class="sxs-lookup"><span data-stu-id="aa0f7-167">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="aa0f7-168">ASP.NET v4 要求が拒否されました = 0</span><span class="sxs-lookup"><span data-stu-id="aa0f7-168">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa0f7-169">SIP スタック</span><span class="sxs-lookup"><span data-stu-id="aa0f7-169">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="aa0f7-170">1秒あたりの平均&lt;受信メッセージ処理</span><span class="sxs-lookup"><span data-stu-id="aa0f7-170">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="aa0f7-171">着信応答ドロップ&lt;された 1/Sec &lt;受信要求ドロップ 1/秒</span><span class="sxs-lookup"><span data-stu-id="aa0f7-171">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="aa0f7-172">キュー待機&lt;時間100ミリ秒</span><span class="sxs-lookup"><span data-stu-id="aa0f7-172">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="aa0f7-173">ストアドプロシージャ&lt;待機時間100ミリ秒</span><span class="sxs-lookup"><span data-stu-id="aa0f7-173">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="aa0f7-174">調整される要求 = 0</span><span class="sxs-lookup"><span data-stu-id="aa0f7-174">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="aa0f7-175">認証エラー &lt; 1/秒</span><span class="sxs-lookup"><span data-stu-id="aa0f7-175">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="aa0f7-176">受信メッセージがタイムアウト&lt;になりました2</span><span class="sxs-lookup"><span data-stu-id="aa0f7-176">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="aa0f7-177">受信メッセージの平均保持&lt;時間1秒</span><span class="sxs-lookup"><span data-stu-id="aa0f7-177">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="aa0f7-178">フロー制御さ&lt;れた接続2</span><span class="sxs-lookup"><span data-stu-id="aa0f7-178">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="aa0f7-179">平均アウトキュー遅延&lt; 2 秒</span><span class="sxs-lookup"><span data-stu-id="aa0f7-179">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0f7-180">LySS</span><span class="sxs-lookup"><span data-stu-id="aa0f7-180">LySS</span></span></p></td>
<td><p><span data-ttu-id="aa0f7-181">Storage Service DB &lt; 80 で使用される領域の割合 (%)</span><span class="sxs-lookup"><span data-stu-id="aa0f7-181">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="aa0f7-182">#レプリカレプリケーションエラーの数 = 0</span><span class="sxs-lookup"><span data-stu-id="aa0f7-182"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="aa0f7-183">#データ損失イベントの数 = 0</span><span class="sxs-lookup"><span data-stu-id="aa0f7-183"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa0f7-184">SQL</span><span class="sxs-lookup"><span data-stu-id="aa0f7-184">SQL</span></span></p></td>
<td><p><span data-ttu-id="aa0f7-185">ページ寿命の&gt;予測300秒。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-185">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="aa0f7-186">Batch requests/sec &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="aa0f7-186">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="aa0f7-187">バックエンドの SQL サーバー</span><span class="sxs-lookup"><span data-stu-id="aa0f7-187">Backend SQL Servers</span></span>

<span data-ttu-id="aa0f7-188">次の KHI ターゲットは、基本的なコンポーネントの正常性に加えて、SQL server に固有のものです。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-188">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa0f7-189">機能領域</span><span class="sxs-lookup"><span data-stu-id="aa0f7-189">Functional area</span></span></th>
<th><span data-ttu-id="aa0f7-190">ターゲット指標</span><span class="sxs-lookup"><span data-stu-id="aa0f7-190">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa0f7-191">SQL</span><span class="sxs-lookup"><span data-stu-id="aa0f7-191">SQL</span></span></p></td>
<td><p><span data-ttu-id="aa0f7-192">ページ寿命の&gt;予測300秒。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-192">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="aa0f7-193">Batch requests/sec &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="aa0f7-193">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="aa0f7-194">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="aa0f7-194">Mediation Servers</span></span>

<span data-ttu-id="aa0f7-195">次の KHI ターゲットは、基本的なコンポーネントの正常性に加えて、仲介サーバーに固有です。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-195">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa0f7-196">機能領域</span><span class="sxs-lookup"><span data-stu-id="aa0f7-196">Functional area</span></span></th>
<th><span data-ttu-id="aa0f7-197">ターゲット指標</span><span class="sxs-lookup"><span data-stu-id="aa0f7-197">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa0f7-198">仲介サーバーサービス</span><span class="sxs-lookup"><span data-stu-id="aa0f7-198">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="aa0f7-199">読み込み呼び出しエラーのインデックス = 0</span><span class="sxs-lookup"><span data-stu-id="aa0f7-199">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="aa0f7-200">プロキシ&lt;10 のために失敗した通話</span><span class="sxs-lookup"><span data-stu-id="aa0f7-200">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="aa0f7-201">ゲートウェイ&lt;10 が原因で失敗した通話</span><span class="sxs-lookup"><span data-stu-id="aa0f7-201">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="aa0f7-202">拒否された呼び出し (in または out) = 0</span><span class="sxs-lookup"><span data-stu-id="aa0f7-202">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="aa0f7-203">メディア候補がありません = 0</span><span class="sxs-lookup"><span data-stu-id="aa0f7-203">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="aa0f7-204">メディア接続チェックの失敗 = 0</span><span class="sxs-lookup"><span data-stu-id="aa0f7-204">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="aa0f7-205">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="aa0f7-205">Edge Servers</span></span>

<span data-ttu-id="aa0f7-206">基本的なコンポーネントの正常性に加えて、エッジサーバーに固有の以下の KHI ターゲットが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-206">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa0f7-207">機能領域</span><span class="sxs-lookup"><span data-stu-id="aa0f7-207">Functional area</span></span></th>
<th><span data-ttu-id="aa0f7-208">ターゲット指標</span><span class="sxs-lookup"><span data-stu-id="aa0f7-208">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa0f7-209">AV 認証</span><span class="sxs-lookup"><span data-stu-id="aa0f7-209">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="aa0f7-210">無効な&lt;要求数 20/秒</span><span class="sxs-lookup"><span data-stu-id="aa0f7-210">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0f7-211">AV エッジ</span><span class="sxs-lookup"><span data-stu-id="aa0f7-211">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="aa0f7-212">Auth. 失敗&lt;回数 20/秒</span><span class="sxs-lookup"><span data-stu-id="aa0f7-212">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="aa0f7-213">割り当てエラー &lt;数 20/秒</span><span class="sxs-lookup"><span data-stu-id="aa0f7-213">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="aa0f7-214">削除&lt;されたパケット数 300/秒</span><span class="sxs-lookup"><span data-stu-id="aa0f7-214">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa0f7-215">データプロキシ</span><span class="sxs-lookup"><span data-stu-id="aa0f7-215">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="aa0f7-216">サーバー接続&lt;の調整3</span><span class="sxs-lookup"><span data-stu-id="aa0f7-216">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="aa0f7-217">システムが調整&lt;1</span><span class="sxs-lookup"><span data-stu-id="aa0f7-217">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0f7-218">SIP スタック</span><span class="sxs-lookup"><span data-stu-id="aa0f7-218">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="aa0f7-219">制限を超えた&lt;接続の削除1</span><span class="sxs-lookup"><span data-stu-id="aa0f7-219">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="aa0f7-220">送信タイムアウト&lt;10</span><span class="sxs-lookup"><span data-stu-id="aa0f7-220">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="aa0f7-221">フロー制御さ&lt;れた接続100</span><span class="sxs-lookup"><span data-stu-id="aa0f7-221">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="aa0f7-222">1/sec &lt;がドロップした着信要求</span><span class="sxs-lookup"><span data-stu-id="aa0f7-222">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="aa0f7-223">平均メッセージ処理&lt;時間3秒</span><span class="sxs-lookup"><span data-stu-id="aa0f7-223">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aa0f7-224">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa0f7-224">See Also</span></span>


[<span data-ttu-id="aa0f7-225">Lync Server ネットワークガイド</span><span class="sxs-lookup"><span data-stu-id="aa0f7-225">Lync Server Networking Guide</span></span>](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="aa0f7-226">主要な正常性インジケーター: 正常な Lync Server を維持するための基礎</span><span class="sxs-lookup"><span data-stu-id="aa0f7-226">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](https://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="aa0f7-227">Lync 通話品質の方法論</span><span class="sxs-lookup"><span data-stu-id="aa0f7-227">Lync Call Quality Methodology</span></span>](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

