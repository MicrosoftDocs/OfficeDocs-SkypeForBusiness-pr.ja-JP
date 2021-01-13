---
title: Skype for Business Server の統計情報マネージャーの計画
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: '概要: このトピックでは、Skype for Business Server の Statistics Manager について説明します。'
ms.openlocfilehash: cdc536abcbd1bd98c4a3c7ce974247a716865582
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821827"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="bec1e-103">Skype for Business Server の統計情報マネージャーの計画</span><span class="sxs-lookup"><span data-stu-id="bec1e-103">Plan for Statistics Manager for Skype for Business Server</span></span>

<span data-ttu-id="bec1e-104">**概要:** このトピックでは、Skype for Business Server の Statistics Manager について説明します。</span><span class="sxs-lookup"><span data-stu-id="bec1e-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server.</span></span>

 <span data-ttu-id="bec1e-105">Skype for Business Server の Statistics Manager は、Skype for Business Server の正常性とパフォーマンスのデータをリアルタイムで表示できる強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="bec1e-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="bec1e-106">数秒ごとに数百のサーバーでパフォーマンス データをポーリングし、統計情報マネージャー Web サイトで即座に結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="bec1e-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="bec1e-107">Statistics Manager を使用すると、継続的なパフォーマンスの問題の特定、環境に対する計画された変更の結果の表示、停止の解決の追跡、その他の機能停止の追跡を行えます。</span><span class="sxs-lookup"><span data-stu-id="bec1e-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="bec1e-108">統計マネージャーはキー正常性インジケーター (KHI) のしきい値で構成され、展開固有のニーズに合わせてカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="bec1e-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="bec1e-109">1 台のサーバーがすべてのサーバー側の Statistics Manager コンポーネントをホストするオンプレミス展開で Statistics Manager を展開できます。</span><span class="sxs-lookup"><span data-stu-id="bec1e-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="bec1e-110">Statistics Manager の展開の詳細については [、「Deploy Statistics Manager for Skype for Business Server」を参照してください](deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="bec1e-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span> <span data-ttu-id="bec1e-111">Statistics Manager の既存の展開があるが、リリース 2.0 にまだアップグレードしていない場合は、「リリース [2.0](plan.md#BKMK_WhatsNew) の新機能」および [「Skype for Business Server](upgrade.md)用の Statistics Manager のアップグレード」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bec1e-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

<span data-ttu-id="bec1e-112">このトピックは、以下のセクションで構成されています。</span><span class="sxs-lookup"><span data-stu-id="bec1e-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="bec1e-113">機能</span><span class="sxs-lookup"><span data-stu-id="bec1e-113">Features and capabilities</span></span>](plan.md#BKMK_Features)

- [<span data-ttu-id="bec1e-114">リリース 2.0 の新機能</span><span class="sxs-lookup"><span data-stu-id="bec1e-114">What's new in Release 2.0</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="bec1e-115">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bec1e-115">Components</span></span>](plan.md#BKMK_Components)

- [<span data-ttu-id="bec1e-116">オンプレミス展開</span><span class="sxs-lookup"><span data-stu-id="bec1e-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- [<span data-ttu-id="bec1e-117">要件</span><span class="sxs-lookup"><span data-stu-id="bec1e-117">Requirements</span></span>](plan.md#BKMK_Requirements)

- [<span data-ttu-id="bec1e-118">セキュリティに関する検討事項</span><span class="sxs-lookup"><span data-stu-id="bec1e-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="bec1e-119">機能</span><span class="sxs-lookup"><span data-stu-id="bec1e-119">Features and capabilities</span></span>
<span data-ttu-id="bec1e-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="bec1e-120"><a name="BKMK_Features"> </a></span></span>

<span data-ttu-id="bec1e-121">統計情報マネージャーでは、次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bec1e-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="bec1e-122">すべてのサーバーの生データをリアルタイムで表示します。</span><span class="sxs-lookup"><span data-stu-id="bec1e-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="bec1e-123">(データは非常に高い速度でサンプリングされ、1 秒未満で Web サイトに送信されます)。</span><span class="sxs-lookup"><span data-stu-id="bec1e-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="bec1e-124">特定のロールについて集計されたデータを表示する。たとえば、フロントエンド サーバー、仲介サーバー、エッジ サーバーなどです。</span><span class="sxs-lookup"><span data-stu-id="bec1e-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="bec1e-125">ドリルダウンして、特定のサイト、サイト内の特定のプール、およびプール内の特定のサーバーのデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="bec1e-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="bec1e-126">選択したカウンターが既定で表示されるカスタム グラフを作成します。</span><span class="sxs-lookup"><span data-stu-id="bec1e-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="bec1e-127">x 軸と y 軸の両方、または x 軸でのみズームとパンを行います。</span><span class="sxs-lookup"><span data-stu-id="bec1e-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="bec1e-128">データをフィルター処理するには、日付範囲またはポイントインタイムを使用します。</span><span class="sxs-lookup"><span data-stu-id="bec1e-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="bec1e-129">確立されたキー正常性インジケーター (KHIs) に基づいてサーバーのパフォーマンスを表示します。</span><span class="sxs-lookup"><span data-stu-id="bec1e-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="bec1e-130">KHIs は、定義された正常な範囲を持つパフォーマンス カウンターのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="bec1e-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="bec1e-131">各カウンターの詳細な測定基準を表示します。</span><span class="sxs-lookup"><span data-stu-id="bec1e-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="bec1e-132">複数の母集団またはサーバー間でデータを比較します。</span><span class="sxs-lookup"><span data-stu-id="bec1e-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="bec1e-133">潜在的なカウンター レポートを表示して、現在のデータをダッシュボード サービスに報告していないエージェントを特定します。</span><span class="sxs-lookup"><span data-stu-id="bec1e-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="bec1e-134">グラフ データの特定のインスタンスをファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="bec1e-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="bec1e-135">更新プログラムを含め、リアルタイムで KHIs を表示します。</span><span class="sxs-lookup"><span data-stu-id="bec1e-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="bec1e-136">履歴ビューが有効になっている場合は、新しいエラーだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bec1e-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="bec1e-137">すべての KHIs を一度に表示する</span><span class="sxs-lookup"><span data-stu-id="bec1e-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="bec1e-138">サーバー別に KHIs を表示する (横向き表示)</span><span class="sxs-lookup"><span data-stu-id="bec1e-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="bec1e-139">KHI の定義を表示する</span><span class="sxs-lookup"><span data-stu-id="bec1e-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-20"></a><span data-ttu-id="bec1e-140">リリース 2.0 の新機能</span><span class="sxs-lookup"><span data-stu-id="bec1e-140">What's new in Release 2.0</span></span>
<span data-ttu-id="bec1e-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="bec1e-141"><a name="BKMK_WhatsNew"> </a></span></span>

<span data-ttu-id="bec1e-142">以下では、リリース 2.0 の新機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="bec1e-142">The following describes what's new in Release 2.0.</span></span> <span data-ttu-id="bec1e-143">Statistics Manager の既存の展開があるが、まだアップグレードしていない場合は [、Skype for Business Server](upgrade.md)の Upgrade Statistics Manager を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bec1e-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

- <span data-ttu-id="bec1e-144">エッジ メディア、ファブリックの正常性、プールのフェールオーバーと登録のシナリオに関するシナリオ ビューが追加されました。</span><span class="sxs-lookup"><span data-stu-id="bec1e-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="bec1e-145">新しいカウンターの多くは、SQL Skype for Business の使用状況カウンターなどのために追加されました。</span><span class="sxs-lookup"><span data-stu-id="bec1e-145">Many new counters have been added for SQL servers, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="bec1e-146">Statistics Manager エージェントの監視ノード統合 - エージェントが監視ノードにインストールされている場合、代理トランザクション統計はカウンターとして統計情報マネージャーに報告されます。</span><span class="sxs-lookup"><span data-stu-id="bec1e-146">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="bec1e-147">信頼性とパフォーマンスの多数の向上。</span><span class="sxs-lookup"><span data-stu-id="bec1e-147">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="bec1e-148">実行している統計情報マネージャー Web サイトのバージョンを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bec1e-148">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="bec1e-149">エクスプローラーで、C:\Program Files\Skype for Business Server StatsMan WebSite\bin を開きます (既定のディレクトリ)</span><span class="sxs-lookup"><span data-stu-id="bec1e-149">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="bec1e-150">ビューを右クリックしてStatsManHubWebSite.dllプロパティを表示する</span><span class="sxs-lookup"><span data-stu-id="bec1e-150">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="bec1e-151">製品バージョンが説明の詳細に表示されます。</span><span class="sxs-lookup"><span data-stu-id="bec1e-151">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="bec1e-152">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bec1e-152">Components</span></span>
<span data-ttu-id="bec1e-153"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="bec1e-153"><a name="BKMK_Components"> </a></span></span>

<span data-ttu-id="bec1e-154">統計情報マネージャーは、次のコンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="bec1e-154">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="bec1e-155">**エージェント。**</span><span class="sxs-lookup"><span data-stu-id="bec1e-155">**Agent.**</span></span> <span data-ttu-id="bec1e-156">監視対象の各サーバーで実行される軽量なエージェント。</span><span class="sxs-lookup"><span data-stu-id="bec1e-156">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="bec1e-157">エージェントを使用すると、ローカル集約を使用してパフォーマンス カウンターの構成可能な高レート ポーリングを実行できます。</span><span class="sxs-lookup"><span data-stu-id="bec1e-157">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="bec1e-158">**リスナー。**</span><span class="sxs-lookup"><span data-stu-id="bec1e-158">**Listener.**</span></span> <span data-ttu-id="bec1e-159">すべてのエージェントからデータを受信し、母集団全体のデータを集計するサーバー側 API。</span><span class="sxs-lookup"><span data-stu-id="bec1e-159">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="bec1e-160">**ハブ。**</span><span class="sxs-lookup"><span data-stu-id="bec1e-160">**Hub.**</span></span> <span data-ttu-id="bec1e-161">システムのクライアント API として機能し、Web サーバー上で実行され、Web サイト経由で接続されたクライアントにリアルタイムのデータ更新を提供します。</span><span class="sxs-lookup"><span data-stu-id="bec1e-161">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="bec1e-162">(ハブは Web サイト msi の一部として自動的にインストールされます)。</span><span class="sxs-lookup"><span data-stu-id="bec1e-162">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="bec1e-163">**Web サイト。**</span><span class="sxs-lookup"><span data-stu-id="bec1e-163">**Website.**</span></span> <span data-ttu-id="bec1e-164">システムで利用可能なすべての機能をまとめるユーザー インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="bec1e-164">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="bec1e-165">さらに、Statistics Manager には、メモリ内キャッシュ用のオープン ソース データ構造サーバーである **Redis** が必要です。</span><span class="sxs-lookup"><span data-stu-id="bec1e-165">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="bec1e-166">Redis のダウンロードの詳細については、「Statistics Manager の展開 [」を参照してください](deploy.md#BKMK_Deploy) 。</span><span class="sxs-lookup"><span data-stu-id="bec1e-166">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="bec1e-167">社内への展開</span><span class="sxs-lookup"><span data-stu-id="bec1e-167">On-premises deployment</span></span>
<span data-ttu-id="bec1e-168"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="bec1e-168"><a name="BKMK_DeploymentOptions"> </a></span></span>

<span data-ttu-id="bec1e-169">オンプレミス展開では、1 台のサーバーがすべてのサーバー側の Statistics Manager コンポーネントをホストします。</span><span class="sxs-lookup"><span data-stu-id="bec1e-169">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="bec1e-170">次の図は、Statistics Manager Web サイト、ハブ、リスナー、および Redis キャッシュ システムが 1 台のコンピューターでホストされているオンプレミス展開を示しています。</span><span class="sxs-lookup"><span data-stu-id="bec1e-170">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="bec1e-171">Statistics Manager は 3 台の Skype for Business サーバーを監視しています。各サーバーには、リスナーにデータを送信する 1 つのエージェントがあります。</span><span class="sxs-lookup"><span data-stu-id="bec1e-171">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="bec1e-172">ユーザーは 1 つの Web サイトに接続して、統計情報マネージャーによって集計されたデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="bec1e-172">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![Stats Manager のオンプレミス展開](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="bec1e-174">要件</span><span class="sxs-lookup"><span data-stu-id="bec1e-174">Requirements</span></span>
<span data-ttu-id="bec1e-175"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="bec1e-175"><a name="BKMK_Requirements"> </a></span></span>

<span data-ttu-id="bec1e-176">Statistics Manager を展開する前に、次のソフトウェア、ネットワーク、およびハードウェアの要件を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bec1e-176">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="bec1e-177">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="bec1e-177">Software requirements</span></span>

- <span data-ttu-id="bec1e-178">Windows Server 2016 および Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="bec1e-178">Windows Server 2016 and 2019</span></span>

- <span data-ttu-id="bec1e-179">IIS (自動インストール)</span><span class="sxs-lookup"><span data-stu-id="bec1e-179">IIS (automatically installed)</span></span>

- <span data-ttu-id="bec1e-180">Redis</span><span class="sxs-lookup"><span data-stu-id="bec1e-180">Redis</span></span>

- <span data-ttu-id="bec1e-181">Statistics Manager サービス (自動的にインストール)</span><span class="sxs-lookup"><span data-stu-id="bec1e-181">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="bec1e-182">PSExec - リモート エージェントの展開に必要</span><span class="sxs-lookup"><span data-stu-id="bec1e-182">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="bec1e-183">.NET 4.5 (2012 R2 に付属) - エージェントとサーバー側コンポーネントに必要</span><span class="sxs-lookup"><span data-stu-id="bec1e-183">.NET 4.5 (included with 2012 R2) - Required for agents and server-side components</span></span>
- <span data-ttu-id="bec1e-184">Skype [for Business Server、Real-Time Statistics Manager (64 ビット) をダウンロードする](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span><span class="sxs-lookup"><span data-stu-id="bec1e-184">Download the [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="bec1e-185">ネットワークの要件</span><span class="sxs-lookup"><span data-stu-id="bec1e-185">Networking requirements</span></span>


|<span data-ttu-id="bec1e-186">**ホスティング サーバー**</span><span class="sxs-lookup"><span data-stu-id="bec1e-186">**Hosting server**</span></span>|<span data-ttu-id="bec1e-187">**Agents**</span><span class="sxs-lookup"><span data-stu-id="bec1e-187">**Agents**</span></span>|<span data-ttu-id="bec1e-188">**リスナー**</span><span class="sxs-lookup"><span data-stu-id="bec1e-188">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bec1e-189">最小ギガビット全二重ネットワーク。</span><span class="sxs-lookup"><span data-stu-id="bec1e-189">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="bec1e-190">リスナーと通信するための送信 TCP ポート 8443 (カスタマイズ可能なポート番号)。</span><span class="sxs-lookup"><span data-stu-id="bec1e-190">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="bec1e-191">リスナーポートは、すべてのサーバーで同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="bec1e-191">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="bec1e-192">Web サイトをホストするために開いている受信 TCP ポート 80 または 443。</span><span class="sxs-lookup"><span data-stu-id="bec1e-192">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="bec1e-193">エージェントが通信するための受信 TCP ポート 8443 (カスタマイズ可能なポート番号)。</span><span class="sxs-lookup"><span data-stu-id="bec1e-193">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="bec1e-194">インストール時に、リスナーと Web サイトのファイアウォール ポートが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="bec1e-194">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="bec1e-195">エージェントの場合、インストールでは、既定で送信 TCP 接続が許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bec1e-195">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="bec1e-196">ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="bec1e-196">Hardware requirements</span></span>

<span data-ttu-id="bec1e-197">1 台のサーバーがすべてのサーバー側の Statistics Manager コンポーネントをホストするオンプレミス展開では、16 GB の RAM と 4 つの CPU を持つサーバーが、平均で 1 秒あたり約 150 サンプルをサポートできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bec1e-197">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="bec1e-198">サポートできるカウンター/エージェントの数を確認するには、次の計算を使用します。</span><span class="sxs-lookup"><span data-stu-id="bec1e-198">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="bec1e-199">各エージェントから 1 分あたり 100 台のサーバー 80 カウンター 1 サンプル \* / \* 60 秒 = 1 秒あたり 133 サンプル。</span><span class="sxs-lookup"><span data-stu-id="bec1e-199">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="bec1e-200">セキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="bec1e-200">Security considerations</span></span>
<span data-ttu-id="bec1e-201"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="bec1e-201"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="bec1e-202">サーバー間のすべてのトラフィックが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="bec1e-202">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="bec1e-203">暗号化された HTTPS トラフィックは、(既定では) ポート 8443 を経由してエージェントからリスナー サーバーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="bec1e-203">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="bec1e-204">エージェントは、サーバー上の SSL 拇印を確認して、リスナー サーバーが想定される受信者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="bec1e-204">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="bec1e-205">エージェントは(チェーン検証ではなく) 証明書の拇印検証を使用します。</span><span class="sxs-lookup"><span data-stu-id="bec1e-205">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="bec1e-206">自己署名証明書を使用する可能性が高いので、証明書の完全な検証は実行しません。</span><span class="sxs-lookup"><span data-stu-id="bec1e-206">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="bec1e-207">エージェントが満たされた後、リスナーが認証を行った後、エージェントによってパスワードが提示され、そのパスワードがリスナーによって検証されます。</span><span class="sxs-lookup"><span data-stu-id="bec1e-207">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="bec1e-208">エージェントは、接続を介してリスナーへのパフォーマンス データの送信を開始します。</span><span class="sxs-lookup"><span data-stu-id="bec1e-208">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="bec1e-209">関連情報</span><span class="sxs-lookup"><span data-stu-id="bec1e-209">For more information</span></span>
<span data-ttu-id="bec1e-210"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="bec1e-210"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="bec1e-211">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bec1e-211">For more information, see the following:</span></span>

- [<span data-ttu-id="bec1e-212">Skype for Business Server の Statistics Manager の展開</span><span class="sxs-lookup"><span data-stu-id="bec1e-212">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)

- [<span data-ttu-id="bec1e-213">Skype for Business Server の Statistics Manager のアップグレード</span><span class="sxs-lookup"><span data-stu-id="bec1e-213">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)

- [<span data-ttu-id="bec1e-214">Skype for Business Server の Statistics Manager のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="bec1e-214">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
