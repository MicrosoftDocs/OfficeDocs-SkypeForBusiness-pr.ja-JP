---
title: Skype for Business Server の Statistics Manager の計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: '概要: Skype for Business Server の統計マネージャーについては、このトピックをお読みください。'
ms.openlocfilehash: a58ca8ea8ed2d612e00a0705bb28e8d6fe95eb45
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299738"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="6c87a-103">Skype for Business Server の Statistics Manager の計画</span><span class="sxs-lookup"><span data-stu-id="6c87a-103">Plan for Statistics Manager for Skype for Business Server</span></span>

<span data-ttu-id="6c87a-104">**概要:** Skype for Business Server の統計情報マネージャーについては、こちらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c87a-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server.</span></span>

 <span data-ttu-id="6c87a-105">Skype for Business Server 統計情報マネージャーは、リアルタイムでビジネス サーバーの状態とパフォーマンス データを Skype で表示する事ができる強力なツールです。  </span><span class="sxs-lookup"><span data-stu-id="6c87a-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="6c87a-106">数秒ごとに数百のサーバーのパフォーマンス データをポーリングでき、その結果をすぐに統計情報 マネージャーのウェブ サイト上に表示することができます。</span><span class="sxs-lookup"><span data-stu-id="6c87a-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="6c87a-107">統計マネージャーを使用すると、進行中のパフォーマンスの問題を特定したり、計画された変更の結果を環境に表示したり、停止の解決などを追跡したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="6c87a-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="6c87a-108">このボックスには表示されません。統計マネージャーは、キー正常性インジケータ (KHI) のしきい値で構成され、展開の固有のニーズに合わせてカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="6c87a-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="6c87a-109">1つのサーバーがすべてのサーバー側統計情報マネージャーコンポーネントをホストするオンプレミスの展開で、統計マネージャーを展開できます。</span><span class="sxs-lookup"><span data-stu-id="6c87a-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="6c87a-110">統計マネージャーの展開について詳しくは、「 [Skype For Business Server の統計情報マネージャーの展開](deploy.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6c87a-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span> <span data-ttu-id="6c87a-111">既に統計情報マネージャーが展開されているが、2.0 にアップグレードしていない場合は、「[リリース2.0 の新機能](plan.md#BKMK_WhatsNew)」と「 [Skype for Business Server の更新統計情報マネージャー](upgrade.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c87a-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

