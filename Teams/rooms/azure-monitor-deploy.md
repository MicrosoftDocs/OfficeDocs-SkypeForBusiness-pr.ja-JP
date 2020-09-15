---
title: Azure Monitor を使用して Microsoft Teams Rooms 管理をデプロイする
ms.author: v-lanac
author: lanachin
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
description: この記事では、Azure モニターを使用して、統合されたエンドツーエンドの方法で Microsoft Teams 室デバイスの管理を展開する方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3c1ecb3906eec551ddaed9a2c748a66c9da7ac9a
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "47766881"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a><span data-ttu-id="2635d-103">:::no-loc text="Microsoft Teams Rooms":::管理を展開する:::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="2635d-103">Deploy :::no-loc text="Microsoft Teams Rooms"::: management with :::no-loc text="Azure Monitor":::</span></span>

<span data-ttu-id="2635d-104">この記事では、を使用して、統合されたエンドツーエンドのデバイス管理をセットアップして展開する方法について説明し :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: ます。</span><span class="sxs-lookup"><span data-stu-id="2635d-104">This article discusses how to set up and deploy integrated, end-to-end management of :::no-loc text="Microsoft Teams Rooms"::: devices by using :::no-loc text="Azure Monitor":::.</span></span>

<span data-ttu-id="2635d-105">会議室のデバイスを管理するのに :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor"::: 役立つ基本的なテレメトリとアラートを提供するように、内で構成することができ :::no-loc text="Microsoft Teams Rooms"::: ます。</span><span class="sxs-lookup"><span data-stu-id="2635d-105">You can configure :::no-loc text="Log Analytics"::: within :::no-loc text="Azure Monitor"::: to provide basic telemetry and alerts that will help you manage :::no-loc text="Microsoft Teams Rooms"::: meeting room devices.</span></span> <span data-ttu-id="2635d-106">管理ソリューションの成熟に応じて、デバイスの可用性とパフォーマンスの詳細なビューを作成するために、追加のデータと管理機能を展開することができます。</span><span class="sxs-lookup"><span data-stu-id="2635d-106">As your management solution matures, you might decide to deploy additional data and management capabilities to create a more detailed view of device availability and performance.</span></span>

<span data-ttu-id="2635d-107">このガイドに従うと、次の例のようなダッシュボードを使用して、デバイスの可用性、アプリケーションとハードウェアの正常性、およびアプリケーションとオペレーティングシステムのバージョンの配布に関する詳細な状態レポートを取得でき :::no-loc text="Microsoft Teams Rooms"::: ます。</span><span class="sxs-lookup"><span data-stu-id="2635d-107">By following this guide, you can use a dashboard like the following example to get detailed status reporting for device availability, application and hardware health, and :::no-loc text="Microsoft Teams Rooms"::: application and operating system version distribution.</span></span>

<span data-ttu-id="2635d-108">![Microsoft Teams ルームのサンプルログ分析ビューのスクリーンショット](../media/Deploy-Azure-Monitor-1.png "Microsoft Teams ルームのサンプルログ分析ビュー")</span><span class="sxs-lookup"><span data-stu-id="2635d-108">![Screenshot of sample Log Analytics view for Microsoft Teams Rooms](../media/Deploy-Azure-Monitor-1.png "Sample Log Analytics view for Microsoft Teams Rooms")</span></span>

<span data-ttu-id="2635d-109">高いレベルでは、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2635d-109">At a high level, you need to perform the following tasks:</span></span>


