---
title: Azure Monitor を使用して Microsoft Teams Rooms 管理をデプロイする
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: この記事では、Azure Monitor を使用して、Microsoft Teams ミーティング デバイスの管理を、統合されたエンドツーエンドの方法でデプロイする方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7046fc0010a4337ea14854e356600ccf3428f9d0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117595"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a><span data-ttu-id="fa677-103">を使用 :::no-loc text="Microsoft Teams Rooms"::: して管理をデプロイする :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="fa677-103">Deploy :::no-loc text="Microsoft Teams Rooms"::: management with :::no-loc text="Azure Monitor":::</span></span>

<span data-ttu-id="fa677-104">この記事では、 を使用してデバイスの統合されたエンドツーエンド管理を設定およびデプロイする方法 :::no-loc text="Microsoft Teams Rooms"::: について説明します :::no-loc text="Azure Monitor"::: 。</span><span class="sxs-lookup"><span data-stu-id="fa677-104">This article discusses how to set up and deploy integrated, end-to-end management of :::no-loc text="Microsoft Teams Rooms"::: devices by using :::no-loc text="Azure Monitor":::.</span></span>

<span data-ttu-id="fa677-105">内を構成 :::no-loc text="Log Analytics"::: して、会議室デバイスの管理に役立つ基本的な :::no-loc text="Azure Monitor"::: テレメトリとアラート :::no-loc text="Microsoft Teams Rooms"::: を提供できます。</span><span class="sxs-lookup"><span data-stu-id="fa677-105">You can configure :::no-loc text="Log Analytics"::: within :::no-loc text="Azure Monitor"::: to provide basic telemetry and alerts that will help you manage :::no-loc text="Microsoft Teams Rooms"::: meeting room devices.</span></span> <span data-ttu-id="fa677-106">管理ソリューションの成熟に合わせ、追加のデータと管理機能をデプロイして、デバイスの可用性とパフォーマンスの詳細なビューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="fa677-106">As your management solution matures, you might decide to deploy additional data and management capabilities to create a more detailed view of device availability and performance.</span></span>

<span data-ttu-id="fa677-107">このガイドに従って、次の例のようなダッシュボードを使用して、デバイスの可用性、アプリケーションとハードウェアの正常性、アプリケーションとオペレーティング システムのバージョンの配布に関する詳細な状態レポート :::no-loc text="Microsoft Teams Rooms"::: を取得できます。</span><span class="sxs-lookup"><span data-stu-id="fa677-107">By following this guide, you can use a dashboard like the following example to get detailed status reporting for device availability, application and hardware health, and :::no-loc text="Microsoft Teams Rooms"::: application and operating system version distribution.</span></span>