<span data-ttu-id="6c87a-112">このトピックには次のセクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6c87a-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="6c87a-113">機能</span><span class="sxs-lookup"><span data-stu-id="6c87a-113">Features and capabilities</span></span>](plan.md#BKMK_Features)

- [<span data-ttu-id="6c87a-114">リリース2.0 の新機能</span><span class="sxs-lookup"><span data-stu-id="6c87a-114">What's new in Release 2.0</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="6c87a-115">Components</span><span class="sxs-lookup"><span data-stu-id="6c87a-115">Components</span></span>](plan.md#BKMK_Components)

- [<span data-ttu-id="6c87a-116">オンプレミスの展開</span><span class="sxs-lookup"><span data-stu-id="6c87a-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- [<span data-ttu-id="6c87a-117">要件</span><span class="sxs-lookup"><span data-stu-id="6c87a-117">Requirements</span></span>](plan.md#BKMK_Requirements)

- [<span data-ttu-id="6c87a-118">セキュリティの考慮事項</span><span class="sxs-lookup"><span data-stu-id="6c87a-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="6c87a-119">機能</span><span class="sxs-lookup"><span data-stu-id="6c87a-119">Features and capabilities</span></span>
<span data-ttu-id="6c87a-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="6c87a-120"></span></span>

<span data-ttu-id="6c87a-121">統計情報マネージャーでは、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="6c87a-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="6c87a-122">すべてのサーバーの生データをリアルタイムで表示します。</span><span class="sxs-lookup"><span data-stu-id="6c87a-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="6c87a-123">(データは、非常に高い料金でサンプリングされ、1秒未満で web サイトに送信されます)。</span><span class="sxs-lookup"><span data-stu-id="6c87a-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="6c87a-124">特定の役割に対して集計されたデータを表示する。たとえば、フロントエンドサーバー、仲介サーバー、エッジサーバーなどです。</span><span class="sxs-lookup"><span data-stu-id="6c87a-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="6c87a-125">ドリルダウンして、特定のサイトのデータ、サイト内の特定のプール、プール内の特定のサーバーのデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="6c87a-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="6c87a-126">ユーザー設定のグラフを作成して、選択したカウンターが既定で表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="6c87a-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="6c87a-127">X 軸と y 軸の両方、または x 軸のどちらでもズームとパンを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6c87a-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="6c87a-128">データをフィルター処理するには、日付の範囲またはポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="6c87a-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="6c87a-129">確立されたキー正常性インジケーター (KHIs) に基づいてサーバーのパフォーマンスを表示します。</span><span class="sxs-lookup"><span data-stu-id="6c87a-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="6c87a-130">KHIs は、定義済みの正常な範囲を持つパフォーマンスカウンターのコレクションを表しています。</span><span class="sxs-lookup"><span data-stu-id="6c87a-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="6c87a-131">各カウンターの詳細なメトリックを表示します。</span><span class="sxs-lookup"><span data-stu-id="6c87a-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="6c87a-132">複数の人口またはサーバー間でデータを比較します。</span><span class="sxs-lookup"><span data-stu-id="6c87a-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="6c87a-133">潜在カウンターレポートを表示して、現在のデータがダッシュボードサービスに報告されていないエージェントを特定します。</span><span class="sxs-lookup"><span data-stu-id="6c87a-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="6c87a-134">グラフデータの特定のインスタンスをファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="6c87a-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="6c87a-135">最新情報を含む、リアルタイムで表示します。</span><span class="sxs-lookup"><span data-stu-id="6c87a-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="6c87a-136">[履歴] ビューが有効になっている場合は、新しいエラーのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c87a-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="6c87a-137">すべての KHIs を一度に表示する</span><span class="sxs-lookup"><span data-stu-id="6c87a-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="6c87a-138">サーバーのビューを表示する (横ビュー)</span><span class="sxs-lookup"><span data-stu-id="6c87a-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="6c87a-139">KHI 定義の表示</span><span class="sxs-lookup"><span data-stu-id="6c87a-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-20"></a><span data-ttu-id="6c87a-140">リリース2.0 の新機能</span><span class="sxs-lookup"><span data-stu-id="6c87a-140">What's new in Release 2.0</span></span>
<span data-ttu-id="6c87a-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="6c87a-141"></span></span>

<span data-ttu-id="6c87a-142">ここでは、リリース2.0 の新機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="6c87a-142">The following describes what's new in Release 2.0.</span></span> <span data-ttu-id="6c87a-143">まだインストールしていない統計マネージャーがある場合は、「 [Skype For Business Server のアップグレード統計情報マネージャー](upgrade.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c87a-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

- <span data-ttu-id="6c87a-144">[シナリオ] ビューは、Edge メディア、ファブリック正常性、プールフェールオーバー、登録シナリオ用に追加されています。</span><span class="sxs-lookup"><span data-stu-id="6c87a-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="6c87a-145">SQL server、Skype for Business の利用状況カウンターなど、多くの新しいカウンターが追加されました。</span><span class="sxs-lookup"><span data-stu-id="6c87a-145">Many new counters have been added for SQL servers, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="6c87a-146">詳細マネージャーエージェントに対するウォッチャーノードの統合-エージェントがウォッチャーノードにインストールされている場合は、代理トランザクションの統計情報をカウンターとして統計マネージャーに報告します。</span><span class="sxs-lookup"><span data-stu-id="6c87a-146">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="6c87a-147">さまざまな信頼性とパフォーマンスの向上。</span><span class="sxs-lookup"><span data-stu-id="6c87a-147">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="6c87a-148">実行している統計マネージャーの Web サイトのバージョンを確認するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6c87a-148">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="6c87a-149">エクスプローラーで、(既定のディレクトリ) C:\Program Files\Skype for Business Server StatsMan WebSite\bin を開きます。</span><span class="sxs-lookup"><span data-stu-id="6c87a-149">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="6c87a-150">StatsManHubWebSite を右クリックしてプロパティを表示する</span><span class="sxs-lookup"><span data-stu-id="6c87a-150">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="6c87a-151">製品のバージョンは [説明] の詳細に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c87a-151">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="6c87a-152">Components</span><span class="sxs-lookup"><span data-stu-id="6c87a-152">Components</span></span>
<span data-ttu-id="6c87a-153"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="6c87a-153"></span></span>

<span data-ttu-id="6c87a-154">統計マネージャーは、次のコンポーネントで構成されています。</span><span class="sxs-lookup"><span data-stu-id="6c87a-154">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="6c87a-155">**エージェント.**</span><span class="sxs-lookup"><span data-stu-id="6c87a-155">**Agent.**</span></span> <span data-ttu-id="6c87a-156">各監視対象サーバー上で実行される簡易エージェント。</span><span class="sxs-lookup"><span data-stu-id="6c87a-156">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="6c87a-157">エージェントでは、ローカル集計を使用して、構成可能な高料金のパフォーマンスカウンターのポーリングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6c87a-157">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="6c87a-158">**リスナー.**</span><span class="sxs-lookup"><span data-stu-id="6c87a-158">**Listener.**</span></span> <span data-ttu-id="6c87a-159">すべてのエージェントからデータを受信し、人口を通じてデータを集計するサーバー側 API。</span><span class="sxs-lookup"><span data-stu-id="6c87a-159">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="6c87a-160">**Bh1.**</span><span class="sxs-lookup"><span data-stu-id="6c87a-160">**Hub.**</span></span> <span data-ttu-id="6c87a-161">は、システムのクライアント API として機能し、web サーバー上で実行され、web サイト経由で接続されたクライアントに対してリアルタイムのデータ更新を提供します。</span><span class="sxs-lookup"><span data-stu-id="6c87a-161">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="6c87a-162">(ハブは、Web サイト msi の一部として自動的にインストールされます。)</span><span class="sxs-lookup"><span data-stu-id="6c87a-162">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="6c87a-163">**当.**</span><span class="sxs-lookup"><span data-stu-id="6c87a-163">**Website.**</span></span> <span data-ttu-id="6c87a-164">システムで利用可能なすべての機能を1つにまとめたユーザーインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6c87a-164">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="6c87a-165">さらに、統計マネージャーには、メモリ内キャッシュ用のオープンソースデータ構造サーバーである**Redis**が必要です。</span><span class="sxs-lookup"><span data-stu-id="6c87a-165">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="6c87a-166">Redis のダウンロードについて詳しくは、「[統計マネージャーの展開](deploy.md#BKMK_Deploy)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6c87a-166">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="6c87a-167">オンプレミスの展開</span><span class="sxs-lookup"><span data-stu-id="6c87a-167">On-premises deployment</span></span>
<span data-ttu-id="6c87a-168"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="6c87a-168"></span></span>

<span data-ttu-id="6c87a-169">オンプレミスの展開では、1つのサーバーがすべてのサーバー側統計情報マネージャーコンポーネントをホストします。</span><span class="sxs-lookup"><span data-stu-id="6c87a-169">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="6c87a-170">次の図は、統計マネージャーの Web サイト、ハブ、リスナー、および Redis Cache システムが1台のコンピューターにホストされているオンプレミスの展開を示しています。</span><span class="sxs-lookup"><span data-stu-id="6c87a-170">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="6c87a-171">統計マネージャーは、3つの Skype for Business サーバーを監視しています。各サーバーでは、1つのエージェントがリスナーにデータを送信します。</span><span class="sxs-lookup"><span data-stu-id="6c87a-171">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="6c87a-172">ユーザーは1つの Web サイトに接続して、統計情報マネージャーで集計されたすべてのデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="6c87a-172">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![Stats Manager のオンプレミス展開](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="6c87a-174">要件</span><span class="sxs-lookup"><span data-stu-id="6c87a-174">Requirements</span></span>
<span data-ttu-id="6c87a-175"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="6c87a-175"></span></span>

<span data-ttu-id="6c87a-176">統計情報管理を展開するには、次のソフトウェア、ネットワーキング、およびハードウェアの要件を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c87a-176">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="6c87a-177">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="6c87a-177">Software requirements</span></span>

- <span data-ttu-id="6c87a-178">Windows Server 2016 および2019</span><span class="sxs-lookup"><span data-stu-id="6c87a-178">Windows Server 2016 and 2019</span></span>

- <span data-ttu-id="6c87a-179">IIS (自動的にインストールされる)</span><span class="sxs-lookup"><span data-stu-id="6c87a-179">IIS (automatically installed)</span></span>

- <span data-ttu-id="6c87a-180">Redis</span><span class="sxs-lookup"><span data-stu-id="6c87a-180">Redis</span></span>

- <span data-ttu-id="6c87a-181">統計マネージャーサービス (自動的にインストールされる)</span><span class="sxs-lookup"><span data-stu-id="6c87a-181">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="6c87a-182">PSExec-リモートエージェントの展開に必要</span><span class="sxs-lookup"><span data-stu-id="6c87a-182">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="6c87a-183">.NET 4.5 (2012 R2 に含まれています)-エージェントおよびサーバー側コンポーネントに必要</span><span class="sxs-lookup"><span data-stu-id="6c87a-183">.NET 4.5 (included with 2012 R2) - Required for agents and server-side components</span></span>
- <span data-ttu-id="6c87a-184">[Skype For Business Server のリアルタイム統計マネージャー (64 ビット) を](https://www.microsoft.com/en-in/download/details.aspx?id=57518)ダウンロードする</span><span class="sxs-lookup"><span data-stu-id="6c87a-184">Download the [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="6c87a-185">ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="6c87a-185">Networking requirements</span></span>


|<span data-ttu-id="6c87a-186">**ホスティングサーバー**</span><span class="sxs-lookup"><span data-stu-id="6c87a-186">**Hosting server**</span></span>|<span data-ttu-id="6c87a-187">**エージェント**</span><span class="sxs-lookup"><span data-stu-id="6c87a-187">**Agents**</span></span>|<span data-ttu-id="6c87a-188">**リスナー**</span><span class="sxs-lookup"><span data-stu-id="6c87a-188">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6c87a-189">最小ギガビット全二重ネットワーク。</span><span class="sxs-lookup"><span data-stu-id="6c87a-189">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="6c87a-190">リスナーと通信するための送信 TCP ポート 8443 (カスタマイズ可能なポート番号)。</span><span class="sxs-lookup"><span data-stu-id="6c87a-190">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="6c87a-191">リスナーポートは、すべてのサーバーで同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c87a-191">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="6c87a-192">受信 TCP ポート80または443は、web サイトをホストするために開かれます。</span><span class="sxs-lookup"><span data-stu-id="6c87a-192">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="6c87a-193">エージェントと通信するための受信 TCP ポート 8443 (カスタマイズ可能なポート番号)。</span><span class="sxs-lookup"><span data-stu-id="6c87a-193">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="6c87a-194">インストール時に、リスナーと Web サイトのファイアウォールポートが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="6c87a-194">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="6c87a-195">エージェントの場合、インストールでは、発信 TCP 接続が既定で許可されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="6c87a-195">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="6c87a-196">ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="6c87a-196">Hardware requirements</span></span>

<span data-ttu-id="6c87a-197">オンプレミスの展開では、1つのサーバーがサーバー側の統計情報マネージャーのすべてのコンポーネントをホストするため、16 GB の RAM を搭載したサーバーでは、1秒あたり平均で150のサンプルについてサポートを受けることができます。</span><span class="sxs-lookup"><span data-stu-id="6c87a-197">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="6c87a-198">サポートできるカウンター/エージェントの数を確認するには、次の計算を実行します。</span><span class="sxs-lookup"><span data-stu-id="6c87a-198">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="6c87a-199">100 server \*80 カウンター \* 1 (各エージェントからの1分あたりのカウンター 1/60 秒 = ~ 133 サンプル/秒)。</span><span class="sxs-lookup"><span data-stu-id="6c87a-199">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="6c87a-200">セキュリティの考慮事項</span><span class="sxs-lookup"><span data-stu-id="6c87a-200">Security considerations</span></span>
<span data-ttu-id="6c87a-201"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="6c87a-201"></span></span>

<span data-ttu-id="6c87a-202">サーバー間のすべてのトラフィックが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="6c87a-202">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="6c87a-203">暗号化された HTTPS トラフィックは、エージェントからリスナーサーバーにポート 8443 (既定) 経由で送信されます。</span><span class="sxs-lookup"><span data-stu-id="6c87a-203">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="6c87a-204">エージェントは、サーバー上の SSL 拇印を確認し、リスナーサーバーが想定される受信者であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6c87a-204">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="6c87a-205">エージェントが (チェーンの検証ではなく) 証明書の拇印の検証を使用することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6c87a-205">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="6c87a-206">自己署名証明書を使用することが可能なため、証明書の完全な検証は行いません。</span><span class="sxs-lookup"><span data-stu-id="6c87a-206">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="6c87a-207">エージェントが処理されると、リスナーは本物であるため、リスナーによって確認されたパスワードがエージェントによって表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c87a-207">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="6c87a-208">エージェントは、リスナーへの接続を介してパフォーマンスデータの転送を開始します。</span><span class="sxs-lookup"><span data-stu-id="6c87a-208">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="6c87a-209">関連情報</span><span class="sxs-lookup"><span data-stu-id="6c87a-209">For more information</span></span>
<span data-ttu-id="6c87a-210"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="6c87a-210"></span></span>

<span data-ttu-id="6c87a-211">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c87a-211">For more information, see the following:</span></span>

- [<span data-ttu-id="6c87a-212">Skype for Business Server の Statistics Manager の展開</span><span class="sxs-lookup"><span data-stu-id="6c87a-212">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)

- [<span data-ttu-id="6c87a-213">Skype for Business Server の Statistics Manager のアップグレード</span><span class="sxs-lookup"><span data-stu-id="6c87a-213">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)

- [<span data-ttu-id="6c87a-214">Skype for Business Server の Statistics Manager のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="6c87a-214">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