1. [<span data-ttu-id="2635d-110">構成の検証 :::no-loc text="Log Analytics":::</span><span class="sxs-lookup"><span data-stu-id="2635d-110">Validate :::no-loc text="Log Analytics"::: configuration</span></span>](azure-monitor-deploy.md#validate_LogAnalytics)
2. [<span data-ttu-id="2635d-111">管理セットアップ用にテストデバイスを構成する :::no-loc text="Log Analytics":::</span><span class="sxs-lookup"><span data-stu-id="2635d-111">Configure test devices for :::no-loc text="Log Analytics"::: management setup</span></span>](azure-monitor-deploy.md#configure_test_devices)
3. [<span data-ttu-id="2635d-112">カスタム フィールドをマップする</span><span class="sxs-lookup"><span data-stu-id="2635d-112">Map custom fields</span></span>](azure-monitor-deploy.md#Custom_fields)
4. [<span data-ttu-id="2635d-113">ビューの定義 :::no-loc text="Microsoft Teams Rooms"::::::no-loc text="Log Analytics":::</span><span class="sxs-lookup"><span data-stu-id="2635d-113">Define the :::no-loc text="Microsoft Teams Rooms"::: views in :::no-loc text="Log Analytics":::</span></span>](azure-monitor-deploy.md#Define_Views)
5. [<span data-ttu-id="2635d-114">通知を定義する</span><span class="sxs-lookup"><span data-stu-id="2635d-114">Define alerts</span></span>](azure-monitor-deploy.md#Alerts)
6. [<span data-ttu-id="2635d-115">すべてのデバイスを監視対象として構成する</span><span class="sxs-lookup"><span data-stu-id="2635d-115">Configure all devices for Monitoring</span></span>](azure-monitor-deploy.md#configure_all_devices)
7. [<span data-ttu-id="2635d-116">その他のソリューションを構成する :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="2635d-116">Configure additional :::no-loc text="Azure Monitor"::: solutions</span></span>](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> <span data-ttu-id="2635d-117">最小限の構成では、 :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: オペレーティングシステムを実行しているコンピューターを監視できますが、 :::no-loc text="Windows"::: すべてのデバイスへのエージェントの展開を開始する前に、いくつか :::no-loc text="Microsoft Teams Rooms"::: の具体的な手順を実行する必要があり :::no-loc text="Microsoft Teams Rooms"::: ます。</span><span class="sxs-lookup"><span data-stu-id="2635d-117">Although with minimal configuration, :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: can monitor a computer running a :::no-loc text="Windows"::: operating system, there are still some :::no-loc text="Microsoft Teams Rooms":::–specific steps that you need to take before you start deploying agents to all :::no-loc text="Microsoft Teams Rooms"::: devices.</span></span>
> <span data-ttu-id="2635d-118">そのため、管理された設定と構成については、すべての構成手順を適切な順序で実行することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2635d-118">Therefore, we highly recommend you perform all configuration steps in the right order for a controlled setup and configuration.</span></span> <span data-ttu-id="2635d-119">最終的な結果の品質は、初期構成の品質によって大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="2635d-119">The quality of the end result very much depends on the quality of the initial configuration.</span></span>

## <a name="validate-no-loc-textlog-analytics-configuration"></a><span data-ttu-id="2635d-120">構成の検証 :::no-loc text="Log Analytics":::</span><span class="sxs-lookup"><span data-stu-id="2635d-120">Validate :::no-loc text="Log Analytics"::: configuration</span></span>
<span data-ttu-id="2635d-121"><a name="validate_LogAnalytics"> </a></span><span class="sxs-lookup"><span data-stu-id="2635d-121"><a name="validate_LogAnalytics"> </a></span></span>

<span data-ttu-id="2635d-122">:::no-loc text="Log Analytics":::デバイスからのログの収集を開始するには、ワークスペースが必要 :::no-loc text="Microsoft Teams Rooms"::: です。</span><span class="sxs-lookup"><span data-stu-id="2635d-122">You need to have a :::no-loc text="Log Analytics"::: workspace to start collecting logs from :::no-loc text="Microsoft Teams Rooms"::: devices.</span></span> <span data-ttu-id="2635d-123">ワークスペースは、 :::no-loc text="Log Analytics"::: 独自のデータリポジトリ、データソース、およびソリューションを備えた、固有の環境です。</span><span class="sxs-lookup"><span data-stu-id="2635d-123">A workspace is a unique :::no-loc text="Log Analytics"::: environment with its own data repository, data sources, and solutions.</span></span> <span data-ttu-id="2635d-124">既存のワークスペースを既に持っている場合 :::no-loc text="Log Analytics"::: は、それを使って展開を監視する :::no-loc text="Microsoft Teams Rooms"::: か、または :::no-loc text="Log Analytics"::: 監視ニーズに合わせた専用のワークスペースを作成することができ :::no-loc text="Microsoft Teams Rooms"::: ます。</span><span class="sxs-lookup"><span data-stu-id="2635d-124">If you already have an existing :::no-loc text="Log Analytics"::: workspace, you might use it to monitor your :::no-loc text="Microsoft Teams Rooms"::: deployment or alternatively, you can create a dedicated :::no-loc text="Log Analytics"::: workspace specific to your :::no-loc text="Microsoft Teams Rooms"::: monitoring needs.</span></span>

<span data-ttu-id="2635d-125">新しいワークスペースを作成する必要がある場合は、 :::no-loc text="Log Analytics"::: 「 [ :::no-loc text="Log Analytics"::: :::no-loc text="Azure"::: ポータルでワークスペースを作成](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)する」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2635d-125">If you need to create a new :::no-loc text="Log Analytics"::: workspace, follow the instructions in the article [Create a :::no-loc text="Log Analytics"::: workspace in the :::no-loc text="Azure"::: portal](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)</span></span>

> [!NOTE]
> <span data-ttu-id="2635d-126">を使用するには :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor"::: 、有効なサブスクリプションが必要 :::no-loc text="Azure"::: です。</span><span class="sxs-lookup"><span data-stu-id="2635d-126">To use :::no-loc text="Log Analytics"::: with :::no-loc text="Azure Monitor":::, you need to have an active :::no-loc text="Azure"::: subscription.</span></span> <span data-ttu-id="2635d-127">サブスクリプションを持っていない場合は :::no-loc text="Azure"::: 、出発点として [無料トライアルサブスクリプションを](https://azure.microsoft.com/free) 作成できます。</span><span class="sxs-lookup"><span data-stu-id="2635d-127">If you don't have an :::no-loc text="Azure"::: subscription, you can create [a free trial subscription](https://azure.microsoft.com/free) as a starting point.</span></span>

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a><span data-ttu-id="2635d-128">:::no-loc text="Log Analytics":::イベントログを収集するように構成する :::no-loc text="Microsoft Teams Rooms":::</span><span class="sxs-lookup"><span data-stu-id="2635d-128">Configure :::no-loc text="Log Analytics"::: to collect :::no-loc text="Microsoft Teams Rooms"::: event logs</span></span>

<span data-ttu-id="2635d-129">:::no-loc text="Log Analytics"::: 設定で指定されたイベントログのイベントのみを収集し :::no-loc text="Windows"::: ます。</span><span class="sxs-lookup"><span data-stu-id="2635d-129">:::no-loc text="Log Analytics"::: only collects events from the :::no-loc text="Windows"::: event logs that are specified in the settings.</span></span> <span data-ttu-id="2635d-130">各ログについて、選択した重大度のイベントのみが収集されます。</span><span class="sxs-lookup"><span data-stu-id="2635d-130">For each log, only the events with the selected severities are collected.</span></span>

<span data-ttu-id="2635d-131">:::no-loc text="Log Analytics":::デバイスとアプリケーションの状態を監視するために必要なログを収集するように構成する必要があり :::no-loc text="Microsoft Teams Rooms"::: ます。</span><span class="sxs-lookup"><span data-stu-id="2635d-131">You need to configure :::no-loc text="Log Analytics"::: to collect the logs required to monitor :::no-loc text="Microsoft Teams Rooms"::: device and application status.</span></span> <span data-ttu-id="2635d-132">:::no-loc text="Microsoft Teams Rooms"::: デバイスは **:::no-loc text="Skype Room System":::** イベントログを使います。</span><span class="sxs-lookup"><span data-stu-id="2635d-132">:::no-loc text="Microsoft Teams Rooms"::: devices use the **:::no-loc text="Skype Room System":::** event log.</span></span>

<span data-ttu-id="2635d-133">イベントを収集するように構成するには :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: 、「 [ :::no-loc text="Windows"::: イベント :::no-loc text="Azure Monitor"::: ログのデータソース](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2635d-133">To configure :::no-loc text="Log Analytics"::: to collect the :::no-loc text="Microsoft Teams Rooms"::: events, see [:::no-loc text="Windows"::: event log data sources in :::no-loc text="Azure Monitor":::](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)</span></span>

<span data-ttu-id="2635d-134">![イベントログ設定のスクリーンショット](../media/Deploy-Azure-Monitor-2.png "イベントログの設定")</span><span class="sxs-lookup"><span data-stu-id="2635d-134">![Screenshot of event log settings](../media/Deploy-Azure-Monitor-2.png "Event log settings")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2635d-135">:::no-loc text="Windows":::イベントログの設定を構成し、イベントログの名前を入力して、 **:::no-loc text="Skype Room System":::** [**エラー**]、[**警告**]、[**情報**] のチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2635d-135">Configure :::no-loc text="Windows"::: Event Log settings and enter **:::no-loc text="Skype Room System":::** as event log name, and then select the **Error**, **Warning**, and **Information** check boxes.</span></span>

## <a name="configure-test-devices-for-azure-monitoring"></a><span data-ttu-id="2635d-136">Azure Monitoring のテストデバイスを構成する</span><span class="sxs-lookup"><span data-stu-id="2635d-136">Configure test devices for Azure Monitoring</span></span>
<span data-ttu-id="2635d-137"><a name="configure_test_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="2635d-137"><a name="configure_test_devices"> </a></span></span>

<span data-ttu-id="2635d-138">関連するイベントを監視できるように準備する必要があり :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: ます。</span><span class="sxs-lookup"><span data-stu-id="2635d-138">You need to prepare :::no-loc text="Log Analytics"::: to be able to monitor :::no-loc text="Microsoft Teams Rooms":::–related events.</span></span> <span data-ttu-id="2635d-139">まず、 :::no-loc text="Microsoft Monitoring"::: 物理的にアクセスできる1つまたは2つのデバイスにエージェントを展開 :::no-loc text="Microsoft Teams Rooms"::: し、それらのテストデバイスでデータを生成してワークスペースにプッシュする必要があり :::no-loc text="Log Analytics"::: ます。</span><span class="sxs-lookup"><span data-stu-id="2635d-139">To start with, you need to deploy :::no-loc text="Microsoft Monitoring"::: agents to just one or two :::no-loc text="Microsoft Teams Rooms"::: devices that you have physical access to, and get those test devices generate some data and push it to the :::no-loc text="Log Analytics"::: workspace.</span></span>

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a><span data-ttu-id="2635d-140">:::no-loc text="Microsoft Monitoring":::エージェントをインストールしてデバイスをテストする</span><span class="sxs-lookup"><span data-stu-id="2635d-140">Install :::no-loc text="Microsoft Monitoring"::: agents to test devices</span></span>

<span data-ttu-id="2635d-141">:::no-loc text="Microsoft Monitoring":::「 [ :::no-loc text="Windows"::: コンピューターを :::no-loc text="Log Analytics"::: サービス :::no-loc text="Azure"::: に接続する](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)」で説明されている手順を使用して、エージェントをテストデバイスに展開します。</span><span class="sxs-lookup"><span data-stu-id="2635d-141">Deploy the :::no-loc text="Microsoft Monitoring"::: agent to the test devices by using the instructions provided in [Connect :::no-loc text="Windows"::: computers to the :::no-loc text="Log Analytics"::: service in :::no-loc text="Azure":::](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows).</span></span> <span data-ttu-id="2635d-142">この記事では :::no-loc text="Microsoft Monitoring"::: 、エージェントの展開手順 :::no-loc text="Windows"::: 、 :::no-loc text="Log Analytics"::: ***ワークスペース ID*** の取得手順、展開に接続するデバイスを取得するための ***主キー*** 、 :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: およびインスタンスへのエージェントの接続性を確認する手順 :::no-loc text="Log Analytics"::: について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="2635d-142">This article provides detailed information about the steps for deploying :::no-loc text="Microsoft Monitoring"::: Agent for :::no-loc text="Windows":::, instructions for obtaining the :::no-loc text="Log Analytics"::: ***Workspace ID*** and the ***primary key*** to get :::no-loc text="Microsoft Teams Rooms"::: devices connected to your :::no-loc text="Azure Monitor"::: deployment, and steps to verify agent connectivity to :::no-loc text="Log Analytics"::: instance.</span></span>

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a><span data-ttu-id="2635d-143">サンプルイベントを生成する :::no-loc text="Microsoft Teams Rooms":::</span><span class="sxs-lookup"><span data-stu-id="2635d-143">Generate sample :::no-loc text="Microsoft Teams Rooms"::: events</span></span>

<span data-ttu-id="2635d-144">エージェントを :::no-loc text="Microsoft Monitoring"::: テストデバイスに展開した後、必要なイベントログデータがで収集されていることを確認し :::no-loc text="Azure Monitor"::: ます。</span><span class="sxs-lookup"><span data-stu-id="2635d-144">After the :::no-loc text="Microsoft Monitoring"::: agent is deployed onto the test devices, verify that the required event log data is collected by :::no-loc text="Azure Monitor":::.</span></span>

> [!NOTE]
> <span data-ttu-id="2635d-145">エージェントをインストールした後でデバイスを再起動 :::no-loc text="Microsoft Monitoring"::: し、 :::no-loc text="Microsoft Teams Rooms"::: アプリが新しいイベントを生成できるように会議アプリが開始されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2635d-145">Reboot the device after the installation of the :::no-loc text="Microsoft Monitoring"::: agent, and make sure that :::no-loc text="Microsoft Teams Rooms"::: Meeting app is started, so that it can generate new events into the Event Log.</span></span>

1.  <span data-ttu-id="2635d-146">[ :::no-loc text="Microsoft Azure"::: ポータル](https://portal.azure.com)にサインインして、ワークスペースに移動して :::no-loc text="Log Analytics"::: 選択します。</span><span class="sxs-lookup"><span data-stu-id="2635d-146">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2.  <span data-ttu-id="2635d-147">デバイスによって生成されるハートビートイベントを一覧表示し :::no-loc text="Microsoft Teams Rooms"::: ます。</span><span class="sxs-lookup"><span data-stu-id="2635d-147">List the heartbeat events generated by a :::no-loc text="Microsoft Teams Rooms"::: device:</span></span>
    1.  <span data-ttu-id="2635d-148">ワークスペースを選択して、[ **ログ** ] に移動し、[クエリ] を使用して、ユーザー設定フィールドを含むハートビートレコードを取得し :::no-loc text="Microsoft Teams Rooms"::: ます。</span><span class="sxs-lookup"><span data-stu-id="2635d-148">Select your workspace and go to **Logs** and use a query to retrieve the heartbeat records that will have the custom fields for :::no-loc text="Microsoft Teams Rooms":::.</span></span>
    2.  <span data-ttu-id="2635d-149">サンプルクエリ: `Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="2635d-149">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3.  <span data-ttu-id="2635d-150">会議アプリによって生成されたイベントを含むログレコードが、クエリによって返されていることを確認してください :::no-loc text="Microsoft Teams Rooms"::: 。</span><span class="sxs-lookup"><span data-stu-id="2635d-150">Make sure that the query returns log records that include events generated by the :::no-loc text="Microsoft Teams Rooms"::: meetings app.</span></span>

4.  <span data-ttu-id="2635d-151">ハードウェアの問題を生成し、必要なイベントがログに記録されていることを確認し :::no-loc text="Azure Log Analytics"::: ます。</span><span class="sxs-lookup"><span data-stu-id="2635d-151">Generate a hardware issue, and validate that the required events are logged in :::no-loc text="Azure Log Analytics":::.</span></span>
    1.  <span data-ttu-id="2635d-152">テストシステムでいずれかの周辺機器を取り外し :::no-loc text="Microsoft Teams Rooms"::: ます。</span><span class="sxs-lookup"><span data-stu-id="2635d-152">Unplug one of the peripheral devices on the test :::no-loc text="Microsoft Teams Rooms"::: system.</span></span> <span data-ttu-id="2635d-153">カメラ、スピーカーフォン、マイク、またはフロントルームディスプレイの場合があります</span><span class="sxs-lookup"><span data-stu-id="2635d-153">This could be the camera, speakerphone, microphone, or Front Room Display</span></span>
    2.  <span data-ttu-id="2635d-154">イベントログが設定されるまで10分待ち :::no-loc text="Azure Log Analytics"::: ます。</span><span class="sxs-lookup"><span data-stu-id="2635d-154">Wait 10 minutes for the event log to be populated in :::no-loc text="Azure Log Analytics":::.</span></span>
    3.  <span data-ttu-id="2635d-155">クエリを使用して、ハードウェアエラーイベントを一覧表示します。 `Event | where Source == "SRS-App" and EventID == 3001`</span><span class="sxs-lookup"><span data-stu-id="2635d-155">Use a query to list hardware error events: `Event | where Source == "SRS-App" and EventID == 3001`</span></span>

5.  <span data-ttu-id="2635d-156">アプリケーションの問題を生成し、必要なイベントがログに記録されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2635d-156">Generate an application issue, and validate that the required events are logged.</span></span>
    1.  <span data-ttu-id="2635d-157">:::no-loc text="Microsoft Teams Rooms":::アプリケーションの構成を変更し、誤ったセッション開始プロトコル (SIP) アドレスとパスワードのペアを入力します。</span><span class="sxs-lookup"><span data-stu-id="2635d-157">Modify :::no-loc text="Microsoft Teams Rooms"::: application configuration, and type an incorrect Session Initiation Protocol (SIP) address/password pair.</span></span>
    2.  <span data-ttu-id="2635d-158">イベントログが設定されるまで10分待ち :::no-loc text="Azure Log Analytics"::: ます。</span><span class="sxs-lookup"><span data-stu-id="2635d-158">Wait 10 minutes for the event log to be populated in :::no-loc text="Azure Log Analytics":::.</span></span>
    3.  <span data-ttu-id="2635d-159">クエリを使用して、アプリケーションエラーイベントを一覧表示します。 `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span><span class="sxs-lookup"><span data-stu-id="2635d-159">Use a query to list application error events: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2635d-160">カスタムフィールドを構成するには、これらのサンプルイベントログが必要です。</span><span class="sxs-lookup"><span data-stu-id="2635d-160">These sample event logs are required before custom fields can be configured.</span></span> <span data-ttu-id="2635d-161">必要なイベントログを収集するまでは、次の手順に進んではいけません。</span><span class="sxs-lookup"><span data-stu-id="2635d-161">Don't proceed to the next step until you have collected the required event logs.</span></span>

## <a name="map-custom-fields"></a><span data-ttu-id="2635d-162">カスタム フィールドをマップする</span><span class="sxs-lookup"><span data-stu-id="2635d-162">Map custom fields</span></span>
<span data-ttu-id="2635d-163"><a name="Custom_fields"> </a></span><span class="sxs-lookup"><span data-stu-id="2635d-163"><a name="Custom_fields"> </a></span></span>

<span data-ttu-id="2635d-164">カスタムフィールドを使って、イベントログから特定のデータを抽出します。</span><span class="sxs-lookup"><span data-stu-id="2635d-164">You use custom fields to extract specific data from the event logs.</span></span> <span data-ttu-id="2635d-165">タイル、ダッシュボードビュー、およびアラートで後で使用されるカスタムフィールドを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2635d-165">You need to define custom fields that will be used later with your tiles, dashboard views, and alerts.</span></span> <span data-ttu-id="2635d-166">カスタムフィールドの作成を開始する前に、「[ユーザー設定フィールド :::no-loc text="Log Analytics"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) 」を参照して、概念を理解しておいてください。</span><span class="sxs-lookup"><span data-stu-id="2635d-166">See [Custom fields in :::no-loc text="Log Analytics":::](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) and become familiar with the concepts before you start creating your custom fields.</span></span>

<span data-ttu-id="2635d-167">キャプチャしたイベントログからカスタムフィールドを抽出するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2635d-167">To extract your custom fields out of the captured event logs, follow these steps:</span></span>

1.  <span data-ttu-id="2635d-168">[ :::no-loc text="Microsoft Azure"::: ポータル](https://portal.azure.com)にサインインして、ワークスペースに移動して :::no-loc text="Log Analytics"::: 選択します。</span><span class="sxs-lookup"><span data-stu-id="2635d-168">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2. <span data-ttu-id="2635d-169">デバイスによって生成されるイベントを一覧表示し :::no-loc text="Microsoft Teams Rooms"::: ます。</span><span class="sxs-lookup"><span data-stu-id="2635d-169">List the events generated by a :::no-loc text="Microsoft Teams Rooms"::: device:</span></span>
   1.  <span data-ttu-id="2635d-170">[ **ログ** ] に移動し、クエリを使用してユーザー設定フィールドを含むレコードを取得します。</span><span class="sxs-lookup"><span data-stu-id="2635d-170">Go to **Logs** and use a query to retrieve the records that will have the custom field.</span></span>
   2.  <span data-ttu-id="2635d-171">サンプルクエリ: `Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="2635d-171">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3. <span data-ttu-id="2635d-172">いずれかのレコードを選び、左側のボタンを選んで、フィールド抽出ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="2635d-172">Select one of the records, select the button to the left, and start the field extraction wizard.</span></span>
4. <span data-ttu-id="2635d-173">RenderedDescription から抽出するデータを強調表示し、フィールドタイトルを入力します。</span><span class="sxs-lookup"><span data-stu-id="2635d-173">Highlight the data you'd like to extract from the RenderedDescription and provide a Field Title.</span></span> <span data-ttu-id="2635d-174">使用する必要があるフィールド名は、表1に記載されています。</span><span class="sxs-lookup"><span data-stu-id="2635d-174">The field names that you should use are provided in Table 1.</span></span>
5. <span data-ttu-id="2635d-175">*表 1*に示されているマッピングを使用します。</span><span class="sxs-lookup"><span data-stu-id="2635d-175">Use the mappings shown in *Table 1*.</span></span> <span data-ttu-id="2635d-176">:::no-loc text="Log Analytics":::新しいフィールドを定義するときに、自動的に\*\* \_ CF\*\*文字列が追加されます。</span><span class="sxs-lookup"><span data-stu-id="2635d-176">:::no-loc text="Log Analytics"::: will automatically append the **\_CF** string when you define the new field.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2635d-177">JSON と :::no-loc text="Log Analytics"::: フィールドはすべて大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2635d-177">Remember that all JSON and :::no-loc text="Log Analytics"::: fields are case-sensitive.</span></span>
> 
> <span data-ttu-id="2635d-178">以下の表のユーザー設定フィールドごとに、必要なクエリに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2635d-178">Pay attention to the queries required for each custom field in the table below.</span></span> <span data-ttu-id="2635d-179">:::no-loc text="Log Analytics":::ユーザー設定フィールドの値を正しく抽出するには、適切なクエリを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2635d-179">You need to use the correct queries for :::no-loc text="Log Analytics"::: to successfully extract custom field values.</span></span>
> 
<span data-ttu-id="2635d-180">**表1**</span><span class="sxs-lookup"><span data-stu-id="2635d-180">**Table 1**</span></span>

| <span data-ttu-id="2635d-181">**JSON フィールド**</span><span class="sxs-lookup"><span data-stu-id="2635d-181">**JSON field**</span></span>                   | <span data-ttu-id="2635d-182">**:::no-loc text="Log Analytics"::: ユーザー設定フィールド**</span><span class="sxs-lookup"><span data-stu-id="2635d-182">**:::no-loc text="Log Analytics"::: custom field**</span></span> | <span data-ttu-id="2635d-183">**イベント ID**</span><span class="sxs-lookup"><span data-stu-id="2635d-183">**Event ID**</span></span> | <span data-ttu-id="2635d-184">**抽出に使用するクエリ**</span><span class="sxs-lookup"><span data-stu-id="2635d-184">**Query to use with the extraction**</span></span>                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| <span data-ttu-id="2635d-185">説明</span><span class="sxs-lookup"><span data-stu-id="2635d-185">Description</span></span>                      | <span data-ttu-id="2635d-186">SRSEventDescription</span><span class="sxs-lookup"><span data-stu-id="2635d-186">SRSEventDescription</span></span>         | <span data-ttu-id="2635d-187">**2000**</span><span class="sxs-lookup"><span data-stu-id="2635d-187">**2000**</span></span>     | <span data-ttu-id="2635d-188">\|Source = = "SRS-アプリ" And EventID = = 2000</span><span class="sxs-lookup"><span data-stu-id="2635d-188">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="2635d-189">ResourceState</span><span class="sxs-lookup"><span data-stu-id="2635d-189">ResourceState</span></span>                    | <span data-ttu-id="2635d-190">SRSResourceState</span><span class="sxs-lookup"><span data-stu-id="2635d-190">SRSResourceState</span></span>            | <span data-ttu-id="2635d-191">**2000**</span><span class="sxs-lookup"><span data-stu-id="2635d-191">**2000**</span></span>     | <span data-ttu-id="2635d-192">\|Source = = "SRS-アプリ" And EventID = = 2000</span><span class="sxs-lookup"><span data-stu-id="2635d-192">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="2635d-193">OperationName</span><span class="sxs-lookup"><span data-stu-id="2635d-193">OperationName</span></span>                    | <span data-ttu-id="2635d-194">SRSOperationName</span><span class="sxs-lookup"><span data-stu-id="2635d-194">SRSOperationName</span></span>            | <span data-ttu-id="2635d-195">**2000**</span><span class="sxs-lookup"><span data-stu-id="2635d-195">**2000**</span></span>     | <span data-ttu-id="2635d-196">\|Source = = "SRS-アプリ" And EventID = = 2000</span><span class="sxs-lookup"><span data-stu-id="2635d-196">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="2635d-197">OperationResult</span><span class="sxs-lookup"><span data-stu-id="2635d-197">OperationResult</span></span>                  | <span data-ttu-id="2635d-198">SRSOperationResult</span><span class="sxs-lookup"><span data-stu-id="2635d-198">SRSOperationResult</span></span>          | <span data-ttu-id="2635d-199">**2000**</span><span class="sxs-lookup"><span data-stu-id="2635d-199">**2000**</span></span>     | <span data-ttu-id="2635d-200">\|Source = = "SRS-アプリ" And EventID = = 2000</span><span class="sxs-lookup"><span data-stu-id="2635d-200">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="2635d-201">OS</span><span class="sxs-lookup"><span data-stu-id="2635d-201">OS</span></span>                               | <span data-ttu-id="2635d-202">SRSOSVersion</span><span class="sxs-lookup"><span data-stu-id="2635d-202">SRSOSVersion</span></span>                | <span data-ttu-id="2635d-203">**2000**</span><span class="sxs-lookup"><span data-stu-id="2635d-203">**2000**</span></span>     | <span data-ttu-id="2635d-204">\|Source = = "SRS-アプリ" And EventID = = 2000</span><span class="sxs-lookup"><span data-stu-id="2635d-204">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="2635d-205">OSVersion</span><span class="sxs-lookup"><span data-stu-id="2635d-205">OSVersion</span></span>                        | <span data-ttu-id="2635d-206">SRSOSLongVersion</span><span class="sxs-lookup"><span data-stu-id="2635d-206">SRSOSLongVersion</span></span>            | <span data-ttu-id="2635d-207">**2000**</span><span class="sxs-lookup"><span data-stu-id="2635d-207">**2000**</span></span>     | <span data-ttu-id="2635d-208">\|Source = = "SRS-アプリ" And EventID = = 2000</span><span class="sxs-lookup"><span data-stu-id="2635d-208">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="2635d-209">Alias</span><span class="sxs-lookup"><span data-stu-id="2635d-209">Alias</span></span>                            | <span data-ttu-id="2635d-210">SRSAlias</span><span class="sxs-lookup"><span data-stu-id="2635d-210">SRSAlias</span></span>                    | <span data-ttu-id="2635d-211">**2000**</span><span class="sxs-lookup"><span data-stu-id="2635d-211">**2000**</span></span>     | <span data-ttu-id="2635d-212">\|Source = = "SRS-アプリ" And EventID = = 2000</span><span class="sxs-lookup"><span data-stu-id="2635d-212">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="2635d-213">DisplayName</span><span class="sxs-lookup"><span data-stu-id="2635d-213">DisplayName</span></span>                      | <span data-ttu-id="2635d-214">SRSDisplayName</span><span class="sxs-lookup"><span data-stu-id="2635d-214">SRSDisplayName</span></span>              | <span data-ttu-id="2635d-215">**2000**</span><span class="sxs-lookup"><span data-stu-id="2635d-215">**2000**</span></span>     | <span data-ttu-id="2635d-216">\|Source = = "SRS-アプリ" And EventID = = 2000</span><span class="sxs-lookup"><span data-stu-id="2635d-216">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="2635d-217">AppVersion</span><span class="sxs-lookup"><span data-stu-id="2635d-217">AppVersion</span></span>                       | <span data-ttu-id="2635d-218">SRSAppVersion</span><span class="sxs-lookup"><span data-stu-id="2635d-218">SRSAppVersion</span></span>               | <span data-ttu-id="2635d-219">**2000**</span><span class="sxs-lookup"><span data-stu-id="2635d-219">**2000**</span></span>     | <span data-ttu-id="2635d-220">\|Source = = "SRS-アプリ" And EventID = = 2000</span><span class="sxs-lookup"><span data-stu-id="2635d-220">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="2635d-221">IPv4Address</span><span class="sxs-lookup"><span data-stu-id="2635d-221">IPv4Address</span></span>                      | <span data-ttu-id="2635d-222">SRSIPv4Address</span><span class="sxs-lookup"><span data-stu-id="2635d-222">SRSIPv4Address</span></span>              | <span data-ttu-id="2635d-223">**2000**</span><span class="sxs-lookup"><span data-stu-id="2635d-223">**2000**</span></span>     | <span data-ttu-id="2635d-224">\|Source = = "SRS-アプリ" And EventID = = 2000</span><span class="sxs-lookup"><span data-stu-id="2635d-224">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="2635d-225">IPv6Address</span><span class="sxs-lookup"><span data-stu-id="2635d-225">IPv6Address</span></span>                      | <span data-ttu-id="2635d-226">SRSIPv6Address</span><span class="sxs-lookup"><span data-stu-id="2635d-226">SRSIPv6Address</span></span>              | <span data-ttu-id="2635d-227">**2000**</span><span class="sxs-lookup"><span data-stu-id="2635d-227">**2000**</span></span>     | <span data-ttu-id="2635d-228">\|Source = = "SRS-アプリ" And EventID = = 2000</span><span class="sxs-lookup"><span data-stu-id="2635d-228">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="2635d-229">会議のマイクの状態</span><span class="sxs-lookup"><span data-stu-id="2635d-229">Conference Microphone status</span></span>     | <span data-ttu-id="2635d-230">Srsconfマイクロ電話の状態</span><span class="sxs-lookup"><span data-stu-id="2635d-230">SRSConfMicrophoneStatus</span></span>     | <span data-ttu-id="2635d-231">**3001**</span><span class="sxs-lookup"><span data-stu-id="2635d-231">**3001**</span></span>     | <span data-ttu-id="2635d-232">\|Source = = "SRS-アプリ" And EventID = = 3001</span><span class="sxs-lookup"><span data-stu-id="2635d-232">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="2635d-233">会議のスピーカーの状態</span><span class="sxs-lookup"><span data-stu-id="2635d-233">Conference Speaker status</span></span>        | <span data-ttu-id="2635d-234">SRSConfSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="2635d-234">SRSConfSpeakerStatus</span></span>        | <span data-ttu-id="2635d-235">**3001**</span><span class="sxs-lookup"><span data-stu-id="2635d-235">**3001**</span></span>     | <span data-ttu-id="2635d-236">\|Source = = "SRS-アプリ" And EventID = = 3001</span><span class="sxs-lookup"><span data-stu-id="2635d-236">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="2635d-237">既定のスピーカーの状態</span><span class="sxs-lookup"><span data-stu-id="2635d-237">Default Speaker status</span></span>           | <span data-ttu-id="2635d-238">SRSDefaultSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="2635d-238">SRSDefaultSpeakerStatus</span></span>     | <span data-ttu-id="2635d-239">**3001**</span><span class="sxs-lookup"><span data-stu-id="2635d-239">**3001**</span></span>     | <span data-ttu-id="2635d-240">\|Source = = "SRS-アプリ" And EventID = = 3001</span><span class="sxs-lookup"><span data-stu-id="2635d-240">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="2635d-241">カメラの状態</span><span class="sxs-lookup"><span data-stu-id="2635d-241">Camera status</span></span>                    | <span data-ttu-id="2635d-242">SRSCameraStatus</span><span class="sxs-lookup"><span data-stu-id="2635d-242">SRSCameraStatus</span></span>             | <span data-ttu-id="2635d-243">**3001**</span><span class="sxs-lookup"><span data-stu-id="2635d-243">**3001**</span></span>     | <span data-ttu-id="2635d-244">\|Source = = "SRS-アプリ" And EventID = = 3001</span><span class="sxs-lookup"><span data-stu-id="2635d-244">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="2635d-245">部屋の表面の表示状態</span><span class="sxs-lookup"><span data-stu-id="2635d-245">Front of Room Display status</span></span>     | <span data-ttu-id="2635d-246">SRSFORDStatus</span><span class="sxs-lookup"><span data-stu-id="2635d-246">SRSFORDStatus</span></span>               | <span data-ttu-id="2635d-247">**3001**</span><span class="sxs-lookup"><span data-stu-id="2635d-247">**3001**</span></span>     | <span data-ttu-id="2635d-248">\|Source = = "SRS-アプリ" And EventID = = 3001</span><span class="sxs-lookup"><span data-stu-id="2635d-248">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="2635d-249">モーションセンサーの状態</span><span class="sxs-lookup"><span data-stu-id="2635d-249">Motion Sensor status</span></span>             | <span data-ttu-id="2635d-250">SRSMotionSensorStatus</span><span class="sxs-lookup"><span data-stu-id="2635d-250">SRSMotionSensorStatus</span></span>       | <span data-ttu-id="2635d-251">**3001**</span><span class="sxs-lookup"><span data-stu-id="2635d-251">**3001**</span></span>     | <span data-ttu-id="2635d-252">\|Source = = "SRS-アプリ" And EventID = = 3001</span><span class="sxs-lookup"><span data-stu-id="2635d-252">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="2635d-253">HDMI 取り込みの状態</span><span class="sxs-lookup"><span data-stu-id="2635d-253">HDMI Ingest status</span></span>               | <span data-ttu-id="2635d-254">SRSHDMIIngestStatus</span><span class="sxs-lookup"><span data-stu-id="2635d-254">SRSHDMIIngestStatus</span></span>         | <span data-ttu-id="2635d-255">**3001**</span><span class="sxs-lookup"><span data-stu-id="2635d-255">**3001**</span></span>     | <span data-ttu-id="2635d-256">\|Source = = "SRS-アプリ" And EventID = = 3001</span><span class="sxs-lookup"><span data-stu-id="2635d-256">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a><span data-ttu-id="2635d-257">ビューの定義 :::no-loc text="Microsoft Teams Rooms"::::::no-loc text="Log Analytics":::</span><span class="sxs-lookup"><span data-stu-id="2635d-257">Define the :::no-loc text="Microsoft Teams Rooms"::: views in :::no-loc text="Log Analytics":::</span></span>
<span data-ttu-id="2635d-258"><a name="Define_Views"> </a></span><span class="sxs-lookup"><span data-stu-id="2635d-258"><a name="Define_Views"> </a></span></span>

<span data-ttu-id="2635d-259">データが収集され、ユーザー設定フィールドがマップされた後、ビューデザイナーを使用して、さまざまなタイルを含むダッシュボードを作成し、イベントを監視することができ :::no-loc text="Microsoft Teams Rooms"::: ます。</span><span class="sxs-lookup"><span data-stu-id="2635d-259">After data is collected and custom fields are mapped, you can use View Designer to develop a dashboard containing various tiles to monitor :::no-loc text="Microsoft Teams Rooms"::: events.</span></span> <span data-ttu-id="2635d-260">次のタイルを作成するには、[ビューデザイナーを使用します。</span><span class="sxs-lookup"><span data-stu-id="2635d-260">Use View Designer to create the following tiles.</span></span> <span data-ttu-id="2635d-261">詳細については、「[デザイナー :::no-loc text="Log Analytics"::: でビューデザイナーを使用してカスタムビューを作成](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2635d-261">For more information, see [Create custom views by using View Designer in :::no-loc text="Log Analytics":::](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)</span></span>

> [!NOTE]
> <span data-ttu-id="2635d-262">ダッシュボードタイルが正常に動作するためには、このガイドの前の手順が完了している必要があります。</span><span class="sxs-lookup"><span data-stu-id="2635d-262">Previous steps in this guide should have been completed for the dashboard tiles to work properly.</span></span>

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a><span data-ttu-id="2635d-263">インポート方法を使用して Microsoft Teams のルームダッシュボードを作成する</span><span class="sxs-lookup"><span data-stu-id="2635d-263">Create a Microsoft Teams Rooms dashboard by using the import method</span></span>

<span data-ttu-id="2635d-264">ダッシュボードをインポート :::no-loc text="Microsoft Teams Rooms"::: して、デバイスの監視をすばやく開始することができます。</span><span class="sxs-lookup"><span data-stu-id="2635d-264">You can import an :::no-loc text="Microsoft Teams Rooms"::: dashboard and start monitoring your devices quickly.</span></span> <span data-ttu-id="2635d-265">ダッシュボードをインポートするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2635d-265">Take the following steps to import the dashboard:</span></span>

1.  <span data-ttu-id="2635d-266">Omsview ダッシュボードファイル [SkypeRoomSystems_v2](https://go.microsoft.com/fwlink/?linkid=835675) を取得します。</span><span class="sxs-lookup"><span data-stu-id="2635d-266">Get the [SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675) dashboard file.</span></span>
2.  <span data-ttu-id="2635d-267">[ :::no-loc text="Microsoft Azure"::: ポータル](https://portal.azure.com)にサインインして、ワークスペースに移動して :::no-loc text="Log Analytics"::: 選択します。</span><span class="sxs-lookup"><span data-stu-id="2635d-267">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>
3.  <span data-ttu-id="2635d-268">**ビューデザイナー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="2635d-268">Open **View Designer**.</span></span>
4.  <span data-ttu-id="2635d-269">[ **インポート**] を選択し、 **omsview ファイル SkypeRoomSystems_v2** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2635d-269">Select **Import**, and then select the **SkypeRoomSystems_v2.omsview** file.</span></span>
5.  <span data-ttu-id="2635d-270">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2635d-270">Select **Save**.</span></span>

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a><span data-ttu-id="2635d-271">Microsoft Teams のルームダッシュボードを手動で作成する</span><span class="sxs-lookup"><span data-stu-id="2635d-271">Create a Microsoft Teams Rooms dashboard manually</span></span>

<span data-ttu-id="2635d-272">または、独自のダッシュボードを作成して、監視するタイルのみを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="2635d-272">Alternatively, you can create your own dashboard and add only the tiles that you wish to monitor.</span></span>

#### <a name="configure-the-overview-tile"></a><span data-ttu-id="2635d-273">概要タイルを構成する</span><span class="sxs-lookup"><span data-stu-id="2635d-273">Configure the Overview Tile</span></span>

1.  <span data-ttu-id="2635d-274">**ビューデザイナー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="2635d-274">Open **View Designer**.</span></span>
2.  <span data-ttu-id="2635d-275">[ **概要] タイル**を選択し、ギャラリーから **2 つの数値** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2635d-275">Select **Overview Tile**, and then select **Two numbers** from the gallery.</span></span>
3.  <span data-ttu-id="2635d-276">タイルに名前を指定 **:::no-loc text="Microsoft Teams Rooms":::** します。</span><span class="sxs-lookup"><span data-stu-id="2635d-276">Name the tile **:::no-loc text="Microsoft Teams Rooms":::**.</span></span>
4.  <span data-ttu-id="2635d-277">最初の **タイル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-277">Define the **First Tile**:</span></span><br>
    <span data-ttu-id="2635d-278">**凡例:** 1ヶ月以内に少なくとも1回、ハートビートを送信したデバイス</span><span class="sxs-lookup"><span data-stu-id="2635d-278">**Legend:** Devices that sent a heartbeat at least once within the last month</span></span><br>
    <span data-ttu-id="2635d-279">**クエリ:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="2635d-279">**Query:** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
5.  <span data-ttu-id="2635d-280">**2 番目のタイル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-280">Define the **Second Tile**:</span></span><br>
    <span data-ttu-id="2635d-281">**凡例:** 1時間以内にハートビートを送信したアクティブなデバイス</span><span class="sxs-lookup"><span data-stu-id="2635d-281">**Legend:** Active devices that sent a heartbeat within the last hour</span></span><br>
    <span data-ttu-id="2635d-282">**クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="2635d-282">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
6.  <span data-ttu-id="2635d-283">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2635d-283">Select **Apply**.</span></span>

### <a name="create-a-tile-that-displays-active-devices"></a><span data-ttu-id="2635d-284">アクティブなデバイスを表示するタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="2635d-284">Create a tile that displays active devices</span></span>

1.  <span data-ttu-id="2635d-285">[ **ダッシュボードの表示** ] を選択して、タイルの追加を開始します。</span><span class="sxs-lookup"><span data-stu-id="2635d-285">Select **View Dashboard** to start adding your tiles.</span></span>
2.  <span data-ttu-id="2635d-286">ギャラリーから **番号 & リスト** を選択する</span><span class="sxs-lookup"><span data-stu-id="2635d-286">Select **Number & list** from the gallery</span></span>
3.  <span data-ttu-id="2635d-287">**一般的な**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-287">Define the **General** properties:</span></span><br>
    <span data-ttu-id="2635d-288">**グループタイトル:** ハートビートの状態</span><span class="sxs-lookup"><span data-stu-id="2635d-288">**Group Title:** Heartbeat Status</span></span><br>
    <span data-ttu-id="2635d-289">**新しいグループ:** 選択した</span><span class="sxs-lookup"><span data-stu-id="2635d-289">**New Group:** Selected</span></span>
4.  <span data-ttu-id="2635d-290">**タイル**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-290">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="2635d-291">**凡例:** アクティブなデバイス (過去20分間に送信されたハートビート)</span><span class="sxs-lookup"><span data-stu-id="2635d-291">**Legend:** Active devices (heartbeat sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="2635d-292">\*\*タイルのクエリ: \*\* ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="2635d-292">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span></span>
5.  <span data-ttu-id="2635d-293">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-293">Define the **List** properties:</span></span><br>
    <span data-ttu-id="2635d-294">**リストクエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="2635d-294">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
6.  <span data-ttu-id="2635d-295">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-295">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="2635d-296">**Name:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="2635d-296">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="2635d-297">**値:** 最終ハートビート</span><span class="sxs-lookup"><span data-stu-id="2635d-297">**Value:** Last Heartbeat</span></span>
7.  <span data-ttu-id="2635d-298">**ナビゲーションクエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-298">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="2635d-299">[ **適用**]、[ **閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="2635d-299">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a><span data-ttu-id="2635d-300">接続の問題が発生しているデバイスを表示するタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="2635d-300">Create a tile that displays devices that have connectivity issues</span></span>

1.  <span data-ttu-id="2635d-301">ギャラリーから [ **番号 & リスト** ] を選び、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="2635d-301">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="2635d-302">**一般的な**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-302">Define the **General** properties:</span></span><br>
    <span data-ttu-id="2635d-303">**グループタイトル:** 空のままにする</span><span class="sxs-lookup"><span data-stu-id="2635d-303">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="2635d-304">**新しいグループ:** 未選択</span><span class="sxs-lookup"><span data-stu-id="2635d-304">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="2635d-305">**タイル**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-305">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="2635d-306">**凡例:** 非アクティブなデバイス (過去20分間送信されたハートビートメッセージなし)</span><span class="sxs-lookup"><span data-stu-id="2635d-306">**Legend:** Inactive Devices (no heartbeat message sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="2635d-307">\*\*タイルのクエリ: \*\* ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span><span class="sxs-lookup"><span data-stu-id="2635d-307">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span></span>
4.  <span data-ttu-id="2635d-308">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-308">Define the **List** properties:</span></span><br>
    <span data-ttu-id="2635d-309">**リストクエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="2635d-309">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="2635d-310">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-310">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="2635d-311">**Name:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="2635d-311">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="2635d-312">**値:** 最終ハートビート</span><span class="sxs-lookup"><span data-stu-id="2635d-312">**Value:** Last Heartbeat</span></span>
6.  <span data-ttu-id="2635d-313">**ナビゲーションクエリ**を定義する:</span><span class="sxs-lookup"><span data-stu-id="2635d-313">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="2635d-314">[ **適用**]、[ **閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="2635d-314">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a><span data-ttu-id="2635d-315">ハードウェアエラーが発生したデバイスを表示するタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="2635d-315">Create a tile that displays devices that have a hardware error</span></span>

1.  <span data-ttu-id="2635d-316">ギャラリーから [ **番号 & リスト** ] を選び、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="2635d-316">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="2635d-317">**一般的な**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-317">Define the **General** properties:</span></span><br>
    <span data-ttu-id="2635d-318">**グループタイトル:** ハードウェアの状態</span><span class="sxs-lookup"><span data-stu-id="2635d-318">**Group Title:** Hardware Status</span></span><br>
    <span data-ttu-id="2635d-319">**新しいグループ:** 選択した</span><span class="sxs-lookup"><span data-stu-id="2635d-319">**New Group:** Selected</span></span>
3.  <span data-ttu-id="2635d-320">**タイル**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-320">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="2635d-321">**凡例:** 過去1時間にハードウェアエラーが発生したデバイス</span><span class="sxs-lookup"><span data-stu-id="2635d-321">**Legend:** Devices that experienced a hardware error in the last hour</span></span><br>
    <span data-ttu-id="2635d-322">\*\*タイルのクエリ: \*\* ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="2635d-322">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="2635d-323">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-323">Define the **List** properties:</span></span><br>
    <span data-ttu-id="2635d-324">**リストクエリ:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="2635d-324">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="2635d-325">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-325">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="2635d-326">**Name:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="2635d-326">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="2635d-327">**値:** 最後のエラー</span><span class="sxs-lookup"><span data-stu-id="2635d-327">**Value:** Last Error</span></span>
6.  <span data-ttu-id="2635d-328">**ナビゲーションクエリ**を定義する:</span><span class="sxs-lookup"><span data-stu-id="2635d-328">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="2635d-329">[ **適用**]、[ **閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="2635d-329">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a><span data-ttu-id="2635d-330">オペレーティングシステムのバージョンを表示するタイルを作成する :::no-loc text="Microsoft Teams Rooms":::</span><span class="sxs-lookup"><span data-stu-id="2635d-330">Create a tile that displays :::no-loc text="Microsoft Teams Rooms"::: Operating System versions</span></span>

1.  <span data-ttu-id="2635d-331">ギャラリーから [ **ドーナツ & リスト** ] を選び、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="2635d-331">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="2635d-332">**一般的な**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-332">Define the **General** properties:</span></span><br>
    <span data-ttu-id="2635d-333">**グループタイトル:** オペレーティングシステムの詳細</span><span class="sxs-lookup"><span data-stu-id="2635d-333">**Group Title:** Operating System details</span></span><br>
    <span data-ttu-id="2635d-334">**新しいグループ:** 選択した</span><span class="sxs-lookup"><span data-stu-id="2635d-334">**New Group:** Selected</span></span>
3.  <span data-ttu-id="2635d-335">**ヘッダー**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-335">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="2635d-336">**タイトル:** オペレーティングシステムのバージョン</span><span class="sxs-lookup"><span data-stu-id="2635d-336">**Title:** Operating System versions</span></span><br>
    <span data-ttu-id="2635d-337">**サブタイトル:** 特定の OS バージョンを実行しているデバイス</span><span class="sxs-lookup"><span data-stu-id="2635d-337">**Subtitle:** Devices running specific OS versions</span></span>
4.  <span data-ttu-id="2635d-338">**ドーナツ**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-338">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="2635d-339">**クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span><span class="sxs-lookup"><span data-stu-id="2635d-339">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span></span><br>
    <span data-ttu-id="2635d-340">**テキストの中央揃え:** デバイス</span><span class="sxs-lookup"><span data-stu-id="2635d-340">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="2635d-341">**操作:** "</span><span class="sxs-lookup"><span data-stu-id="2635d-341">**Operation:** Sum</span></span>
5.  <span data-ttu-id="2635d-342">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-342">Define the **List** properties.</span></span><br>
    <span data-ttu-id="2635d-343">**リストクエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span><span class="sxs-lookup"><span data-stu-id="2635d-343">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="2635d-344">**グラフの非表示:** 選択した</span><span class="sxs-lookup"><span data-stu-id="2635d-344">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="2635d-345">**スパークラインを有効にする:** 未選択</span><span class="sxs-lookup"><span data-stu-id="2635d-345">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="2635d-346">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-346">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="2635d-347">**Name:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="2635d-347">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="2635d-348">**値:** 空のままにする</span><span class="sxs-lookup"><span data-stu-id="2635d-348">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="2635d-349">**ナビゲーションクエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-349">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="2635d-350">[ **適用** ]、[ **閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="2635d-350">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a><span data-ttu-id="2635d-351">アプリケーションのバージョンを表示するタイルを作成する :::no-loc text="Microsoft Teams Rooms":::</span><span class="sxs-lookup"><span data-stu-id="2635d-351">Create a tile that displays :::no-loc text="Microsoft Teams Rooms"::: application versions</span></span>

1.  <span data-ttu-id="2635d-352">ギャラリーから [ **ドーナツ & リスト** ] を選び、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="2635d-352">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="2635d-353">**一般的な**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-353">Define the **General** properties:</span></span><br>
    <span data-ttu-id="2635d-354">**グループタイトル:** :::no-loc text="Microsoft Teams Rooms"::: アプリケーションの詳細</span><span class="sxs-lookup"><span data-stu-id="2635d-354">**Group Title:** :::no-loc text="Microsoft Teams Rooms"::: application details</span></span><br>
    <span data-ttu-id="2635d-355">**新しいグループ:** 選択した</span><span class="sxs-lookup"><span data-stu-id="2635d-355">**New Group:** Selected</span></span>
3.  <span data-ttu-id="2635d-356">**ヘッダー**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-356">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="2635d-357">**タイトル:** アプリケーションのバージョン</span><span class="sxs-lookup"><span data-stu-id="2635d-357">**Title:** Application versions</span></span><br>
    <span data-ttu-id="2635d-358">**サブタイトル:** 特定のアプリケーションバージョンを実行しているデバイス</span><span class="sxs-lookup"><span data-stu-id="2635d-358">**Subtitle:** Devices running specific application versions</span></span>
4.  <span data-ttu-id="2635d-359">**ドーナツ**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-359">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="2635d-360">**クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span><span class="sxs-lookup"><span data-stu-id="2635d-360">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span></span><br>
    <span data-ttu-id="2635d-361">**テキストの中央揃え:** デバイス</span><span class="sxs-lookup"><span data-stu-id="2635d-361">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="2635d-362">**操作:** "</span><span class="sxs-lookup"><span data-stu-id="2635d-362">**Operation:** Sum</span></span>
5.  <span data-ttu-id="2635d-363">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-363">Define the **List** properties.</span></span><br>
    <span data-ttu-id="2635d-364">**リストクエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span><span class="sxs-lookup"><span data-stu-id="2635d-364">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="2635d-365">**グラフの非表示:** 選択した</span><span class="sxs-lookup"><span data-stu-id="2635d-365">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="2635d-366">**スパークラインを有効にする:** 未選択</span><span class="sxs-lookup"><span data-stu-id="2635d-366">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="2635d-367">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-367">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="2635d-368">**Name:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="2635d-368">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="2635d-369">**値:** 空のままにする</span><span class="sxs-lookup"><span data-stu-id="2635d-369">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="2635d-370">**ナビゲーションクエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-370">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="2635d-371">[ **適用** ]、[ **閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="2635d-371">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a><span data-ttu-id="2635d-372">アプリケーションエラーが発生しているデバイスを表示するタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="2635d-372">Create a tile that displays devices that have an application error</span></span>

1.  <span data-ttu-id="2635d-373">ギャラリーから [ **番号 & リスト** ] を選び、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="2635d-373">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="2635d-374">**一般的な**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-374">Define the **General** properties.</span></span><br>
    <span data-ttu-id="2635d-375">**グループタイトル:** 空のままにする</span><span class="sxs-lookup"><span data-stu-id="2635d-375">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="2635d-376">**新しいグループ:** 未選択</span><span class="sxs-lookup"><span data-stu-id="2635d-376">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="2635d-377">**タイル**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-377">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="2635d-378">**凡例:** 過去1時間にアプリケーションにエラーが発生したデバイス</span><span class="sxs-lookup"><span data-stu-id="2635d-378">**Legend:** Devices that experienced an application error in the last hour</span></span><br>
    <span data-ttu-id="2635d-379">\*\*タイルのクエリ: \*\* ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="2635d-379">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="2635d-380">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-380">Define the **List** properties.</span></span><br>
    <span data-ttu-id="2635d-381">**リストクエリ:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="2635d-381">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="2635d-382">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-382">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="2635d-383">**Name:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="2635d-383">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="2635d-384">**値:** 最後のエラー</span><span class="sxs-lookup"><span data-stu-id="2635d-384">**Value:** Last Error</span></span>
6.  <span data-ttu-id="2635d-385">**ナビゲーションクエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-385">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="2635d-386">[ **適用** ]、[ **閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="2635d-386">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a><span data-ttu-id="2635d-387">再起動されたデバイスを表示するタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="2635d-387">Create a tile that displays devices that have been restarted</span></span>

1.  <span data-ttu-id="2635d-388">ギャラリーから [ **番号 & リスト** ] を選び、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="2635d-388">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="2635d-389">**一般的な**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-389">Define the **General** properties.</span></span><br>
    <span data-ttu-id="2635d-390">**グループタイトル:** 空のままにする</span><span class="sxs-lookup"><span data-stu-id="2635d-390">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="2635d-391">**新しいグループ:** 未選択</span><span class="sxs-lookup"><span data-stu-id="2635d-391">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="2635d-392">**タイル**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-392">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="2635d-393">**凡例:** 過去24時間以内にアプリケーションを再起動したデバイスと再起動回数</span><span class="sxs-lookup"><span data-stu-id="2635d-393">**Legend:** Devices where the application was restarted in the last 24 hours, and number of restarts</span></span><br>
    <span data-ttu-id="2635d-394">\*\*タイルのクエリ: \*\* ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="2635d-394">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="2635d-395">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-395">Define the **List** properties.</span></span><br>
    <span data-ttu-id="2635d-396">**リストクエリ:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span><span class="sxs-lookup"><span data-stu-id="2635d-396">**List Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span></span>
5.  <span data-ttu-id="2635d-397">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-397">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="2635d-398">**Name:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="2635d-398">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="2635d-399">**値:** 再起動回数</span><span class="sxs-lookup"><span data-stu-id="2635d-399">**Value:** Number of Restarts</span></span>
6.  <span data-ttu-id="2635d-400">**ナビゲーションクエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="2635d-400">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="2635d-401">[ **適用** ]、[ **閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="2635d-401">Select **Apply** and then **Close**.</span></span>
8.  <span data-ttu-id="2635d-402">[ **保存** ] を選択してダッシュボードを保存します。</span><span class="sxs-lookup"><span data-stu-id="2635d-402">Select **Save** to save your dashboard.</span></span>

<span data-ttu-id="2635d-403">これで、ビューの作成が完了しました。</span><span class="sxs-lookup"><span data-stu-id="2635d-403">Now you've completed creating your views.</span></span>

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a><span data-ttu-id="2635d-404">通知を設定する :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="2635d-404">Configure Alerts in :::no-loc text="Azure Monitor":::</span></span>
<span data-ttu-id="2635d-405"><a name="Alerts"> </a></span><span class="sxs-lookup"><span data-stu-id="2635d-405"><a name="Alerts"> </a></span></span>

<span data-ttu-id="2635d-406">:::no-loc text="Azure Monitor"::: コンソールで問題が発生したときに、管理者に通知する通知を生成でき :::no-loc text="Microsoft Teams Rooms"::: ます。</span><span class="sxs-lookup"><span data-stu-id="2635d-406">:::no-loc text="Azure Monitor"::: can raise alerts to notify the administrators, when a :::no-loc text="Microsoft Teams Rooms"::: console encounters an issue.</span></span>

<span data-ttu-id="2635d-407">:::no-loc text="Azure Monitor"::: スケジュールされたログ検索を定期的に実行する組み込みの通知メカニズムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2635d-407">:::no-loc text="Azure Monitor"::: includes a built-in alerting mechanism that runs through scheduled log searches at regular intervals.</span></span> <span data-ttu-id="2635d-408">ログ検索の結果が特定の条件と一致する場合は、通知レコードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2635d-408">If the results of the log search match some particular criteria, an alert record is created.</span></span>

<span data-ttu-id="2635d-409">このルールでは、1つ以上のアクションを自動的に実行して、通知を事前に通知するか、別のプロセスを起動することができます。</span><span class="sxs-lookup"><span data-stu-id="2635d-409">The rule can then automatically run one or more actions to proactively notify you of the alert or invoke another process.</span></span> <span data-ttu-id="2635d-410">次のような警告のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="2635d-410">The possible options with alerts are:</span></span>
-   <span data-ttu-id="2635d-411">メールを送信する</span><span class="sxs-lookup"><span data-stu-id="2635d-411">Sending an email</span></span>
-   <span data-ttu-id="2635d-412">HTTP POST 要求による外部プロセスの呼び出し</span><span class="sxs-lookup"><span data-stu-id="2635d-412">Invoking an external process through an HTTP POST request</span></span>
-   <span data-ttu-id="2635d-413">サービスでの runbook の開始 :::no-loc text="Azure Automation":::</span><span class="sxs-lookup"><span data-stu-id="2635d-413">Starting a runbook in :::no-loc text="Azure Automation"::: service</span></span>

<span data-ttu-id="2635d-414">通知の詳細については、「[ログの警告 :::no-loc text="Azure Monitor"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) 」を参照してください :::no-loc text="Azure Monitor"::: 。</span><span class="sxs-lookup"><span data-stu-id="2635d-414">See [Log alerts in :::no-loc text="Azure Monitor":::](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) to learn more about the alerts in :::no-loc text="Azure Monitor":::.</span></span>

> [!NOTE]
> <span data-ttu-id="2635d-415">次の例では、デバイスが :::no-loc text="Microsoft Teams Rooms"::: ハードウェアまたはアプリケーションエラーを生成したときにメール通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="2635d-415">The following examples send email alerts when a :::no-loc text="Microsoft Teams Rooms"::: device generates a hardware or an application error.</span></span>

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a><span data-ttu-id="2635d-416">ハードウェアの問題に関する電子メール通知を構成する :::no-loc text="Microsoft Teams Rooms":::</span><span class="sxs-lookup"><span data-stu-id="2635d-416">Configure an email alert for :::no-loc text="Microsoft Teams Rooms"::: hardware issues</span></span>

<span data-ttu-id="2635d-417">:::no-loc text="Microsoft Teams Rooms":::過去1時間以内にハードウェアの問題が発生したデバイスを確認する通知ルールを構成します。</span><span class="sxs-lookup"><span data-stu-id="2635d-417">Configure an alert rule that checks for :::no-loc text="Microsoft Teams Rooms"::: devices that have encountered hardware issues within the last hour.</span></span>
1.  <span data-ttu-id="2635d-418">[ :::no-loc text="Microsoft Azure"::: ポータル](https://portal.azure.com)にサインインして、ワークスペースに移動して :::no-loc text="Log Analytics"::: 選択します。</span><span class="sxs-lookup"><span data-stu-id="2635d-418">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2. <span data-ttu-id="2635d-419">ワークスペースに移動して、[ :::no-loc text="Log Analytics"::: **警告**] を選択し、[**新しい通知ルール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2635d-419">Navigate to your :::no-loc text="Log Analytics"::: workspace and select **Alerts** and then select **New alert rule**</span></span>

3. <span data-ttu-id="2635d-420">[**条件の追加**] を選択し、[**カスタムログの検索**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2635d-420">Select **Add condition** and then **Custom log search**</span></span>

4.  <span data-ttu-id="2635d-421">[検索クエリ] テキストボックスに、次のクエリを入力します。</span><span class="sxs-lookup"><span data-stu-id="2635d-421">Enter the following query to the Search query text box.</span></span><br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  <span data-ttu-id="2635d-422">アラートのロジック設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="2635d-422">Configure the Alert logic settings:</span></span><br>
    <span data-ttu-id="2635d-423">**基準:** 結果の数</span><span class="sxs-lookup"><span data-stu-id="2635d-423">**Based on:** Number of results</span></span><br>
    <span data-ttu-id="2635d-424">**条件:** より大きい</span><span class="sxs-lookup"><span data-stu-id="2635d-424">**Condition:** Greater then</span></span><br>
    <span data-ttu-id="2635d-425">**しきい値:** 0</span><span class="sxs-lookup"><span data-stu-id="2635d-425">**Threshold:** 0</span></span><br>

6. <span data-ttu-id="2635d-426">評価の設定を構成し、[ **完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2635d-426">Configure Evaluation settings and select **Done**:</span></span> <br>
    <span data-ttu-id="2635d-427">**期間 (分):** 60</span><span class="sxs-lookup"><span data-stu-id="2635d-427">**Period (in minutes):** 60</span></span><br>
    <span data-ttu-id="2635d-428">**頻度 (分):** 60</span><span class="sxs-lookup"><span data-stu-id="2635d-428">**Frequency (in minutes):** 60</span></span><br>

7. <span data-ttu-id="2635d-429">アクショングループを構成します。</span><span class="sxs-lookup"><span data-stu-id="2635d-429">Configure action groups:</span></span>
    1.  <span data-ttu-id="2635d-430">[**新規作成**] を選ぶ</span><span class="sxs-lookup"><span data-stu-id="2635d-430">Select **Create New**</span></span>
    2.  <span data-ttu-id="2635d-431">[ *アクショングループ名]* フィールドと [ *短縮名* ] フィールドに適切な名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2635d-431">Provide suitable names for the *Action group name* and *Short Name* fields.</span></span>
    3.  <span data-ttu-id="2635d-432">一意の *アクション名* を指定し、[ **メール/SMS/プッシュ/ボイス**] を選択して、[ **詳細の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2635d-432">Specify a unique *Action Name* and select **Email/SMS/Push/Voice**, and then select **Edit details**.</span></span>
    4.  <span data-ttu-id="2635d-433">[ **メール** ] チェックボックスをオンにして、アラートを受信するユーザーまたはグループのメールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="2635d-433">Select the **Email** checkbox and provide the email address of the person or group that will receive the alerts.</span></span>
    5.  <span data-ttu-id="2635d-434">また、SMS、音声通話、またはその両方の通知を受け取るために、電話番号を入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="2635d-434">You may also provide your phone number to get notified with SMS, a voice call or both.</span></span>
    6. <span data-ttu-id="2635d-435">[ **OK]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="2635d-435">Select **OK**.</span></span>

8. <span data-ttu-id="2635d-436">通知メールの件名行を上書きする場合は、[**アクションのカスタマイズ**を行う。</span><span class="sxs-lookup"><span data-stu-id="2635d-436">**Customize Actions** if you like to override the subject line of the alert emails.</span></span>

9. <span data-ttu-id="2635d-437">ルールの名前と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="2635d-437">Specify a rule name and description.</span></span><br>
    <span data-ttu-id="2635d-438">**ルール名:** :::no-loc text="Microsoft Teams Rooms"::: ハードウェアエラーアラート</span><span class="sxs-lookup"><span data-stu-id="2635d-438">**Rule Name:** :::no-loc text="Microsoft Teams Rooms"::: Hardware Failure Alert</span></span><br>
    <span data-ttu-id="2635d-439">**説明:** 過去1時間以内にハードウェアの問題が発生したデバイスの一覧</span><span class="sxs-lookup"><span data-stu-id="2635d-439">**Description:** List of devices that encountered a hardware issue within the last hour</span></span><br>

10. <span data-ttu-id="2635d-440">目的の重要度を選び、ルールが有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2635d-440">Select the intended severity and make sure the rule is enabled.</span></span>

11. <span data-ttu-id="2635d-441">[ **通知ルールの作成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2635d-441">Select **Create alert rule**.</span></span>

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a><span data-ttu-id="2635d-442">アプリケーションの問題に関する電子メール通知を構成する :::no-loc text="Microsoft Teams Rooms":::</span><span class="sxs-lookup"><span data-stu-id="2635d-442">Configure an email alert for :::no-loc text="Microsoft Teams Rooms"::: application issues</span></span>

<span data-ttu-id="2635d-443">同じ手順を繰り返しますが、次のクエリを使用して、過去1時間以内にアプリケーションの問題が発生したデバイスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="2635d-443">Repeat the same procedure but use the following query to list devices that have encountered application issues within the last hour.</span></span>

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

<span data-ttu-id="2635d-444">これで、通知の定義が完了しました。</span><span class="sxs-lookup"><span data-stu-id="2635d-444">Now you've completed defining alerts.</span></span> <span data-ttu-id="2635d-445">上記の例を使用して、追加の警告を定義できます。</span><span class="sxs-lookup"><span data-stu-id="2635d-445">You can define additional alerts by using the examples above.</span></span>

<span data-ttu-id="2635d-446">アラートが生成されると、過去1時間以内に問題が発生したデバイスの一覧を示すメールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2635d-446">When an alert is generated, you'll get an email that lists the devices that encountered an issue within the last hour.</span></span>

<span data-ttu-id="2635d-447">![サンプルの :::no-loc text="Azure Monitor"::: 通知メール] (.../media/Deploy-Azure-Monitor-6.png "サンプルの :::no-loc text="Azure Monitor"::: 通知メール")</span><span class="sxs-lookup"><span data-stu-id="2635d-447">![Sample :::no-loc text="Azure Monitor"::: alert email](../media/Deploy-Azure-Monitor-6.png "Sample :::no-loc text="Azure Monitor"::: alert email")</span></span>

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a><span data-ttu-id="2635d-448">すべてのデバイスを構成する :::no-loc text="Azure Monitoring":::</span><span class="sxs-lookup"><span data-stu-id="2635d-448">Configure all devices for :::no-loc text="Azure Monitoring":::</span></span>
<span data-ttu-id="2635d-449"><a name="configure_all_devices"> </a>ダッシュボードとアラートを構成したら、すべてのデバイスでエージェントをセットアップして構成し、 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: 監視展開を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="2635d-449"><a name="configure_all_devices"> </a> After the dashboards and alerts are configured, you can set up and configure :::no-loc text="Microsoft Monitoring"::: agent on all :::no-loc text="Microsoft Teams Rooms"::: devices to complete your monitoring deployment.</span></span>

<span data-ttu-id="2635d-450">エージェントは各デバイスで手動でインストールして構成することもでき :::no-loc text="Microsoft Monitoring"::: ますが、既存のソフトウェア展開ツールと方法を活用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2635d-450">Although you can install and configure the :::no-loc text="Microsoft Monitoring"::: agent manually on each device, we highly recommend you leverage existing software deployment tools and methods.</span></span>

<span data-ttu-id="2635d-451">初めてデバイスを構築する場合は :::no-loc text="Microsoft Teams Rooms"::: 、 :::no-loc text="Microsoft Monitoring"::: 構築プロセスの一部としてエージェントのセットアップと構成の手順を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="2635d-451">If you're building your :::no-loc text="Microsoft Teams Rooms"::: devices for the first time, you might want to include the :::no-loc text="Microsoft Monitoring"::: agent setup and configuration steps as part of your build process.</span></span> <span data-ttu-id="2635d-452">詳細については、「 [コマンドラインを使用してエージェントをインストール](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2635d-452">For more information, see [Install the agent using the command line](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).</span></span>

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a><span data-ttu-id="2635d-453">:::no-loc text="Microsoft Monitoring":::グループポリシーオブジェクト (GPO) を使用したエージェントの展開</span><span class="sxs-lookup"><span data-stu-id="2635d-453">Deploying :::no-loc text="Microsoft Monitoring"::: agent by using a Group Policy Object (GPO)</span></span>

<span data-ttu-id="2635d-454">実装前に既にデバイスを展開している場合は、提供されたスクリプトを使用して、 :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitoring"::: グループポリシーオブジェクトを使ってエージェントをセットアップし、構成することができ :::no-loc text="Active Directory"::: ます。</span><span class="sxs-lookup"><span data-stu-id="2635d-454">If you already deployed your :::no-loc text="Microsoft Teams Rooms"::: devices before you implement :::no-loc text="Azure Monitoring":::, you can use the provided script to set up and configure the agents by using :::no-loc text="Active Directory"::: group policy objects.</span></span>

1.  <span data-ttu-id="2635d-455">共有ネットワークパスを作成し、 **ドメインコンピューター** グループに読み取りアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="2635d-455">Create a shared network path and grant read access to **Domain Computers** group.</span></span>

2.  <span data-ttu-id="2635d-456">64ビット版のエージェントをダウンロードする :::no-loc text="Microsoft Monitoring"::: には :::no-loc text="Windows"::: 、 <https://go.microsoft.com/fwlink/?LinkID=517476></span><span class="sxs-lookup"><span data-stu-id="2635d-456">Download the 64-bit version of the :::no-loc text="Microsoft Monitoring"::: Agent for :::no-loc text="Windows"::: from <https://go.microsoft.com/fwlink/?LinkID=517476></span></span>

3.  <span data-ttu-id="2635d-457">ネットワーク共有にセットアップパッケージの内容を抽出します。</span><span class="sxs-lookup"><span data-stu-id="2635d-457">Extract the contents of the setup package into the network share.</span></span>
    1.  <span data-ttu-id="2635d-458">コマンドプロンプトウィンドウを開き、 **MMASetup-AMD64.exe/c**を実行します。</span><span class="sxs-lookup"><span data-stu-id="2635d-458">Open a Command Prompt window, and then execute **MMASetup-AMD64.exe /c**</span></span>
    2.  <span data-ttu-id="2635d-459">作成した共有を指定し、コンテンツを抽出します。</span><span class="sxs-lookup"><span data-stu-id="2635d-459">Specify the share you just created, and extract the content.</span></span>

4.  <span data-ttu-id="2635d-460">新しいグループポリシーオブジェクトを作成し、 :::no-loc text="Microsoft Teams Rooms"::: コンピューターアカウントがある組織単位に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2635d-460">Create a new Group Policy Object and assign it to the organizational unit where :::no-loc text="Microsoft Teams Rooms"::: machine accounts are located.</span></span>

5.  <span data-ttu-id="2635d-461">PowerShell 実行ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="2635d-461">Configure PowerShell execution policy:</span></span>
    1.  <span data-ttu-id="2635d-462">新しく作成されたグループポリシーオブジェクトを編集し、コンピューター構成 \\ ポリシー \\ 管理用テンプレートの \\ :::no-loc text="Windows"::: コンポーネント \\ に移動する :::no-loc text="Windows PowerShell":::</span><span class="sxs-lookup"><span data-stu-id="2635d-462">Edit the newly created Group Policy Object and navigate to Computer Configuration \\ Policies \\ Administrative Templates \\ :::no-loc text="Windows"::: Components \\ :::no-loc text="Windows PowerShell":::</span></span>
    2.  <span data-ttu-id="2635d-463">[**スクリプト実行を有効**にする] を有効にして、**ローカルスクリプトを許可**する**実行ポリシー**を設定します。</span><span class="sxs-lookup"><span data-stu-id="2635d-463">Enable the **Turn on Script Execution** and set **Execution Policy** to **Allow Local Scripts**.</span></span>

6.  <span data-ttu-id="2635d-464">スタートアップスクリプトを構成します。</span><span class="sxs-lookup"><span data-stu-id="2635d-464">Configure the startup script:</span></span>
    1.  <span data-ttu-id="2635d-465">次のスクリプトをコピーして Install-MMAgent.ps1 として保存します。</span><span class="sxs-lookup"><span data-stu-id="2635d-465">Copy the following script and save it as Install-MMAgent.ps1.</span></span>
    2.  <span data-ttu-id="2635d-466">構成に合わせて WorkspaceId、WorkspaceKey、SetupPath の各パラメーターを変更します。</span><span class="sxs-lookup"><span data-stu-id="2635d-466">Modify WorkspaceId, WorkspaceKey, and SetupPath parameters to match your configuration.</span></span>
    3.  <span data-ttu-id="2635d-467">同じグループポリシーオブジェクトを編集して、コンピューター構成 \\ ポリシーの \\ :::no-loc text="Windows"::: 設定 \\ スクリプト (スタートアップ/シャットダウン) に移動します。</span><span class="sxs-lookup"><span data-stu-id="2635d-467">Edit the same Group Policy Object and navigate to Computer Configuration \\ Policies \\ :::no-loc text="Windows"::: Settings \\ Scripts (Startup/Shutdown)</span></span>
    4.  <span data-ttu-id="2635d-468">[ **スタートアップ**] をダブルクリックして選択し、[ **PowerShell スクリプト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2635d-468">Double-click to select **Startup**, and then select **PowerShell Scripts**.</span></span>
    5.  <span data-ttu-id="2635d-469">[ **ファイルの表示**] を選択し、 **Install-MMAgent.ps1** ファイルをそのフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="2635d-469">Select **Show Files**, and then copy the **Install-MMAgent.ps1** file to that folder.</span></span>
    6.  <span data-ttu-id="2635d-470">[ **追加**]、[ **参照**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="2635d-470">Select **Add**, and then **Browse**.</span></span>
    7.  <span data-ttu-id="2635d-471">コピーした ps1 スクリプトを選択します。</span><span class="sxs-lookup"><span data-stu-id="2635d-471">Select the ps1 script you just copied.</span></span>

7.  <span data-ttu-id="2635d-472">:::no-loc text="Microsoft Teams Rooms"::: デバイスは、 :::no-loc text="Microsoft Monitoring"::: 2 回目の再起動でエージェントをインストールして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2635d-472">:::no-loc text="Microsoft Teams Rooms"::: devices should install and configure the :::no-loc text="Microsoft Monitoring"::: agent with the second reboot.</span></span>

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
> <span data-ttu-id="2635d-473">エージェントの再構成、別のワークスペースへの移動、または最初のインストール後のプロキシ設定の変更を行う必要がある場合は、「 [ :::no-loc text="Log Analytics"::: エージェントの管理と保守](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2635d-473">You can refer to the article [Managing and maintaining the :::no-loc text="Log Analytics"::: agent](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) when you need to reconfigure an agent, move it to a different workspace, or modify proxy settings after the initial installation.</span></span>

## <a name="additional-solutions"></a><span data-ttu-id="2635d-474">その他の解決策</span><span class="sxs-lookup"><span data-stu-id="2635d-474">Additional Solutions</span></span>
<span data-ttu-id="2635d-475"><a name="Solutions"> </a></span><span class="sxs-lookup"><span data-stu-id="2635d-475"><a name="Solutions"> </a></span></span>

<span data-ttu-id="2635d-476">:::no-loc text="Azure Monitor":::[ソリューションギャラリー](https://docs.microsoft.com/azure/azure-monitor/insights/solutions)を通じて、お客様の環境を監視するための組み込みの管理ソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="2635d-476">:::no-loc text="Azure Monitor"::: provides built-in management solutions through its [solution gallery](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) to further help you monitor your environment.</span></span> <span data-ttu-id="2635d-477">[通知管理](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution)と[ :::no-loc text="Azure Log Analytics"::: エージェントの正常性](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth)の解決策もワークスペースに追加することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2635d-477">We highly recommend that you add [Alert Management](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) and [:::no-loc text="Azure Log Analytics"::: Agent Health](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) solutions to your workspace as well.</span></span>

> [!NOTE]
> <span data-ttu-id="2635d-478">エージェント正常性ソリューションは、環境内の古いまたは破損したエージェントを特定するのに役立ち :::no-loc text="Microsoft Monitoring"::: ます。また、アラート管理ソリューションは、一定の期間内に発生した警告に関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="2635d-478">The Agent Health solution can help you identify outdated or broken :::no-loc text="Microsoft Monitoring"::: agents within your environment, and the Alert Management solution provides details about the alerts that have been raised within a given period.</span></span>

## <a name="see-also"></a><span data-ttu-id="2635d-479">関連項目</span><span class="sxs-lookup"><span data-stu-id="2635d-479">See also</span></span>

[<span data-ttu-id="2635d-480">計画 :::no-loc text="Microsoft Teams Rooms"::: 管理 :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="2635d-480">Plan :::no-loc text="Microsoft Teams Rooms"::: management with :::no-loc text="Azure Monitor":::</span></span>](azure-monitor-plan.md)

[<span data-ttu-id="2635d-481">:::no-loc text="Microsoft Teams Rooms":::デバイスの管理:::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="2635d-481">Manage :::no-loc text="Microsoft Teams Rooms"::: devices with :::no-loc text="Azure Monitor":::</span></span>](azure-monitor-manage.md)
