---
title: ビジネス サーバー 2015 Skype 統計マネージャーの計画します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 5/23/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: '概要: は、Skype のビジネス サーバー 2015 の統計マネージャーの概要を学習するには、このトピックを読みます。'
ms.openlocfilehash: de4f2bedcbd03191b852366504423ebb031cf5f1
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23244007"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server-2015"></a><span data-ttu-id="77c15-103">ビジネス サーバー 2015 Skype 統計マネージャーの計画します。</span><span class="sxs-lookup"><span data-stu-id="77c15-103">Plan for Statistics Manager for Skype for Business Server 2015</span></span>

<span data-ttu-id="77c15-104">**の概要:** Skype のビジネス サーバー 2015 の統計マネージャーの概要を学習するには、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77c15-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server 2015.</span></span>

 <span data-ttu-id="77c15-105">Skype ビジネス サーバーの統計情報マネージャーとは、Skype をビジネスのサーバーの稼働状態とパフォーマンスのデータをリアルタイムに表示できるようにする強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="77c15-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="77c15-106">数秒ごとに数百のサーバー間でのパフォーマンス データをポーリングし、統計マネージャーの web サイトですぐに結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="77c15-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="77c15-107">統計マネージャーを使用するには継続的なパフォーマンス問題を特定する、お客様の環境を計画的な変更の結果を表示、停止、解像度などの作業を追跡します。</span><span class="sxs-lookup"><span data-stu-id="77c15-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="77c15-108">統計マネージャーは、キーの状態インジケーター (KHI) のしきい値が設定されているし、配置のニーズに合わせてカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="77c15-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="77c15-109">統計マネージャーを 1 つのサーバーをホストのすべてのサーバー側の統計マネージャー コンポーネントの設置型展開で展開できます。</span><span class="sxs-lookup"><span data-stu-id="77c15-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="77c15-110">統計マネージャーの展開の詳細については、 [Skype のビジネス サーバー 2015 の統計マネージャーの展開](deploy.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77c15-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server 2015](deploy.md).</span></span> <span data-ttu-id="77c15-111">統計マネージャーの既存の展開がある、まだリリース 1.1 にアップグレードしていない場合は、[リリース 1.1 の新機能としては](plan.md#BKMK_WhatsNew) [Skype のビジネス サーバー 2015 の統計マネージャーのアップグレード](upgrade.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77c15-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 1.1, see [What's new in Release 1.1](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server 2015](upgrade.md).</span></span>

<span data-ttu-id="77c15-112">このトピックには次のセクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="77c15-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="77c15-113">特徴と機能</span><span class="sxs-lookup"><span data-stu-id="77c15-113">Features and capabilities</span></span>](https://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Features)

