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
description: この記事では、Azure Monitor を使用して、統合されたエンドツーエンドの方法で Microsoft Teams Rooms デバイスの管理を展開する方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7046fc0010a4337ea14854e356600ccf3428f9d0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117595"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a><span data-ttu-id="eaf8a-103">次 :::no-loc text="Microsoft Teams Rooms"::: の方法で管理を展開します。 :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="eaf8a-103">Deploy :::no-loc text="Microsoft Teams Rooms"::: management with :::no-loc text="Azure Monitor":::</span></span>

<span data-ttu-id="eaf8a-104">この記事では、デバイスの統合されたエンドツーエンド管理をセットアップして展開する方法 :::no-loc text="Microsoft Teams Rooms"::: について説明します :::no-loc text="Azure Monitor"::: 。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-104">This article discusses how to set up and deploy integrated, end-to-end management of :::no-loc text="Microsoft Teams Rooms"::: devices by using :::no-loc text="Azure Monitor":::.</span></span>

<span data-ttu-id="eaf8a-105">会議室デバイスの管理に役立つ基本的なテレメトリとアラートを提供するために、その中 :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor"::: :::no-loc text="Microsoft Teams Rooms"::: を構成できます。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-105">You can configure :::no-loc text="Log Analytics"::: within :::no-loc text="Azure Monitor"::: to provide basic telemetry and alerts that will help you manage :::no-loc text="Microsoft Teams Rooms"::: meeting room devices.</span></span> <span data-ttu-id="eaf8a-106">管理ソリューションの成熟に合わせ、追加のデータと管理機能を展開して、デバイスの可用性とパフォーマンスの詳細なビューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-106">As your management solution matures, you might decide to deploy additional data and management capabilities to create a more detailed view of device availability and performance.</span></span>

<span data-ttu-id="eaf8a-107">このガイドに従って、次の例のようなダッシュボードを使用して、デバイスの可用性、アプリケーションとハードウェアの正常性、アプリケーションとオペレーティング システムのバージョンの配布に関する詳細な状態レポートを :::no-loc text="Microsoft Teams Rooms"::: 取得できます。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-107">By following this guide, you can use a dashboard like the following example to get detailed status reporting for device availability, application and hardware health, and :::no-loc text="Microsoft Teams Rooms"::: application and operating system version distribution.</span></span>

<span data-ttu-id="eaf8a-108">![Microsoft Teams の会議室のログ分析ビューのサンプルのスクリーンショット](../media/Deploy-Azure-Monitor-1.png "Microsoft Teams 会議室の [ログ分析] ビューの例")</span><span class="sxs-lookup"><span data-stu-id="eaf8a-108">![Screenshot of sample Log Analytics view for Microsoft Teams Rooms](../media/Deploy-Azure-Monitor-1.png "Sample Log Analytics view for Microsoft Teams Rooms")</span></span>

<span data-ttu-id="eaf8a-109">高いレベルでは、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-109">At a high level, you need to perform the following tasks:</span></span>