<span data-ttu-id="fa677-108">![サンプルの Log Analytics ビューのスクリーンショット (Microsoft Teams ミーティング](../media/Deploy-Azure-Monitor-1.png "サンプル Log Analytics ビュー (Microsoft Teams ミーティング")</span><span class="sxs-lookup"><span data-stu-id="fa677-108">![Screenshot of sample Log Analytics view for Microsoft Teams Rooms](../media/Deploy-Azure-Monitor-1.png "Sample Log Analytics view for Microsoft Teams Rooms")</span></span>

<span data-ttu-id="fa677-109">高いレベルでは、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa677-109">At a high level, you need to perform the following tasks:</span></span>


1. [<span data-ttu-id="fa677-110">構成の :::no-loc text="Log Analytics"::: 検証</span><span class="sxs-lookup"><span data-stu-id="fa677-110">Validate :::no-loc text="Log Analytics"::: configuration</span></span>](azure-monitor-deploy.md#validate_LogAnalytics)
2. [<span data-ttu-id="fa677-111">管理セットアップ用にテスト デバイス :::no-loc text="Log Analytics"::: を構成する</span><span class="sxs-lookup"><span data-stu-id="fa677-111">Configure test devices for :::no-loc text="Log Analytics"::: management setup</span></span>](azure-monitor-deploy.md#configure_test_devices)
3. [<span data-ttu-id="fa677-112">カスタム フィールドをマップする</span><span class="sxs-lookup"><span data-stu-id="fa677-112">Map custom fields</span></span>](azure-monitor-deploy.md#Custom_fields)
4. [<span data-ttu-id="fa677-113">でビュー :::no-loc text="Microsoft Teams Rooms"::: を定義する :::no-loc text="Log Analytics":::</span><span class="sxs-lookup"><span data-stu-id="fa677-113">Define the :::no-loc text="Microsoft Teams Rooms"::: views in :::no-loc text="Log Analytics":::</span></span>](azure-monitor-deploy.md#Define_Views)
5. [<span data-ttu-id="fa677-114">アラートを定義する</span><span class="sxs-lookup"><span data-stu-id="fa677-114">Define alerts</span></span>](azure-monitor-deploy.md#Alerts)
6. [<span data-ttu-id="fa677-115">監視用にすべてのデバイスを構成する</span><span class="sxs-lookup"><span data-stu-id="fa677-115">Configure all devices for Monitoring</span></span>](azure-monitor-deploy.md#configure_all_devices)
7. [<span data-ttu-id="fa677-116">その他のソリューションを :::no-loc text="Azure Monitor"::: 構成する</span><span class="sxs-lookup"><span data-stu-id="fa677-116">Configure additional :::no-loc text="Azure Monitor"::: solutions</span></span>](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> <span data-ttu-id="fa677-117">最小限の構成では、オペレーティング システムを実行しているコンピューターを監視することができますが、すべてのデバイスへのエージェントのデプロイを開始する前に実行する必要があるいくつかの具体的な手順がまだ :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: :::no-loc text="Windows"::: :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Microsoft Teams Rooms"::: 存在します。</span><span class="sxs-lookup"><span data-stu-id="fa677-117">Although with minimal configuration, :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: can monitor a computer running a :::no-loc text="Windows"::: operating system, there are still some :::no-loc text="Microsoft Teams Rooms":::–specific steps that you need to take before you start deploying agents to all :::no-loc text="Microsoft Teams Rooms"::: devices.</span></span>
> <span data-ttu-id="fa677-118">そのため、制御されたセットアップと構成に対して、すべての構成手順を適切な順序で実行することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fa677-118">Therefore, we highly recommend you perform all configuration steps in the right order for a controlled setup and configuration.</span></span> <span data-ttu-id="fa677-119">結果の品質は、初期構成の品質によって大きな違いがあります。</span><span class="sxs-lookup"><span data-stu-id="fa677-119">The quality of the end result very much depends on the quality of the initial configuration.</span></span>

## <a name="validate-no-loc-textlog-analytics-configuration"></a><span data-ttu-id="fa677-120">構成の :::no-loc text="Log Analytics"::: 検証</span><span class="sxs-lookup"><span data-stu-id="fa677-120">Validate :::no-loc text="Log Analytics"::: configuration</span></span>
<span data-ttu-id="fa677-121"><a name="validate_LogAnalytics"> </a></span><span class="sxs-lookup"><span data-stu-id="fa677-121"><a name="validate_LogAnalytics"> </a></span></span>

<span data-ttu-id="fa677-122">デバイスからログの収集 :::no-loc text="Log Analytics"::: を開始するには、ワークスペースが必要 :::no-loc text="Microsoft Teams Rooms"::: です。</span><span class="sxs-lookup"><span data-stu-id="fa677-122">You need to have a :::no-loc text="Log Analytics"::: workspace to start collecting logs from :::no-loc text="Microsoft Teams Rooms"::: devices.</span></span> <span data-ttu-id="fa677-123">ワークスペースは、独自の :::no-loc text="Log Analytics"::: データ リポジトリ、データ ソース、ソリューションを備える一意の環境です。</span><span class="sxs-lookup"><span data-stu-id="fa677-123">A workspace is a unique :::no-loc text="Log Analytics"::: environment with its own data repository, data sources, and solutions.</span></span> <span data-ttu-id="fa677-124">既存のワークスペースが既に存在する場合は、それを使用してデプロイを監視するか、または監視ニーズに固有の専用ワークスペース :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Log Analytics"::: を :::no-loc text="Microsoft Teams Rooms"::: 作成できます。</span><span class="sxs-lookup"><span data-stu-id="fa677-124">If you already have an existing :::no-loc text="Log Analytics"::: workspace, you might use it to monitor your :::no-loc text="Microsoft Teams Rooms"::: deployment or alternatively, you can create a dedicated :::no-loc text="Log Analytics"::: workspace specific to your :::no-loc text="Microsoft Teams Rooms"::: monitoring needs.</span></span>

<span data-ttu-id="fa677-125">新しいワークスペースを作成する必要がある場合は、「ポータルでワークスペースを作成する」の :::no-loc text="Log Analytics"::: [ :::no-loc text="Log Analytics"::: 手順に従 :::no-loc text="Azure"::: ってください。](/azure/azure-monitor/learn/quick-create-workspace)</span><span class="sxs-lookup"><span data-stu-id="fa677-125">If you need to create a new :::no-loc text="Log Analytics"::: workspace, follow the instructions in the article [Create a :::no-loc text="Log Analytics"::: workspace in the :::no-loc text="Azure"::: portal](/azure/azure-monitor/learn/quick-create-workspace)</span></span>

> [!NOTE]
> <span data-ttu-id="fa677-126">で使用 :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor"::: するには、アクティブなサブスクリプションが必要 :::no-loc text="Azure"::: です。</span><span class="sxs-lookup"><span data-stu-id="fa677-126">To use :::no-loc text="Log Analytics"::: with :::no-loc text="Azure Monitor":::, you need to have an active :::no-loc text="Azure"::: subscription.</span></span> <span data-ttu-id="fa677-127">サブスクリプションをお持ちでない :::no-loc text="Azure"::: 場合は、開始点として[](https://azure.microsoft.com/free)無料試用版サブスクリプションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="fa677-127">If you don't have an :::no-loc text="Azure"::: subscription, you can create [a free trial subscription](https://azure.microsoft.com/free) as a starting point.</span></span>

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a><span data-ttu-id="fa677-128">イベント :::no-loc text="Log Analytics"::: ログを収集 :::no-loc text="Microsoft Teams Rooms"::: する構成</span><span class="sxs-lookup"><span data-stu-id="fa677-128">Configure :::no-loc text="Log Analytics"::: to collect :::no-loc text="Microsoft Teams Rooms"::: event logs</span></span>

<span data-ttu-id="fa677-129">:::no-loc text="Log Analytics"::: 設定で指定されているイベント :::no-loc text="Windows"::: ログからのイベントのみを収集します。</span><span class="sxs-lookup"><span data-stu-id="fa677-129">:::no-loc text="Log Analytics"::: only collects events from the :::no-loc text="Windows"::: event logs that are specified in the settings.</span></span> <span data-ttu-id="fa677-130">ログごとに、選択した重大度のイベントだけが収集されます。</span><span class="sxs-lookup"><span data-stu-id="fa677-130">For each log, only the events with the selected severities are collected.</span></span>

<span data-ttu-id="fa677-131">デバイスとアプリケーションの :::no-loc text="Log Analytics"::: 状態を監視するために必要なログを収集するために :::no-loc text="Microsoft Teams Rooms"::: 構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa677-131">You need to configure :::no-loc text="Log Analytics"::: to collect the logs required to monitor :::no-loc text="Microsoft Teams Rooms"::: device and application status.</span></span> <span data-ttu-id="fa677-132">:::no-loc text="Microsoft Teams Rooms"::: デバイスはイベント ログ **:::no-loc text="Skype Room System":::** を使用します。</span><span class="sxs-lookup"><span data-stu-id="fa677-132">:::no-loc text="Microsoft Teams Rooms"::: devices use the **:::no-loc text="Skype Room System":::** event log.</span></span>

<span data-ttu-id="fa677-133">イベントを :::no-loc text="Log Analytics"::: 収集するために構成 :::no-loc text="Microsoft Teams Rooms"::: するには、 の[ :::no-loc text="Windows"::: イベント ログ データ :::no-loc text="Azure Monitor"::: ソースに関するページを参照してください。](/azure/azure-monitor/platform/data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="fa677-133">To configure :::no-loc text="Log Analytics"::: to collect the :::no-loc text="Microsoft Teams Rooms"::: events, see [:::no-loc text="Windows"::: event log data sources in :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/data-sources-windows-events)</span></span>

<span data-ttu-id="fa677-134">![イベント ログ設定のスクリーンショット](../media/Deploy-Azure-Monitor-2.png "イベント ログの設定")</span><span class="sxs-lookup"><span data-stu-id="fa677-134">![Screenshot of event log settings](../media/Deploy-Azure-Monitor-2.png "Event log settings")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa677-135">イベント ログの設定を構成し、イベント ログ名として「」と入力し、[エラー]、[警告]、および [情報] :::no-loc text="Windows"::: **:::no-loc text="Skype Room System":::** チェック ボックスをオンにします。   </span><span class="sxs-lookup"><span data-stu-id="fa677-135">Configure :::no-loc text="Windows"::: Event Log settings and enter **:::no-loc text="Skype Room System":::** as event log name, and then select the **Error**, **Warning**, and **Information** check boxes.</span></span>

## <a name="configure-test-devices-for-azure-monitoring"></a><span data-ttu-id="fa677-136">Azure Monitoring のテスト デバイスを構成する</span><span class="sxs-lookup"><span data-stu-id="fa677-136">Configure test devices for Azure Monitoring</span></span>
<span data-ttu-id="fa677-137"><a name="configure_test_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="fa677-137"><a name="configure_test_devices"> </a></span></span>

<span data-ttu-id="fa677-138">関連するイベント :::no-loc text="Log Analytics"::: を監視できる状態 :::no-loc text="Microsoft Teams Rooms"::: を準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa677-138">You need to prepare :::no-loc text="Log Analytics"::: to be able to monitor :::no-loc text="Microsoft Teams Rooms":::–related events.</span></span> <span data-ttu-id="fa677-139">最初に、物理的にアクセスできる 1 台または 2 台のデバイスにエージェントをデプロイし、それらのテスト デバイスにデータを生成してワークスペースにプッシュする :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: 必要 :::no-loc text="Log Analytics"::: があります。</span><span class="sxs-lookup"><span data-stu-id="fa677-139">To start with, you need to deploy :::no-loc text="Microsoft Monitoring"::: agents to just one or two :::no-loc text="Microsoft Teams Rooms"::: devices that you have physical access to, and get those test devices generate some data and push it to the :::no-loc text="Log Analytics"::: workspace.</span></span>

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a><span data-ttu-id="fa677-140">エージェント :::no-loc text="Microsoft Monitoring"::: をインストールしてデバイスをテストする</span><span class="sxs-lookup"><span data-stu-id="fa677-140">Install :::no-loc text="Microsoft Monitoring"::: agents to test devices</span></span>

<span data-ttu-id="fa677-141">エージェントをテスト デバイスにデプロイするには、次のコンピューターに関するページに記載Connectを使用して :::no-loc text="Microsoft Monitoring"::: [、 :::no-loc text="Windows"::: :::no-loc text="Log Analytics"::: のサービスにデプロイします :::no-loc text="Azure"::: ](/azure/azure-monitor/platform/agent-windows)。</span><span class="sxs-lookup"><span data-stu-id="fa677-141">Deploy the :::no-loc text="Microsoft Monitoring"::: agent to the test devices by using the instructions provided in [Connect :::no-loc text="Windows"::: computers to the :::no-loc text="Log Analytics"::: service in :::no-loc text="Azure":::](/azure/azure-monitor/platform/agent-windows).</span></span> <span data-ttu-id="fa677-142">この記事では、エージェントをデプロイする手順について詳しく説明します。ワークスペース ID _ と _ 主キー :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Windows"::: :::no-loc text="Log Analytics":::  \* \*\*\* :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: を取得してデプロイに接続するデバイスを取得する手順と、インスタンスへのエージェント接続を確認する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="fa677-142">This article provides detailed information about the steps for deploying :::no-loc text="Microsoft Monitoring"::: Agent for :::no-loc text="Windows":::, instructions for obtaining the :::no-loc text="Log Analytics"::: ***Workspace ID** _ and the _ *_primary key_** to get :::no-loc text="Microsoft Teams Rooms"::: devices connected to your :::no-loc text="Azure Monitor"::: deployment, and steps to verify agent connectivity to :::no-loc text="Log Analytics"::: instance.</span></span>

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a><span data-ttu-id="fa677-143">サンプル イベントを生成 :::no-loc text="Microsoft Teams Rooms"::: する</span><span class="sxs-lookup"><span data-stu-id="fa677-143">Generate sample :::no-loc text="Microsoft Teams Rooms"::: events</span></span>

<span data-ttu-id="fa677-144">エージェントを :::no-loc text="Microsoft Monitoring"::: テスト デバイスにデプロイした後、必要なイベント ログ データが によって収集されるのを確認します :::no-loc text="Azure Monitor"::: 。</span><span class="sxs-lookup"><span data-stu-id="fa677-144">After the :::no-loc text="Microsoft Monitoring"::: agent is deployed onto the test devices, verify that the required event log data is collected by :::no-loc text="Azure Monitor":::.</span></span>

> [!NOTE]
> <span data-ttu-id="fa677-145">エージェントのインストール後にデバイスを再起動し、会議アプリが開始され、イベント ログに新しいイベントを生成できるよう :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: します。</span><span class="sxs-lookup"><span data-stu-id="fa677-145">Reboot the device after the installation of the :::no-loc text="Microsoft Monitoring"::: agent, and make sure that :::no-loc text="Microsoft Teams Rooms"::: Meeting app is started, so that it can generate new events into the Event Log.</span></span>

1.  <span data-ttu-id="fa677-146">ポータルにサインイン[ :::no-loc text="Microsoft Azure"::: し、 に](https://portal.azure.com)移動して :::no-loc text="Log Analytics"::: ワークスペースを選択します。</span><span class="sxs-lookup"><span data-stu-id="fa677-146">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2.  <span data-ttu-id="fa677-147">デバイスによって生成されたハートビート イベントを一覧表示 :::no-loc text="Microsoft Teams Rooms"::: します。</span><span class="sxs-lookup"><span data-stu-id="fa677-147">List the heartbeat events generated by a :::no-loc text="Microsoft Teams Rooms"::: device:</span></span>
    1.  <span data-ttu-id="fa677-148">ワークスペースを選択し、[ログ] **に移動** し、クエリを使用して、 のカスタム フィールドを持つハートビート レコードを取得します :::no-loc text="Microsoft Teams Rooms"::: 。</span><span class="sxs-lookup"><span data-stu-id="fa677-148">Select your workspace and go to **Logs** and use a query to retrieve the heartbeat records that will have the custom fields for :::no-loc text="Microsoft Teams Rooms":::.</span></span>
    2.  <span data-ttu-id="fa677-149">サンプル クエリ: `Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="fa677-149">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3.  <span data-ttu-id="fa677-150">クエリが、会議アプリによって生成されたイベントを含むログ レコードを返す :::no-loc text="Microsoft Teams Rooms"::: 必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa677-150">Make sure that the query returns log records that include events generated by the :::no-loc text="Microsoft Teams Rooms"::: meetings app.</span></span>

4.  <span data-ttu-id="fa677-151">ハードウェアの問題を生成し、必要なイベントが に記録されるのを検証します :::no-loc text="Azure Log Analytics"::: 。</span><span class="sxs-lookup"><span data-stu-id="fa677-151">Generate a hardware issue, and validate that the required events are logged in :::no-loc text="Azure Log Analytics":::.</span></span>
    1.  <span data-ttu-id="fa677-152">テスト システムの周辺機器の 1 つを取り外 :::no-loc text="Microsoft Teams Rooms"::: します。</span><span class="sxs-lookup"><span data-stu-id="fa677-152">Unplug one of the peripheral devices on the test :::no-loc text="Microsoft Teams Rooms"::: system.</span></span> <span data-ttu-id="fa677-153">カメラ、スピーカーフォン、マイク、フロント ルーム ディスプレイなどです。</span><span class="sxs-lookup"><span data-stu-id="fa677-153">This could be the camera, speakerphone, microphone, or Front Room Display</span></span>
    2.  <span data-ttu-id="fa677-154">イベント ログが に設定されるのを 10 分待ちます :::no-loc text="Azure Log Analytics"::: 。</span><span class="sxs-lookup"><span data-stu-id="fa677-154">Wait 10 minutes for the event log to be populated in :::no-loc text="Azure Log Analytics":::.</span></span>
    3.  <span data-ttu-id="fa677-155">クエリを使用してハードウェア エラー イベントを一覧表示します。 `Event | where Source == "SRS-App" and EventID == 3001`</span><span class="sxs-lookup"><span data-stu-id="fa677-155">Use a query to list hardware error events: `Event | where Source == "SRS-App" and EventID == 3001`</span></span>

5.  <span data-ttu-id="fa677-156">アプリケーションの問題を生成し、必要なイベントがログに記録されるのを検証します。</span><span class="sxs-lookup"><span data-stu-id="fa677-156">Generate an application issue, and validate that the required events are logged.</span></span>
    1.  <span data-ttu-id="fa677-157">アプリケーション :::no-loc text="Microsoft Teams Rooms"::: の構成を変更し、正しくないセッション開始プロトコル (SIP) アドレスとパスワードのペアを入力します。</span><span class="sxs-lookup"><span data-stu-id="fa677-157">Modify :::no-loc text="Microsoft Teams Rooms"::: application configuration, and type an incorrect Session Initiation Protocol (SIP) address/password pair.</span></span>
    2.  <span data-ttu-id="fa677-158">イベント ログが に設定されるのを 10 分待ちます :::no-loc text="Azure Log Analytics"::: 。</span><span class="sxs-lookup"><span data-stu-id="fa677-158">Wait 10 minutes for the event log to be populated in :::no-loc text="Azure Log Analytics":::.</span></span>
    3.  <span data-ttu-id="fa677-159">クエリを使用して、アプリケーション エラー イベントを一覧表示します。 `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span><span class="sxs-lookup"><span data-stu-id="fa677-159">Use a query to list application error events: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa677-160">これらのサンプル イベント ログは、カスタム フィールドを構成する前に必要です。</span><span class="sxs-lookup"><span data-stu-id="fa677-160">These sample event logs are required before custom fields can be configured.</span></span> <span data-ttu-id="fa677-161">必要なイベント ログを収集するまで、次の手順に進む必要はありません。</span><span class="sxs-lookup"><span data-stu-id="fa677-161">Don't proceed to the next step until you have collected the required event logs.</span></span>

## <a name="map-custom-fields"></a><span data-ttu-id="fa677-162">カスタム フィールドをマップする</span><span class="sxs-lookup"><span data-stu-id="fa677-162">Map custom fields</span></span>
<span data-ttu-id="fa677-163"><a name="Custom_fields"> </a></span><span class="sxs-lookup"><span data-stu-id="fa677-163"><a name="Custom_fields"> </a></span></span>

<span data-ttu-id="fa677-164">カスタム フィールドを使用して、イベント ログから特定のデータを抽出します。</span><span class="sxs-lookup"><span data-stu-id="fa677-164">You use custom fields to extract specific data from the event logs.</span></span> <span data-ttu-id="fa677-165">後でタイル、ダッシュボード ビュー、アラートで使用するカスタム フィールドを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa677-165">You need to define custom fields that will be used later with your tiles, dashboard views, and alerts.</span></span> <span data-ttu-id="fa677-166">カスタム[フィールドの :::no-loc text="Log Analytics"::: 作成を開始](/azure/azure-monitor/platform/custom-fields)する前に、「カスタム フィールド」を参照し、概念を理解してください。</span><span class="sxs-lookup"><span data-stu-id="fa677-166">See [Custom fields in :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/custom-fields) and become familiar with the concepts before you start creating your custom fields.</span></span>

<span data-ttu-id="fa677-167">キャプチャしたイベント ログからカスタム フィールドを抽出するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="fa677-167">To extract your custom fields out of the captured event logs, follow these steps:</span></span>

1.  <span data-ttu-id="fa677-168">ポータルにサインイン[ :::no-loc text="Microsoft Azure"::: し、 に](https://portal.azure.com)移動して :::no-loc text="Log Analytics"::: ワークスペースを選択します。</span><span class="sxs-lookup"><span data-stu-id="fa677-168">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2. <span data-ttu-id="fa677-169">デバイスによって生成されたイベントを一覧表示 :::no-loc text="Microsoft Teams Rooms"::: します。</span><span class="sxs-lookup"><span data-stu-id="fa677-169">List the events generated by a :::no-loc text="Microsoft Teams Rooms"::: device:</span></span>
   1.  <span data-ttu-id="fa677-170">[ログ **] に** 移動し、クエリを使用して、カスタム フィールドを持つレコードを取得します。</span><span class="sxs-lookup"><span data-stu-id="fa677-170">Go to **Logs** and use a query to retrieve the records that will have the custom field.</span></span>
   2.  <span data-ttu-id="fa677-171">サンプル クエリ: `Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="fa677-171">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3. <span data-ttu-id="fa677-172">レコードのいずれかを選択し、左側のボタンを選択して、フィールド抽出ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="fa677-172">Select one of the records, select the button to the left, and start the field extraction wizard.</span></span>
4. <span data-ttu-id="fa677-173">RenderedDescription から抽出するデータを強調表示し、フィールド タイトルを指定します。</span><span class="sxs-lookup"><span data-stu-id="fa677-173">Highlight the data you'd like to extract from the RenderedDescription and provide a Field Title.</span></span> <span data-ttu-id="fa677-174">使用する必要があるフィールド名を表 1 に示します。</span><span class="sxs-lookup"><span data-stu-id="fa677-174">The field names that you should use are provided in Table 1.</span></span>
5. <span data-ttu-id="fa677-175">表 1 に示すマッピング *を使用します*。</span><span class="sxs-lookup"><span data-stu-id="fa677-175">Use the mappings shown in *Table 1*.</span></span> <span data-ttu-id="fa677-176">:::no-loc text="Log Analytics":::は、新しいフィールド **\_ を定義** するときに CF 文字列を自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="fa677-176">:::no-loc text="Log Analytics"::: will automatically append the **\_CF** string when you define the new field.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa677-177">すべての JSON とフィールドでは大文字 :::no-loc text="Log Analytics"::: と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="fa677-177">Remember that all JSON and :::no-loc text="Log Analytics"::: fields are case-sensitive.</span></span>
> 
> <span data-ttu-id="fa677-178">次の表のカスタム フィールドごとに必要なクエリに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fa677-178">Pay attention to the queries required for each custom field in the table below.</span></span> <span data-ttu-id="fa677-179">カスタム フィールド値を正常に抽出するには、 の :::no-loc text="Log Analytics"::: 適切なクエリを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa677-179">You need to use the correct queries for :::no-loc text="Log Analytics"::: to successfully extract custom field values.</span></span>
> 
<span data-ttu-id="fa677-180">**表 1**</span><span class="sxs-lookup"><span data-stu-id="fa677-180">**Table 1**</span></span>

| <span data-ttu-id="fa677-181">**JSON フィールド**</span><span class="sxs-lookup"><span data-stu-id="fa677-181">**JSON field**</span></span>                   | <span data-ttu-id="fa677-182">**:::no-loc text="Log Analytics"::: カスタム フィールド**</span><span class="sxs-lookup"><span data-stu-id="fa677-182">**:::no-loc text="Log Analytics"::: custom field**</span></span> | <span data-ttu-id="fa677-183">**イベント ID**</span><span class="sxs-lookup"><span data-stu-id="fa677-183">**Event ID**</span></span> | <span data-ttu-id="fa677-184">**抽出で使用するクエリ**</span><span class="sxs-lookup"><span data-stu-id="fa677-184">**Query to use with the extraction**</span></span>                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| <span data-ttu-id="fa677-185">説明</span><span class="sxs-lookup"><span data-stu-id="fa677-185">Description</span></span>                      | <span data-ttu-id="fa677-186">SRSEventDescription</span><span class="sxs-lookup"><span data-stu-id="fa677-186">SRSEventDescription</span></span>         | <span data-ttu-id="fa677-187">**2000**</span><span class="sxs-lookup"><span data-stu-id="fa677-187">**2000**</span></span>     | <span data-ttu-id="fa677-188">\|Source == "SRS-App" と EventID == 2000 のイベント</span><span class="sxs-lookup"><span data-stu-id="fa677-188">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="fa677-189">ResourceState</span><span class="sxs-lookup"><span data-stu-id="fa677-189">ResourceState</span></span>                    | <span data-ttu-id="fa677-190">SRSResourceState</span><span class="sxs-lookup"><span data-stu-id="fa677-190">SRSResourceState</span></span>            | <span data-ttu-id="fa677-191">**2000**</span><span class="sxs-lookup"><span data-stu-id="fa677-191">**2000**</span></span>     | <span data-ttu-id="fa677-192">\|Source == "SRS-App" と EventID == 2000 のイベント</span><span class="sxs-lookup"><span data-stu-id="fa677-192">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="fa677-193">OperationName</span><span class="sxs-lookup"><span data-stu-id="fa677-193">OperationName</span></span>                    | <span data-ttu-id="fa677-194">SRSOperationName</span><span class="sxs-lookup"><span data-stu-id="fa677-194">SRSOperationName</span></span>            | <span data-ttu-id="fa677-195">**2000**</span><span class="sxs-lookup"><span data-stu-id="fa677-195">**2000**</span></span>     | <span data-ttu-id="fa677-196">\|Source == "SRS-App" と EventID == 2000 のイベント</span><span class="sxs-lookup"><span data-stu-id="fa677-196">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="fa677-197">OperationResult</span><span class="sxs-lookup"><span data-stu-id="fa677-197">OperationResult</span></span>                  | <span data-ttu-id="fa677-198">SRSOperationResult</span><span class="sxs-lookup"><span data-stu-id="fa677-198">SRSOperationResult</span></span>          | <span data-ttu-id="fa677-199">**2000**</span><span class="sxs-lookup"><span data-stu-id="fa677-199">**2000**</span></span>     | <span data-ttu-id="fa677-200">\|Source == "SRS-App" と EventID == 2000 のイベント</span><span class="sxs-lookup"><span data-stu-id="fa677-200">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="fa677-201">OS</span><span class="sxs-lookup"><span data-stu-id="fa677-201">OS</span></span>                               | <span data-ttu-id="fa677-202">SRSOSVersion</span><span class="sxs-lookup"><span data-stu-id="fa677-202">SRSOSVersion</span></span>                | <span data-ttu-id="fa677-203">**2000**</span><span class="sxs-lookup"><span data-stu-id="fa677-203">**2000**</span></span>     | <span data-ttu-id="fa677-204">\|Source == "SRS-App" と EventID == 2000 のイベント</span><span class="sxs-lookup"><span data-stu-id="fa677-204">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="fa677-205">OSVersion</span><span class="sxs-lookup"><span data-stu-id="fa677-205">OSVersion</span></span>                        | <span data-ttu-id="fa677-206">SRSOSLongVersion</span><span class="sxs-lookup"><span data-stu-id="fa677-206">SRSOSLongVersion</span></span>            | <span data-ttu-id="fa677-207">**2000**</span><span class="sxs-lookup"><span data-stu-id="fa677-207">**2000**</span></span>     | <span data-ttu-id="fa677-208">\|Source == "SRS-App" と EventID == 2000 のイベント</span><span class="sxs-lookup"><span data-stu-id="fa677-208">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="fa677-209">Alias</span><span class="sxs-lookup"><span data-stu-id="fa677-209">Alias</span></span>                            | <span data-ttu-id="fa677-210">SRSAlias</span><span class="sxs-lookup"><span data-stu-id="fa677-210">SRSAlias</span></span>                    | <span data-ttu-id="fa677-211">**2000**</span><span class="sxs-lookup"><span data-stu-id="fa677-211">**2000**</span></span>     | <span data-ttu-id="fa677-212">\|Source == "SRS-App" と EventID == 2000 のイベント</span><span class="sxs-lookup"><span data-stu-id="fa677-212">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="fa677-213">DisplayName</span><span class="sxs-lookup"><span data-stu-id="fa677-213">DisplayName</span></span>                      | <span data-ttu-id="fa677-214">SRSDisplayName</span><span class="sxs-lookup"><span data-stu-id="fa677-214">SRSDisplayName</span></span>              | <span data-ttu-id="fa677-215">**2000**</span><span class="sxs-lookup"><span data-stu-id="fa677-215">**2000**</span></span>     | <span data-ttu-id="fa677-216">\|Source == "SRS-App" と EventID == 2000 のイベント</span><span class="sxs-lookup"><span data-stu-id="fa677-216">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="fa677-217">AppVersion</span><span class="sxs-lookup"><span data-stu-id="fa677-217">AppVersion</span></span>                       | <span data-ttu-id="fa677-218">SRSAppVersion</span><span class="sxs-lookup"><span data-stu-id="fa677-218">SRSAppVersion</span></span>               | <span data-ttu-id="fa677-219">**2000**</span><span class="sxs-lookup"><span data-stu-id="fa677-219">**2000**</span></span>     | <span data-ttu-id="fa677-220">\|Source == "SRS-App" と EventID == 2000 のイベント</span><span class="sxs-lookup"><span data-stu-id="fa677-220">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="fa677-221">IPv4Address</span><span class="sxs-lookup"><span data-stu-id="fa677-221">IPv4Address</span></span>                      | <span data-ttu-id="fa677-222">SRSIPv4Address</span><span class="sxs-lookup"><span data-stu-id="fa677-222">SRSIPv4Address</span></span>              | <span data-ttu-id="fa677-223">**2000**</span><span class="sxs-lookup"><span data-stu-id="fa677-223">**2000**</span></span>     | <span data-ttu-id="fa677-224">\|Source == "SRS-App" と EventID == 2000 のイベント</span><span class="sxs-lookup"><span data-stu-id="fa677-224">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="fa677-225">IPv6Address</span><span class="sxs-lookup"><span data-stu-id="fa677-225">IPv6Address</span></span>                      | <span data-ttu-id="fa677-226">SRSIPv6Address</span><span class="sxs-lookup"><span data-stu-id="fa677-226">SRSIPv6Address</span></span>              | <span data-ttu-id="fa677-227">**2000**</span><span class="sxs-lookup"><span data-stu-id="fa677-227">**2000**</span></span>     | <span data-ttu-id="fa677-228">\|Source == "SRS-App" と EventID == 2000 のイベント</span><span class="sxs-lookup"><span data-stu-id="fa677-228">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="fa677-229">電話会議マイクの状態</span><span class="sxs-lookup"><span data-stu-id="fa677-229">Conference Microphone status</span></span>     | <span data-ttu-id="fa677-230">SRSConfMicrophoneStatus</span><span class="sxs-lookup"><span data-stu-id="fa677-230">SRSConfMicrophoneStatus</span></span>     | <span data-ttu-id="fa677-231">**3001**</span><span class="sxs-lookup"><span data-stu-id="fa677-231">**3001**</span></span>     | <span data-ttu-id="fa677-232">\|Source == "SRS-App" と EventID == 3001 のイベント</span><span class="sxs-lookup"><span data-stu-id="fa677-232">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="fa677-233">電話会議の発表者の状態</span><span class="sxs-lookup"><span data-stu-id="fa677-233">Conference Speaker status</span></span>        | <span data-ttu-id="fa677-234">SRSConfSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="fa677-234">SRSConfSpeakerStatus</span></span>        | <span data-ttu-id="fa677-235">**3001**</span><span class="sxs-lookup"><span data-stu-id="fa677-235">**3001**</span></span>     | <span data-ttu-id="fa677-236">\|Source == "SRS-App" と EventID == 3001 のイベント</span><span class="sxs-lookup"><span data-stu-id="fa677-236">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="fa677-237">スピーカーの既定の状態</span><span class="sxs-lookup"><span data-stu-id="fa677-237">Default Speaker status</span></span>           | <span data-ttu-id="fa677-238">SRSDefaultSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="fa677-238">SRSDefaultSpeakerStatus</span></span>     | <span data-ttu-id="fa677-239">**3001**</span><span class="sxs-lookup"><span data-stu-id="fa677-239">**3001**</span></span>     | <span data-ttu-id="fa677-240">\|Source == "SRS-App" と EventID == 3001 のイベント</span><span class="sxs-lookup"><span data-stu-id="fa677-240">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="fa677-241">カメラの状態</span><span class="sxs-lookup"><span data-stu-id="fa677-241">Camera status</span></span>                    | <span data-ttu-id="fa677-242">SRSCameraStatus</span><span class="sxs-lookup"><span data-stu-id="fa677-242">SRSCameraStatus</span></span>             | <span data-ttu-id="fa677-243">**3001**</span><span class="sxs-lookup"><span data-stu-id="fa677-243">**3001**</span></span>     | <span data-ttu-id="fa677-244">\|Source == "SRS-App" と EventID == 3001 のイベント</span><span class="sxs-lookup"><span data-stu-id="fa677-244">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="fa677-245">ルームの前面の表示状態</span><span class="sxs-lookup"><span data-stu-id="fa677-245">Front of Room Display status</span></span>     | <span data-ttu-id="fa677-246">SRSFORDStatus</span><span class="sxs-lookup"><span data-stu-id="fa677-246">SRSFORDStatus</span></span>               | <span data-ttu-id="fa677-247">**3001**</span><span class="sxs-lookup"><span data-stu-id="fa677-247">**3001**</span></span>     | <span data-ttu-id="fa677-248">\|Source == "SRS-App" と EventID == 3001 のイベント</span><span class="sxs-lookup"><span data-stu-id="fa677-248">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="fa677-249">モーション センサーの状態</span><span class="sxs-lookup"><span data-stu-id="fa677-249">Motion Sensor status</span></span>             | <span data-ttu-id="fa677-250">SRSMotionSensorStatus</span><span class="sxs-lookup"><span data-stu-id="fa677-250">SRSMotionSensorStatus</span></span>       | <span data-ttu-id="fa677-251">**3001**</span><span class="sxs-lookup"><span data-stu-id="fa677-251">**3001**</span></span>     | <span data-ttu-id="fa677-252">\|Source == "SRS-App" と EventID == 3001 のイベント</span><span class="sxs-lookup"><span data-stu-id="fa677-252">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="fa677-253">HDMI 取り込み状態</span><span class="sxs-lookup"><span data-stu-id="fa677-253">HDMI Ingest status</span></span>               | <span data-ttu-id="fa677-254">SRSHDMIIngestStatus</span><span class="sxs-lookup"><span data-stu-id="fa677-254">SRSHDMIIngestStatus</span></span>         | <span data-ttu-id="fa677-255">**3001**</span><span class="sxs-lookup"><span data-stu-id="fa677-255">**3001**</span></span>     | <span data-ttu-id="fa677-256">\|Source == "SRS-App" と EventID == 3001 のイベント</span><span class="sxs-lookup"><span data-stu-id="fa677-256">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a><span data-ttu-id="fa677-257">でビュー :::no-loc text="Microsoft Teams Rooms"::: を定義する :::no-loc text="Log Analytics":::</span><span class="sxs-lookup"><span data-stu-id="fa677-257">Define the :::no-loc text="Microsoft Teams Rooms"::: views in :::no-loc text="Log Analytics":::</span></span>
<span data-ttu-id="fa677-258"><a name="Define_Views"> </a></span><span class="sxs-lookup"><span data-stu-id="fa677-258"><a name="Define_Views"> </a></span></span>

<span data-ttu-id="fa677-259">データが収集され、カスタム フィールドがマップされた後、ビュー デザイナーを使用して、イベントを監視するさまざまなタイルを含むダッシュボードを開発 :::no-loc text="Microsoft Teams Rooms"::: できます。</span><span class="sxs-lookup"><span data-stu-id="fa677-259">After data is collected and custom fields are mapped, you can use View Designer to develop a dashboard containing various tiles to monitor :::no-loc text="Microsoft Teams Rooms"::: events.</span></span> <span data-ttu-id="fa677-260">ビュー デザイナーを使用して、次のタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="fa677-260">Use View Designer to create the following tiles.</span></span> <span data-ttu-id="fa677-261">詳細については、「ビュー デザイナーを[使用してカスタム ビューを :::no-loc text="Log Analytics"::: 作成する」を参照してください。](/azure/azure-monitor/platform/view-designer)</span><span class="sxs-lookup"><span data-stu-id="fa677-261">For more information, see [Create custom views by using View Designer in :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/view-designer)</span></span>

> [!NOTE]
> <span data-ttu-id="fa677-262">ダッシュボード タイルが正常に動作するには、このガイドの前の手順を完了している必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa677-262">Previous steps in this guide should have been completed for the dashboard tiles to work properly.</span></span>

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a><span data-ttu-id="fa677-263">import メソッドMicrosoft Teams ミーティングダッシュボードを作成する</span><span class="sxs-lookup"><span data-stu-id="fa677-263">Create a Microsoft Teams Rooms dashboard by using the import method</span></span>

<span data-ttu-id="fa677-264">ダッシュボードをインポートして :::no-loc text="Microsoft Teams Rooms"::: 、デバイスの監視をすばやく開始できます。</span><span class="sxs-lookup"><span data-stu-id="fa677-264">You can import an :::no-loc text="Microsoft Teams Rooms"::: dashboard and start monitoring your devices quickly.</span></span> <span data-ttu-id="fa677-265">ダッシュボードをインポートするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fa677-265">Take the following steps to import the dashboard:</span></span>

1.  <span data-ttu-id="fa677-266">[SkypeRoomSystems_v2.omsview ダッシュボード ファイルを](https://go.microsoft.com/fwlink/?linkid=835675)取得します。</span><span class="sxs-lookup"><span data-stu-id="fa677-266">Get the [SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675) dashboard file.</span></span>
2.  <span data-ttu-id="fa677-267">ポータルにサインイン[ :::no-loc text="Microsoft Azure"::: し、 に](https://portal.azure.com)移動して :::no-loc text="Log Analytics"::: ワークスペースを選択します。</span><span class="sxs-lookup"><span data-stu-id="fa677-267">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>
3.  <span data-ttu-id="fa677-268">ビュー **デザイナー を開きます**。</span><span class="sxs-lookup"><span data-stu-id="fa677-268">Open **View Designer**.</span></span>
4.  <span data-ttu-id="fa677-269">[ **インポート]** を選択し **、SkypeRoomSystems_v2.omsview ファイルを選択** します。</span><span class="sxs-lookup"><span data-stu-id="fa677-269">Select **Import**, and then select the **SkypeRoomSystems_v2.omsview** file.</span></span>
5.  <span data-ttu-id="fa677-270">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fa677-270">Select **Save**.</span></span>

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a><span data-ttu-id="fa677-271">ダッシュボードを手動Microsoft Teams ミーティング作成する</span><span class="sxs-lookup"><span data-stu-id="fa677-271">Create a Microsoft Teams Rooms dashboard manually</span></span>

<span data-ttu-id="fa677-272">または、独自のダッシュボードを作成し、監視するタイルのみを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="fa677-272">Alternatively, you can create your own dashboard and add only the tiles that you wish to monitor.</span></span>

#### <a name="configure-the-overview-tile"></a><span data-ttu-id="fa677-273">[概要] タイルを構成する</span><span class="sxs-lookup"><span data-stu-id="fa677-273">Configure the Overview Tile</span></span>

1.  <span data-ttu-id="fa677-274">ビュー **デザイナー を開きます**。</span><span class="sxs-lookup"><span data-stu-id="fa677-274">Open **View Designer**.</span></span>
2.  <span data-ttu-id="fa677-275">[概要 **タイル] を** 選択し、ギャラリーから **[2 つの** 数値] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fa677-275">Select **Overview Tile**, and then select **Two numbers** from the gallery.</span></span>
3.  <span data-ttu-id="fa677-276">タイルに という名前を付 **:::no-loc text="Microsoft Teams Rooms":::** けします。</span><span class="sxs-lookup"><span data-stu-id="fa677-276">Name the tile **:::no-loc text="Microsoft Teams Rooms":::**.</span></span>
4.  <span data-ttu-id="fa677-277">最初のタイル **を定義します**。</span><span class="sxs-lookup"><span data-stu-id="fa677-277">Define the **First Tile**:</span></span><br>
    <span data-ttu-id="fa677-278">**凡例:** 前月に少なくとも 1 回ハートビートを送信したデバイス</span><span class="sxs-lookup"><span data-stu-id="fa677-278">**Legend:** Devices that sent a heartbeat at least once within the last month</span></span><br>
    <span data-ttu-id="fa677-279">**クエリ:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="fa677-279">**Query:** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
5.  <span data-ttu-id="fa677-280">2 番目 **のタイルを定義します**。</span><span class="sxs-lookup"><span data-stu-id="fa677-280">Define the **Second Tile**:</span></span><br>
    <span data-ttu-id="fa677-281">**凡例:** 最後の 1 時間以内にハートビートを送信したアクティブ なデバイス</span><span class="sxs-lookup"><span data-stu-id="fa677-281">**Legend:** Active devices that sent a heartbeat within the last hour</span></span><br>
    <span data-ttu-id="fa677-282">**クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="fa677-282">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
6.  <span data-ttu-id="fa677-283">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fa677-283">Select **Apply**.</span></span>

### <a name="create-a-tile-that-displays-active-devices"></a><span data-ttu-id="fa677-284">アクティブなデバイスを表示するタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="fa677-284">Create a tile that displays active devices</span></span>

1.  <span data-ttu-id="fa677-285">[ダッシュボード **の表示] を** 選択して、タイルの追加を開始します。</span><span class="sxs-lookup"><span data-stu-id="fa677-285">Select **View Dashboard** to start adding your tiles.</span></span>
2.  <span data-ttu-id="fa677-286">ギャラリー **から [番号&リスト** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fa677-286">Select **Number & list** from the gallery</span></span>
3.  <span data-ttu-id="fa677-287">[全般] **プロパティを定義** します。</span><span class="sxs-lookup"><span data-stu-id="fa677-287">Define the **General** properties:</span></span><br>
    <span data-ttu-id="fa677-288">**グループ タイトル:** ハートビートの状態</span><span class="sxs-lookup"><span data-stu-id="fa677-288">**Group Title:** Heartbeat Status</span></span><br>
    <span data-ttu-id="fa677-289">**新しいグループ:** 選択</span><span class="sxs-lookup"><span data-stu-id="fa677-289">**New Group:** Selected</span></span>
4.  <span data-ttu-id="fa677-290">タイルのプロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="fa677-290">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="fa677-291">**凡例:** アクティブなデバイス (過去 20 分間に送信されたハートビート)</span><span class="sxs-lookup"><span data-stu-id="fa677-291">**Legend:** Active devices (heartbeat sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="fa677-292">**タイルのクエリ:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="fa677-292">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span></span>
5.  <span data-ttu-id="fa677-293">List プロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="fa677-293">Define the **List** properties:</span></span><br>
    <span data-ttu-id="fa677-294">**リスト クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="fa677-294">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
6.  <span data-ttu-id="fa677-295">列 **タイトルを定義する**:</span><span class="sxs-lookup"><span data-stu-id="fa677-295">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="fa677-296">**名前:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="fa677-296">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="fa677-297">**値:** 最後のハートビート</span><span class="sxs-lookup"><span data-stu-id="fa677-297">**Value:** Last Heartbeat</span></span>
7.  <span data-ttu-id="fa677-298">ナビゲーション **クエリ を定義します**。</span><span class="sxs-lookup"><span data-stu-id="fa677-298">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="fa677-299">[適用 **] を選択** し、[閉じる] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fa677-299">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a><span data-ttu-id="fa677-300">接続の問題があるデバイスを表示するタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="fa677-300">Create a tile that displays devices that have connectivity issues</span></span>

1.  <span data-ttu-id="fa677-301">ギャラリー **から [&番号** ] リストを選択し、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa677-301">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="fa677-302">[全般] **プロパティを定義** します。</span><span class="sxs-lookup"><span data-stu-id="fa677-302">Define the **General** properties:</span></span><br>
    <span data-ttu-id="fa677-303">**グループ タイトル:** 空のままにする</span><span class="sxs-lookup"><span data-stu-id="fa677-303">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="fa677-304">**新しいグループ:** 選択されていない</span><span class="sxs-lookup"><span data-stu-id="fa677-304">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="fa677-305">タイルのプロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="fa677-305">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="fa677-306">**凡例:** 非アクティブなデバイス (過去 20 分間にハートビート メッセージが送信されません)</span><span class="sxs-lookup"><span data-stu-id="fa677-306">**Legend:** Inactive Devices (no heartbeat message sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="fa677-307">**タイルのクエリ:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span><span class="sxs-lookup"><span data-stu-id="fa677-307">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span></span>
4.  <span data-ttu-id="fa677-308">List プロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="fa677-308">Define the **List** properties:</span></span><br>
    <span data-ttu-id="fa677-309">**リスト クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="fa677-309">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="fa677-310">列 **タイトルを定義する**:</span><span class="sxs-lookup"><span data-stu-id="fa677-310">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="fa677-311">**名前:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="fa677-311">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="fa677-312">**値:** 最後のハートビート</span><span class="sxs-lookup"><span data-stu-id="fa677-312">**Value:** Last Heartbeat</span></span>
6.  <span data-ttu-id="fa677-313">ナビゲーション **クエリを定義する**:</span><span class="sxs-lookup"><span data-stu-id="fa677-313">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="fa677-314">[適用 **] を選択** し、[閉じる] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fa677-314">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a><span data-ttu-id="fa677-315">ハードウェア エラーが発生したデバイスを表示するタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="fa677-315">Create a tile that displays devices that have a hardware error</span></span>

1.  <span data-ttu-id="fa677-316">ギャラリー **から [&番号** ] リストを選択し、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa677-316">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="fa677-317">[全般] **プロパティを定義** します。</span><span class="sxs-lookup"><span data-stu-id="fa677-317">Define the **General** properties:</span></span><br>
    <span data-ttu-id="fa677-318">**グループ タイトル:** ハードウェアの状態</span><span class="sxs-lookup"><span data-stu-id="fa677-318">**Group Title:** Hardware Status</span></span><br>
    <span data-ttu-id="fa677-319">**新しいグループ:** 選択</span><span class="sxs-lookup"><span data-stu-id="fa677-319">**New Group:** Selected</span></span>
3.  <span data-ttu-id="fa677-320">タイルのプロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="fa677-320">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="fa677-321">**凡例:** 過去 1 時間にハードウェア エラーが発生したデバイス</span><span class="sxs-lookup"><span data-stu-id="fa677-321">**Legend:** Devices that experienced a hardware error in the last hour</span></span><br>
    <span data-ttu-id="fa677-322">**タイルのクエリ:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="fa677-322">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="fa677-323">List プロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="fa677-323">Define the **List** properties:</span></span><br>
    <span data-ttu-id="fa677-324">**リスト クエリ:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="fa677-324">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="fa677-325">列 **タイトルを定義する**:</span><span class="sxs-lookup"><span data-stu-id="fa677-325">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="fa677-326">**名前:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="fa677-326">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="fa677-327">**値:** 最後のエラー</span><span class="sxs-lookup"><span data-stu-id="fa677-327">**Value:** Last Error</span></span>
6.  <span data-ttu-id="fa677-328">ナビゲーション **クエリを定義する**:</span><span class="sxs-lookup"><span data-stu-id="fa677-328">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="fa677-329">[適用 **] を選択** し、[閉じる] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fa677-329">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a><span data-ttu-id="fa677-330">オペレーティング システムのバージョンを表示 :::no-loc text="Microsoft Teams Rooms"::: するタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="fa677-330">Create a tile that displays :::no-loc text="Microsoft Teams Rooms"::: Operating System versions</span></span>

1.  <span data-ttu-id="fa677-331">ギャラリー **から [&] リスト** を選択し、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa677-331">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="fa677-332">[全般] **プロパティを定義** します。</span><span class="sxs-lookup"><span data-stu-id="fa677-332">Define the **General** properties:</span></span><br>
    <span data-ttu-id="fa677-333">**グループ タイトル:** オペレーティング システムの詳細</span><span class="sxs-lookup"><span data-stu-id="fa677-333">**Group Title:** Operating System details</span></span><br>
    <span data-ttu-id="fa677-334">**新しいグループ:** 選択</span><span class="sxs-lookup"><span data-stu-id="fa677-334">**New Group:** Selected</span></span>
3.  <span data-ttu-id="fa677-335">ヘッダーのプロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="fa677-335">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="fa677-336">**タイトル:** オペレーティング システムのバージョン</span><span class="sxs-lookup"><span data-stu-id="fa677-336">**Title:** Operating System versions</span></span><br>
    <span data-ttu-id="fa677-337">**字幕:** 特定の OS バージョンを実行しているデバイス</span><span class="sxs-lookup"><span data-stu-id="fa677-337">**Subtitle:** Devices running specific OS versions</span></span>
4.  <span data-ttu-id="fa677-338">Donut **プロパティを定義** します。</span><span class="sxs-lookup"><span data-stu-id="fa677-338">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="fa677-339">**クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span><span class="sxs-lookup"><span data-stu-id="fa677-339">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span></span><br>
    <span data-ttu-id="fa677-340">**中央のテキスト:** デバイス</span><span class="sxs-lookup"><span data-stu-id="fa677-340">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="fa677-341">**操作:** 合計</span><span class="sxs-lookup"><span data-stu-id="fa677-341">**Operation:** Sum</span></span>
5.  <span data-ttu-id="fa677-342">List プロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="fa677-342">Define the **List** properties.</span></span><br>
    <span data-ttu-id="fa677-343">**リスト クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span><span class="sxs-lookup"><span data-stu-id="fa677-343">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="fa677-344">**[非表示Graph:** 選択</span><span class="sxs-lookup"><span data-stu-id="fa677-344">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="fa677-345">**スパークラインを有効にする:** 選択されていない</span><span class="sxs-lookup"><span data-stu-id="fa677-345">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="fa677-346">列タイトル **を定義します**。</span><span class="sxs-lookup"><span data-stu-id="fa677-346">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="fa677-347">**名前:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="fa677-347">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="fa677-348">**値:** 空のままにする</span><span class="sxs-lookup"><span data-stu-id="fa677-348">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="fa677-349">ナビゲーション **クエリ を定義します**。</span><span class="sxs-lookup"><span data-stu-id="fa677-349">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="fa677-350">[適用 **] を選択** し、[閉じる] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fa677-350">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a><span data-ttu-id="fa677-351">アプリケーションのバージョンを表示する :::no-loc text="Microsoft Teams Rooms"::: タイルを作成する</span><span class="sxs-lookup"><span data-stu-id="fa677-351">Create a tile that displays :::no-loc text="Microsoft Teams Rooms"::: application versions</span></span>

1.  <span data-ttu-id="fa677-352">ギャラリー **から [&] リスト** を選択し、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa677-352">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="fa677-353">[全般] **プロパティを定義** します。</span><span class="sxs-lookup"><span data-stu-id="fa677-353">Define the **General** properties:</span></span><br>
    <span data-ttu-id="fa677-354">**グループ タイトル:** :::no-loc text="Microsoft Teams Rooms"::: アプリケーションの詳細</span><span class="sxs-lookup"><span data-stu-id="fa677-354">**Group Title:** :::no-loc text="Microsoft Teams Rooms"::: application details</span></span><br>
    <span data-ttu-id="fa677-355">**新しいグループ:** 選択</span><span class="sxs-lookup"><span data-stu-id="fa677-355">**New Group:** Selected</span></span>
3.  <span data-ttu-id="fa677-356">ヘッダーのプロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="fa677-356">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="fa677-357">**タイトル:** アプリケーションのバージョン</span><span class="sxs-lookup"><span data-stu-id="fa677-357">**Title:** Application versions</span></span><br>
    <span data-ttu-id="fa677-358">**字幕:** 特定のアプリケーション バージョンを実行しているデバイス</span><span class="sxs-lookup"><span data-stu-id="fa677-358">**Subtitle:** Devices running specific application versions</span></span>
4.  <span data-ttu-id="fa677-359">Donut **プロパティを定義** します。</span><span class="sxs-lookup"><span data-stu-id="fa677-359">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="fa677-360">**クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span><span class="sxs-lookup"><span data-stu-id="fa677-360">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span></span><br>
    <span data-ttu-id="fa677-361">**中央のテキスト:** デバイス</span><span class="sxs-lookup"><span data-stu-id="fa677-361">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="fa677-362">**操作:** 合計</span><span class="sxs-lookup"><span data-stu-id="fa677-362">**Operation:** Sum</span></span>
5.  <span data-ttu-id="fa677-363">List プロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="fa677-363">Define the **List** properties.</span></span><br>
    <span data-ttu-id="fa677-364">**リスト クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span><span class="sxs-lookup"><span data-stu-id="fa677-364">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="fa677-365">**[非表示Graph:** 選択</span><span class="sxs-lookup"><span data-stu-id="fa677-365">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="fa677-366">**スパークラインを有効にする:** 選択されていない</span><span class="sxs-lookup"><span data-stu-id="fa677-366">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="fa677-367">列タイトル **を定義します**。</span><span class="sxs-lookup"><span data-stu-id="fa677-367">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="fa677-368">**名前:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="fa677-368">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="fa677-369">**値:** 空のままにする</span><span class="sxs-lookup"><span data-stu-id="fa677-369">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="fa677-370">ナビゲーション **クエリ を定義します**。</span><span class="sxs-lookup"><span data-stu-id="fa677-370">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="fa677-371">[適用 **] を選択** し、[閉じる] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fa677-371">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a><span data-ttu-id="fa677-372">アプリケーション エラーが発生したデバイスを表示するタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="fa677-372">Create a tile that displays devices that have an application error</span></span>

1.  <span data-ttu-id="fa677-373">ギャラリー **から [&番号** ] リストを選択し、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa677-373">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="fa677-374">[全般] **プロパティを定義** します。</span><span class="sxs-lookup"><span data-stu-id="fa677-374">Define the **General** properties.</span></span><br>
    <span data-ttu-id="fa677-375">**グループ タイトル:** 空のままにする</span><span class="sxs-lookup"><span data-stu-id="fa677-375">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="fa677-376">**新しいグループ:** 選択されていない</span><span class="sxs-lookup"><span data-stu-id="fa677-376">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="fa677-377">タイルのプロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="fa677-377">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="fa677-378">**凡例:** 過去 1 時間にアプリケーション エラーが発生したデバイス</span><span class="sxs-lookup"><span data-stu-id="fa677-378">**Legend:** Devices that experienced an application error in the last hour</span></span><br>
    <span data-ttu-id="fa677-379">**タイルのクエリ:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="fa677-379">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="fa677-380">List プロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="fa677-380">Define the **List** properties.</span></span><br>
    <span data-ttu-id="fa677-381">**リスト クエリ:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="fa677-381">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="fa677-382">列タイトル **を定義します**。</span><span class="sxs-lookup"><span data-stu-id="fa677-382">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="fa677-383">**名前:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="fa677-383">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="fa677-384">**値:** 最後のエラー</span><span class="sxs-lookup"><span data-stu-id="fa677-384">**Value:** Last Error</span></span>
6.  <span data-ttu-id="fa677-385">ナビゲーション **クエリ を定義します**。</span><span class="sxs-lookup"><span data-stu-id="fa677-385">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="fa677-386">[適用 **] を選択** し、[閉じる] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fa677-386">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a><span data-ttu-id="fa677-387">再起動されたデバイスを表示するタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="fa677-387">Create a tile that displays devices that have been restarted</span></span>

1.  <span data-ttu-id="fa677-388">ギャラリー **から [&番号** ] リストを選択し、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa677-388">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="fa677-389">[全般] **プロパティを定義** します。</span><span class="sxs-lookup"><span data-stu-id="fa677-389">Define the **General** properties.</span></span><br>
    <span data-ttu-id="fa677-390">**グループ タイトル:** 空のままにする</span><span class="sxs-lookup"><span data-stu-id="fa677-390">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="fa677-391">**新しいグループ:** 選択されていない</span><span class="sxs-lookup"><span data-stu-id="fa677-391">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="fa677-392">タイルのプロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="fa677-392">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="fa677-393">**凡例:** 過去 24 時間にアプリケーションが再起動されたデバイスと再起動数</span><span class="sxs-lookup"><span data-stu-id="fa677-393">**Legend:** Devices where the application was restarted in the last 24 hours, and number of restarts</span></span><br>
    <span data-ttu-id="fa677-394">**タイルのクエリ:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="fa677-394">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="fa677-395">List プロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="fa677-395">Define the **List** properties.</span></span><br>
    <span data-ttu-id="fa677-396">**リスト クエリ:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span><span class="sxs-lookup"><span data-stu-id="fa677-396">**List Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span></span>
5.  <span data-ttu-id="fa677-397">列タイトル **を定義します**。</span><span class="sxs-lookup"><span data-stu-id="fa677-397">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="fa677-398">**名前:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="fa677-398">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="fa677-399">**値:** 再起動の数</span><span class="sxs-lookup"><span data-stu-id="fa677-399">**Value:** Number of Restarts</span></span>
6.  <span data-ttu-id="fa677-400">ナビゲーション **クエリ を定義します**。</span><span class="sxs-lookup"><span data-stu-id="fa677-400">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="fa677-401">[適用 **] を選択** し、[閉じる] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fa677-401">Select **Apply** and then **Close**.</span></span>
8.  <span data-ttu-id="fa677-402">[保存 **] を** 選択してダッシュボードを保存します。</span><span class="sxs-lookup"><span data-stu-id="fa677-402">Select **Save** to save your dashboard.</span></span>

<span data-ttu-id="fa677-403">これで、ビューの作成が完了しました。</span><span class="sxs-lookup"><span data-stu-id="fa677-403">Now you've completed creating your views.</span></span>

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a><span data-ttu-id="fa677-404">でアラートを構成する :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="fa677-404">Configure Alerts in :::no-loc text="Azure Monitor":::</span></span>
<span data-ttu-id="fa677-405"><a name="Alerts"> </a></span><span class="sxs-lookup"><span data-stu-id="fa677-405"><a name="Alerts"> </a></span></span>

<span data-ttu-id="fa677-406">:::no-loc text="Azure Monitor"::: は、本体で問題が発生した場合に管理者に :::no-loc text="Microsoft Teams Rooms"::: 通知するアラートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="fa677-406">:::no-loc text="Azure Monitor"::: can raise alerts to notify the administrators, when a :::no-loc text="Microsoft Teams Rooms"::: console encounters an issue.</span></span>

<span data-ttu-id="fa677-407">:::no-loc text="Azure Monitor"::: には、定期的にスケジュールされたログ検索を実行する組み込みのアラート メカニズムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fa677-407">:::no-loc text="Azure Monitor"::: includes a built-in alerting mechanism that runs through scheduled log searches at regular intervals.</span></span> <span data-ttu-id="fa677-408">ログ検索の結果が特定の条件と一致する場合は、アラート レコードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="fa677-408">If the results of the log search match some particular criteria, an alert record is created.</span></span>

<span data-ttu-id="fa677-409">その後、ルールは 1 つ以上のアクションを自動的に実行して、アラートを事前に通知したり、別のプロセスを呼び出したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="fa677-409">The rule can then automatically run one or more actions to proactively notify you of the alert or invoke another process.</span></span> <span data-ttu-id="fa677-410">アラートで使用できるオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fa677-410">The possible options with alerts are:</span></span>
-   <span data-ttu-id="fa677-411">メールの送信</span><span class="sxs-lookup"><span data-stu-id="fa677-411">Sending an email</span></span>
-   <span data-ttu-id="fa677-412">HTTP POST 要求を介した外部プロセスの呼び出し</span><span class="sxs-lookup"><span data-stu-id="fa677-412">Invoking an external process through an HTTP POST request</span></span>
-   <span data-ttu-id="fa677-413">サービスでの Runbook の :::no-loc text="Azure Automation"::: 開始</span><span class="sxs-lookup"><span data-stu-id="fa677-413">Starting a runbook in :::no-loc text="Azure Automation"::: service</span></span>

<span data-ttu-id="fa677-414">の[アラートの詳細 :::no-loc text="Azure Monitor"::: については、「](/azure/azure-monitor/platform/alerts-unified-log)ログイン アラート」を参照してください :::no-loc text="Azure Monitor"::: 。</span><span class="sxs-lookup"><span data-stu-id="fa677-414">See [Log alerts in :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/alerts-unified-log) to learn more about the alerts in :::no-loc text="Azure Monitor":::.</span></span>

> [!NOTE]
> <span data-ttu-id="fa677-415">次の例では、デバイスがハードウェアまたはアプリケーション エラー :::no-loc text="Microsoft Teams Rooms"::: を生成するときに電子メール アラートを送信します。</span><span class="sxs-lookup"><span data-stu-id="fa677-415">The following examples send email alerts when a :::no-loc text="Microsoft Teams Rooms"::: device generates a hardware or an application error.</span></span>

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a><span data-ttu-id="fa677-416">ハードウェアの問題に関する電子 :::no-loc text="Microsoft Teams Rooms"::: メール アラートを構成する</span><span class="sxs-lookup"><span data-stu-id="fa677-416">Configure an email alert for :::no-loc text="Microsoft Teams Rooms"::: hardware issues</span></span>

<span data-ttu-id="fa677-417">前の 1 時間以内にハードウェアの問題が発生したデバイスをチェックするアラート :::no-loc text="Microsoft Teams Rooms"::: ルールを構成します。</span><span class="sxs-lookup"><span data-stu-id="fa677-417">Configure an alert rule that checks for :::no-loc text="Microsoft Teams Rooms"::: devices that have encountered hardware issues within the last hour.</span></span>
1.  <span data-ttu-id="fa677-418">ポータルにサインイン[ :::no-loc text="Microsoft Azure"::: し、 に](https://portal.azure.com)移動して :::no-loc text="Log Analytics"::: ワークスペースを選択します。</span><span class="sxs-lookup"><span data-stu-id="fa677-418">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2. <span data-ttu-id="fa677-419">ワークスペースに移動し :::no-loc text="Log Analytics"::: 、[アラート] を **選択し** 、[新しいアラート **ルール] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="fa677-419">Navigate to your :::no-loc text="Log Analytics"::: workspace and select **Alerts** and then select **New alert rule**</span></span>

3. <span data-ttu-id="fa677-420">[条件 **の追加] を** 選択し、[ **カスタム ログ検索] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="fa677-420">Select **Add condition** and then **Custom log search**</span></span>

4.  <span data-ttu-id="fa677-421">[検索クエリ] テキスト ボックスに次のクエリを入力します。</span><span class="sxs-lookup"><span data-stu-id="fa677-421">Enter the following query to the Search query text box.</span></span><br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  <span data-ttu-id="fa677-422">アラート ロジックの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="fa677-422">Configure the Alert logic settings:</span></span><br>
    <span data-ttu-id="fa677-423">**次の条件に基づいて、** 結果の数</span><span class="sxs-lookup"><span data-stu-id="fa677-423">**Based on:** Number of results</span></span><br>
    <span data-ttu-id="fa677-424">**条件:** 次に大きい</span><span class="sxs-lookup"><span data-stu-id="fa677-424">**Condition:** Greater then</span></span><br>
    <span data-ttu-id="fa677-425">**しきい値:** 0</span><span class="sxs-lookup"><span data-stu-id="fa677-425">**Threshold:** 0</span></span><br>

6. <span data-ttu-id="fa677-426">評価設定を構成し、[完了] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="fa677-426">Configure Evaluation settings and select **Done**:</span></span> <br>
    <span data-ttu-id="fa677-427">**期間 (分):** 60</span><span class="sxs-lookup"><span data-stu-id="fa677-427">**Period (in minutes):** 60</span></span><br>
    <span data-ttu-id="fa677-428">**頻度 (分):** 60</span><span class="sxs-lookup"><span data-stu-id="fa677-428">**Frequency (in minutes):** 60</span></span><br>

7. <span data-ttu-id="fa677-429">アクション グループを構成する:</span><span class="sxs-lookup"><span data-stu-id="fa677-429">Configure action groups:</span></span>
    1.  <span data-ttu-id="fa677-430">[Create **New]を選択します。**</span><span class="sxs-lookup"><span data-stu-id="fa677-430">Select **Create New**</span></span>
    2.  <span data-ttu-id="fa677-431">[アクション グループ名] フィールドと *[短い名前] フィールドに\*\*適した名前を指定* します。</span><span class="sxs-lookup"><span data-stu-id="fa677-431">Provide suitable names for the *Action group name* and *Short Name* fields.</span></span>
    3.  <span data-ttu-id="fa677-432">一意の *アクション名を指定し*、[**電子メール/携帯ショートメール/プッシュ/** 音声] を選択し、[詳細の編集]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fa677-432">Specify a unique *Action Name* and select **Email/SMS/Push/Voice**, and then select **Edit details**.</span></span>
    4.  <span data-ttu-id="fa677-433">[電子メール **] チェック** ボックスをオンにして、アラートを受信するユーザーまたはグループのメール アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="fa677-433">Select the **Email** checkbox and provide the email address of the person or group that will receive the alerts.</span></span>
    5.  <span data-ttu-id="fa677-434">また、電話番号を入力して、通話、音声通話、携帯ショートメール通知を受け取る場合があります。</span><span class="sxs-lookup"><span data-stu-id="fa677-434">You may also provide your phone number to get notified with SMS, a voice call or both.</span></span>
    6. <span data-ttu-id="fa677-435">**[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fa677-435">Select **OK**.</span></span>

8. <span data-ttu-id="fa677-436">**アラート メール** の件名行をオーバーライドする場合は、[アクション] をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="fa677-436">**Customize Actions** if you like to override the subject line of the alert emails.</span></span>

9. <span data-ttu-id="fa677-437">ルールの名前と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="fa677-437">Specify a rule name and description.</span></span><br>
    <span data-ttu-id="fa677-438">**ルール名:** :::no-loc text="Microsoft Teams Rooms"::: ハードウェア障害アラート</span><span class="sxs-lookup"><span data-stu-id="fa677-438">**Rule Name:** :::no-loc text="Microsoft Teams Rooms"::: Hardware Failure Alert</span></span><br>
    <span data-ttu-id="fa677-439">**説明:** 最後の 1 時間以内にハードウェアの問題が発生したデバイスの一覧</span><span class="sxs-lookup"><span data-stu-id="fa677-439">**Description:** List of devices that encountered a hardware issue within the last hour</span></span><br>

10. <span data-ttu-id="fa677-440">目的の重大度を選択し、ルールが有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="fa677-440">Select the intended severity and make sure the rule is enabled.</span></span>

11. <span data-ttu-id="fa677-441">[アラート **ルールの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fa677-441">Select **Create alert rule**.</span></span>

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a><span data-ttu-id="fa677-442">アプリケーションの問題に関する電子メール :::no-loc text="Microsoft Teams Rooms"::: アラートを構成する</span><span class="sxs-lookup"><span data-stu-id="fa677-442">Configure an email alert for :::no-loc text="Microsoft Teams Rooms"::: application issues</span></span>

<span data-ttu-id="fa677-443">同じ手順を繰り返しますが、次のクエリを使用して、最後の 1 時間以内にアプリケーションの問題が発生したデバイスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="fa677-443">Repeat the same procedure but use the following query to list devices that have encountered application issues within the last hour.</span></span>

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

<span data-ttu-id="fa677-444">これで、アラートの定義が完了しました。</span><span class="sxs-lookup"><span data-stu-id="fa677-444">Now you've completed defining alerts.</span></span> <span data-ttu-id="fa677-445">上記の例を使用して、追加のアラートを定義できます。</span><span class="sxs-lookup"><span data-stu-id="fa677-445">You can define additional alerts by using the examples above.</span></span>

<span data-ttu-id="fa677-446">アラートが生成されると、前の 1 時間以内に問題が発生したデバイスを一覧表示する電子メールが届きます。</span><span class="sxs-lookup"><span data-stu-id="fa677-446">When an alert is generated, you'll get an email that lists the devices that encountered an issue within the last hour.</span></span>

<span data-ttu-id="fa677-447">![アラート :::no-loc text="Azure Monitor"::: 電子メールのサンプル](../media/Deploy-Azure-Monitor-6.png " :::no-loc text=&quot;Azure Monitor&quot;::: サンプル アラート 電子メール")</span><span class="sxs-lookup"><span data-stu-id="fa677-447">![Sample :::no-loc text="Azure Monitor"::: alert email](../media/Deploy-Azure-Monitor-6.png "Sample :::no-loc text=&quot;Azure Monitor&quot;::: alert email")</span></span>

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a><span data-ttu-id="fa677-448">すべてのデバイスを構成する :::no-loc text="Azure Monitoring":::</span><span class="sxs-lookup"><span data-stu-id="fa677-448">Configure all devices for :::no-loc text="Azure Monitoring":::</span></span>
<span data-ttu-id="fa677-449"><a name="configure_all_devices"></a>ダッシュボードとアラートを構成したら、すべてのデバイスでエージェントを設定して構成し、監視 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: のデプロイを完了できます。</span><span class="sxs-lookup"><span data-stu-id="fa677-449"><a name="configure_all_devices"> </a> After the dashboards and alerts are configured, you can set up and configure :::no-loc text="Microsoft Monitoring"::: agent on all :::no-loc text="Microsoft Teams Rooms"::: devices to complete your monitoring deployment.</span></span>

<span data-ttu-id="fa677-450">各デバイスにエージェントを手動でインストールして構成することもできますが、既存のソフトウェア展開ツールと方法を活用 :::no-loc text="Microsoft Monitoring"::: することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fa677-450">Although you can install and configure the :::no-loc text="Microsoft Monitoring"::: agent manually on each device, we highly recommend you leverage existing software deployment tools and methods.</span></span>

<span data-ttu-id="fa677-451">初めてデバイスをビルドする場合は、ビルド プロセスの一部としてエージェントのセットアップと構成 :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Microsoft Monitoring"::: の手順を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa677-451">If you're building your :::no-loc text="Microsoft Teams Rooms"::: devices for the first time, you might want to include the :::no-loc text="Microsoft Monitoring"::: agent setup and configuration steps as part of your build process.</span></span> <span data-ttu-id="fa677-452">詳細については、コマンド ラインを [使用したエージェントのインストールに関するページを参照してください](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="fa677-452">For more information, see [Install the agent using the command line](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).</span></span>

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a><span data-ttu-id="fa677-453">グループ ポリシー :::no-loc text="Microsoft Monitoring"::: オブジェクト (GPO) を使用したエージェントのデプロイ</span><span class="sxs-lookup"><span data-stu-id="fa677-453">Deploying :::no-loc text="Microsoft Monitoring"::: agent by using a Group Policy Object (GPO)</span></span>

<span data-ttu-id="fa677-454">を実装する前にデバイスを既にデプロイしている場合は、提供されているスクリプトを使用して、グループ ポリシー オブジェクトを使用してエージェントを :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitoring"::: :::no-loc text="Active Directory"::: 設定および構成できます。</span><span class="sxs-lookup"><span data-stu-id="fa677-454">If you already deployed your :::no-loc text="Microsoft Teams Rooms"::: devices before you implement :::no-loc text="Azure Monitoring":::, you can use the provided script to set up and configure the agents by using :::no-loc text="Active Directory"::: group policy objects.</span></span>

1.  <span data-ttu-id="fa677-455">共有ネットワーク パスを作成し、ドメイン コンピューター グループへの読み取 **りアクセス権を付与** します。</span><span class="sxs-lookup"><span data-stu-id="fa677-455">Create a shared network path and grant read access to **Domain Computers** group.</span></span>

2.  <span data-ttu-id="fa677-456">エージェントの 64 ビット バージョンを :::no-loc text="Microsoft Monitoring"::: からダウンロード :::no-loc text="Windows"::: します。 <https://go.microsoft.com/fwlink/?LinkID=517476></span><span class="sxs-lookup"><span data-stu-id="fa677-456">Download the 64-bit version of the :::no-loc text="Microsoft Monitoring"::: Agent for :::no-loc text="Windows"::: from <https://go.microsoft.com/fwlink/?LinkID=517476></span></span>

3.  <span data-ttu-id="fa677-457">セットアップ パッケージの内容をネットワーク共有に抽出します。</span><span class="sxs-lookup"><span data-stu-id="fa677-457">Extract the contents of the setup package into the network share.</span></span>
    1.  <span data-ttu-id="fa677-458">コマンド プロンプト ウィンドウを開き、/cMMASetup-AMD64.exe **実行します。**</span><span class="sxs-lookup"><span data-stu-id="fa677-458">Open a Command Prompt window, and then execute **MMASetup-AMD64.exe /c**</span></span>
    2.  <span data-ttu-id="fa677-459">作成した共有を指定し、コンテンツを抽出します。</span><span class="sxs-lookup"><span data-stu-id="fa677-459">Specify the share you just created, and extract the content.</span></span>

4.  <span data-ttu-id="fa677-460">新しいグループ ポリシー オブジェクトを作成し、マシン アカウントがある組織単位 :::no-loc text="Microsoft Teams Rooms"::: に割り当てる。</span><span class="sxs-lookup"><span data-stu-id="fa677-460">Create a new Group Policy Object and assign it to the organizational unit where :::no-loc text="Microsoft Teams Rooms"::: machine accounts are located.</span></span>

5.  <span data-ttu-id="fa677-461">PowerShell 実行ポリシーの構成:</span><span class="sxs-lookup"><span data-stu-id="fa677-461">Configure PowerShell execution policy:</span></span>
    1.  <span data-ttu-id="fa677-462">新しく作成したグループ ポリシー オブジェクトを編集し、[コンピューター構成ポリシー] \\ 管理用テンプレート コンポーネント \\ に \\ :::no-loc text="Windows"::: 移動します。 \\:::no-loc text="Windows PowerShell":::</span><span class="sxs-lookup"><span data-stu-id="fa677-462">Edit the newly created Group Policy Object and navigate to Computer Configuration \\ Policies \\ Administrative Templates \\ :::no-loc text="Windows"::: Components \\ :::no-loc text="Windows PowerShell":::</span></span>
    2.  <span data-ttu-id="fa677-463">[スクリプトの **実行を有効にする] を有効にして**、[**実行ポリシー] を [ローカル\*\*\*\*スクリプトを許可] に設定します**。</span><span class="sxs-lookup"><span data-stu-id="fa677-463">Enable the **Turn on Script Execution** and set **Execution Policy** to **Allow Local Scripts**.</span></span>

6.  <span data-ttu-id="fa677-464">スタートアップ スクリプトを構成します。</span><span class="sxs-lookup"><span data-stu-id="fa677-464">Configure the startup script:</span></span>
    1.  <span data-ttu-id="fa677-465">次のスクリプトをコピーし、次のスクリプトとしてInstall-MMAgent.ps1。</span><span class="sxs-lookup"><span data-stu-id="fa677-465">Copy the following script and save it as Install-MMAgent.ps1.</span></span>
    2.  <span data-ttu-id="fa677-466">構成に合わせて WorkspaceId、WorkspaceKey、SetupPath パラメーターを変更します。</span><span class="sxs-lookup"><span data-stu-id="fa677-466">Modify WorkspaceId, WorkspaceKey, and SetupPath parameters to match your configuration.</span></span>
    3.  <span data-ttu-id="fa677-467">同じグループ ポリシー オブジェクトを編集し、[コンピューター構成ポリシー] 設定 \\ \\ :::no-loc text="Windows"::: \\ (スタートアップ/シャットダウン) に移動します。</span><span class="sxs-lookup"><span data-stu-id="fa677-467">Edit the same Group Policy Object and navigate to Computer Configuration \\ Policies \\ :::no-loc text="Windows"::: Settings \\ Scripts (Startup/Shutdown)</span></span>
    4.  <span data-ttu-id="fa677-468">ダブルクリックして [スタートアップ]**を選択し\*\*\*\*、[PowerShell スクリプト] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fa677-468">Double-click to select **Startup**, and then select **PowerShell Scripts**.</span></span>
    5.  <span data-ttu-id="fa677-469">[ **ファイルの表示]** を選択し、Install-MMAgent.ps1 **ファイルを** そのフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="fa677-469">Select **Show Files**, and then copy the **Install-MMAgent.ps1** file to that folder.</span></span>
    6.  <span data-ttu-id="fa677-470">[追加 **] を選択** し、[参照] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fa677-470">Select **Add**, and then **Browse**.</span></span>
    7.  <span data-ttu-id="fa677-471">コピーした ps1 スクリプトを選択します。</span><span class="sxs-lookup"><span data-stu-id="fa677-471">Select the ps1 script you just copied.</span></span>

7.  <span data-ttu-id="fa677-472">:::no-loc text="Microsoft Teams Rooms"::: デバイスは、2 回目の再起動で :::no-loc text="Microsoft Monitoring"::: エージェントをインストールして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa677-472">:::no-loc text="Microsoft Teams Rooms"::: devices should install and configure the :::no-loc text="Microsoft Monitoring"::: agent with the second reboot.</span></span>

```PowerShell
# Install-MMAgent.ps1
<#
Date:        04/20/2018
Script:      Install-MMAgent.ps1
Version:     1.0
#>

# Set the parameters
$WorkspaceId = "<your workspace id>"
$WorkspaceKey = "<your workspace key>"
$SetupPath = "\\Server\Share"

$SetupParameters = "/qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1 OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE=0 OPINSIGHTS_WORKSPACE_ID=$WorkspaceId OPINSIGHTS_WORKSPACE_KEY=$WorkspaceKey AcceptEndUserLicenseAgreement=1"

# $SetupParameters = $SetupParameters + " OPINSIGHTS_PROXY_URL=<Proxy server URL> OPINSIGHTS_PROXY_USERNAME=<Proxy server username> OPINSIGHTS_PROXY_PASSWORD=<Proxy server password>"

# Start PowerShell logging
Start-Transcript -Path C:\Temp\MMA-Install.Log

# Check if the Microsoft Monitoring Agent is installed
$mma = New-Object -ComObject 'AgentConfigManager.MgmtSvcCfg'

# Check if the Microsoft Monitoring agent is installed
if (!$mma)
{
    #Install agent
    Start-Process -FilePath "$SetupPath\Setup.exe" -ArgumentList $SetupParameters -ErrorAction Stop -Wait
}

# Check if the agent has a valid configuration
$CheckMMA = $mma.GetCloudWorkspace($WorkspaceId).AgentId
if (!$CheckMMA)
{
    # Apply new configuration
    $mma.AddCloudWorkspace($WorkspaceId, $WorkspaceKey)
    $mma.ReloadConfiguration()
}

Stop-Transcript
```

> [!NOTE]
> <span data-ttu-id="fa677-473">エージェントの再構成、別の [ :::no-loc text="Log Analytics"::: ](/azure/azure-monitor/platform/agent-manage) ワークスペースへの移動、または初期インストール後のプロキシ設定の変更が必要な場合のエージェントの管理と保守に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa677-473">You can refer to the article [Managing and maintaining the :::no-loc text="Log Analytics"::: agent](/azure/azure-monitor/platform/agent-manage) when you need to reconfigure an agent, move it to a different workspace, or modify proxy settings after the initial installation.</span></span>

## <a name="additional-solutions"></a><span data-ttu-id="fa677-474">その他のソリューション</span><span class="sxs-lookup"><span data-stu-id="fa677-474">Additional Solutions</span></span>
<span data-ttu-id="fa677-475"><a name="Solutions"> </a></span><span class="sxs-lookup"><span data-stu-id="fa677-475"><a name="Solutions"> </a></span></span>

<span data-ttu-id="fa677-476">:::no-loc text="Azure Monitor"::: は、環境の監視に [役立つソリューション](/azure/azure-monitor/insights/solutions) ギャラリーを通じて組み込みの管理ソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="fa677-476">:::no-loc text="Azure Monitor"::: provides built-in management solutions through its [solution gallery](/azure/azure-monitor/insights/solutions) to further help you monitor your environment.</span></span> <span data-ttu-id="fa677-477">アラート管理ソリューションと[Agent](/azure/azure-monitor/platform/alert-management-solution) [ :::no-loc text="Azure Log Analytics"::: Health](/azure/azure-monitor/insights/solution-agenthealth)ソリューションもワークスペースに追加することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fa677-477">We highly recommend that you add [Alert Management](/azure/azure-monitor/platform/alert-management-solution) and [:::no-loc text="Azure Log Analytics"::: Agent Health](/azure/azure-monitor/insights/solution-agenthealth) solutions to your workspace as well.</span></span>

> [!NOTE]
> <span data-ttu-id="fa677-478">Agent Health ソリューションは、環境内の古いエージェントや破損したエージェントを特定するのに役立ちます。アラート管理ソリューションは、特定の期間に発生したアラートに関する詳細 :::no-loc text="Microsoft Monitoring"::: を提供します。</span><span class="sxs-lookup"><span data-stu-id="fa677-478">The Agent Health solution can help you identify outdated or broken :::no-loc text="Microsoft Monitoring"::: agents within your environment, and the Alert Management solution provides details about the alerts that have been raised within a given period.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa677-479">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa677-479">See also</span></span>

[<span data-ttu-id="fa677-480">を :::no-loc text="Microsoft Teams Rooms"::: 使用した計画管理 :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="fa677-480">Plan :::no-loc text="Microsoft Teams Rooms"::: management with :::no-loc text="Azure Monitor":::</span></span>](azure-monitor-plan.md)

[<span data-ttu-id="fa677-481">を :::no-loc text="Microsoft Teams Rooms"::: 使用してデバイスを管理する :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="fa677-481">Manage :::no-loc text="Microsoft Teams Rooms"::: devices with :::no-loc text="Azure Monitor":::</span></span>](azure-monitor-manage.md)