- [<span data-ttu-id="77c15-114">リリース 1.1 の新機能</span><span class="sxs-lookup"><span data-stu-id="77c15-114">What's new in Release 1.1</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="77c15-115">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="77c15-115">Components</span></span>](https://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Components)

- [<span data-ttu-id="77c15-116">設置型展開</span><span class="sxs-lookup"><span data-stu-id="77c15-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- [<span data-ttu-id="77c15-117">要件</span><span class="sxs-lookup"><span data-stu-id="77c15-117">Requirements</span></span>](https://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Requirements)

- [<span data-ttu-id="77c15-118">セキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="77c15-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="77c15-119">特徴と機能</span><span class="sxs-lookup"><span data-stu-id="77c15-119">Features and capabilities</span></span>
<span data-ttu-id="77c15-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="77c15-120"></span></span>

<span data-ttu-id="77c15-121">統計マネージャーことができます。</span><span class="sxs-lookup"><span data-stu-id="77c15-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="77c15-122">すべてのサーバー用の生データをリアルタイムで表示します。</span><span class="sxs-lookup"><span data-stu-id="77c15-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="77c15-123">(データは非常に高いレートでサンプリングされた、1 秒未満の web サイトに送信される)</span><span class="sxs-lookup"><span data-stu-id="77c15-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="77c15-124">特定の役割に集計されたデータの表示などのフロント エンド サーバー、仲介サーバー、エッジ サーバー、およびように。</span><span class="sxs-lookup"><span data-stu-id="77c15-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="77c15-125">特定のサイト、サイト内の特定のプールとプール内のサーバーを特定し、ビューのデータにドリルダウンできます。</span><span class="sxs-lookup"><span data-stu-id="77c15-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="77c15-126">カウンターが既定で表示されるように選択できるように、ユーザー定義のグラフを作成します。</span><span class="sxs-lookup"><span data-stu-id="77c15-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="77c15-127">ズームし、の両方、x: と y 軸または x 軸だけにパンします。</span><span class="sxs-lookup"><span data-stu-id="77c15-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="77c15-128">データをフィルター処理するときに日付の範囲または要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="77c15-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="77c15-129">に基づいてサーバーのパフォーマンスを表示するには、主要な稼働状態インジケーター (KHIs) が確立されます。</span><span class="sxs-lookup"><span data-stu-id="77c15-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="77c15-130">KHIs は、正常な範囲が定義されているパフォーマンス カウンターのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="77c15-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="77c15-131">各カウンターの詳細な測定基準を表示します。</span><span class="sxs-lookup"><span data-stu-id="77c15-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="77c15-132">複数のカタログの作成またはサーバー間でデータを比較します。</span><span class="sxs-lookup"><span data-stu-id="77c15-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="77c15-133">ダッシュ ボードのサービスに現在のデータを報告していないエージェントを識別するには、潜在的なカウンターのレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="77c15-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="77c15-134">グラフのデータの特定のインスタンスをファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="77c15-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="77c15-135">リアルタイムで更新プログラムを含む KHIs を表示します。</span><span class="sxs-lookup"><span data-stu-id="77c15-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="77c15-136">履歴の表示を有効にすると、新しいエラーのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="77c15-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="77c15-137">すべての KHIs を同時に表示します。</span><span class="sxs-lookup"><span data-stu-id="77c15-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="77c15-138">サーバー (横向き) で KHIs を表示します。</span><span class="sxs-lookup"><span data-stu-id="77c15-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="77c15-139">KHI のビューの定義</span><span class="sxs-lookup"><span data-stu-id="77c15-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-11"></a><span data-ttu-id="77c15-140">リリース 1.1 の新機能</span><span class="sxs-lookup"><span data-stu-id="77c15-140">What's new in Release 1.1</span></span>
<span data-ttu-id="77c15-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="77c15-141"></span></span>

<span data-ttu-id="77c15-142">以下は、リリース 1.1 の新機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="77c15-142">The following describes what's new in Release 1.1.</span></span> <span data-ttu-id="77c15-143">統計マネージャーの既存の展開があり、まだアップグレードした場合は、 [Skype のビジネス サーバー 2015 の統計マネージャーのアップグレード](upgrade.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77c15-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server 2015](upgrade.md).</span></span>

- <span data-ttu-id="77c15-144">エッジのメディア、ファブリックの稼働状態、プールのフェールオーバーおよび登録シナリオのシナリオのビューが追加されました。</span><span class="sxs-lookup"><span data-stu-id="77c15-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="77c15-145">(リスナーには、インストールされている) コマンド ・ ライン ・ PerfAgentStorageManager.exe では、csv 形式カウンター データをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="77c15-145">Command line PerfAgentStorageManager.exe (installed with the Listener) can now export counter data as a CSV.</span></span>

- <span data-ttu-id="77c15-146">多くの新しいカウンターは、SQL サーバーでは、複数のファブリックの Windows カウンターでは、複数の Skype ビジネス使用状況カウンターの新たに追加されなどです。</span><span class="sxs-lookup"><span data-stu-id="77c15-146">Many new counters have been added for SQL servers, more Windows Fabric counters, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="77c15-147">統計マネージャー エージェントの監視ノードの統合監視ノードでは、エージェントがインストールされている場合が報告されます代理トランザクションの統計情報カウンターと統計マネージャーにします。</span><span class="sxs-lookup"><span data-stu-id="77c15-147">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="77c15-148">さまざまな信頼性とパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="77c15-148">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="77c15-149">統計マネージャーの web サイトを実行しているのバージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="77c15-149">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="77c15-150">ファイル エクスプ ローラーで開くには (既定のディレクトリ) ビジネス サーバー ・ StatsMan ・ WebSite\bin の C:\Program Files\Skype</span><span class="sxs-lookup"><span data-stu-id="77c15-150">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="77c15-151">StatsManHubWebSite.dll を右クリックし、そのプロパティを表示</span><span class="sxs-lookup"><span data-stu-id="77c15-151">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="77c15-152">製品のバージョンは [説明] の詳細に表示されます。</span><span class="sxs-lookup"><span data-stu-id="77c15-152">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="77c15-153">Components</span><span class="sxs-lookup"><span data-stu-id="77c15-153">Components</span></span>
<span data-ttu-id="77c15-154"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="77c15-154"></span></span>

<span data-ttu-id="77c15-155">統計マネージャーは、次のコンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="77c15-155">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="77c15-156">**エージェントです。**</span><span class="sxs-lookup"><span data-stu-id="77c15-156">**Agent.**</span></span> <span data-ttu-id="77c15-157">各監視対象のサーバー上で実行される軽量のエージェントです。</span><span class="sxs-lookup"><span data-stu-id="77c15-157">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="77c15-158">エージェントは、ローカルの集計でパフォーマンス カウンターの構成可能な率が高いポーリングを使用します。</span><span class="sxs-lookup"><span data-stu-id="77c15-158">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="77c15-159">**リスナー。**</span><span class="sxs-lookup"><span data-stu-id="77c15-159">**Listener.**</span></span> <span data-ttu-id="77c15-160">サーバー側の API すべてのエージェントからデータを受信し、人口の間でデータを集計します。</span><span class="sxs-lookup"><span data-stu-id="77c15-160">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="77c15-161">**ハブです。**</span><span class="sxs-lookup"><span data-stu-id="77c15-161">**Hub.**</span></span> <span data-ttu-id="77c15-162">システムは、クライアント API は、web サーバー、上で動作し、リアルタイム データの更新は、web サイト経由で接続しているクライアントとして機能します。</span><span class="sxs-lookup"><span data-stu-id="77c15-162">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="77c15-163">(ハブは web サイトの msi ファイルの一部として自動的にインストール)。</span><span class="sxs-lookup"><span data-stu-id="77c15-163">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="77c15-164">**Web サイトです。**</span><span class="sxs-lookup"><span data-stu-id="77c15-164">**Website.**</span></span> <span data-ttu-id="77c15-165">システムで利用可能なすべての機能をまとめて、ユーザー インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="77c15-165">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="77c15-166">さらに、 **Redis**で、オープン ・ ソースのデータ構造のサーバーのメモリ内キャッシュの統計情報のマネージャーが必要です。</span><span class="sxs-lookup"><span data-stu-id="77c15-166">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="77c15-167">Redis のダウンロードの詳細については、[統計マネージャーの展開](deploy.md#BKMK_Deploy)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77c15-167">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="77c15-168">設置型展開</span><span class="sxs-lookup"><span data-stu-id="77c15-168">On-premises deployment</span></span>
<span data-ttu-id="77c15-169"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="77c15-169"></span></span>

<span data-ttu-id="77c15-170">設置型展開では、1 台のサーバーはすべてのサーバー側の統計マネージャー コンポーネントをホストします。</span><span class="sxs-lookup"><span data-stu-id="77c15-170">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="77c15-171">次の図は、1 台のコンピューターで統計マネージャーの web サイト、ハブ、リスナー、およびキャッシュ システム Redis がホストされている、設置型の展開を示しています。</span><span class="sxs-lookup"><span data-stu-id="77c15-171">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="77c15-172">統計マネージャーは次の 3 つの Skype ビジネス サーバーでは、リスナーにデータを送信する 1 つのエージェントがあるを監視しています。</span><span class="sxs-lookup"><span data-stu-id="77c15-172">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="77c15-173">ユーザーは、集計統計マネージャーですべてのデータを表示するのには 1 つの web サイトに接続します。</span><span class="sxs-lookup"><span data-stu-id="77c15-173">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![Stats Manager のオンプレミス展開](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="77c15-175">要件</span><span class="sxs-lookup"><span data-stu-id="77c15-175">Requirements</span></span>
<span data-ttu-id="77c15-176"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="77c15-176"></span></span>

<span data-ttu-id="77c15-177">統計マネージャーを展開する前に次のソフトウェア、ネットワーク、およびハードウェア要件を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77c15-177">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="77c15-178">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="77c15-178">Software requirements</span></span>

- <span data-ttu-id="77c15-179">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="77c15-179">Windows Server 2012 R2</span></span>

- <span data-ttu-id="77c15-180">IIS が (自動的にインストールされています)</span><span class="sxs-lookup"><span data-stu-id="77c15-180">IIS (automatically installed)</span></span>

- <span data-ttu-id="77c15-181">Redis</span><span class="sxs-lookup"><span data-stu-id="77c15-181">Redis</span></span>

- <span data-ttu-id="77c15-182">統計マネージャーのサービス (自動的にインストール)</span><span class="sxs-lookup"><span data-stu-id="77c15-182">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="77c15-183">PSExec - リモート エージェントの展開を行う必要</span><span class="sxs-lookup"><span data-stu-id="77c15-183">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="77c15-184">.NET 4.5 の (2012 R2 に含まれている) は、サーバー側コンポーネントに必要な</span><span class="sxs-lookup"><span data-stu-id="77c15-184">.NET 4.5 (included with 2012 R2) - Required for server-side components</span></span>

- <span data-ttu-id="77c15-185">.NET 4.0 のエージェントに必要な</span><span class="sxs-lookup"><span data-stu-id="77c15-185">.NET 4.0 - Required for agents</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="77c15-186">ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="77c15-186">Networking requirements</span></span>


|<span data-ttu-id="77c15-187">**サーバーをホストしています。**</span><span class="sxs-lookup"><span data-stu-id="77c15-187">**Hosting server**</span></span>|<span data-ttu-id="77c15-188">**エージェント**</span><span class="sxs-lookup"><span data-stu-id="77c15-188">**Agents**</span></span>|<span data-ttu-id="77c15-189">**リスナー**</span><span class="sxs-lookup"><span data-stu-id="77c15-189">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="77c15-190">全二重の最低限のギガビットのネットワークです。</span><span class="sxs-lookup"><span data-stu-id="77c15-190">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="77c15-191">送信 TCP ポート 8443、リスナーとの通信を (カスタマイズ可能なポートの番号)。</span><span class="sxs-lookup"><span data-stu-id="77c15-191">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="77c15-192">リスナーのポートは、すべてのサーバーで同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="77c15-192">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="77c15-193">80 または 443 が開いている web サイトをホストするための TCP ポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="77c15-193">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="77c15-194">エージェントと通信するためには、TCP ポート 8443 (カスタマイズ可能なポート番号) を受信します。</span><span class="sxs-lookup"><span data-stu-id="77c15-194">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="77c15-195">インストール中に、リスナーと web サイトのファイアウォールのポートが自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="77c15-195">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="77c15-196">エージェントのインストールでは、送信 TCP 接続は、既定で許可されてと見なされます。</span><span class="sxs-lookup"><span data-stu-id="77c15-196">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="77c15-197">ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="77c15-197">Hardware requirements</span></span>

<span data-ttu-id="77c15-198">展開では、設置型、1 台のサーバーがすべてのサーバー側の統計マネージャー コンポーネント、16 GB の RAM と 4 を持つサーバーにホスト CPU の平均で 1 秒あたり約 150 のサンプルをサポートできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="77c15-198">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="77c15-199">数のカウンターとエージェントをサポートできることを確認するのには、次の計算を使用します。</span><span class="sxs-lookup"><span data-stu-id="77c15-199">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="77c15-200">100 台のサーバー \*80 カウンター\*各エージェントから/60 秒、1 分あたり 1 サンプル = ~ 133 です。</span><span class="sxs-lookup"><span data-stu-id="77c15-200">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="77c15-201">セキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="77c15-201">Security considerations</span></span>
<span data-ttu-id="77c15-202"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="77c15-202"></span></span>

<span data-ttu-id="77c15-203">サーバー間のすべてのトラフィックが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="77c15-203">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="77c15-204">暗号化された HTTP トラフィックはポート 8443 を (デフォルト) でエージェントからサーバーに送信、リスナーです。</span><span class="sxs-lookup"><span data-stu-id="77c15-204">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="77c15-205">エージェントでは、リスナーのサーバーが必要な受信者であることを確認するのにはサーバー上で SSL の拇印を確認します。</span><span class="sxs-lookup"><span data-stu-id="77c15-205">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="77c15-206">エージェントが (チェーンの検証ではなく) 証明書の拇印の検証を使用することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="77c15-206">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="77c15-207">自己署名証明書を使用することが可能なため、証明書の完全な検証は行いません。</span><span class="sxs-lookup"><span data-stu-id="77c15-207">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="77c15-208">エージェントが完了したら、リスナーが本物であり、エージェント、リスナーによって確認が行われますが、パスワードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="77c15-208">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="77c15-209">エージェントでは、リスナーへの接続でパフォーマンス データを送信を開始します。</span><span class="sxs-lookup"><span data-stu-id="77c15-209">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="77c15-210">詳細情報</span><span class="sxs-lookup"><span data-stu-id="77c15-210">For more information</span></span>
<span data-ttu-id="77c15-211"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="77c15-211"></span></span>

<span data-ttu-id="77c15-212">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77c15-212">For more information, see the following:</span></span>

- [<span data-ttu-id="77c15-213">Skype for Business Server 2015 の Statistics Manager の展開</span><span class="sxs-lookup"><span data-stu-id="77c15-213">Deploy Statistics Manager for Skype for Business Server 2015</span></span>](deploy.md)

- [<span data-ttu-id="77c15-214">Skype for Business Server 2015 の Statistics Manager のアップグレード</span><span class="sxs-lookup"><span data-stu-id="77c15-214">Upgrade Statistics Manager for Skype for Business Server 2015</span></span>](upgrade.md)

- [<span data-ttu-id="77c15-215">Skype for Business Server 2015 の Statistics Manager のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="77c15-215">Troubleshoot Statistics Manager for Skype for Business Server 2015</span></span>](troubleshoot.md)

- [<span data-ttu-id="77c15-216">Skype ビジネス サーバー統計マネージャーのブログ</span><span class="sxs-lookup"><span data-stu-id="77c15-216">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/skypestatsman/)