1. [<span data-ttu-id="eaf8a-110">構成を検証 :::no-loc text="Log Analytics"::: する</span><span class="sxs-lookup"><span data-stu-id="eaf8a-110">Validate :::no-loc text="Log Analytics"::: configuration</span></span>](azure-monitor-deploy.md#validate_LogAnalytics)
2. [<span data-ttu-id="eaf8a-111">管理セットアップ用にテスト デバイス :::no-loc text="Log Analytics"::: を構成する</span><span class="sxs-lookup"><span data-stu-id="eaf8a-111">Configure test devices for :::no-loc text="Log Analytics"::: management setup</span></span>](azure-monitor-deploy.md#configure_test_devices)
3. [<span data-ttu-id="eaf8a-112">カスタム フィールドをマップする</span><span class="sxs-lookup"><span data-stu-id="eaf8a-112">Map custom fields</span></span>](azure-monitor-deploy.md#Custom_fields)
4. [<span data-ttu-id="eaf8a-113">ビューを :::no-loc text="Microsoft Teams Rooms"::: 定義するには、 :::no-loc text="Log Analytics":::</span><span class="sxs-lookup"><span data-stu-id="eaf8a-113">Define the :::no-loc text="Microsoft Teams Rooms"::: views in :::no-loc text="Log Analytics":::</span></span>](azure-monitor-deploy.md#Define_Views)
5. [<span data-ttu-id="eaf8a-114">通知を定義する</span><span class="sxs-lookup"><span data-stu-id="eaf8a-114">Define alerts</span></span>](azure-monitor-deploy.md#Alerts)
6. [<span data-ttu-id="eaf8a-115">監視用のすべてのデバイスを構成する</span><span class="sxs-lookup"><span data-stu-id="eaf8a-115">Configure all devices for Monitoring</span></span>](azure-monitor-deploy.md#configure_all_devices)
7. [<span data-ttu-id="eaf8a-116">その他のソリューションを :::no-loc text="Azure Monitor"::: 構成する</span><span class="sxs-lookup"><span data-stu-id="eaf8a-116">Configure additional :::no-loc text="Azure Monitor"::: solutions</span></span>](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> <span data-ttu-id="eaf8a-117">構成は最小限ですが、オペレーティング システムを実行しているコンピューターを監視することもできますが、すべてのデバイスへのエージェントの展開を開始する前に実行する必要があるいくつかの具体的な手順がまだ :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: :::no-loc text="Windows"::: :::no-loc text="Microsoft Teams Rooms"::: 存在 :::no-loc text="Microsoft Teams Rooms"::: します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-117">Although with minimal configuration, :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: can monitor a computer running a :::no-loc text="Windows"::: operating system, there are still some :::no-loc text="Microsoft Teams Rooms":::–specific steps that you need to take before you start deploying agents to all :::no-loc text="Microsoft Teams Rooms"::: devices.</span></span>
> <span data-ttu-id="eaf8a-118">そのため、制御されたセットアップと構成に対して、すべての構成手順を正しい順序で実行することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-118">Therefore, we highly recommend you perform all configuration steps in the right order for a controlled setup and configuration.</span></span> <span data-ttu-id="eaf8a-119">結果の品質は、初期構成の品質によって大きな違いがあります。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-119">The quality of the end result very much depends on the quality of the initial configuration.</span></span>

## <a name="validate-no-loc-textlog-analytics-configuration"></a><span data-ttu-id="eaf8a-120">構成を検証 :::no-loc text="Log Analytics"::: する</span><span class="sxs-lookup"><span data-stu-id="eaf8a-120">Validate :::no-loc text="Log Analytics"::: configuration</span></span>
<span data-ttu-id="eaf8a-121"><a name="validate_LogAnalytics"> </a></span><span class="sxs-lookup"><span data-stu-id="eaf8a-121"><a name="validate_LogAnalytics"> </a></span></span>

<span data-ttu-id="eaf8a-122">デバイスからログの収集 :::no-loc text="Log Analytics"::: を開始するには、ワークスペースが必要 :::no-loc text="Microsoft Teams Rooms"::: です。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-122">You need to have a :::no-loc text="Log Analytics"::: workspace to start collecting logs from :::no-loc text="Microsoft Teams Rooms"::: devices.</span></span> <span data-ttu-id="eaf8a-123">ワークスペースは、独自のデータ リポジトリ、データ ソース、ソリューション :::no-loc text="Log Analytics"::: を持つ固有の環境です。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-123">A workspace is a unique :::no-loc text="Log Analytics"::: environment with its own data repository, data sources, and solutions.</span></span> <span data-ttu-id="eaf8a-124">既に既存のワークスペースがある場合は、それを使用して展開を監視するか、監視のニーズに固有の専用ワークスペース :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: を作成できます。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-124">If you already have an existing :::no-loc text="Log Analytics"::: workspace, you might use it to monitor your :::no-loc text="Microsoft Teams Rooms"::: deployment or alternatively, you can create a dedicated :::no-loc text="Log Analytics"::: workspace specific to your :::no-loc text="Microsoft Teams Rooms"::: monitoring needs.</span></span>

<span data-ttu-id="eaf8a-125">新しいワークスペースを作成する必要がある場合は、「ポータルでワークスペースを作成する」の :::no-loc text="Log Analytics"::: [ :::no-loc text="Log Analytics"::: 記事の手順に従 :::no-loc text="Azure"::: ってください。](/azure/azure-monitor/learn/quick-create-workspace)</span><span class="sxs-lookup"><span data-stu-id="eaf8a-125">If you need to create a new :::no-loc text="Log Analytics"::: workspace, follow the instructions in the article [Create a :::no-loc text="Log Analytics"::: workspace in the :::no-loc text="Azure"::: portal](/azure/azure-monitor/learn/quick-create-workspace)</span></span>

> [!NOTE]
> <span data-ttu-id="eaf8a-126">一緒に :::no-loc text="Log Analytics"::: 使用 :::no-loc text="Azure Monitor"::: するには、アクティブなサブスクリプションが必要 :::no-loc text="Azure"::: です。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-126">To use :::no-loc text="Log Analytics"::: with :::no-loc text="Azure Monitor":::, you need to have an active :::no-loc text="Azure"::: subscription.</span></span> <span data-ttu-id="eaf8a-127">サブスクリプションを持ってない場合は、開始点として無料試用版 :::no-loc text="Azure"::: サブスクリプションを作成できます。 [](https://azure.microsoft.com/free)</span><span class="sxs-lookup"><span data-stu-id="eaf8a-127">If you don't have an :::no-loc text="Azure"::: subscription, you can create [a free trial subscription](https://azure.microsoft.com/free) as a starting point.</span></span>

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a><span data-ttu-id="eaf8a-128">イベント :::no-loc text="Log Analytics"::: ログを収集 :::no-loc text="Microsoft Teams Rooms"::: するために構成する</span><span class="sxs-lookup"><span data-stu-id="eaf8a-128">Configure :::no-loc text="Log Analytics"::: to collect :::no-loc text="Microsoft Teams Rooms"::: event logs</span></span>

<span data-ttu-id="eaf8a-129">:::no-loc text="Log Analytics"::: 設定で指定されているイベント :::no-loc text="Windows"::: ログからのイベントのみを収集します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-129">:::no-loc text="Log Analytics"::: only collects events from the :::no-loc text="Windows"::: event logs that are specified in the settings.</span></span> <span data-ttu-id="eaf8a-130">ログごとに、選択した重大度のイベントだけが収集されます。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-130">For each log, only the events with the selected severities are collected.</span></span>

<span data-ttu-id="eaf8a-131">デバイスとアプリケーションの :::no-loc text="Log Analytics"::: 状態を監視するために必要なログを収集するために :::no-loc text="Microsoft Teams Rooms"::: 構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-131">You need to configure :::no-loc text="Log Analytics"::: to collect the logs required to monitor :::no-loc text="Microsoft Teams Rooms"::: device and application status.</span></span> <span data-ttu-id="eaf8a-132">:::no-loc text="Microsoft Teams Rooms"::: デバイスはイベント ログ **:::no-loc text="Skype Room System":::** を使用します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-132">:::no-loc text="Microsoft Teams Rooms"::: devices use the **:::no-loc text="Skype Room System":::** event log.</span></span>

<span data-ttu-id="eaf8a-133">イベントを :::no-loc text="Log Analytics"::: 収集するために構成 :::no-loc text="Microsoft Teams Rooms"::: するには[ :::no-loc text="Windows"::: :::no-loc text="Azure Monitor"::: 、](/azure/azure-monitor/platform/data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="eaf8a-133">To configure :::no-loc text="Log Analytics"::: to collect the :::no-loc text="Microsoft Teams Rooms"::: events, see [:::no-loc text="Windows"::: event log data sources in :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/data-sources-windows-events)</span></span>

<span data-ttu-id="eaf8a-134">![イベント ログの設定のスクリーンショット](../media/Deploy-Azure-Monitor-2.png "イベント ログの設定")</span><span class="sxs-lookup"><span data-stu-id="eaf8a-134">![Screenshot of event log settings](../media/Deploy-Azure-Monitor-2.png "Event log settings")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eaf8a-135">イベント ログの設定を構成し、イベント ログ名として入力し、[エラー]、[警告]、および [情報] チェック ボックス :::no-loc text="Windows"::: **:::no-loc text="Skype Room System":::** をオンにします。   </span><span class="sxs-lookup"><span data-stu-id="eaf8a-135">Configure :::no-loc text="Windows"::: Event Log settings and enter **:::no-loc text="Skype Room System":::** as event log name, and then select the **Error**, **Warning**, and **Information** check boxes.</span></span>

## <a name="configure-test-devices-for-azure-monitoring"></a><span data-ttu-id="eaf8a-136">Azure Monitoring のテスト デバイスを構成する</span><span class="sxs-lookup"><span data-stu-id="eaf8a-136">Configure test devices for Azure Monitoring</span></span>
<span data-ttu-id="eaf8a-137"><a name="configure_test_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="eaf8a-137"><a name="configure_test_devices"> </a></span></span>

<span data-ttu-id="eaf8a-138">関連するイベント :::no-loc text="Log Analytics"::: を監視するには、準備 :::no-loc text="Microsoft Teams Rooms"::: が必要です。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-138">You need to prepare :::no-loc text="Log Analytics"::: to be able to monitor :::no-loc text="Microsoft Teams Rooms":::–related events.</span></span> <span data-ttu-id="eaf8a-139">最初に、物理的にアクセスできる 1 つか 2 つのデバイスにエージェントを展開し、それらのテスト デバイスにデータを生成してワークスペースにプッシュする必要 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Log Analytics"::: があります。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-139">To start with, you need to deploy :::no-loc text="Microsoft Monitoring"::: agents to just one or two :::no-loc text="Microsoft Teams Rooms"::: devices that you have physical access to, and get those test devices generate some data and push it to the :::no-loc text="Log Analytics"::: workspace.</span></span>

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a><span data-ttu-id="eaf8a-140">エージェント :::no-loc text="Microsoft Monitoring"::: をインストールしてデバイスをテストする</span><span class="sxs-lookup"><span data-stu-id="eaf8a-140">Install :::no-loc text="Microsoft Monitoring"::: agents to test devices</span></span>

<span data-ttu-id="eaf8a-141">「コンピューターをサービスに接続する」に記載されている手順を使用して、エージェント :::no-loc text="Microsoft Monitoring"::: [ :::no-loc text="Windows"::: をテスト デバイス :::no-loc text="Log Analytics"::: に展開します :::no-loc text="Azure"::: ](/azure/azure-monitor/platform/agent-windows)。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-141">Deploy the :::no-loc text="Microsoft Monitoring"::: agent to the test devices by using the instructions provided in [Connect :::no-loc text="Windows"::: computers to the :::no-loc text="Log Analytics"::: service in :::no-loc text="Azure":::](/azure/azure-monitor/platform/agent-windows).</span></span> <span data-ttu-id="eaf8a-142">この記事では、エージェントを展開する手順、ワークスペース ID _ と _ 主キー :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Windows"::: :::no-loc text="Log Analytics":::  \* \*\*\* :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: を取得してデバイスを展開に接続するための手順、およびインスタンスへのエージェント接続を確認する手順について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-142">This article provides detailed information about the steps for deploying :::no-loc text="Microsoft Monitoring"::: Agent for :::no-loc text="Windows":::, instructions for obtaining the :::no-loc text="Log Analytics"::: ***Workspace ID** _ and the _ *_primary key_** to get :::no-loc text="Microsoft Teams Rooms"::: devices connected to your :::no-loc text="Azure Monitor"::: deployment, and steps to verify agent connectivity to :::no-loc text="Log Analytics"::: instance.</span></span>

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a><span data-ttu-id="eaf8a-143">サンプル イベントを生成 :::no-loc text="Microsoft Teams Rooms"::: する</span><span class="sxs-lookup"><span data-stu-id="eaf8a-143">Generate sample :::no-loc text="Microsoft Teams Rooms"::: events</span></span>

<span data-ttu-id="eaf8a-144">エージェントをテスト デバイスに展開した後、必要なイベント ログ データが収集 :::no-loc text="Microsoft Monitoring"::: されるのを確認します :::no-loc text="Azure Monitor"::: 。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-144">After the :::no-loc text="Microsoft Monitoring"::: agent is deployed onto the test devices, verify that the required event log data is collected by :::no-loc text="Azure Monitor":::.</span></span>

> [!NOTE]
> <span data-ttu-id="eaf8a-145">エージェントのインストール後にデバイスを再起動し、会議アプリが開始され、イベント ログに新しいイベントが :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: 生成されるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-145">Reboot the device after the installation of the :::no-loc text="Microsoft Monitoring"::: agent, and make sure that :::no-loc text="Microsoft Teams Rooms"::: Meeting app is started, so that it can generate new events into the Event Log.</span></span>

1.  <span data-ttu-id="eaf8a-146">ポータルにサインイン[ :::no-loc text="Microsoft Azure"::: し、](https://portal.azure.com)ワークスペースに移動 :::no-loc text="Log Analytics"::: して選択します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-146">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2.  <span data-ttu-id="eaf8a-147">デバイスによって生成されたハートビート イベントを一覧表示 :::no-loc text="Microsoft Teams Rooms"::: します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-147">List the heartbeat events generated by a :::no-loc text="Microsoft Teams Rooms"::: device:</span></span>
    1.  <span data-ttu-id="eaf8a-148">ワークスペースを選択し、[ **ログ** ] に移動し、クエリを使用して、カスタム フィールドを持つハートビート レコードを取得します :::no-loc text="Microsoft Teams Rooms"::: 。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-148">Select your workspace and go to **Logs** and use a query to retrieve the heartbeat records that will have the custom fields for :::no-loc text="Microsoft Teams Rooms":::.</span></span>
    2.  <span data-ttu-id="eaf8a-149">サンプル クエリ: `Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="eaf8a-149">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3.  <span data-ttu-id="eaf8a-150">クエリが、会議アプリによって生成されたイベントを含むログ レコードを :::no-loc text="Microsoft Teams Rooms"::: 返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-150">Make sure that the query returns log records that include events generated by the :::no-loc text="Microsoft Teams Rooms"::: meetings app.</span></span>

4.  <span data-ttu-id="eaf8a-151">ハードウェアの問題を生成し、必要なイベントがログイン状態を確認します :::no-loc text="Azure Log Analytics"::: 。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-151">Generate a hardware issue, and validate that the required events are logged in :::no-loc text="Azure Log Analytics":::.</span></span>
    1.  <span data-ttu-id="eaf8a-152">テスト システム上の周辺機器の 1 つを取り外 :::no-loc text="Microsoft Teams Rooms"::: します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-152">Unplug one of the peripheral devices on the test :::no-loc text="Microsoft Teams Rooms"::: system.</span></span> <span data-ttu-id="eaf8a-153">カメラ、スピーカーフォン、マイク、フロント ルームディスプレイなど</span><span class="sxs-lookup"><span data-stu-id="eaf8a-153">This could be the camera, speakerphone, microphone, or Front Room Display</span></span>
    2.  <span data-ttu-id="eaf8a-154">イベント ログが入力されるのを 10 分待ちます :::no-loc text="Azure Log Analytics"::: 。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-154">Wait 10 minutes for the event log to be populated in :::no-loc text="Azure Log Analytics":::.</span></span>
    3.  <span data-ttu-id="eaf8a-155">クエリを使用してハードウェア エラー イベントを一覧表示します。 `Event | where Source == "SRS-App" and EventID == 3001`</span><span class="sxs-lookup"><span data-stu-id="eaf8a-155">Use a query to list hardware error events: `Event | where Source == "SRS-App" and EventID == 3001`</span></span>

5.  <span data-ttu-id="eaf8a-156">アプリケーションの問題を生成し、必要なイベントがログに記録される検証を行います。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-156">Generate an application issue, and validate that the required events are logged.</span></span>
    1.  <span data-ttu-id="eaf8a-157">アプリケーション :::no-loc text="Microsoft Teams Rooms"::: 構成を変更し、正しくないセッション開始プロトコル (SIP) アドレス/パスワードのペアを入力します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-157">Modify :::no-loc text="Microsoft Teams Rooms"::: application configuration, and type an incorrect Session Initiation Protocol (SIP) address/password pair.</span></span>
    2.  <span data-ttu-id="eaf8a-158">イベント ログが入力されるのを 10 分待ちます :::no-loc text="Azure Log Analytics"::: 。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-158">Wait 10 minutes for the event log to be populated in :::no-loc text="Azure Log Analytics":::.</span></span>
    3.  <span data-ttu-id="eaf8a-159">クエリを使用して、アプリケーションのエラー イベントを一覧表示します。 `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span><span class="sxs-lookup"><span data-stu-id="eaf8a-159">Use a query to list application error events: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eaf8a-160">これらのサンプル イベント ログは、カスタム フィールドを構成する前に必要です。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-160">These sample event logs are required before custom fields can be configured.</span></span> <span data-ttu-id="eaf8a-161">必要なイベント ログを収集するまで、次の手順に進む必要はありません。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-161">Don't proceed to the next step until you have collected the required event logs.</span></span>

## <a name="map-custom-fields"></a><span data-ttu-id="eaf8a-162">カスタム フィールドをマップする</span><span class="sxs-lookup"><span data-stu-id="eaf8a-162">Map custom fields</span></span>
<span data-ttu-id="eaf8a-163"><a name="Custom_fields"> </a></span><span class="sxs-lookup"><span data-stu-id="eaf8a-163"><a name="Custom_fields"> </a></span></span>

<span data-ttu-id="eaf8a-164">カスタム フィールドを使用して、イベント ログから特定のデータを抽出します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-164">You use custom fields to extract specific data from the event logs.</span></span> <span data-ttu-id="eaf8a-165">後でタイル、ダッシュボード ビュー、通知で使用するカスタム フィールドを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-165">You need to define custom fields that will be used later with your tiles, dashboard views, and alerts.</span></span> <span data-ttu-id="eaf8a-166">カスタム[フィールドの :::no-loc text="Log Analytics"::: 作成を](/azure/azure-monitor/platform/custom-fields)開始する前に、「カスタム フィールド」を参照し、概念を理解してください。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-166">See [Custom fields in :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/custom-fields) and become familiar with the concepts before you start creating your custom fields.</span></span>

<span data-ttu-id="eaf8a-167">キャプチャされたイベント ログからカスタム フィールドを抽出するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-167">To extract your custom fields out of the captured event logs, follow these steps:</span></span>

1.  <span data-ttu-id="eaf8a-168">ポータルにサインイン[ :::no-loc text="Microsoft Azure"::: し、](https://portal.azure.com)ワークスペースに移動 :::no-loc text="Log Analytics"::: して選択します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-168">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2. <span data-ttu-id="eaf8a-169">デバイスによって生成されたイベントを一覧表示 :::no-loc text="Microsoft Teams Rooms"::: します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-169">List the events generated by a :::no-loc text="Microsoft Teams Rooms"::: device:</span></span>
   1.  <span data-ttu-id="eaf8a-170">[ログ **] に** 移動し、クエリを使用して、カスタム フィールドを含むレコードを取得します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-170">Go to **Logs** and use a query to retrieve the records that will have the custom field.</span></span>
   2.  <span data-ttu-id="eaf8a-171">サンプル クエリ: `Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="eaf8a-171">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3. <span data-ttu-id="eaf8a-172">レコードのいずれかを選択し、左側のボタンを選択して、フィールド抽出ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-172">Select one of the records, select the button to the left, and start the field extraction wizard.</span></span>
4. <span data-ttu-id="eaf8a-173">RenderedDescription から抽出するデータを強調表示し、フィールド タイトルを指定します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-173">Highlight the data you'd like to extract from the RenderedDescription and provide a Field Title.</span></span> <span data-ttu-id="eaf8a-174">使用する必要があるフィールド名は、表 1 に示されています。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-174">The field names that you should use are provided in Table 1.</span></span>
5. <span data-ttu-id="eaf8a-175">表 1 に示すマッピング *を使用します*。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-175">Use the mappings shown in *Table 1*.</span></span> <span data-ttu-id="eaf8a-176">:::no-loc text="Log Analytics":::は、新しいフィールド **\_ を定義** するときに CF 文字列を自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-176">:::no-loc text="Log Analytics"::: will automatically append the **\_CF** string when you define the new field.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eaf8a-177">すべての JSON とフィールドでは大文字 :::no-loc text="Log Analytics"::: と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-177">Remember that all JSON and :::no-loc text="Log Analytics"::: fields are case-sensitive.</span></span>
> 
> <span data-ttu-id="eaf8a-178">次の表のカスタム フィールドごとに必要なクエリに注意してください。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-178">Pay attention to the queries required for each custom field in the table below.</span></span> <span data-ttu-id="eaf8a-179">ユーザー設定フィールドの値を正常に抽出するには、正 :::no-loc text="Log Analytics"::: しいクエリを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-179">You need to use the correct queries for :::no-loc text="Log Analytics"::: to successfully extract custom field values.</span></span>
> 
<span data-ttu-id="eaf8a-180">**表 1**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-180">**Table 1**</span></span>

| <span data-ttu-id="eaf8a-181">**JSON フィールド**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-181">**JSON field**</span></span>                   | <span data-ttu-id="eaf8a-182">**:::no-loc text="Log Analytics"::: ユーザー設定フィールド**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-182">**:::no-loc text="Log Analytics"::: custom field**</span></span> | <span data-ttu-id="eaf8a-183">**イベント ID**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-183">**Event ID**</span></span> | <span data-ttu-id="eaf8a-184">**抽出で使用するクエリ**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-184">**Query to use with the extraction**</span></span>                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| <span data-ttu-id="eaf8a-185">説明</span><span class="sxs-lookup"><span data-stu-id="eaf8a-185">Description</span></span>                      | <span data-ttu-id="eaf8a-186">SRSEventDescription</span><span class="sxs-lookup"><span data-stu-id="eaf8a-186">SRSEventDescription</span></span>         | <span data-ttu-id="eaf8a-187">**2000**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-187">**2000**</span></span>     | <span data-ttu-id="eaf8a-188">\|Source == "SRS-App" と EventID == 2000 のイベント</span><span class="sxs-lookup"><span data-stu-id="eaf8a-188">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="eaf8a-189">ResourceState</span><span class="sxs-lookup"><span data-stu-id="eaf8a-189">ResourceState</span></span>                    | <span data-ttu-id="eaf8a-190">SRSResourceState</span><span class="sxs-lookup"><span data-stu-id="eaf8a-190">SRSResourceState</span></span>            | <span data-ttu-id="eaf8a-191">**2000**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-191">**2000**</span></span>     | <span data-ttu-id="eaf8a-192">\|Source == "SRS-App" と EventID == 2000 のイベント</span><span class="sxs-lookup"><span data-stu-id="eaf8a-192">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="eaf8a-193">OperationName</span><span class="sxs-lookup"><span data-stu-id="eaf8a-193">OperationName</span></span>                    | <span data-ttu-id="eaf8a-194">SRSOperationName</span><span class="sxs-lookup"><span data-stu-id="eaf8a-194">SRSOperationName</span></span>            | <span data-ttu-id="eaf8a-195">**2000**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-195">**2000**</span></span>     | <span data-ttu-id="eaf8a-196">\|Source == "SRS-App" と EventID == 2000 のイベント</span><span class="sxs-lookup"><span data-stu-id="eaf8a-196">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="eaf8a-197">OperationResult</span><span class="sxs-lookup"><span data-stu-id="eaf8a-197">OperationResult</span></span>                  | <span data-ttu-id="eaf8a-198">SRSOperationResult</span><span class="sxs-lookup"><span data-stu-id="eaf8a-198">SRSOperationResult</span></span>          | <span data-ttu-id="eaf8a-199">**2000**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-199">**2000**</span></span>     | <span data-ttu-id="eaf8a-200">\|Source == "SRS-App" と EventID == 2000 のイベント</span><span class="sxs-lookup"><span data-stu-id="eaf8a-200">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="eaf8a-201">OS</span><span class="sxs-lookup"><span data-stu-id="eaf8a-201">OS</span></span>                               | <span data-ttu-id="eaf8a-202">SRSOSVersion</span><span class="sxs-lookup"><span data-stu-id="eaf8a-202">SRSOSVersion</span></span>                | <span data-ttu-id="eaf8a-203">**2000**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-203">**2000**</span></span>     | <span data-ttu-id="eaf8a-204">\|Source == "SRS-App" と EventID == 2000 のイベント</span><span class="sxs-lookup"><span data-stu-id="eaf8a-204">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="eaf8a-205">OSVersion</span><span class="sxs-lookup"><span data-stu-id="eaf8a-205">OSVersion</span></span>                        | <span data-ttu-id="eaf8a-206">SRSOSLongVersion</span><span class="sxs-lookup"><span data-stu-id="eaf8a-206">SRSOSLongVersion</span></span>            | <span data-ttu-id="eaf8a-207">**2000**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-207">**2000**</span></span>     | <span data-ttu-id="eaf8a-208">\|Source == "SRS-App" および EventID == 2000 のイベント</span><span class="sxs-lookup"><span data-stu-id="eaf8a-208">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="eaf8a-209">Alias</span><span class="sxs-lookup"><span data-stu-id="eaf8a-209">Alias</span></span>                            | <span data-ttu-id="eaf8a-210">SRSAlias</span><span class="sxs-lookup"><span data-stu-id="eaf8a-210">SRSAlias</span></span>                    | <span data-ttu-id="eaf8a-211">**2000**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-211">**2000**</span></span>     | <span data-ttu-id="eaf8a-212">\|Source == "SRS-App" および EventID == 2000 のイベント</span><span class="sxs-lookup"><span data-stu-id="eaf8a-212">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="eaf8a-213">DisplayName</span><span class="sxs-lookup"><span data-stu-id="eaf8a-213">DisplayName</span></span>                      | <span data-ttu-id="eaf8a-214">SRSDisplayName</span><span class="sxs-lookup"><span data-stu-id="eaf8a-214">SRSDisplayName</span></span>              | <span data-ttu-id="eaf8a-215">**2000**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-215">**2000**</span></span>     | <span data-ttu-id="eaf8a-216">\|Source == "SRS-App" と EventID == 2000 のイベント</span><span class="sxs-lookup"><span data-stu-id="eaf8a-216">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="eaf8a-217">AppVersion</span><span class="sxs-lookup"><span data-stu-id="eaf8a-217">AppVersion</span></span>                       | <span data-ttu-id="eaf8a-218">SRSAppVersion</span><span class="sxs-lookup"><span data-stu-id="eaf8a-218">SRSAppVersion</span></span>               | <span data-ttu-id="eaf8a-219">**2000**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-219">**2000**</span></span>     | <span data-ttu-id="eaf8a-220">\|Source == "SRS-App" と EventID == 2000 のイベント</span><span class="sxs-lookup"><span data-stu-id="eaf8a-220">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="eaf8a-221">IPv4Address</span><span class="sxs-lookup"><span data-stu-id="eaf8a-221">IPv4Address</span></span>                      | <span data-ttu-id="eaf8a-222">SRSIPv4Address</span><span class="sxs-lookup"><span data-stu-id="eaf8a-222">SRSIPv4Address</span></span>              | <span data-ttu-id="eaf8a-223">**2000**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-223">**2000**</span></span>     | <span data-ttu-id="eaf8a-224">\|Source == "SRS-App" と EventID == 2000 のイベント</span><span class="sxs-lookup"><span data-stu-id="eaf8a-224">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="eaf8a-225">IPv6Address</span><span class="sxs-lookup"><span data-stu-id="eaf8a-225">IPv6Address</span></span>                      | <span data-ttu-id="eaf8a-226">SRSIPv6Address</span><span class="sxs-lookup"><span data-stu-id="eaf8a-226">SRSIPv6Address</span></span>              | <span data-ttu-id="eaf8a-227">**2000**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-227">**2000**</span></span>     | <span data-ttu-id="eaf8a-228">\|Source == "SRS-App" と EventID == 2000 のイベント</span><span class="sxs-lookup"><span data-stu-id="eaf8a-228">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="eaf8a-229">電話会議マイクの状態</span><span class="sxs-lookup"><span data-stu-id="eaf8a-229">Conference Microphone status</span></span>     | <span data-ttu-id="eaf8a-230">SRSConfMicrophoneStatus</span><span class="sxs-lookup"><span data-stu-id="eaf8a-230">SRSConfMicrophoneStatus</span></span>     | <span data-ttu-id="eaf8a-231">**3001**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-231">**3001**</span></span>     | <span data-ttu-id="eaf8a-232">\|Source == "SRS-App" と EventID == 3001 のイベント</span><span class="sxs-lookup"><span data-stu-id="eaf8a-232">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="eaf8a-233">電話会議のスピーカーの状態</span><span class="sxs-lookup"><span data-stu-id="eaf8a-233">Conference Speaker status</span></span>        | <span data-ttu-id="eaf8a-234">SRSConfSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="eaf8a-234">SRSConfSpeakerStatus</span></span>        | <span data-ttu-id="eaf8a-235">**3001**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-235">**3001**</span></span>     | <span data-ttu-id="eaf8a-236">\|Source == "SRS-App" と EventID == 3001 のイベント</span><span class="sxs-lookup"><span data-stu-id="eaf8a-236">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="eaf8a-237">既定のスピーカーの状態</span><span class="sxs-lookup"><span data-stu-id="eaf8a-237">Default Speaker status</span></span>           | <span data-ttu-id="eaf8a-238">SRSDefaultSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="eaf8a-238">SRSDefaultSpeakerStatus</span></span>     | <span data-ttu-id="eaf8a-239">**3001**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-239">**3001**</span></span>     | <span data-ttu-id="eaf8a-240">\|Source == "SRS-App" と EventID == 3001 のイベント</span><span class="sxs-lookup"><span data-stu-id="eaf8a-240">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="eaf8a-241">カメラの状態</span><span class="sxs-lookup"><span data-stu-id="eaf8a-241">Camera status</span></span>                    | <span data-ttu-id="eaf8a-242">SRSCameraStatus</span><span class="sxs-lookup"><span data-stu-id="eaf8a-242">SRSCameraStatus</span></span>             | <span data-ttu-id="eaf8a-243">**3001**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-243">**3001**</span></span>     | <span data-ttu-id="eaf8a-244">\|Source == "SRS-App" と EventID == 3001 のイベント</span><span class="sxs-lookup"><span data-stu-id="eaf8a-244">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="eaf8a-245">[ルームの表示の前] の状態</span><span class="sxs-lookup"><span data-stu-id="eaf8a-245">Front of Room Display status</span></span>     | <span data-ttu-id="eaf8a-246">SRSFORDStatus</span><span class="sxs-lookup"><span data-stu-id="eaf8a-246">SRSFORDStatus</span></span>               | <span data-ttu-id="eaf8a-247">**3001**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-247">**3001**</span></span>     | <span data-ttu-id="eaf8a-248">\|Source == "SRS-App" と EventID == 3001 のイベント</span><span class="sxs-lookup"><span data-stu-id="eaf8a-248">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="eaf8a-249">モーション センサーの状態</span><span class="sxs-lookup"><span data-stu-id="eaf8a-249">Motion Sensor status</span></span>             | <span data-ttu-id="eaf8a-250">SRSMotionSensorStatus</span><span class="sxs-lookup"><span data-stu-id="eaf8a-250">SRSMotionSensorStatus</span></span>       | <span data-ttu-id="eaf8a-251">**3001**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-251">**3001**</span></span>     | <span data-ttu-id="eaf8a-252">\|Source == "SRS-App" と EventID == 3001 のイベント</span><span class="sxs-lookup"><span data-stu-id="eaf8a-252">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="eaf8a-253">HDMI 取り込みの状態</span><span class="sxs-lookup"><span data-stu-id="eaf8a-253">HDMI Ingest status</span></span>               | <span data-ttu-id="eaf8a-254">SRSHDMIIngestStatus</span><span class="sxs-lookup"><span data-stu-id="eaf8a-254">SRSHDMIIngestStatus</span></span>         | <span data-ttu-id="eaf8a-255">**3001**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-255">**3001**</span></span>     | <span data-ttu-id="eaf8a-256">\|Source == "SRS-App" と EventID == 3001 のイベント</span><span class="sxs-lookup"><span data-stu-id="eaf8a-256">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a><span data-ttu-id="eaf8a-257">ビューを :::no-loc text="Microsoft Teams Rooms"::: 定義するには、 :::no-loc text="Log Analytics":::</span><span class="sxs-lookup"><span data-stu-id="eaf8a-257">Define the :::no-loc text="Microsoft Teams Rooms"::: views in :::no-loc text="Log Analytics":::</span></span>
<span data-ttu-id="eaf8a-258"><a name="Define_Views"> </a></span><span class="sxs-lookup"><span data-stu-id="eaf8a-258"><a name="Define_Views"> </a></span></span>

<span data-ttu-id="eaf8a-259">データが収集され、カスタム フィールドがマップされた後は、ビュー デザイナーを使用して、イベントを監視するさまざまなタイルを含むダッシュボードを作成 :::no-loc text="Microsoft Teams Rooms"::: できます。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-259">After data is collected and custom fields are mapped, you can use View Designer to develop a dashboard containing various tiles to monitor :::no-loc text="Microsoft Teams Rooms"::: events.</span></span> <span data-ttu-id="eaf8a-260">ビュー デザイナーを使用して、次のタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-260">Use View Designer to create the following tiles.</span></span> <span data-ttu-id="eaf8a-261">詳細については、「ビュー デザイナー[を使用してカスタム ビューを :::no-loc text="Log Analytics"::: 作成する」を参照してください。](/azure/azure-monitor/platform/view-designer)</span><span class="sxs-lookup"><span data-stu-id="eaf8a-261">For more information, see [Create custom views by using View Designer in :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/view-designer)</span></span>

> [!NOTE]
> <span data-ttu-id="eaf8a-262">ダッシュボード タイルが正常に動作するには、このガイドの前の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-262">Previous steps in this guide should have been completed for the dashboard tiles to work properly.</span></span>

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a><span data-ttu-id="eaf8a-263">インポート方法を使用して Microsoft Teams Rooms ダッシュボードを作成する</span><span class="sxs-lookup"><span data-stu-id="eaf8a-263">Create a Microsoft Teams Rooms dashboard by using the import method</span></span>

<span data-ttu-id="eaf8a-264">ダッシュボードをインポートして :::no-loc text="Microsoft Teams Rooms"::: 、デバイスの監視をすばやく開始できます。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-264">You can import an :::no-loc text="Microsoft Teams Rooms"::: dashboard and start monitoring your devices quickly.</span></span> <span data-ttu-id="eaf8a-265">ダッシュボードをインポートするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-265">Take the following steps to import the dashboard:</span></span>

1.  <span data-ttu-id="eaf8a-266">[SkypeRoomSystems_v2.omsview ダッシュボード ファイルを](https://go.microsoft.com/fwlink/?linkid=835675)取得します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-266">Get the [SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675) dashboard file.</span></span>
2.  <span data-ttu-id="eaf8a-267">ポータルにサインイン[ :::no-loc text="Microsoft Azure"::: し、](https://portal.azure.com)ワークスペースに移動 :::no-loc text="Log Analytics"::: して選択します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-267">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>
3.  <span data-ttu-id="eaf8a-268">ビュー **デザイナーを開きます**。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-268">Open **View Designer**.</span></span>
4.  <span data-ttu-id="eaf8a-269">[ **インポート]** を選択し **、SkypeRoomSystems_v2.omsview ファイルを選択** します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-269">Select **Import**, and then select the **SkypeRoomSystems_v2.omsview** file.</span></span>
5.  <span data-ttu-id="eaf8a-270">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-270">Select **Save**.</span></span>

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a><span data-ttu-id="eaf8a-271">Microsoft Teams の会議室ダッシュボードを手動で作成する</span><span class="sxs-lookup"><span data-stu-id="eaf8a-271">Create a Microsoft Teams Rooms dashboard manually</span></span>

<span data-ttu-id="eaf8a-272">または、独自のダッシュボードを作成し、監視するタイルのみを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-272">Alternatively, you can create your own dashboard and add only the tiles that you wish to monitor.</span></span>

#### <a name="configure-the-overview-tile"></a><span data-ttu-id="eaf8a-273">概要タイルを構成する</span><span class="sxs-lookup"><span data-stu-id="eaf8a-273">Configure the Overview Tile</span></span>

1.  <span data-ttu-id="eaf8a-274">ビュー **デザイナーを開きます**。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-274">Open **View Designer**.</span></span>
2.  <span data-ttu-id="eaf8a-275">[ **概要] タイルを** 選択し、ギャラリーから **2 つの** 数字を選択します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-275">Select **Overview Tile**, and then select **Two numbers** from the gallery.</span></span>
3.  <span data-ttu-id="eaf8a-276">タイルに名前を付 **:::no-loc text="Microsoft Teams Rooms":::** け.</span><span class="sxs-lookup"><span data-stu-id="eaf8a-276">Name the tile **:::no-loc text="Microsoft Teams Rooms":::**.</span></span>
4.  <span data-ttu-id="eaf8a-277">最初のタイル **を定義する**:</span><span class="sxs-lookup"><span data-stu-id="eaf8a-277">Define the **First Tile**:</span></span><br>
    <span data-ttu-id="eaf8a-278">**凡例:** 先月に少なくとも 1 回はハートビートを送信したデバイス</span><span class="sxs-lookup"><span data-stu-id="eaf8a-278">**Legend:** Devices that sent a heartbeat at least once within the last month</span></span><br>
    <span data-ttu-id="eaf8a-279">**クエリ:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="eaf8a-279">**Query:** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
5.  <span data-ttu-id="eaf8a-280">2 つ目 **のタイルを定義する**:</span><span class="sxs-lookup"><span data-stu-id="eaf8a-280">Define the **Second Tile**:</span></span><br>
    <span data-ttu-id="eaf8a-281">**凡例:** 最後の 1 時間以内にハートビートを送信したアクティブ なデバイス</span><span class="sxs-lookup"><span data-stu-id="eaf8a-281">**Legend:** Active devices that sent a heartbeat within the last hour</span></span><br>
    <span data-ttu-id="eaf8a-282">**クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="eaf8a-282">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
6.  <span data-ttu-id="eaf8a-283">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-283">Select **Apply**.</span></span>

### <a name="create-a-tile-that-displays-active-devices"></a><span data-ttu-id="eaf8a-284">アクティブなデバイスを表示するタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="eaf8a-284">Create a tile that displays active devices</span></span>

1.  <span data-ttu-id="eaf8a-285">[ダッシュボード **の表示] を** 選び、タイルの追加を開始します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-285">Select **View Dashboard** to start adding your tiles.</span></span>
2.  <span data-ttu-id="eaf8a-286">ギャラリー **から [番号&リスト** を選択する</span><span class="sxs-lookup"><span data-stu-id="eaf8a-286">Select **Number & list** from the gallery</span></span>
3.  <span data-ttu-id="eaf8a-287">[全般] プロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-287">Define the **General** properties:</span></span><br>
    <span data-ttu-id="eaf8a-288">**グループ タイトル:** Heartbeat の状態</span><span class="sxs-lookup"><span data-stu-id="eaf8a-288">**Group Title:** Heartbeat Status</span></span><br>
    <span data-ttu-id="eaf8a-289">**新しいグループ:** 選択されている</span><span class="sxs-lookup"><span data-stu-id="eaf8a-289">**New Group:** Selected</span></span>
4.  <span data-ttu-id="eaf8a-290">タイルのプロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-290">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="eaf8a-291">**凡例:** アクティブ なデバイス (過去 20 分間に送信されたハートビート)</span><span class="sxs-lookup"><span data-stu-id="eaf8a-291">**Legend:** Active devices (heartbeat sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="eaf8a-292">**タイルのクエリ:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="eaf8a-292">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span></span>
5.  <span data-ttu-id="eaf8a-293">リストのプロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-293">Define the **List** properties:</span></span><br>
    <span data-ttu-id="eaf8a-294">**リスト クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="eaf8a-294">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
6.  <span data-ttu-id="eaf8a-295">列タイトル **を定義する**:</span><span class="sxs-lookup"><span data-stu-id="eaf8a-295">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="eaf8a-296">**名前:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="eaf8a-296">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="eaf8a-297">**値:** Last Heartbeat</span><span class="sxs-lookup"><span data-stu-id="eaf8a-297">**Value:** Last Heartbeat</span></span>
7.  <span data-ttu-id="eaf8a-298">ナビゲーション **クエリを定義します**。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-298">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="eaf8a-299">[適用 **] を選択** し、[閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-299">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a><span data-ttu-id="eaf8a-300">接続の問題があるデバイスを表示するタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="eaf8a-300">Create a tile that displays devices that have connectivity issues</span></span>

1.  <span data-ttu-id="eaf8a-301">ギャラリー **から [番号&** リストを選択し、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-301">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="eaf8a-302">[全般] プロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-302">Define the **General** properties:</span></span><br>
    <span data-ttu-id="eaf8a-303">**グループ タイトル:** 空のままにする</span><span class="sxs-lookup"><span data-stu-id="eaf8a-303">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="eaf8a-304">**新しいグループ:** 選択されていない</span><span class="sxs-lookup"><span data-stu-id="eaf8a-304">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="eaf8a-305">タイルのプロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-305">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="eaf8a-306">**凡例:** 非アクティブデバイス (過去 20 分間に送信されたハートビート メッセージなし)</span><span class="sxs-lookup"><span data-stu-id="eaf8a-306">**Legend:** Inactive Devices (no heartbeat message sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="eaf8a-307">**タイルのクエリ:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span><span class="sxs-lookup"><span data-stu-id="eaf8a-307">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span></span>
4.  <span data-ttu-id="eaf8a-308">リストのプロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-308">Define the **List** properties:</span></span><br>
    <span data-ttu-id="eaf8a-309">**リスト クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="eaf8a-309">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="eaf8a-310">列タイトル **を定義する**:</span><span class="sxs-lookup"><span data-stu-id="eaf8a-310">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="eaf8a-311">**名前:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="eaf8a-311">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="eaf8a-312">**値:** Last Heartbeat</span><span class="sxs-lookup"><span data-stu-id="eaf8a-312">**Value:** Last Heartbeat</span></span>
6.  <span data-ttu-id="eaf8a-313">ナビゲーション **クエリを定義する**:</span><span class="sxs-lookup"><span data-stu-id="eaf8a-313">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="eaf8a-314">[適用 **] を選択** し、[閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-314">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a><span data-ttu-id="eaf8a-315">ハードウェア エラーが発生しているデバイスを表示するタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="eaf8a-315">Create a tile that displays devices that have a hardware error</span></span>

1.  <span data-ttu-id="eaf8a-316">ギャラリー **から [番号&** リストを選択し、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-316">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="eaf8a-317">[全般] プロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-317">Define the **General** properties:</span></span><br>
    <span data-ttu-id="eaf8a-318">**グループ タイトル:** ハードウェアの状態</span><span class="sxs-lookup"><span data-stu-id="eaf8a-318">**Group Title:** Hardware Status</span></span><br>
    <span data-ttu-id="eaf8a-319">**新しいグループ:** 選択されている</span><span class="sxs-lookup"><span data-stu-id="eaf8a-319">**New Group:** Selected</span></span>
3.  <span data-ttu-id="eaf8a-320">タイルのプロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-320">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="eaf8a-321">**凡例:** 過去 1 時間にハードウェア エラーが発生したデバイス</span><span class="sxs-lookup"><span data-stu-id="eaf8a-321">**Legend:** Devices that experienced a hardware error in the last hour</span></span><br>
    <span data-ttu-id="eaf8a-322">**タイルのクエリ:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="eaf8a-322">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="eaf8a-323">リストのプロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-323">Define the **List** properties:</span></span><br>
    <span data-ttu-id="eaf8a-324">**リスト クエリ:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="eaf8a-324">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="eaf8a-325">列タイトル **を定義する**:</span><span class="sxs-lookup"><span data-stu-id="eaf8a-325">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="eaf8a-326">**名前:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="eaf8a-326">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="eaf8a-327">**値:** 最後のエラー</span><span class="sxs-lookup"><span data-stu-id="eaf8a-327">**Value:** Last Error</span></span>
6.  <span data-ttu-id="eaf8a-328">ナビゲーション **クエリを定義する**:</span><span class="sxs-lookup"><span data-stu-id="eaf8a-328">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="eaf8a-329">[適用 **] を選択** し、[閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-329">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a><span data-ttu-id="eaf8a-330">オペレーティング システムのバージョンを表示する :::no-loc text="Microsoft Teams Rooms"::: タイルを作成する</span><span class="sxs-lookup"><span data-stu-id="eaf8a-330">Create a tile that displays :::no-loc text="Microsoft Teams Rooms"::: Operating System versions</span></span>

1.  <span data-ttu-id="eaf8a-331">ギャラリー **から [ドーナツ&を** 選び、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-331">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="eaf8a-332">[全般] プロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-332">Define the **General** properties:</span></span><br>
    <span data-ttu-id="eaf8a-333">**グループ タイトル:** オペレーティング システムの詳細</span><span class="sxs-lookup"><span data-stu-id="eaf8a-333">**Group Title:** Operating System details</span></span><br>
    <span data-ttu-id="eaf8a-334">**新しいグループ:** 選択されている</span><span class="sxs-lookup"><span data-stu-id="eaf8a-334">**New Group:** Selected</span></span>
3.  <span data-ttu-id="eaf8a-335">ヘッダープロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-335">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="eaf8a-336">**タイトル:** オペレーティング システムのバージョン</span><span class="sxs-lookup"><span data-stu-id="eaf8a-336">**Title:** Operating System versions</span></span><br>
    <span data-ttu-id="eaf8a-337">**サブタイトル:** 特定の OS バージョンを実行しているデバイス</span><span class="sxs-lookup"><span data-stu-id="eaf8a-337">**Subtitle:** Devices running specific OS versions</span></span>
4.  <span data-ttu-id="eaf8a-338">ドーナツ の **プロパティを定義** します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-338">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="eaf8a-339">**クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span><span class="sxs-lookup"><span data-stu-id="eaf8a-339">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span></span><br>
    <span data-ttu-id="eaf8a-340">**テキストの中央:** デバイス</span><span class="sxs-lookup"><span data-stu-id="eaf8a-340">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="eaf8a-341">**操作:** 合計</span><span class="sxs-lookup"><span data-stu-id="eaf8a-341">**Operation:** Sum</span></span>
5.  <span data-ttu-id="eaf8a-342">リストのプロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-342">Define the **List** properties.</span></span><br>
    <span data-ttu-id="eaf8a-343">**リスト クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span><span class="sxs-lookup"><span data-stu-id="eaf8a-343">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="eaf8a-344">**グラフを非表示にする:** 選択されている</span><span class="sxs-lookup"><span data-stu-id="eaf8a-344">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="eaf8a-345">**スパークラインを有効にする:** 選択されていない</span><span class="sxs-lookup"><span data-stu-id="eaf8a-345">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="eaf8a-346">列タイトル **を定義します**。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-346">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="eaf8a-347">**名前:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="eaf8a-347">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="eaf8a-348">**値:** 空のままにする</span><span class="sxs-lookup"><span data-stu-id="eaf8a-348">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="eaf8a-349">ナビゲーション **クエリを定義します**。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-349">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="eaf8a-350">[適用 **] を選択** し、[閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-350">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a><span data-ttu-id="eaf8a-351">アプリケーションのバージョンを表示する :::no-loc text="Microsoft Teams Rooms"::: タイルを作成する</span><span class="sxs-lookup"><span data-stu-id="eaf8a-351">Create a tile that displays :::no-loc text="Microsoft Teams Rooms"::: application versions</span></span>

1.  <span data-ttu-id="eaf8a-352">ギャラリー **から [ドーナツ&を** 選び、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-352">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="eaf8a-353">[全般] プロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-353">Define the **General** properties:</span></span><br>
    <span data-ttu-id="eaf8a-354">**グループ タイトル:** :::no-loc text="Microsoft Teams Rooms"::: アプリケーションの詳細</span><span class="sxs-lookup"><span data-stu-id="eaf8a-354">**Group Title:** :::no-loc text="Microsoft Teams Rooms"::: application details</span></span><br>
    <span data-ttu-id="eaf8a-355">**新しいグループ:** 選択されている</span><span class="sxs-lookup"><span data-stu-id="eaf8a-355">**New Group:** Selected</span></span>
3.  <span data-ttu-id="eaf8a-356">ヘッダープロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-356">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="eaf8a-357">**タイトル:** アプリケーションのバージョン</span><span class="sxs-lookup"><span data-stu-id="eaf8a-357">**Title:** Application versions</span></span><br>
    <span data-ttu-id="eaf8a-358">**サブタイトル:** 特定のアプリケーション バージョンを実行しているデバイス</span><span class="sxs-lookup"><span data-stu-id="eaf8a-358">**Subtitle:** Devices running specific application versions</span></span>
4.  <span data-ttu-id="eaf8a-359">ドーナツ の **プロパティを定義** します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-359">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="eaf8a-360">**クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span><span class="sxs-lookup"><span data-stu-id="eaf8a-360">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span></span><br>
    <span data-ttu-id="eaf8a-361">**テキストの中央:** デバイス</span><span class="sxs-lookup"><span data-stu-id="eaf8a-361">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="eaf8a-362">**操作:** 合計</span><span class="sxs-lookup"><span data-stu-id="eaf8a-362">**Operation:** Sum</span></span>
5.  <span data-ttu-id="eaf8a-363">リストのプロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-363">Define the **List** properties.</span></span><br>
    <span data-ttu-id="eaf8a-364">**リスト クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span><span class="sxs-lookup"><span data-stu-id="eaf8a-364">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="eaf8a-365">**グラフを非表示にする:** 選択されている</span><span class="sxs-lookup"><span data-stu-id="eaf8a-365">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="eaf8a-366">**スパークラインを有効にする:** 選択されていない</span><span class="sxs-lookup"><span data-stu-id="eaf8a-366">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="eaf8a-367">列タイトル **を定義します**。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-367">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="eaf8a-368">**名前:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="eaf8a-368">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="eaf8a-369">**値:** 空のままにする</span><span class="sxs-lookup"><span data-stu-id="eaf8a-369">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="eaf8a-370">ナビゲーション **クエリを定義します**。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-370">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="eaf8a-371">[適用 **] を選択** し、[閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-371">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a><span data-ttu-id="eaf8a-372">アプリケーション エラーが発生しているデバイスを表示するタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="eaf8a-372">Create a tile that displays devices that have an application error</span></span>

1.  <span data-ttu-id="eaf8a-373">ギャラリー **から [番号&** リストを選択し、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-373">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="eaf8a-374">[全般] プロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-374">Define the **General** properties.</span></span><br>
    <span data-ttu-id="eaf8a-375">**グループ タイトル:** 空のままにする</span><span class="sxs-lookup"><span data-stu-id="eaf8a-375">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="eaf8a-376">**新しいグループ:** 選択されていない</span><span class="sxs-lookup"><span data-stu-id="eaf8a-376">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="eaf8a-377">タイルのプロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-377">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="eaf8a-378">**凡例:** 過去 1 時間にアプリケーション エラーが発生したデバイス</span><span class="sxs-lookup"><span data-stu-id="eaf8a-378">**Legend:** Devices that experienced an application error in the last hour</span></span><br>
    <span data-ttu-id="eaf8a-379">**タイルのクエリ:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="eaf8a-379">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="eaf8a-380">リストのプロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-380">Define the **List** properties.</span></span><br>
    <span data-ttu-id="eaf8a-381">**リスト クエリ:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="eaf8a-381">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="eaf8a-382">列タイトル **を定義します**。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-382">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="eaf8a-383">**名前:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="eaf8a-383">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="eaf8a-384">**値:** 最後のエラー</span><span class="sxs-lookup"><span data-stu-id="eaf8a-384">**Value:** Last Error</span></span>
6.  <span data-ttu-id="eaf8a-385">ナビゲーション **クエリを定義します**。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-385">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="eaf8a-386">[適用 **] を選択** し、[閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-386">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a><span data-ttu-id="eaf8a-387">再起動されたデバイスを表示するタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="eaf8a-387">Create a tile that displays devices that have been restarted</span></span>

1.  <span data-ttu-id="eaf8a-388">ギャラリー **から [番号&** リストを選択し、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-388">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="eaf8a-389">[全般] プロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-389">Define the **General** properties.</span></span><br>
    <span data-ttu-id="eaf8a-390">**グループ タイトル:** 空のままにする</span><span class="sxs-lookup"><span data-stu-id="eaf8a-390">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="eaf8a-391">**新しいグループ:** 選択されていない</span><span class="sxs-lookup"><span data-stu-id="eaf8a-391">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="eaf8a-392">タイルのプロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-392">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="eaf8a-393">**凡例:** 過去 24 時間にアプリケーションが再起動されたデバイスと再起動数</span><span class="sxs-lookup"><span data-stu-id="eaf8a-393">**Legend:** Devices where the application was restarted in the last 24 hours, and number of restarts</span></span><br>
    <span data-ttu-id="eaf8a-394">**タイルのクエリ:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="eaf8a-394">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="eaf8a-395">リストのプロパティ **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-395">Define the **List** properties.</span></span><br>
    <span data-ttu-id="eaf8a-396">**リスト クエリ:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span><span class="sxs-lookup"><span data-stu-id="eaf8a-396">**List Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span></span>
5.  <span data-ttu-id="eaf8a-397">列タイトル **を定義します**。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-397">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="eaf8a-398">**名前:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="eaf8a-398">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="eaf8a-399">**値:** 再起動数</span><span class="sxs-lookup"><span data-stu-id="eaf8a-399">**Value:** Number of Restarts</span></span>
6.  <span data-ttu-id="eaf8a-400">ナビゲーション **クエリを定義します**。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-400">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="eaf8a-401">[適用 **] を選択** し、[閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-401">Select **Apply** and then **Close**.</span></span>
8.  <span data-ttu-id="eaf8a-402">[保存 **] を** 選び、ダッシュボードを保存します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-402">Select **Save** to save your dashboard.</span></span>

<span data-ttu-id="eaf8a-403">これで、ビューの作成が完了しました。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-403">Now you've completed creating your views.</span></span>

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a><span data-ttu-id="eaf8a-404">[通知の構成] :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="eaf8a-404">Configure Alerts in :::no-loc text="Azure Monitor":::</span></span>
<span data-ttu-id="eaf8a-405"><a name="Alerts"> </a></span><span class="sxs-lookup"><span data-stu-id="eaf8a-405"><a name="Alerts"> </a></span></span>

<span data-ttu-id="eaf8a-406">:::no-loc text="Azure Monitor"::: 本体で問題が発生した場合に、管理者に通知 :::no-loc text="Microsoft Teams Rooms"::: する通知を送信できます。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-406">:::no-loc text="Azure Monitor"::: can raise alerts to notify the administrators, when a :::no-loc text="Microsoft Teams Rooms"::: console encounters an issue.</span></span>

<span data-ttu-id="eaf8a-407">:::no-loc text="Azure Monitor"::: には、定期的にスケジュールされたログ検索を実行する組み込みの通知メカニズムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-407">:::no-loc text="Azure Monitor"::: includes a built-in alerting mechanism that runs through scheduled log searches at regular intervals.</span></span> <span data-ttu-id="eaf8a-408">ログ検索の結果が特定の条件と一致する場合は、通知レコードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-408">If the results of the log search match some particular criteria, an alert record is created.</span></span>

<span data-ttu-id="eaf8a-409">その後、ルールは 1 つ以上のアクションを自動的に実行して、通知を事前に通知したり、別のプロセスを呼び出したりします。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-409">The rule can then automatically run one or more actions to proactively notify you of the alert or invoke another process.</span></span> <span data-ttu-id="eaf8a-410">通知で使用できるオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-410">The possible options with alerts are:</span></span>
-   <span data-ttu-id="eaf8a-411">メールを送信する</span><span class="sxs-lookup"><span data-stu-id="eaf8a-411">Sending an email</span></span>
-   <span data-ttu-id="eaf8a-412">HTTP POST 要求による外部プロセスの呼び出し</span><span class="sxs-lookup"><span data-stu-id="eaf8a-412">Invoking an external process through an HTTP POST request</span></span>
-   <span data-ttu-id="eaf8a-413">サービスで実行ブックを開始 :::no-loc text="Azure Automation"::: する</span><span class="sxs-lookup"><span data-stu-id="eaf8a-413">Starting a runbook in :::no-loc text="Azure Automation"::: service</span></span>

<span data-ttu-id="eaf8a-414">アラート[の詳細については :::no-loc text="Azure Monitor"::: 、](/azure/azure-monitor/platform/alerts-unified-log)ログインに関するページを参照してください :::no-loc text="Azure Monitor"::: 。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-414">See [Log alerts in :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/alerts-unified-log) to learn more about the alerts in :::no-loc text="Azure Monitor":::.</span></span>

> [!NOTE]
> <span data-ttu-id="eaf8a-415">次の例では、デバイスでハードウェアまたはアプリケーション エラーが生成された :::no-loc text="Microsoft Teams Rooms"::: 場合にメール通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-415">The following examples send email alerts when a :::no-loc text="Microsoft Teams Rooms"::: device generates a hardware or an application error.</span></span>

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a><span data-ttu-id="eaf8a-416">ハードウェアの問題に関するメール通知 :::no-loc text="Microsoft Teams Rooms"::: を構成する</span><span class="sxs-lookup"><span data-stu-id="eaf8a-416">Configure an email alert for :::no-loc text="Microsoft Teams Rooms"::: hardware issues</span></span>

<span data-ttu-id="eaf8a-417">1 時間以内にハードウェアの問題が発生したデバイスをチェックする通知 :::no-loc text="Microsoft Teams Rooms"::: ルールを構成します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-417">Configure an alert rule that checks for :::no-loc text="Microsoft Teams Rooms"::: devices that have encountered hardware issues within the last hour.</span></span>
1.  <span data-ttu-id="eaf8a-418">ポータルにサインイン[ :::no-loc text="Microsoft Azure"::: し、](https://portal.azure.com)ワークスペースに移動 :::no-loc text="Log Analytics"::: して選択します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-418">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2. <span data-ttu-id="eaf8a-419">ワークスペースに移動し :::no-loc text="Log Analytics"::: 、[通知] を **選択** し、[新しい **通知ルール] を選択する**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-419">Navigate to your :::no-loc text="Log Analytics"::: workspace and select **Alerts** and then select **New alert rule**</span></span>

3. <span data-ttu-id="eaf8a-420">[条件 **の追加] を選択** し、[ **カスタム ログの検索] を選択する**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-420">Select **Add condition** and then **Custom log search**</span></span>

4.  <span data-ttu-id="eaf8a-421">[検索クエリ] テキスト ボックスに次のクエリを入力します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-421">Enter the following query to the Search query text box.</span></span><br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  <span data-ttu-id="eaf8a-422">通知ロジックの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-422">Configure the Alert logic settings:</span></span><br>
    <span data-ttu-id="eaf8a-423">**次の条件に基づいて行います。** 結果の数</span><span class="sxs-lookup"><span data-stu-id="eaf8a-423">**Based on:** Number of results</span></span><br>
    <span data-ttu-id="eaf8a-424">**条件:** 次に大きい値</span><span class="sxs-lookup"><span data-stu-id="eaf8a-424">**Condition:** Greater then</span></span><br>
    <span data-ttu-id="eaf8a-425">**しきい値:** 0</span><span class="sxs-lookup"><span data-stu-id="eaf8a-425">**Threshold:** 0</span></span><br>

6. <span data-ttu-id="eaf8a-426">評価設定を構成し、[完了] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-426">Configure Evaluation settings and select **Done**:</span></span> <br>
    <span data-ttu-id="eaf8a-427">**期 (分数):** 60</span><span class="sxs-lookup"><span data-stu-id="eaf8a-427">**Period (in minutes):** 60</span></span><br>
    <span data-ttu-id="eaf8a-428">**頻度 (分):** 60</span><span class="sxs-lookup"><span data-stu-id="eaf8a-428">**Frequency (in minutes):** 60</span></span><br>

7. <span data-ttu-id="eaf8a-429">アクション グループを構成する:</span><span class="sxs-lookup"><span data-stu-id="eaf8a-429">Configure action groups:</span></span>
    1.  <span data-ttu-id="eaf8a-430">[新規 **作成] を選択する**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-430">Select **Create New**</span></span>
    2.  <span data-ttu-id="eaf8a-431">[アクション] グループ名と *[短い名前] フィールドに適\*\*した名前を指定* します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-431">Provide suitable names for the *Action group name* and *Short Name* fields.</span></span>
    3.  <span data-ttu-id="eaf8a-432">一意のアクション *名を指定し* 、[ **メール/SMS/プッシュ/音声**] を選択し、[詳細の編集] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-432">Specify a unique *Action Name* and select **Email/SMS/Push/Voice**, and then select **Edit details**.</span></span>
    4.  <span data-ttu-id="eaf8a-433">[メール **] チェック** ボックスをオンにして、通知を受信するユーザーまたはグループのメール アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-433">Select the **Email** checkbox and provide the email address of the person or group that will receive the alerts.</span></span>
    5.  <span data-ttu-id="eaf8a-434">また、SMS、音声通話、または両方で通知を受け取る電話番号を入力できます。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-434">You may also provide your phone number to get notified with SMS, a voice call or both.</span></span>
    6. <span data-ttu-id="eaf8a-435">**[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-435">Select **OK**.</span></span>

8. <span data-ttu-id="eaf8a-436">**通知メール** の件名行を上書きする場合は、アクションをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-436">**Customize Actions** if you like to override the subject line of the alert emails.</span></span>

9. <span data-ttu-id="eaf8a-437">ルールの名前と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-437">Specify a rule name and description.</span></span><br>
    <span data-ttu-id="eaf8a-438">**ルール名:** :::no-loc text="Microsoft Teams Rooms"::: ハードウェア障害の警告</span><span class="sxs-lookup"><span data-stu-id="eaf8a-438">**Rule Name:** :::no-loc text="Microsoft Teams Rooms"::: Hardware Failure Alert</span></span><br>
    <span data-ttu-id="eaf8a-439">**説明:** 最後の 1 時間以内にハードウェアの問題が発生したデバイスの一覧</span><span class="sxs-lookup"><span data-stu-id="eaf8a-439">**Description:** List of devices that encountered a hardware issue within the last hour</span></span><br>

10. <span data-ttu-id="eaf8a-440">目的の重大度を選択し、ルールが有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-440">Select the intended severity and make sure the rule is enabled.</span></span>

11. <span data-ttu-id="eaf8a-441">[通知 **ルールの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-441">Select **Create alert rule**.</span></span>

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a><span data-ttu-id="eaf8a-442">アプリケーションの問題に関するメール通知 :::no-loc text="Microsoft Teams Rooms"::: を構成する</span><span class="sxs-lookup"><span data-stu-id="eaf8a-442">Configure an email alert for :::no-loc text="Microsoft Teams Rooms"::: application issues</span></span>

<span data-ttu-id="eaf8a-443">同じ手順を繰り返しますが、次のクエリを使用して、最後の 1 時間以内にアプリケーションの問題が発生したデバイスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-443">Repeat the same procedure but use the following query to list devices that have encountered application issues within the last hour.</span></span>

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

<span data-ttu-id="eaf8a-444">これで、通知の定義が完了しました。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-444">Now you've completed defining alerts.</span></span> <span data-ttu-id="eaf8a-445">上記の例を使用して、追加の通知を定義できます。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-445">You can define additional alerts by using the examples above.</span></span>

<span data-ttu-id="eaf8a-446">通知が生成されると、1 時間以内に問題が発生したデバイスを一覧表示するメールが届きます。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-446">When an alert is generated, you'll get an email that lists the devices that encountered an issue within the last hour.</span></span>

<span data-ttu-id="eaf8a-447">![サンプル :::no-loc text="Azure Monitor"::: 通知メール](.../media/Deploy-Azure-Monitor-6.png "サンプル :::no-loc text="Azure Monitor"::: 通知メール")</span><span class="sxs-lookup"><span data-stu-id="eaf8a-447">![Sample :::no-loc text="Azure Monitor"::: alert email](../media/Deploy-Azure-Monitor-6.png "Sample :::no-loc text="Azure Monitor"::: alert email")</span></span>

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a><span data-ttu-id="eaf8a-448">すべてのデバイスの構成 :::no-loc text="Azure Monitoring":::</span><span class="sxs-lookup"><span data-stu-id="eaf8a-448">Configure all devices for :::no-loc text="Azure Monitoring":::</span></span>
<span data-ttu-id="eaf8a-449"><a name="configure_all_devices"></a>ダッシュボードとアラートを構成したら、すべてのデバイスでエージェントを設定して構成し、監視 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: 展開を完了できます。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-449"><a name="configure_all_devices"> </a> After the dashboards and alerts are configured, you can set up and configure :::no-loc text="Microsoft Monitoring"::: agent on all :::no-loc text="Microsoft Teams Rooms"::: devices to complete your monitoring deployment.</span></span>

<span data-ttu-id="eaf8a-450">各デバイスにエージェントを手動でインストールして構成することができますが、既存のソフトウェア展開ツールと方法を活用することを :::no-loc text="Microsoft Monitoring"::: 強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-450">Although you can install and configure the :::no-loc text="Microsoft Monitoring"::: agent manually on each device, we highly recommend you leverage existing software deployment tools and methods.</span></span>

<span data-ttu-id="eaf8a-451">初めてデバイスを構築する場合は、ビルド プロセスの一部としてエージェントのセットアップと構成の手順 :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Microsoft Monitoring"::: を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-451">If you're building your :::no-loc text="Microsoft Teams Rooms"::: devices for the first time, you might want to include the :::no-loc text="Microsoft Monitoring"::: agent setup and configuration steps as part of your build process.</span></span> <span data-ttu-id="eaf8a-452">詳細については、コマンド ライン [を使用してエージェントをインストールするを参照してください](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-452">For more information, see [Install the agent using the command line](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).</span></span>

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a><span data-ttu-id="eaf8a-453">グループ ポリシー :::no-loc text="Microsoft Monitoring"::: オブジェクト (GPO) を使用したエージェントの展開</span><span class="sxs-lookup"><span data-stu-id="eaf8a-453">Deploying :::no-loc text="Microsoft Monitoring"::: agent by using a Group Policy Object (GPO)</span></span>

<span data-ttu-id="eaf8a-454">実装する前にデバイスを既に展開している場合は、提供されているスクリプトを使用して、グループ ポリシー オブジェクトを使用してエージェントを :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitoring"::: 設定および :::no-loc text="Active Directory"::: 構成できます。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-454">If you already deployed your :::no-loc text="Microsoft Teams Rooms"::: devices before you implement :::no-loc text="Azure Monitoring":::, you can use the provided script to set up and configure the agents by using :::no-loc text="Active Directory"::: group policy objects.</span></span>

1.  <span data-ttu-id="eaf8a-455">共有ネットワーク パスを作成し、[ドメイン コンピューター] グループへの読み取 **りアクセス権を付与** します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-455">Create a shared network path and grant read access to **Domain Computers** group.</span></span>

2.  <span data-ttu-id="eaf8a-456">64 ビット版の :::no-loc text="Microsoft Monitoring"::: エージェントをダウンロードする :::no-loc text="Windows":::<https://go.microsoft.com/fwlink/?LinkID=517476></span><span class="sxs-lookup"><span data-stu-id="eaf8a-456">Download the 64-bit version of the :::no-loc text="Microsoft Monitoring"::: Agent for :::no-loc text="Windows"::: from <https://go.microsoft.com/fwlink/?LinkID=517476></span></span>

3.  <span data-ttu-id="eaf8a-457">セットアップ パッケージのコンテンツをネットワーク共有に抽出します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-457">Extract the contents of the setup package into the network share.</span></span>
    1.  <span data-ttu-id="eaf8a-458">コマンド プロンプト ウィンドウを開き **、/cMMASetup-AMD64.exe実行する**</span><span class="sxs-lookup"><span data-stu-id="eaf8a-458">Open a Command Prompt window, and then execute **MMASetup-AMD64.exe /c**</span></span>
    2.  <span data-ttu-id="eaf8a-459">作成した共有を指定し、コンテンツを抽出します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-459">Specify the share you just created, and extract the content.</span></span>

4.  <span data-ttu-id="eaf8a-460">新しいグループ ポリシー オブジェクトを作成し、コンピューター アカウントがある組織単位 :::no-loc text="Microsoft Teams Rooms"::: に割り当てる。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-460">Create a new Group Policy Object and assign it to the organizational unit where :::no-loc text="Microsoft Teams Rooms"::: machine accounts are located.</span></span>

5.  <span data-ttu-id="eaf8a-461">PowerShell 実行ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-461">Configure PowerShell execution policy:</span></span>
    1.  <span data-ttu-id="eaf8a-462">新しく作成したグループ ポリシー オブジェクトを編集し、[コンピューター構成 \\ ポリシー管理用テンプレート コンポーネント \\ ] に \\ :::no-loc text="Windows"::: 移動する \\:::no-loc text="Windows PowerShell":::</span><span class="sxs-lookup"><span data-stu-id="eaf8a-462">Edit the newly created Group Policy Object and navigate to Computer Configuration \\ Policies \\ Administrative Templates \\ :::no-loc text="Windows"::: Components \\ :::no-loc text="Windows PowerShell":::</span></span>
    2.  <span data-ttu-id="eaf8a-463">スクリプトの **実行を有効にして、実行** ポリシーをローカル スクリプト **を許可\*\*\*\*する設定を行います**。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-463">Enable the **Turn on Script Execution** and set **Execution Policy** to **Allow Local Scripts**.</span></span>

6.  <span data-ttu-id="eaf8a-464">スタートアップ スクリプトを構成します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-464">Configure the startup script:</span></span>
    1.  <span data-ttu-id="eaf8a-465">次のスクリプトをコピーし、そのスクリプトをInstall-MMAgent.ps1。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-465">Copy the following script and save it as Install-MMAgent.ps1.</span></span>
    2.  <span data-ttu-id="eaf8a-466">WorkspaceId、WorkspaceKey、SetupPath のパラメーターを構成に合わせて変更します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-466">Modify WorkspaceId, WorkspaceKey, and SetupPath parameters to match your configuration.</span></span>
    3.  <span data-ttu-id="eaf8a-467">同じグループ ポリシー オブジェクトを編集し、コンピューター構成 \\ ポリシー \\ :::no-loc text="Windows"::: 設定 \\ スクリプト (スタートアップ/シャットダウン) に移動する</span><span class="sxs-lookup"><span data-stu-id="eaf8a-467">Edit the same Group Policy Object and navigate to Computer Configuration \\ Policies \\ :::no-loc text="Windows"::: Settings \\ Scripts (Startup/Shutdown)</span></span>
    4.  <span data-ttu-id="eaf8a-468">ダブルクリックして [スタートアップ] を **選択** し **、[PowerShell スクリプト] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-468">Double-click to select **Startup**, and then select **PowerShell Scripts**.</span></span>
    5.  <span data-ttu-id="eaf8a-469">[ **ファイルの表示]** を選択し、 **そのInstall-MMAgent.ps1ファイル** をコピーします。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-469">Select **Show Files**, and then copy the **Install-MMAgent.ps1** file to that folder.</span></span>
    6.  <span data-ttu-id="eaf8a-470">[追加 **] を選択** し、[参照] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-470">Select **Add**, and then **Browse**.</span></span>
    7.  <span data-ttu-id="eaf8a-471">コピーした ps1 スクリプトを選択します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-471">Select the ps1 script you just copied.</span></span>

7.  <span data-ttu-id="eaf8a-472">:::no-loc text="Microsoft Teams Rooms"::: デバイスは、2 回目の再起動 :::no-loc text="Microsoft Monitoring"::: でエージェントをインストールして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-472">:::no-loc text="Microsoft Teams Rooms"::: devices should install and configure the :::no-loc text="Microsoft Monitoring"::: agent with the second reboot.</span></span>

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
> <span data-ttu-id="eaf8a-473">エージェントを再構成する必要がある [ :::no-loc text="Log Analytics"::: ](/azure/azure-monitor/platform/agent-manage) 場合、エージェントを別のワークスペースに移動する必要がある場合、または最初のインストール後にプロキシ設定を変更する必要がある場合は、「エージェントを管理および保守する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-473">You can refer to the article [Managing and maintaining the :::no-loc text="Log Analytics"::: agent](/azure/azure-monitor/platform/agent-manage) when you need to reconfigure an agent, move it to a different workspace, or modify proxy settings after the initial installation.</span></span>

## <a name="additional-solutions"></a><span data-ttu-id="eaf8a-474">その他のソリューション</span><span class="sxs-lookup"><span data-stu-id="eaf8a-474">Additional Solutions</span></span>
<span data-ttu-id="eaf8a-475"><a name="Solutions"> </a></span><span class="sxs-lookup"><span data-stu-id="eaf8a-475"><a name="Solutions"> </a></span></span>

<span data-ttu-id="eaf8a-476">:::no-loc text="Azure Monitor":::は、環境の監視に役立つ[](/azure/azure-monitor/insights/solutions)ソリューション ギャラリーを通じて組み込みの管理ソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-476">:::no-loc text="Azure Monitor"::: provides built-in management solutions through its [solution gallery](/azure/azure-monitor/insights/solutions) to further help you monitor your environment.</span></span> <span data-ttu-id="eaf8a-477">通知管理ソリューション[とエージェント正常性](/azure/azure-monitor/platform/alert-management-solution)[ :::no-loc text="Azure Log Analytics"::: ソリューションをワークスペース](/azure/azure-monitor/insights/solution-agenthealth)にも追加することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-477">We highly recommend that you add [Alert Management](/azure/azure-monitor/platform/alert-management-solution) and [:::no-loc text="Azure Log Analytics"::: Agent Health](/azure/azure-monitor/insights/solution-agenthealth) solutions to your workspace as well.</span></span>

> [!NOTE]
> <span data-ttu-id="eaf8a-478">エージェント正常性ソリューションは、環境内の古いエージェントまたは破損したエージェントを特定するのに役立ち、通知管理ソリューションは、指定した期間中に発生したアラートに関する詳細 :::no-loc text="Microsoft Monitoring"::: を提供します。</span><span class="sxs-lookup"><span data-stu-id="eaf8a-478">The Agent Health solution can help you identify outdated or broken :::no-loc text="Microsoft Monitoring"::: agents within your environment, and the Alert Management solution provides details about the alerts that have been raised within a given period.</span></span>

## <a name="see-also"></a><span data-ttu-id="eaf8a-479">関連項目</span><span class="sxs-lookup"><span data-stu-id="eaf8a-479">See also</span></span>

[<span data-ttu-id="eaf8a-480">プラン :::no-loc text="Microsoft Teams Rooms"::: の管理 :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="eaf8a-480">Plan :::no-loc text="Microsoft Teams Rooms"::: management with :::no-loc text="Azure Monitor":::</span></span>](azure-monitor-plan.md)

[<span data-ttu-id="eaf8a-481">次 :::no-loc text="Microsoft Teams Rooms"::: の方法でデバイスを管理します。 :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="eaf8a-481">Manage :::no-loc text="Microsoft Teams Rooms"::: devices with :::no-loc text="Azure Monitor":::</span></span>](azure-monitor-manage.md)