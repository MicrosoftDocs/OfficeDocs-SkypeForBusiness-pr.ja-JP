---
title: Azure モニターを使用して Microsoft Teams のルーム管理を展開する
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
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: この記事では、Azure モニターを使用して、統合されたエンドツーエンドの方法で Microsoft Teams 室デバイスの管理を展開する方法について説明します。
ms.openlocfilehash: 54268676eadab25599d4f8b6e415ff373717943f
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826265"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a><span data-ttu-id="cf8aa-103">管理:::no-loc text="Microsoft Teams Rooms":::を展開する:::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="cf8aa-103">Deploy :::no-loc text="Microsoft Teams Rooms"::: management with :::no-loc text="Azure Monitor":::</span></span>

<span data-ttu-id="cf8aa-104">この記事では、を使用:::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor":::して、統合されたエンドツーエンドのデバイス管理をセットアップして展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-104">This article discusses how to set up and deploy integrated, end-to-end management of :::no-loc text="Microsoft Teams Rooms"::: devices by using :::no-loc text="Azure Monitor":::.</span></span>

<span data-ttu-id="cf8aa-105">会議室の:::no-loc text="Log Analytics":::デバイス:::no-loc text="Azure Monitor":::を管理:::no-loc text="Microsoft Teams Rooms":::するのに役立つ基本的なテレメトリとアラートを提供するように、内で構成することができます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-105">You can configure :::no-loc text="Log Analytics"::: within :::no-loc text="Azure Monitor"::: to provide basic telemetry and alerts that will help you manage :::no-loc text="Microsoft Teams Rooms"::: meeting room devices.</span></span> <span data-ttu-id="cf8aa-106">管理ソリューションの成熟に応じて、デバイスの可用性とパフォーマンスの詳細なビューを作成するために、追加のデータと管理機能を展開することができます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-106">As your management solution matures, you might decide to deploy additional data and management capabilities to create a more detailed view of device availability and performance.</span></span>

<span data-ttu-id="cf8aa-107">このガイドに従うと、次の例のようなダッシュボードを使用して、デバイスの可用性、アプリケーションとハードウェアの正常性、 :::no-loc text="Microsoft Teams Rooms":::およびアプリケーションとオペレーティングシステムのバージョンの配布に関する詳細な状態レポートを取得できます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-107">By following this guide, you can use a dashboard like the following example to get detailed status reporting for device availability, application and hardware health, and :::no-loc text="Microsoft Teams Rooms"::: application and operating system version distribution.</span></span>

<span data-ttu-id="cf8aa-108">![の:::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms":::サンプルビューのスクリーンショット](../メディア/7 月30日「"サンプル:::no-loc text="Log Analytics":::ビュー"」を参照:::no-loc text="Microsoft Teams Rooms":::してください。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-108">![Screen shot of sample :::no-loc text="Log Analytics"::: view for :::no-loc text="Microsoft Teams Rooms":::](../media/Deploy-Azure-Monitor-1.png "Sample :::no-loc text="Log Analytics"::: view for :::no-loc text="Microsoft Teams Rooms":::")</span></span>

<span data-ttu-id="cf8aa-109">高いレベルでは、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-109">At a high level, you need to perform the following tasks:</span></span>


1. [<span data-ttu-id="cf8aa-110">構成:::no-loc text="Log Analytics":::の検証</span><span class="sxs-lookup"><span data-stu-id="cf8aa-110">Validate :::no-loc text="Log Analytics"::: configuration</span></span>](azure-monitor-deploy.md#validate_LogAnalytics)
2. [<span data-ttu-id="cf8aa-111">管理セットアップ用に:::no-loc text="Log Analytics":::テストデバイスを構成する</span><span class="sxs-lookup"><span data-stu-id="cf8aa-111">Configure test devices for :::no-loc text="Log Analytics"::: management setup</span></span>](azure-monitor-deploy.md#configure_test_devices)
3. [<span data-ttu-id="cf8aa-112">カスタム フィールドをマップする</span><span class="sxs-lookup"><span data-stu-id="cf8aa-112">Map custom fields</span></span>](azure-monitor-deploy.md#Custom_fields)
4. [<span data-ttu-id="cf8aa-113">ビューの:::no-loc text="Microsoft Teams Rooms":::定義:::no-loc text="Log Analytics":::</span><span class="sxs-lookup"><span data-stu-id="cf8aa-113">Define the :::no-loc text="Microsoft Teams Rooms"::: views in :::no-loc text="Log Analytics":::</span></span>](azure-monitor-deploy.md#Define_Views)
5. [<span data-ttu-id="cf8aa-114">通知を定義する</span><span class="sxs-lookup"><span data-stu-id="cf8aa-114">Define alerts</span></span>](azure-monitor-deploy.md#Alerts)
6. [<span data-ttu-id="cf8aa-115">すべてのデバイスを監視対象として構成する</span><span class="sxs-lookup"><span data-stu-id="cf8aa-115">Configure all devices for Monitoring</span></span>](azure-monitor-deploy.md#configure_all_devices)
7. [<span data-ttu-id="cf8aa-116">その他:::no-loc text="Azure Monitor":::のソリューションを構成する</span><span class="sxs-lookup"><span data-stu-id="cf8aa-116">Configure additional :::no-loc text="Azure Monitor"::: solutions</span></span>](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> <span data-ttu-id="cf8aa-117">最小限の構成では:::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: 、 :::no-loc text="Windows":::オペレーティングシステムを実行しているコンピューターを監視できます:::no-loc text="Microsoft Teams Rooms":::が、すべて:::no-loc text="Microsoft Teams Rooms":::のデバイスへのエージェントの展開を開始する前に、いくつかの具体的な手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-117">Although with minimal configuration, :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: can monitor a computer running a :::no-loc text="Windows"::: operating system, there are still some :::no-loc text="Microsoft Teams Rooms":::–specific steps that you need to take before you start deploying agents to all :::no-loc text="Microsoft Teams Rooms"::: devices.</span></span>
> <span data-ttu-id="cf8aa-118">そのため、管理された設定と構成については、すべての構成手順を適切な順序で実行することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-118">Therefore, we highly recommend you perform all configuration steps in the right order for a controlled setup and configuration.</span></span> <span data-ttu-id="cf8aa-119">最終的な結果の品質は、初期構成の品質によって大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-119">The quality of the end result very much depends on the quality of the initial configuration.</span></span>

## <a name="validate-no-loc-textlog-analytics-configuration"></a><span data-ttu-id="cf8aa-120">構成:::no-loc text="Log Analytics":::の検証</span><span class="sxs-lookup"><span data-stu-id="cf8aa-120">Validate :::no-loc text="Log Analytics"::: configuration</span></span>
<span data-ttu-id="cf8aa-121"><a name="validate_LogAnalytics"> </a></span><span class="sxs-lookup"><span data-stu-id="cf8aa-121"><a name="validate_LogAnalytics"> </a></span></span>

<span data-ttu-id="cf8aa-122">デバイスからの:::no-loc text="Microsoft Teams Rooms":::ログの:::no-loc text="Log Analytics":::収集を開始するには、ワークスペースが必要です。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-122">You need to have a :::no-loc text="Log Analytics"::: workspace to start collecting logs from :::no-loc text="Microsoft Teams Rooms"::: devices.</span></span> <span data-ttu-id="cf8aa-123">ワークスペースは、独自:::no-loc text="Log Analytics":::のデータリポジトリ、データソース、およびソリューションを備えた、固有の環境です。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-123">A workspace is a unique :::no-loc text="Log Analytics"::: environment with its own data repository, data sources, and solutions.</span></span> <span data-ttu-id="cf8aa-124">既存:::no-loc text="Log Analytics":::のワークスペースを既に持っている場合は、それを:::no-loc text="Microsoft Teams Rooms":::使って展開を監視するか、また:::no-loc text="Log Analytics":::は:::no-loc text="Microsoft Teams Rooms":::監視ニーズに合わせた専用のワークスペースを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-124">If you already have an existing :::no-loc text="Log Analytics"::: workspace, you might use it to monitor your :::no-loc text="Microsoft Teams Rooms"::: deployment or alternatively, you can create a dedicated :::no-loc text="Log Analytics"::: workspace specific to your :::no-loc text="Microsoft Teams Rooms"::: monitoring needs.</span></span>

<span data-ttu-id="cf8aa-125">新しい:::no-loc text="Log Analytics":::ワークスペースを作成する必要がある場合は、「 [ :::no-loc text="Log Analytics"::: :::no-loc text="Azure":::ポータルでワークスペースを作成](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)する」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-125">If you need to create a new :::no-loc text="Log Analytics"::: workspace, follow the instructions in the article [Create a :::no-loc text="Log Analytics"::: workspace in the :::no-loc text="Azure"::: portal](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)</span></span>

> [!NOTE]
> <span data-ttu-id="cf8aa-126">を使用:::no-loc text="Log Analytics":::する:::no-loc text="Azure Monitor":::には、有効:::no-loc text="Azure":::なサブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-126">To use :::no-loc text="Log Analytics"::: with :::no-loc text="Azure Monitor":::, you need to have an active :::no-loc text="Azure"::: subscription.</span></span> <span data-ttu-id="cf8aa-127">:::no-loc text="Azure":::サブスクリプションを持っていない場合は、出発点として[無料トライアルサブスクリプションを](https://azure.microsoft.com/free)作成できます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-127">If you don’t have an :::no-loc text="Azure"::: subscription, you can create [a free trial subscription](https://azure.microsoft.com/free) as a starting point.</span></span>

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a><span data-ttu-id="cf8aa-128">イベント:::no-loc text="Log Analytics":::ログを:::no-loc text="Microsoft Teams Rooms":::収集するように構成する</span><span class="sxs-lookup"><span data-stu-id="cf8aa-128">Configure :::no-loc text="Log Analytics"::: to collect :::no-loc text="Microsoft Teams Rooms"::: event logs</span></span>

<span data-ttu-id="cf8aa-129">:::no-loc text="Log Analytics":::設定で指定され:::no-loc text="Windows":::たイベントログのイベントのみを収集します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-129">:::no-loc text="Log Analytics"::: only collects events from the :::no-loc text="Windows"::: event logs that are specified in the settings.</span></span> <span data-ttu-id="cf8aa-130">各ログについて、選択した重大度のイベントのみが収集されます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-130">For each log, only the events with the selected severities are collected.</span></span>

<span data-ttu-id="cf8aa-131">デバイスとアプリケーションの:::no-loc text="Log Analytics":::状態を監視:::no-loc text="Microsoft Teams Rooms":::するために必要なログを収集するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-131">You need to configure :::no-loc text="Log Analytics"::: to collect the logs required to monitor :::no-loc text="Microsoft Teams Rooms"::: device and application status.</span></span> <span data-ttu-id="cf8aa-132">:::no-loc text="Microsoft Teams Rooms":::デバイスは**:::no-loc text="Skype Room System":::** イベントログを使います。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-132">:::no-loc text="Microsoft Teams Rooms"::: devices use the **:::no-loc text="Skype Room System":::** event log.</span></span>

<span data-ttu-id="cf8aa-133">イベントを:::no-loc text="Log Analytics":::収集するように構成するには、「 [ :::no-loc text="Windows":::イベント:::no-loc text="Azure Monitor":::ログのデータソース](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)」を参照してください。 :::no-loc text="Microsoft Teams Rooms":::</span><span class="sxs-lookup"><span data-stu-id="cf8aa-133">To configure :::no-loc text="Log Analytics"::: to collect the :::no-loc text="Microsoft Teams Rooms"::: events, see [:::no-loc text="Windows"::: event log data sources in :::no-loc text="Azure Monitor":::](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)</span></span>

<span data-ttu-id="cf8aa-134">![イベントログ設定のスクリーンショット](../media/Deploy-Azure-Monitor-2.png "イベントログの設定")</span><span class="sxs-lookup"><span data-stu-id="cf8aa-134">![Screen shot of event log settings](../media/Deploy-Azure-Monitor-2.png "Event log settings")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf8aa-135">イベント:::no-loc text="Windows":::ログの設定を構成**:::no-loc text="Skype Room System":::** し、イベントログの名前を入力して、[**エラー**]、[**警告**]、[**情報**] のチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-135">Configure :::no-loc text="Windows"::: Event Log settings and enter **:::no-loc text="Skype Room System":::** as event log name, and then select the **Error**, **Warning**, and **Information** check boxes.</span></span>

## <a name="configure-test-devices-for-azure-monitoring"></a><span data-ttu-id="cf8aa-136">Azure Monitoring のテストデバイスを構成する</span><span class="sxs-lookup"><span data-stu-id="cf8aa-136">Configure test devices for Azure Monitoring</span></span>
<span data-ttu-id="cf8aa-137"><a name="configure_test_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="cf8aa-137"><a name="configure_test_devices"> </a></span></span>

<span data-ttu-id="cf8aa-138">関連するイベントを:::no-loc text="Log Analytics":::監視:::no-loc text="Microsoft Teams Rooms":::できるように準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-138">You need to prepare :::no-loc text="Log Analytics"::: to be able to monitor :::no-loc text="Microsoft Teams Rooms":::–related events.</span></span> <span data-ttu-id="cf8aa-139">まず、物理的にアクセスできる1つ:::no-loc text="Microsoft Monitoring":::または2つ:::no-loc text="Microsoft Teams Rooms":::のデバイスにエージェントを展開し、それらのテストデバイスでデータを生成して:::no-loc text="Log Analytics":::ワークスペースにプッシュする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-139">To start with, you need to deploy :::no-loc text="Microsoft Monitoring"::: agents to just one or two :::no-loc text="Microsoft Teams Rooms"::: devices that you have physical access to, and get those test devices generate some data and push it to the :::no-loc text="Log Analytics"::: workspace.</span></span>

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a><span data-ttu-id="cf8aa-140">エージェント:::no-loc text="Microsoft Monitoring":::をインストールしてデバイスをテストする</span><span class="sxs-lookup"><span data-stu-id="cf8aa-140">Install :::no-loc text="Microsoft Monitoring"::: agents to test devices</span></span>

<span data-ttu-id="cf8aa-141">「[コンピューター :::no-loc text="Windows":::を:::no-loc text="Log Analytics":::サービス:::no-loc text="Azure":::に接続する](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)」で説明されている手順を使用して、 :::no-loc text="Microsoft Monitoring":::エージェントをテストデバイスに展開します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-141">Deploy the :::no-loc text="Microsoft Monitoring"::: agent to the test devices by using the instructions provided in [Connect :::no-loc text="Windows"::: computers to the :::no-loc text="Log Analytics"::: service in :::no-loc text="Azure":::](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows).</span></span> <span data-ttu-id="cf8aa-142">この:::no-loc text="Microsoft Monitoring":::記事では、エージェントの:::no-loc text="Windows":::展開手順、 :::no-loc text="Log Analytics"::: ***ワークスペース ID***の取得手順、 :::no-loc text="Azure Monitor":::展開に接続するデバイスを取得:::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms":::するための***主キー*** 、およびインスタンスへのエージェントの接続性を確認する手順について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-142">This article provides detailed information about the steps for deploying :::no-loc text="Microsoft Monitoring"::: Agent for :::no-loc text="Windows":::, instructions for obtaining the :::no-loc text="Log Analytics"::: ***Workspace ID*** and the ***primary key*** to get :::no-loc text="Microsoft Teams Rooms"::: devices connected to your :::no-loc text="Azure Monitor"::: deployment, and steps to verify agent connectivity to :::no-loc text="Log Analytics"::: instance.</span></span>

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a><span data-ttu-id="cf8aa-143">サンプル:::no-loc text="Microsoft Teams Rooms":::イベントを生成する</span><span class="sxs-lookup"><span data-stu-id="cf8aa-143">Generate sample :::no-loc text="Microsoft Teams Rooms"::: events</span></span>

<span data-ttu-id="cf8aa-144">:::no-loc text="Microsoft Monitoring":::エージェントをテストデバイスに展開した後、必要なイベントログデータがで:::no-loc text="Azure Monitor":::収集されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-144">After the :::no-loc text="Microsoft Monitoring"::: agent is deployed onto the test devices, verify that the required event log data is collected by :::no-loc text="Azure Monitor":::.</span></span>

> [!NOTE]
> <span data-ttu-id="cf8aa-145">:::no-loc text="Microsoft Monitoring":::エージェントをインストールした後でデバイスを再起動し、アプリ:::no-loc text="Microsoft Teams Rooms":::が新しいイベントを生成できるように会議アプリが開始されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-145">Reboot the device after the installation of the :::no-loc text="Microsoft Monitoring"::: agent, and make sure that :::no-loc text="Microsoft Teams Rooms"::: Meeting app is started, so that it can generate new events into the Event Log.</span></span>

1.  <span data-ttu-id="cf8aa-146">ポータルにサインインして、ワークスペース:::no-loc text="Log Analytics":::に移動して選択します。 [ :::no-loc text="Microsoft Azure"::: ](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="cf8aa-146">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2.  <span data-ttu-id="cf8aa-147">:::no-loc text="Microsoft Teams Rooms":::デバイスによって生成されるハートビートイベントを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-147">List the heartbeat events generated by a :::no-loc text="Microsoft Teams Rooms"::: device:</span></span>
    1.  <span data-ttu-id="cf8aa-148">ワークスペースを選択して、[**ログ**] に移動し、[クエリ] を使用して、ユーザー :::no-loc text="Microsoft Teams Rooms":::設定フィールドを含むハートビートレコードを取得します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-148">Select your workspace and go to **Logs** and use a query to retrieve the heartbeat records that will have the custom fields for :::no-loc text="Microsoft Teams Rooms":::.</span></span>
    2.  <span data-ttu-id="cf8aa-149">サンプルクエリ:`Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="cf8aa-149">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3.  <span data-ttu-id="cf8aa-150">:::no-loc text="Microsoft Teams Rooms":::会議アプリによって生成されたイベントを含むログレコードが、クエリによって返されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-150">Make sure that the query returns log records that include events generated by the :::no-loc text="Microsoft Teams Rooms"::: meetings app.</span></span>

4.  <span data-ttu-id="cf8aa-151">ハードウェアの問題を生成し、必要なイベントがログに:::no-loc text="Azure Log Analytics":::記録されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-151">Generate a hardware issue, and validate that the required events are logged in :::no-loc text="Azure Log Analytics":::.</span></span>
    1.  <span data-ttu-id="cf8aa-152">テスト:::no-loc text="Microsoft Teams Rooms":::システムでいずれかの周辺機器を取り外します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-152">Unplug one of the peripheral devices on the test :::no-loc text="Microsoft Teams Rooms"::: system.</span></span> <span data-ttu-id="cf8aa-153">カメラ、スピーカーフォン、マイク、またはフロントルームディスプレイの場合があります</span><span class="sxs-lookup"><span data-stu-id="cf8aa-153">This could be the camera, speakerphone, microphone, or Front Room Display</span></span>
    2.  <span data-ttu-id="cf8aa-154">イベントログが設定されるまで10分待ち:::no-loc text="Azure Log Analytics":::ます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-154">Wait 10 minutes for the event log to be populated in :::no-loc text="Azure Log Analytics":::.</span></span>
    3.  <span data-ttu-id="cf8aa-155">クエリを使用して、ハードウェアエラーイベントを一覧表示します。`Event | where Source == "SRS-App" and EventID == 3001`</span><span class="sxs-lookup"><span data-stu-id="cf8aa-155">Use a query to list hardware error events: `Event | where Source == "SRS-App" and EventID == 3001`</span></span>

5.  <span data-ttu-id="cf8aa-156">アプリケーションの問題を生成し、必要なイベントがログに記録されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-156">Generate an application issue, and validate that the required events are logged.</span></span>
    1.  <span data-ttu-id="cf8aa-157">アプリケーション:::no-loc text="Microsoft Teams Rooms":::の構成を変更し、誤ったセッション開始プロトコル (SIP) アドレスとパスワードのペアを入力します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-157">Modify :::no-loc text="Microsoft Teams Rooms"::: application configuration, and type an incorrect Session Initiation Protocol (SIP) address/password pair.</span></span>
    2.  <span data-ttu-id="cf8aa-158">イベントログが設定されるまで10分待ち:::no-loc text="Azure Log Analytics":::ます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-158">Wait 10 minutes for the event log to be populated in :::no-loc text="Azure Log Analytics":::.</span></span>
    3.  <span data-ttu-id="cf8aa-159">クエリを使用して、アプリケーションエラーイベントを一覧表示します。`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span><span class="sxs-lookup"><span data-stu-id="cf8aa-159">Use a query to list application error events: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf8aa-160">カスタムフィールドを構成するには、これらのサンプルイベントログが必要です。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-160">These sample event logs are required before custom fields can be configured.</span></span> <span data-ttu-id="cf8aa-161">必要なイベントログを収集するまでは、次の手順に進んではいけません。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-161">Don’t proceed to the next step until you have collected the required event logs.</span></span>

## <a name="map-custom-fields"></a><span data-ttu-id="cf8aa-162">カスタム フィールドをマップする</span><span class="sxs-lookup"><span data-stu-id="cf8aa-162">Map custom fields</span></span>
<span data-ttu-id="cf8aa-163"><a name="Custom_fields"> </a></span><span class="sxs-lookup"><span data-stu-id="cf8aa-163"><a name="Custom_fields"> </a></span></span>

<span data-ttu-id="cf8aa-164">カスタムフィールドを使って、イベントログから特定のデータを抽出します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-164">You use custom fields to extract specific data from the event logs.</span></span> <span data-ttu-id="cf8aa-165">タイル、ダッシュボードビュー、およびアラートで後で使用されるカスタムフィールドを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-165">You need to define custom fields that will be used later with your tiles, dashboard views, and alerts.</span></span> <span data-ttu-id="cf8aa-166">カスタムフィールドの作成を開始する前に、「[ユーザー設定フィールド:::no-loc text="Log Analytics"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) 」を参照して、概念を理解しておいてください。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-166">See [Custom fields in :::no-loc text="Log Analytics":::](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) and become familiar with the concepts before you start creating your custom fields.</span></span>

<span data-ttu-id="cf8aa-167">キャプチャしたイベントログからカスタムフィールドを抽出するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-167">To extract your custom fields out of the captured event logs, follow these steps:</span></span>

1.  <span data-ttu-id="cf8aa-168">ポータルにサインインして、ワークスペース:::no-loc text="Log Analytics":::に移動して選択します。 [ :::no-loc text="Microsoft Azure"::: ](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="cf8aa-168">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2. <span data-ttu-id="cf8aa-169">:::no-loc text="Microsoft Teams Rooms":::デバイスによって生成されるイベントを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-169">List the events generated by a :::no-loc text="Microsoft Teams Rooms"::: device:</span></span>
   1.  <span data-ttu-id="cf8aa-170">[**ログ**] に移動し、クエリを使用してユーザー設定フィールドを含むレコードを取得します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-170">Go to **Logs** and use a query to retrieve the records that will have the custom field.</span></span>
   2.  <span data-ttu-id="cf8aa-171">サンプルクエリ:`Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="cf8aa-171">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3. <span data-ttu-id="cf8aa-172">いずれかのレコードを選び、左側のボタンを選んで、フィールド抽出ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-172">Select one of the records, select the button to the left, and start the field extraction wizard.</span></span>
4. <span data-ttu-id="cf8aa-173">RenderedDescription から抽出するデータを強調表示し、フィールドタイトルを入力します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-173">Highlight the data you’d like to extract from the RenderedDescription and provide a Field Title.</span></span> <span data-ttu-id="cf8aa-174">使用する必要があるフィールド名は、表1に記載されています。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-174">The field names that you should use are provided in Table 1.</span></span>

   <span data-ttu-id="cf8aa-175">![ユーザー設定フィールドの定義](../media/Deploy-Azure-Monitor-4.png "ユーザー設定フィールドの定義")</span><span class="sxs-lookup"><span data-stu-id="cf8aa-175">![Custom field definition](../media/Deploy-Azure-Monitor-4.png "Custom field definition")</span></span>

5. <span data-ttu-id="cf8aa-176">*表 1*に示されているマッピングを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-176">Use the mappings shown in *Table 1*.</span></span> <span data-ttu-id="cf8aa-177">:::no-loc text="Log Analytics":::新しいフィールドを定義\*\* \_\*\* するときに、自動的に CF 文字列が追加されます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-177">:::no-loc text="Log Analytics"::: will automatically append the **\_CF** string when you define the new field.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf8aa-178">JSON とフィールドはすべて:::no-loc text="Log Analytics":::大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-178">Remember that all JSON and :::no-loc text="Log Analytics"::: fields are case-sensitive.</span></span>
> 
> <span data-ttu-id="cf8aa-179">以下の表のユーザー設定フィールドごとに、必要なクエリに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-179">Pay attention to the queries required for each custom field in the table below.</span></span> <span data-ttu-id="cf8aa-180">ユーザー設定フィールドの:::no-loc text="Log Analytics":::値を正しく抽出するには、適切なクエリを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-180">You need to use the correct queries for :::no-loc text="Log Analytics"::: to successfully extract custom field values.</span></span>
> 
 <span data-ttu-id="cf8aa-181">![ユーザー設定フィールドの定義](../media/Deploy-Azure-Monitor-5.png "ユーザー設定フィールドの定義")</span><span class="sxs-lookup"><span data-stu-id="cf8aa-181">![Custom field definition](../media/Deploy-Azure-Monitor-5.png "Custom field definition")</span></span>

<span data-ttu-id="cf8aa-182">**表1**</span><span class="sxs-lookup"><span data-stu-id="cf8aa-182">**Table 1**</span></span>

| <span data-ttu-id="cf8aa-183">**JSON フィールド**</span><span class="sxs-lookup"><span data-stu-id="cf8aa-183">**JSON field**</span></span>                   | <span data-ttu-id="cf8aa-184">**:::no-loc text="Log Analytics":::ユーザー設定フィールド**</span><span class="sxs-lookup"><span data-stu-id="cf8aa-184">**:::no-loc text="Log Analytics"::: custom field**</span></span> | <span data-ttu-id="cf8aa-185">**イベント ID**</span><span class="sxs-lookup"><span data-stu-id="cf8aa-185">**Event ID**</span></span> | <span data-ttu-id="cf8aa-186">**抽出に使用するクエリ**</span><span class="sxs-lookup"><span data-stu-id="cf8aa-186">**Query to use with the extraction**</span></span>                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| <span data-ttu-id="cf8aa-187">説明</span><span class="sxs-lookup"><span data-stu-id="cf8aa-187">Description</span></span>                      | <span data-ttu-id="cf8aa-188">SRSEventDescription</span><span class="sxs-lookup"><span data-stu-id="cf8aa-188">SRSEventDescription</span></span>         | <span data-ttu-id="cf8aa-189">**2000**</span><span class="sxs-lookup"><span data-stu-id="cf8aa-189">**2000**</span></span>     | <span data-ttu-id="cf8aa-190">\| Source = = "SRS-アプリ" and EventID = = 2000</span><span class="sxs-lookup"><span data-stu-id="cf8aa-190">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="cf8aa-191">ResourceState</span><span class="sxs-lookup"><span data-stu-id="cf8aa-191">ResourceState</span></span>                    | <span data-ttu-id="cf8aa-192">SRSResourceState</span><span class="sxs-lookup"><span data-stu-id="cf8aa-192">SRSResourceState</span></span>            | <span data-ttu-id="cf8aa-193">**2000**</span><span class="sxs-lookup"><span data-stu-id="cf8aa-193">**2000**</span></span>     | <span data-ttu-id="cf8aa-194">\| Source = = "SRS-アプリ" and EventID = = 2000</span><span class="sxs-lookup"><span data-stu-id="cf8aa-194">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="cf8aa-195">OperationName</span><span class="sxs-lookup"><span data-stu-id="cf8aa-195">OperationName</span></span>                    | <span data-ttu-id="cf8aa-196">SRSOperationName</span><span class="sxs-lookup"><span data-stu-id="cf8aa-196">SRSOperationName</span></span>            | <span data-ttu-id="cf8aa-197">**2000**</span><span class="sxs-lookup"><span data-stu-id="cf8aa-197">**2000**</span></span>     | <span data-ttu-id="cf8aa-198">\| Source = = "SRS-アプリ" and EventID = = 2000</span><span class="sxs-lookup"><span data-stu-id="cf8aa-198">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="cf8aa-199">OperationResult</span><span class="sxs-lookup"><span data-stu-id="cf8aa-199">OperationResult</span></span>                  | <span data-ttu-id="cf8aa-200">SRSOperationResult</span><span class="sxs-lookup"><span data-stu-id="cf8aa-200">SRSOperationResult</span></span>          | <span data-ttu-id="cf8aa-201">**2000**</span><span class="sxs-lookup"><span data-stu-id="cf8aa-201">**2000**</span></span>     | <span data-ttu-id="cf8aa-202">\| Source = = "SRS-アプリ" and EventID = = 2000</span><span class="sxs-lookup"><span data-stu-id="cf8aa-202">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="cf8aa-203">OS</span><span class="sxs-lookup"><span data-stu-id="cf8aa-203">OS</span></span>                               | <span data-ttu-id="cf8aa-204">SRSOSVersion</span><span class="sxs-lookup"><span data-stu-id="cf8aa-204">SRSOSVersion</span></span>                | <span data-ttu-id="cf8aa-205">**2000**</span><span class="sxs-lookup"><span data-stu-id="cf8aa-205">**2000**</span></span>     | <span data-ttu-id="cf8aa-206">\| Source = = "SRS-アプリ" and EventID = = 2000</span><span class="sxs-lookup"><span data-stu-id="cf8aa-206">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="cf8aa-207">OSVersion</span><span class="sxs-lookup"><span data-stu-id="cf8aa-207">OSVersion</span></span>                        | <span data-ttu-id="cf8aa-208">SRSOSLongVersion</span><span class="sxs-lookup"><span data-stu-id="cf8aa-208">SRSOSLongVersion</span></span>            | <span data-ttu-id="cf8aa-209">**2000**</span><span class="sxs-lookup"><span data-stu-id="cf8aa-209">**2000**</span></span>     | <span data-ttu-id="cf8aa-210">\| Source = = "SRS-アプリ" and EventID = = 2000</span><span class="sxs-lookup"><span data-stu-id="cf8aa-210">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="cf8aa-211">Alias</span><span class="sxs-lookup"><span data-stu-id="cf8aa-211">Alias</span></span>                            | <span data-ttu-id="cf8aa-212">SRSAlias</span><span class="sxs-lookup"><span data-stu-id="cf8aa-212">SRSAlias</span></span>                    | <span data-ttu-id="cf8aa-213">**2000**</span><span class="sxs-lookup"><span data-stu-id="cf8aa-213">**2000**</span></span>     | <span data-ttu-id="cf8aa-214">\| Source = = "SRS-アプリ" and EventID = = 2000</span><span class="sxs-lookup"><span data-stu-id="cf8aa-214">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="cf8aa-215">DisplayName</span><span class="sxs-lookup"><span data-stu-id="cf8aa-215">DisplayName</span></span>                      | <span data-ttu-id="cf8aa-216">SRSDisplayName</span><span class="sxs-lookup"><span data-stu-id="cf8aa-216">SRSDisplayName</span></span>              | <span data-ttu-id="cf8aa-217">**2000**</span><span class="sxs-lookup"><span data-stu-id="cf8aa-217">**2000**</span></span>     | <span data-ttu-id="cf8aa-218">\| Source = = "SRS-アプリ" and EventID = = 2000</span><span class="sxs-lookup"><span data-stu-id="cf8aa-218">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="cf8aa-219">AppVersion</span><span class="sxs-lookup"><span data-stu-id="cf8aa-219">AppVersion</span></span>                       | <span data-ttu-id="cf8aa-220">SRSAppVersion</span><span class="sxs-lookup"><span data-stu-id="cf8aa-220">SRSAppVersion</span></span>               | <span data-ttu-id="cf8aa-221">**2000**</span><span class="sxs-lookup"><span data-stu-id="cf8aa-221">**2000**</span></span>     | <span data-ttu-id="cf8aa-222">\| Source = = "SRS-アプリ" and EventID = = 2000</span><span class="sxs-lookup"><span data-stu-id="cf8aa-222">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="cf8aa-223">IPv4Address</span><span class="sxs-lookup"><span data-stu-id="cf8aa-223">IPv4Address</span></span>                      | <span data-ttu-id="cf8aa-224">SRSIPv4Address</span><span class="sxs-lookup"><span data-stu-id="cf8aa-224">SRSIPv4Address</span></span>              | <span data-ttu-id="cf8aa-225">**2000**</span><span class="sxs-lookup"><span data-stu-id="cf8aa-225">**2000**</span></span>     | <span data-ttu-id="cf8aa-226">\| Source = = "SRS-アプリ" and EventID = = 2000</span><span class="sxs-lookup"><span data-stu-id="cf8aa-226">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="cf8aa-227">IPv6Address</span><span class="sxs-lookup"><span data-stu-id="cf8aa-227">IPv6Address</span></span>                      | <span data-ttu-id="cf8aa-228">SRSIPv6Address</span><span class="sxs-lookup"><span data-stu-id="cf8aa-228">SRSIPv6Address</span></span>              | <span data-ttu-id="cf8aa-229">**2000**</span><span class="sxs-lookup"><span data-stu-id="cf8aa-229">**2000**</span></span>     | <span data-ttu-id="cf8aa-230">\| Source = = "SRS-アプリ" and EventID = = 2000</span><span class="sxs-lookup"><span data-stu-id="cf8aa-230">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="cf8aa-231">会議のマイクの状態</span><span class="sxs-lookup"><span data-stu-id="cf8aa-231">Conference Microphone status</span></span>     | <span data-ttu-id="cf8aa-232">Srsconfマイクロ電話の状態</span><span class="sxs-lookup"><span data-stu-id="cf8aa-232">SRSConfMicrophoneStatus</span></span>     | <span data-ttu-id="cf8aa-233">**3001**</span><span class="sxs-lookup"><span data-stu-id="cf8aa-233">**3001**</span></span>     | <span data-ttu-id="cf8aa-234">\| Source = = "SRS-アプリ" and EventID = = 3001</span><span class="sxs-lookup"><span data-stu-id="cf8aa-234">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="cf8aa-235">会議のスピーカーの状態</span><span class="sxs-lookup"><span data-stu-id="cf8aa-235">Conference Speaker status</span></span>        | <span data-ttu-id="cf8aa-236">SRSConfSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="cf8aa-236">SRSConfSpeakerStatus</span></span>        | <span data-ttu-id="cf8aa-237">**3001**</span><span class="sxs-lookup"><span data-stu-id="cf8aa-237">**3001**</span></span>     | <span data-ttu-id="cf8aa-238">\| Source = = "SRS-アプリ" and EventID = = 3001</span><span class="sxs-lookup"><span data-stu-id="cf8aa-238">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="cf8aa-239">既定のスピーカーの状態</span><span class="sxs-lookup"><span data-stu-id="cf8aa-239">Default Speaker status</span></span>           | <span data-ttu-id="cf8aa-240">SRSDefaultSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="cf8aa-240">SRSDefaultSpeakerStatus</span></span>     | <span data-ttu-id="cf8aa-241">**3001**</span><span class="sxs-lookup"><span data-stu-id="cf8aa-241">**3001**</span></span>     | <span data-ttu-id="cf8aa-242">\| Source = = "SRS-アプリ" and EventID = = 3001</span><span class="sxs-lookup"><span data-stu-id="cf8aa-242">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="cf8aa-243">カメラの状態</span><span class="sxs-lookup"><span data-stu-id="cf8aa-243">Camera status</span></span>                    | <span data-ttu-id="cf8aa-244">SRSCameraStatus</span><span class="sxs-lookup"><span data-stu-id="cf8aa-244">SRSCameraStatus</span></span>             | <span data-ttu-id="cf8aa-245">**3001**</span><span class="sxs-lookup"><span data-stu-id="cf8aa-245">**3001**</span></span>     | <span data-ttu-id="cf8aa-246">\| Source = = "SRS-アプリ" and EventID = = 3001</span><span class="sxs-lookup"><span data-stu-id="cf8aa-246">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="cf8aa-247">部屋の表面の表示状態</span><span class="sxs-lookup"><span data-stu-id="cf8aa-247">Front of Room Display status</span></span>     | <span data-ttu-id="cf8aa-248">SRSFORDStatus</span><span class="sxs-lookup"><span data-stu-id="cf8aa-248">SRSFORDStatus</span></span>               | <span data-ttu-id="cf8aa-249">**3001**</span><span class="sxs-lookup"><span data-stu-id="cf8aa-249">**3001**</span></span>     | <span data-ttu-id="cf8aa-250">\| Source = = "SRS-アプリ" and EventID = = 3001</span><span class="sxs-lookup"><span data-stu-id="cf8aa-250">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="cf8aa-251">モーションセンサーの状態</span><span class="sxs-lookup"><span data-stu-id="cf8aa-251">Motion Sensor status</span></span>             | <span data-ttu-id="cf8aa-252">SRSMotionSensorStatus</span><span class="sxs-lookup"><span data-stu-id="cf8aa-252">SRSMotionSensorStatus</span></span>       | <span data-ttu-id="cf8aa-253">**3001**</span><span class="sxs-lookup"><span data-stu-id="cf8aa-253">**3001**</span></span>     | <span data-ttu-id="cf8aa-254">\| Source = = "SRS-アプリ" and EventID = = 3001</span><span class="sxs-lookup"><span data-stu-id="cf8aa-254">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="cf8aa-255">HDMI 取り込みの状態</span><span class="sxs-lookup"><span data-stu-id="cf8aa-255">HDMI Ingest status</span></span>               | <span data-ttu-id="cf8aa-256">SRSHDMIIngestStatus</span><span class="sxs-lookup"><span data-stu-id="cf8aa-256">SRSHDMIIngestStatus</span></span>         | <span data-ttu-id="cf8aa-257">**3001**</span><span class="sxs-lookup"><span data-stu-id="cf8aa-257">**3001**</span></span>     | <span data-ttu-id="cf8aa-258">\| Source = = "SRS-アプリ" and EventID = = 3001</span><span class="sxs-lookup"><span data-stu-id="cf8aa-258">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a><span data-ttu-id="cf8aa-259">ビューの:::no-loc text="Microsoft Teams Rooms":::定義:::no-loc text="Log Analytics":::</span><span class="sxs-lookup"><span data-stu-id="cf8aa-259">Define the :::no-loc text="Microsoft Teams Rooms"::: views in :::no-loc text="Log Analytics":::</span></span>
<span data-ttu-id="cf8aa-260"><a name="Define_Views"> </a></span><span class="sxs-lookup"><span data-stu-id="cf8aa-260"><a name="Define_Views"> </a></span></span>

<span data-ttu-id="cf8aa-261">データが収集され、ユーザー設定フィールドがマップされた後、ビューデザイナーを使用して、さまざま:::no-loc text="Microsoft Teams Rooms":::なタイルを含むダッシュボードを作成し、イベントを監視することができます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-261">After data is collected and custom fields are mapped, you can use View Designer to develop a dashboard containing various tiles to monitor :::no-loc text="Microsoft Teams Rooms"::: events.</span></span> <span data-ttu-id="cf8aa-262">次のタイルを作成するには、[ビューデザイナーを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-262">Use View Designer to create the following tiles.</span></span> <span data-ttu-id="cf8aa-263">詳細については、「[デザイナー :::no-loc text="Log Analytics":::でビューデザイナーを使用してカスタムビューを作成](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-263">For more information, see [Create custom views by using View Designer in :::no-loc text="Log Analytics":::](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)</span></span>

> [!NOTE]
> <span data-ttu-id="cf8aa-264">ダッシュボードタイルが正常に動作するためには、このガイドの前の手順が完了している必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-264">Previous steps in this guide should have been completed for the dashboard tiles to work properly.</span></span>

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a><span data-ttu-id="cf8aa-265">インポート方法を使用して Microsoft Teams のルームダッシュボードを作成する</span><span class="sxs-lookup"><span data-stu-id="cf8aa-265">Create a Microsoft Teams Rooms dashboard by using the import method</span></span>

<span data-ttu-id="cf8aa-266">:::no-loc text="Microsoft Teams Rooms":::ダッシュボードをインポートして、デバイスの監視をすばやく開始することができます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-266">You can import an :::no-loc text="Microsoft Teams Rooms"::: dashboard and start monitoring your devices quickly.</span></span> <span data-ttu-id="cf8aa-267">ダッシュボードをインポートするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-267">Take the following steps to import the dashboard:</span></span>

1.  <span data-ttu-id="cf8aa-268">Omsview ダッシュボードファイル[SkypeRoomSystems_v2](https://go.microsoft.com/fwlink/?linkid=835675)を取得します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-268">Get the [SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675) dashboard file.</span></span>
2.  <span data-ttu-id="cf8aa-269">ポータルにサインインして、ワークスペース:::no-loc text="Log Analytics":::に移動して選択します。 [ :::no-loc text="Microsoft Azure"::: ](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="cf8aa-269">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>
3.  <span data-ttu-id="cf8aa-270">**ビューデザイナー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-270">Open **View Designer**.</span></span>
4.  <span data-ttu-id="cf8aa-271">[**インポート**] を選択し、 **omsview ファイル SkypeRoomSystems_v2**を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-271">Select **Import**, and then select the **SkypeRoomSystems_v2.omsview** file.</span></span>
5.  <span data-ttu-id="cf8aa-272">[**保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-272">Select **Save**.</span></span>

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a><span data-ttu-id="cf8aa-273">Microsoft Teams のルームダッシュボードを手動で作成する</span><span class="sxs-lookup"><span data-stu-id="cf8aa-273">Create a Microsoft Teams Rooms dashboard manually</span></span>

<span data-ttu-id="cf8aa-274">または、独自のダッシュボードを作成して、監視するタイルのみを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-274">Alternatively, you can create your own dashboard and add only the tiles that you wish to monitor.</span></span>

#### <a name="configure-the-overview-tile"></a><span data-ttu-id="cf8aa-275">概要タイルを構成する</span><span class="sxs-lookup"><span data-stu-id="cf8aa-275">Configure the Overview Tile</span></span>

1.  <span data-ttu-id="cf8aa-276">**ビューデザイナー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-276">Open **View Designer**.</span></span>
2.  <span data-ttu-id="cf8aa-277">[**概要] タイル**を選択し、ギャラリーから**2 つの数値**を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-277">Select **Overview Tile**, and then select **Two numbers** from the gallery.</span></span>
3.  <span data-ttu-id="cf8aa-278">タイル**:::no-loc text="Microsoft Teams Rooms":::** に名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-278">Name the tile **:::no-loc text="Microsoft Teams Rooms":::**.</span></span>
4.  <span data-ttu-id="cf8aa-279">最初の**タイル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-279">Define the **First Tile**:</span></span><br>
    <span data-ttu-id="cf8aa-280">**凡例:** 1ヶ月以内に少なくとも1回、ハートビートを送信したデバイス</span><span class="sxs-lookup"><span data-stu-id="cf8aa-280">**Legend:** Devices that sent a heartbeat at least once within the last month</span></span><br>
    <span data-ttu-id="cf8aa-281">**クエリ:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="cf8aa-281">**Query:** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
5.  <span data-ttu-id="cf8aa-282">**2 番目のタイル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-282">Define the **Second Tile**:</span></span><br>
    <span data-ttu-id="cf8aa-283">**凡例:** 1時間以内にハートビートを送信したアクティブなデバイス</span><span class="sxs-lookup"><span data-stu-id="cf8aa-283">**Legend:** Active devices that sent a heartbeat within the last hour</span></span><br>
    <span data-ttu-id="cf8aa-284">**クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="cf8aa-284">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
6.  <span data-ttu-id="cf8aa-285">[**適用**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-285">Select **Apply**.</span></span>

### <a name="create-a-tile-that-displays-active-devices"></a><span data-ttu-id="cf8aa-286">アクティブなデバイスを表示するタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="cf8aa-286">Create a tile that displays active devices</span></span>

1.  <span data-ttu-id="cf8aa-287">[**ダッシュボードの表示**] を選択して、タイルの追加を開始します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-287">Select **View Dashboard** to start adding your tiles.</span></span>
2.  <span data-ttu-id="cf8aa-288">ギャラリーから**番号 & リスト**を選択する</span><span class="sxs-lookup"><span data-stu-id="cf8aa-288">Select **Number & list** from the gallery</span></span>
3.  <span data-ttu-id="cf8aa-289">**一般的な**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-289">Define the **General** properties:</span></span><br>
    <span data-ttu-id="cf8aa-290">**グループタイトル:** ハートビートの状態</span><span class="sxs-lookup"><span data-stu-id="cf8aa-290">**Group Title:** Heartbeat Status</span></span><br>
    <span data-ttu-id="cf8aa-291">**新しいグループ:** 選択した</span><span class="sxs-lookup"><span data-stu-id="cf8aa-291">**New Group:** Selected</span></span>
4.  <span data-ttu-id="cf8aa-292">**タイル**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-292">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="cf8aa-293">**凡例:** アクティブなデバイス (過去20分間に送信されたハートビート)</span><span class="sxs-lookup"><span data-stu-id="cf8aa-293">**Legend:** Active devices (heartbeat sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="cf8aa-294">\*\*タイルのクエリ: \*\* ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="cf8aa-294">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span></span>
5.  <span data-ttu-id="cf8aa-295">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-295">Define the **List** properties:</span></span><br>
    <span data-ttu-id="cf8aa-296">**リストクエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="cf8aa-296">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
6.  <span data-ttu-id="cf8aa-297">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-297">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="cf8aa-298">**Name:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="cf8aa-298">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="cf8aa-299">**値:** 最終ハートビート</span><span class="sxs-lookup"><span data-stu-id="cf8aa-299">**Value:** Last Heartbeat</span></span>
7.  <span data-ttu-id="cf8aa-300">**ナビゲーションクエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-300">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="cf8aa-301">[**適用**]、[**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-301">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a><span data-ttu-id="cf8aa-302">接続の問題が発生しているデバイスを表示するタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="cf8aa-302">Create a tile that displays devices that have connectivity issues</span></span>

1.  <span data-ttu-id="cf8aa-303">ギャラリーから [**番号 & リスト**] を選び、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-303">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="cf8aa-304">**一般的な**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-304">Define the **General** properties:</span></span><br>
    <span data-ttu-id="cf8aa-305">**グループタイトル:** 空のままにする</span><span class="sxs-lookup"><span data-stu-id="cf8aa-305">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="cf8aa-306">**新しいグループ:** 未選択</span><span class="sxs-lookup"><span data-stu-id="cf8aa-306">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="cf8aa-307">**タイル**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-307">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="cf8aa-308">**凡例:** 非アクティブなデバイス (過去20分間送信されたハートビートメッセージなし)</span><span class="sxs-lookup"><span data-stu-id="cf8aa-308">**Legend:** Inactive Devices (no heartbeat message sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="cf8aa-309">\*\*タイルのクエリ: \*\* ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span><span class="sxs-lookup"><span data-stu-id="cf8aa-309">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span></span>
4.  <span data-ttu-id="cf8aa-310">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-310">Define the **List** properties:</span></span><br>
    <span data-ttu-id="cf8aa-311">**リストクエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="cf8aa-311">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="cf8aa-312">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-312">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="cf8aa-313">**Name:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="cf8aa-313">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="cf8aa-314">**値:** 最終ハートビート</span><span class="sxs-lookup"><span data-stu-id="cf8aa-314">**Value:** Last Heartbeat</span></span>
6.  <span data-ttu-id="cf8aa-315">**ナビゲーションクエリ**を定義する:</span><span class="sxs-lookup"><span data-stu-id="cf8aa-315">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="cf8aa-316">[**適用**]、[**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-316">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a><span data-ttu-id="cf8aa-317">ハードウェアエラーが発生したデバイスを表示するタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="cf8aa-317">Create a tile that displays devices that have a hardware error</span></span>

1.  <span data-ttu-id="cf8aa-318">ギャラリーから [**番号 & リスト**] を選び、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-318">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="cf8aa-319">**一般的な**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-319">Define the **General** properties:</span></span><br>
    <span data-ttu-id="cf8aa-320">**グループタイトル:** ハードウェアの状態</span><span class="sxs-lookup"><span data-stu-id="cf8aa-320">**Group Title:** Hardware Status</span></span><br>
    <span data-ttu-id="cf8aa-321">**新しいグループ:** 選択した</span><span class="sxs-lookup"><span data-stu-id="cf8aa-321">**New Group:** Selected</span></span>
3.  <span data-ttu-id="cf8aa-322">**タイル**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-322">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="cf8aa-323">**凡例:** 過去1時間にハードウェアエラーが発生したデバイス</span><span class="sxs-lookup"><span data-stu-id="cf8aa-323">**Legend:** Devices that experienced a hardware error in the last hour</span></span><br>
    <span data-ttu-id="cf8aa-324">\*\*タイルのクエリ: \*\* ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="cf8aa-324">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="cf8aa-325">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-325">Define the **List** properties:</span></span><br>
    <span data-ttu-id="cf8aa-326">**リストクエリ:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="cf8aa-326">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="cf8aa-327">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-327">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="cf8aa-328">**Name:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="cf8aa-328">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="cf8aa-329">**値:** 最後のエラー</span><span class="sxs-lookup"><span data-stu-id="cf8aa-329">**Value:** Last Error</span></span>
6.  <span data-ttu-id="cf8aa-330">**ナビゲーションクエリ**を定義する:</span><span class="sxs-lookup"><span data-stu-id="cf8aa-330">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="cf8aa-331">[**適用**]、[**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-331">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a><span data-ttu-id="cf8aa-332">オペレーティングシステムのバージョンを:::no-loc text="Microsoft Teams Rooms":::表示するタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="cf8aa-332">Create a tile that displays :::no-loc text="Microsoft Teams Rooms"::: Operating System versions</span></span>

1.  <span data-ttu-id="cf8aa-333">ギャラリーから [**ドーナツ & リスト**] を選び、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-333">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="cf8aa-334">**一般的な**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-334">Define the **General** properties:</span></span><br>
    <span data-ttu-id="cf8aa-335">**グループタイトル:** オペレーティングシステムの詳細</span><span class="sxs-lookup"><span data-stu-id="cf8aa-335">**Group Title:** Operating System details</span></span><br>
    <span data-ttu-id="cf8aa-336">**新しいグループ:** 選択した</span><span class="sxs-lookup"><span data-stu-id="cf8aa-336">**New Group:** Selected</span></span>
3.  <span data-ttu-id="cf8aa-337">**ヘッダー**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-337">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="cf8aa-338">**タイトル:** オペレーティングシステムのバージョン</span><span class="sxs-lookup"><span data-stu-id="cf8aa-338">**Title:** Operating System versions</span></span><br>
    <span data-ttu-id="cf8aa-339">**サブタイトル:** 特定の OS バージョンを実行しているデバイス</span><span class="sxs-lookup"><span data-stu-id="cf8aa-339">**Subtitle:** Devices running specific OS versions</span></span>
4.  <span data-ttu-id="cf8aa-340">**ドーナツ**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-340">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="cf8aa-341">**クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span><span class="sxs-lookup"><span data-stu-id="cf8aa-341">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span></span><br>
    <span data-ttu-id="cf8aa-342">**テキストの中央揃え:** デバイス</span><span class="sxs-lookup"><span data-stu-id="cf8aa-342">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="cf8aa-343">**操作:**"</span><span class="sxs-lookup"><span data-stu-id="cf8aa-343">**Operation:** Sum</span></span>
5.  <span data-ttu-id="cf8aa-344">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-344">Define the **List** properties.</span></span><br>
    <span data-ttu-id="cf8aa-345">**リストクエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span><span class="sxs-lookup"><span data-stu-id="cf8aa-345">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="cf8aa-346">**グラフの非表示:** 選択した</span><span class="sxs-lookup"><span data-stu-id="cf8aa-346">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="cf8aa-347">**スパークラインを有効にする:** 未選択</span><span class="sxs-lookup"><span data-stu-id="cf8aa-347">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="cf8aa-348">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-348">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="cf8aa-349">**Name:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="cf8aa-349">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="cf8aa-350">**値:** 空のままにする</span><span class="sxs-lookup"><span data-stu-id="cf8aa-350">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="cf8aa-351">**ナビゲーションクエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-351">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="cf8aa-352">[**適用**]、[**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-352">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a><span data-ttu-id="cf8aa-353">アプリケーションのバージョンを表示:::no-loc text="Microsoft Teams Rooms":::するタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="cf8aa-353">Create a tile that displays :::no-loc text="Microsoft Teams Rooms"::: application versions</span></span>

1.  <span data-ttu-id="cf8aa-354">ギャラリーから [**ドーナツ & リスト**] を選び、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-354">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="cf8aa-355">**一般的な**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-355">Define the **General** properties:</span></span><br>
    <span data-ttu-id="cf8aa-356">**グループタイトル:** :::no-loc text="Microsoft Teams Rooms":::アプリケーションの詳細</span><span class="sxs-lookup"><span data-stu-id="cf8aa-356">**Group Title:** :::no-loc text="Microsoft Teams Rooms"::: application details</span></span><br>
    <span data-ttu-id="cf8aa-357">**新しいグループ:** 選択した</span><span class="sxs-lookup"><span data-stu-id="cf8aa-357">**New Group:** Selected</span></span>
3.  <span data-ttu-id="cf8aa-358">**ヘッダー**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-358">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="cf8aa-359">**タイトル:** アプリケーションのバージョン</span><span class="sxs-lookup"><span data-stu-id="cf8aa-359">**Title:** Application versions</span></span><br>
    <span data-ttu-id="cf8aa-360">**サブタイトル:** 特定のアプリケーションバージョンを実行しているデバイス</span><span class="sxs-lookup"><span data-stu-id="cf8aa-360">**Subtitle:** Devices running specific application versions</span></span>
4.  <span data-ttu-id="cf8aa-361">**ドーナツ**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-361">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="cf8aa-362">**クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span><span class="sxs-lookup"><span data-stu-id="cf8aa-362">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span></span><br>
    <span data-ttu-id="cf8aa-363">**テキストの中央揃え:** デバイス</span><span class="sxs-lookup"><span data-stu-id="cf8aa-363">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="cf8aa-364">**操作:**"</span><span class="sxs-lookup"><span data-stu-id="cf8aa-364">**Operation:** Sum</span></span>
5.  <span data-ttu-id="cf8aa-365">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-365">Define the **List** properties.</span></span><br>
    <span data-ttu-id="cf8aa-366">**リストクエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span><span class="sxs-lookup"><span data-stu-id="cf8aa-366">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="cf8aa-367">**グラフの非表示:** 選択した</span><span class="sxs-lookup"><span data-stu-id="cf8aa-367">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="cf8aa-368">**スパークラインを有効にする:** 未選択</span><span class="sxs-lookup"><span data-stu-id="cf8aa-368">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="cf8aa-369">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-369">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="cf8aa-370">**Name:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="cf8aa-370">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="cf8aa-371">**値:** 空のままにする</span><span class="sxs-lookup"><span data-stu-id="cf8aa-371">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="cf8aa-372">**ナビゲーションクエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-372">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="cf8aa-373">[**適用**]、[**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-373">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a><span data-ttu-id="cf8aa-374">アプリケーションエラーが発生しているデバイスを表示するタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="cf8aa-374">Create a tile that displays devices that have an application error</span></span>

1.  <span data-ttu-id="cf8aa-375">ギャラリーから [**番号 & リスト**] を選び、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-375">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="cf8aa-376">**一般的な**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-376">Define the **General** properties.</span></span><br>
    <span data-ttu-id="cf8aa-377">**グループタイトル:** 空のままにする</span><span class="sxs-lookup"><span data-stu-id="cf8aa-377">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="cf8aa-378">**新しいグループ:** 未選択</span><span class="sxs-lookup"><span data-stu-id="cf8aa-378">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="cf8aa-379">**タイル**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-379">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="cf8aa-380">**凡例:** 過去1時間にアプリケーションにエラーが発生したデバイス</span><span class="sxs-lookup"><span data-stu-id="cf8aa-380">**Legend:** Devices that experienced an application error in the last hour</span></span><br>
    <span data-ttu-id="cf8aa-381">\*\*タイルのクエリ: \*\* ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="cf8aa-381">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="cf8aa-382">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-382">Define the **List** properties.</span></span><br>
    <span data-ttu-id="cf8aa-383">**リストクエリ:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="cf8aa-383">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="cf8aa-384">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-384">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="cf8aa-385">**Name:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="cf8aa-385">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="cf8aa-386">**値:** 最後のエラー</span><span class="sxs-lookup"><span data-stu-id="cf8aa-386">**Value:** Last Error</span></span>
6.  <span data-ttu-id="cf8aa-387">**ナビゲーションクエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-387">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="cf8aa-388">[**適用**]、[**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-388">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a><span data-ttu-id="cf8aa-389">再起動されたデバイスを表示するタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="cf8aa-389">Create a tile that displays devices that have been restarted</span></span>

1.  <span data-ttu-id="cf8aa-390">ギャラリーから [**番号 & リスト**] を選び、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-390">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="cf8aa-391">**一般的な**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-391">Define the **General** properties.</span></span><br>
    <span data-ttu-id="cf8aa-392">**グループタイトル:** 空のままにする</span><span class="sxs-lookup"><span data-stu-id="cf8aa-392">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="cf8aa-393">**新しいグループ:** 未選択</span><span class="sxs-lookup"><span data-stu-id="cf8aa-393">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="cf8aa-394">**タイル**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-394">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="cf8aa-395">**凡例:** 過去24時間以内にアプリケーションを再起動したデバイスと再起動回数</span><span class="sxs-lookup"><span data-stu-id="cf8aa-395">**Legend:** Devices where the application was restarted in the last 24 hours, and number of restarts</span></span><br>
    <span data-ttu-id="cf8aa-396">\*\*タイルのクエリ: \*\* ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="cf8aa-396">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="cf8aa-397">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-397">Define the **List** properties.</span></span><br>
    <span data-ttu-id="cf8aa-398">**リストクエリ:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span><span class="sxs-lookup"><span data-stu-id="cf8aa-398">**List Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span></span>
5.  <span data-ttu-id="cf8aa-399">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-399">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="cf8aa-400">**Name:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="cf8aa-400">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="cf8aa-401">**値:** 再起動回数</span><span class="sxs-lookup"><span data-stu-id="cf8aa-401">**Value:** Number of Restarts</span></span>
6.  <span data-ttu-id="cf8aa-402">**ナビゲーションクエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-402">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="cf8aa-403">[**適用**]、[**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-403">Select **Apply** and then **Close**.</span></span>
8.  <span data-ttu-id="cf8aa-404">[**保存**] を選択してダッシュボードを保存します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-404">Select **Save** to save your dashboard.</span></span>

<span data-ttu-id="cf8aa-405">これで、ビューの作成が完了しました。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-405">Now you’ve completed creating your views.</span></span>

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a><span data-ttu-id="cf8aa-406">通知を設定する:::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="cf8aa-406">Configure Alerts in :::no-loc text="Azure Monitor":::</span></span>
<span data-ttu-id="cf8aa-407"><a name="Alerts"> </a></span><span class="sxs-lookup"><span data-stu-id="cf8aa-407"><a name="Alerts"> </a></span></span>

<span data-ttu-id="cf8aa-408">:::no-loc text="Azure Monitor"::::::no-loc text="Microsoft Teams Rooms":::コンソールで問題が発生したときに、管理者に通知する通知を生成できます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-408">:::no-loc text="Azure Monitor"::: can raise alerts to notify the administrators, when a :::no-loc text="Microsoft Teams Rooms"::: console encounters an issue.</span></span>

<span data-ttu-id="cf8aa-409">:::no-loc text="Azure Monitor":::スケジュールされたログ検索を定期的に実行する組み込みの通知メカニズムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-409">:::no-loc text="Azure Monitor"::: includes a built-in alerting mechanism that runs through scheduled log searches at regular intervals.</span></span> <span data-ttu-id="cf8aa-410">ログ検索の結果が特定の条件と一致する場合は、通知レコードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-410">If the results of the log search match some particular criteria, an alert record is created.</span></span>

<span data-ttu-id="cf8aa-411">このルールでは、1つ以上のアクションを自動的に実行して、通知を事前に通知するか、別のプロセスを起動することができます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-411">The rule can then automatically run one or more actions to proactively notify you of the alert or invoke another process.</span></span> <span data-ttu-id="cf8aa-412">次のような警告のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-412">The possible options with alerts are:</span></span>
-   <span data-ttu-id="cf8aa-413">メールを送信する</span><span class="sxs-lookup"><span data-stu-id="cf8aa-413">Sending an email</span></span>
-   <span data-ttu-id="cf8aa-414">HTTP POST 要求による外部プロセスの呼び出し</span><span class="sxs-lookup"><span data-stu-id="cf8aa-414">Invoking an external process through an HTTP POST request</span></span>
-   <span data-ttu-id="cf8aa-415">サービスでの:::no-loc text="Azure Automation"::: runbook の開始</span><span class="sxs-lookup"><span data-stu-id="cf8aa-415">Starting a runbook in :::no-loc text="Azure Automation"::: service</span></span>

<span data-ttu-id="cf8aa-416">通知の詳細については、「ログの:::no-loc text="Azure Monitor":::[警告:::no-loc text="Azure Monitor"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-416">See [Log alerts in :::no-loc text="Azure Monitor":::](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) to learn more about the alerts in :::no-loc text="Azure Monitor":::.</span></span>

> [!NOTE]
> <span data-ttu-id="cf8aa-417">次の例では、デバイスが:::no-loc text="Microsoft Teams Rooms":::ハードウェアまたはアプリケーションエラーを生成したときにメール通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-417">The following examples send email alerts when a :::no-loc text="Microsoft Teams Rooms"::: device generates a hardware or an application error.</span></span>

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a><span data-ttu-id="cf8aa-418">ハードウェアの問題に関する:::no-loc text="Microsoft Teams Rooms":::電子メール通知を構成する</span><span class="sxs-lookup"><span data-stu-id="cf8aa-418">Configure an email alert for :::no-loc text="Microsoft Teams Rooms"::: hardware issues</span></span>

<span data-ttu-id="cf8aa-419">過去1時間以内にハードウェアの:::no-loc text="Microsoft Teams Rooms":::問題が発生したデバイスを確認する通知ルールを構成します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-419">Configure an alert rule that checks for :::no-loc text="Microsoft Teams Rooms"::: devices that have encountered hardware issues within the last hour.</span></span>
1.  <span data-ttu-id="cf8aa-420">ポータルにサインインして、ワークスペース:::no-loc text="Log Analytics":::に移動して選択します。 [ :::no-loc text="Microsoft Azure"::: ](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="cf8aa-420">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2. <span data-ttu-id="cf8aa-421">:::no-loc text="Log Analytics":::ワークスペースに移動して、[**警告**] を選択し、[**新しい通知ルール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-421">Navigate to your :::no-loc text="Log Analytics"::: workspace and select **Alerts** and then select **New alert rule**</span></span>

3. <span data-ttu-id="cf8aa-422">[**条件の追加**] を選択し、[**カスタムログの検索**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-422">Select **Add condition** and then **Custom log search**</span></span>

4.  <span data-ttu-id="cf8aa-423">[検索クエリ] テキストボックスに、次のクエリを入力します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-423">Enter the following query to the Search query text box.</span></span><br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  <span data-ttu-id="cf8aa-424">アラートのロジック設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-424">Configure the Alert logic settings:</span></span><br>
    <span data-ttu-id="cf8aa-425">**基準:** 結果の数</span><span class="sxs-lookup"><span data-stu-id="cf8aa-425">**Based on:** Number of results</span></span><br>
    <span data-ttu-id="cf8aa-426">**条件:** より大きい</span><span class="sxs-lookup"><span data-stu-id="cf8aa-426">**Condition:** Greater then</span></span><br>
    <span data-ttu-id="cf8aa-427">**Treshold:** 0</span><span class="sxs-lookup"><span data-stu-id="cf8aa-427">**Treshold:** 0</span></span><br>

6. <span data-ttu-id="cf8aa-428">評価の設定を構成し、[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-428">Configure Evaluation settings and select **Done**:</span></span> <br>
    <span data-ttu-id="cf8aa-429">**期間 (分):** 60</span><span class="sxs-lookup"><span data-stu-id="cf8aa-429">**Period (in minutes):** 60</span></span><br>
    <span data-ttu-id="cf8aa-430">**頻度 (分):** 60</span><span class="sxs-lookup"><span data-stu-id="cf8aa-430">**Frequency (in minutes):** 60</span></span><br>

7. <span data-ttu-id="cf8aa-431">アクショングループを構成します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-431">Configure action groups:</span></span>
    1.  <span data-ttu-id="cf8aa-432">[**新規作成**] を選ぶ</span><span class="sxs-lookup"><span data-stu-id="cf8aa-432">Select **Create New**</span></span>
    2.  <span data-ttu-id="cf8aa-433">[*アクショングループ名]* フィールドと [*短縮名*] フィールドに適切な名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-433">Provide suitable names for the *Action group name* and *Short Name* fields.</span></span>
    3.  <span data-ttu-id="cf8aa-434">一意の*アクション名*を指定し、[**メール/SMS/プッシュ/ボイス**] を選択して、[**詳細の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-434">Specify a unique *Action Name* and select **Email/SMS/Push/Voice**, and then select **Edit details**.</span></span>
    4.  <span data-ttu-id="cf8aa-435">[メール] チェックボックスをオンにして、アラートを受信するユーザーまたはグループのメールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-435">Select the Email checkbox and provide the email address of the person or group that will recieve the alerts.</span></span>
    5.  <span data-ttu-id="cf8aa-436">また、SMS、音声通話、またはその両方の通知を受け取るために、電話番号を入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-436">You may also provide your phone number to get notified with SMS, a voice call or both.</span></span>
    6. <span data-ttu-id="cf8aa-437">[ **OK]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-437">Select **OK**.</span></span>

8. <span data-ttu-id="cf8aa-438">通知メールの件名行を上書きする場合は、[**アクションのカスタマイズ**を行う。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-438">**Customize Actions** if you like to override the subject line of the alert emails.</span></span>

9. <span data-ttu-id="cf8aa-439">ルールの名前と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-439">Specify a rule name and description.</span></span><br>
    <span data-ttu-id="cf8aa-440">**ルール名:** :::no-loc text="Microsoft Teams Rooms":::ハードウェアエラーアラート</span><span class="sxs-lookup"><span data-stu-id="cf8aa-440">**Rule Name:** :::no-loc text="Microsoft Teams Rooms"::: Hardware Failure Alert</span></span><br>
    <span data-ttu-id="cf8aa-441">**説明:** 過去1時間以内にハードウェアの問題が発生したデバイスの一覧</span><span class="sxs-lookup"><span data-stu-id="cf8aa-441">**Description:** List of devices that encountered a hardware issue within the last hour</span></span><br>

10. <span data-ttu-id="cf8aa-442">目的の重要度を選び、ルールが有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-442">Select the intended severity and make sure the rule is enabled.</span></span>

11. <span data-ttu-id="cf8aa-443">[**通知ルールの作成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-443">Select **Create alert rule**.</span></span>

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a><span data-ttu-id="cf8aa-444">アプリケーションの問題に:::no-loc text="Microsoft Teams Rooms":::関する電子メール通知を構成する</span><span class="sxs-lookup"><span data-stu-id="cf8aa-444">Configure an email alert for :::no-loc text="Microsoft Teams Rooms"::: application issues</span></span>

<span data-ttu-id="cf8aa-445">同じ手順を繰り返しますが、次のクエリを使用して、過去1時間以内にアプリケーションの問題が発生したデバイスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-445">Repeat the same procedure but use the following query to list devices that have encountered application issues within the last hour.</span></span>

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

<span data-ttu-id="cf8aa-446">これで、通知の定義が完了しました。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-446">Now you’ve completed defining alerts.</span></span> <span data-ttu-id="cf8aa-447">上記の例を使用して、追加の警告を定義できます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-447">You can define additional alerts by using the examples above.</span></span>

<span data-ttu-id="cf8aa-448">アラートが生成されると、過去1時間以内に問題が発生したデバイスの一覧を示すメールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-448">When an alert is generated, you’ll get an email that lists the devices that encountered an issue within the last hour.</span></span>

<span data-ttu-id="cf8aa-449">![サンプル:::no-loc text="Azure Monitor":::の通知メール](../メディア/または "サンプル通知メール" の例:::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="cf8aa-449">![Sample :::no-loc text="Azure Monitor"::: alert email](../media/Deploy-Azure-Monitor-6.png "Sample :::no-loc text="Azure Monitor"::: alert email")</span></span>

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a><span data-ttu-id="cf8aa-450">すべてのデバイスを構成する:::no-loc text="Azure Monitoring":::</span><span class="sxs-lookup"><span data-stu-id="cf8aa-450">Configure all devices for :::no-loc text="Azure Monitoring":::</span></span>
<span data-ttu-id="cf8aa-451"><a name="configure_all_devices"></a>ダッシュボードとアラートを構成したら、すべて:::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms":::のデバイスでエージェントをセットアップして構成し、監視展開を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-451"><a name="configure_all_devices"> </a> After the dashboards and alerts are configured, you can set up and configure :::no-loc text="Microsoft Monitoring"::: agent on all :::no-loc text="Microsoft Teams Rooms"::: devices to complete your monitoring deployment.</span></span>

<span data-ttu-id="cf8aa-452">エージェントは:::no-loc text="Microsoft Monitoring":::各デバイスで手動でインストールして構成することもできますが、既存のソフトウェア展開ツールと方法を活用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-452">Although you can install and configure the :::no-loc text="Microsoft Monitoring"::: agent manually on each device, we highly recommend you leverage existing software deployment tools and methods.</span></span>

<span data-ttu-id="cf8aa-453">初めて:::no-loc text="Microsoft Teams Rooms":::デバイスを構築する場合は、構築プロセスの一部としてエージェント:::no-loc text="Microsoft Monitoring":::のセットアップと構成の手順を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-453">If you’re building your :::no-loc text="Microsoft Teams Rooms"::: devices for the first time, you might want to include the :::no-loc text="Microsoft Monitoring"::: agent setup and configuration steps as part of your build process.</span></span> <span data-ttu-id="cf8aa-454">詳細については、「[コマンドラインを使用してエージェントをインストール](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-454">For more information, see [Install the agent using the command line](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).</span></span>

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a><span data-ttu-id="cf8aa-455">グループ:::no-loc text="Microsoft Monitoring":::ポリシーオブジェクト (GPO) を使用したエージェントの展開</span><span class="sxs-lookup"><span data-stu-id="cf8aa-455">Deploying :::no-loc text="Microsoft Monitoring"::: agent by using a Group Policy Object (GPO)</span></span>

<span data-ttu-id="cf8aa-456">実装:::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitoring":::前に既にデバイスを展開している場合は、提供されたスクリプトを使用して、グループ:::no-loc text="Active Directory":::ポリシーオブジェクトを使ってエージェントをセットアップし、構成することができます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-456">If you already deployed your :::no-loc text="Microsoft Teams Rooms"::: devices before you implement :::no-loc text="Azure Monitoring":::, you can use the provided script to set up and configure the agents by using :::no-loc text="Active Directory"::: group policy objects.</span></span>

1.  <span data-ttu-id="cf8aa-457">共有ネットワークパスを作成し、**ドメインコンピューター**グループに読み取りアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-457">Create a shared network path and grant read access to **Domain Computers** group.</span></span>

2.  <span data-ttu-id="cf8aa-458">64ビット版の:::no-loc text="Microsoft Monitoring":::エージェントをダウンロードするに:::no-loc text="Windows":::は、<https://go.microsoft.com/fwlink/?LinkID=517476></span><span class="sxs-lookup"><span data-stu-id="cf8aa-458">Download the 64-bit version of the :::no-loc text="Microsoft Monitoring"::: Agent for :::no-loc text="Windows"::: from <https://go.microsoft.com/fwlink/?LinkID=517476></span></span>

3.  <span data-ttu-id="cf8aa-459">ネットワーク共有にセットアップパッケージの内容を抽出します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-459">Extract the contents of the setup package into the network share.</span></span>
    1.  <span data-ttu-id="cf8aa-460">コマンドプロンプトウィンドウを開き、MMASetup-AMD64 を実行し**ます。**</span><span class="sxs-lookup"><span data-stu-id="cf8aa-460">Open a Command Prompt window, and then execute **MMASetup-AMD64.exe /c**</span></span>
    2.  <span data-ttu-id="cf8aa-461">作成した共有を指定し、コンテンツを抽出します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-461">Specify the share you just created, and extract the content.</span></span>

4.  <span data-ttu-id="cf8aa-462">新しいグループポリシーオブジェクトを作成し、 :::no-loc text="Microsoft Teams Rooms":::コンピューターアカウントがある組織単位に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-462">Create a new Group Policy Object and assign it to the organizational unit where :::no-loc text="Microsoft Teams Rooms"::: machine accounts are located.</span></span>

5.  <span data-ttu-id="cf8aa-463">PowerShell 実行ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-463">Configure PowerShell execution policy:</span></span>
    1.  <span data-ttu-id="cf8aa-464">新しく作成されたグループポリシーオブジェクトを編集し、 \\コンピューター \\構成ポリシー \\ :::no-loc text="Windows":::管理\\用テンプレートのコンポーネントに移動する:::no-loc text="Windows PowerShell":::</span><span class="sxs-lookup"><span data-stu-id="cf8aa-464">Edit the newly created Group Policy Object and navigate to Computer Configuration \\ Policies \\ Administrative Templates \\ :::no-loc text="Windows"::: Components \\ :::no-loc text="Windows PowerShell":::</span></span>
    2.  <span data-ttu-id="cf8aa-465">[**スクリプト実行を有効**にする] を有効にして、**ローカルスクリプトを許可**する**実行ポリシー**を設定します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-465">Enable the **Turn on Script Execution** and set **Execution Policy** to **Allow Local Scripts**.</span></span>

6.  <span data-ttu-id="cf8aa-466">スタートアップスクリプトを構成します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-466">Configure the startup script:</span></span>
    1.  <span data-ttu-id="cf8aa-467">次のスクリプトをコピーし、Install-MMAgent として保存します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-467">Copy the following script and save it as Install-MMAgent.ps1.</span></span>
    2.  <span data-ttu-id="cf8aa-468">構成に合わせて WorkspaceId、WorkspaceKey、SetupPath の各パラメーターを変更します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-468">Modify WorkspaceId, WorkspaceKey, and SetupPath parameters to match your configuration.</span></span>
    3.  <span data-ttu-id="cf8aa-469">同じグループポリシーオブジェクトを編集して、コンピューター構成\\ポリシー \\ :::no-loc text="Windows":::の\\設定スクリプト (スタートアップ/シャットダウン) に移動します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-469">Edit the same Group Policy Object and navigate to Computer Configuration \\ Policies \\ :::no-loc text="Windows"::: Settings \\ Scripts (Startup/Shutdown)</span></span>
    4.  <span data-ttu-id="cf8aa-470">[**スタートアップ**] をダブルクリックして選択し、[ **PowerShell スクリプト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-470">Double-click to select **Startup**, and then select **PowerShell Scripts**.</span></span>
    5.  <span data-ttu-id="cf8aa-471">[**ファイルの表示**] を選択し、 **Install-MMAgent**ファイルをそのフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-471">Select **Show Files**, and then copy the **Install-MMAgent.ps1** file to that folder.</span></span>
    6.  <span data-ttu-id="cf8aa-472">[**追加**]、[**参照**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-472">Select **Add**, and then **Browse**.</span></span>
    7.  <span data-ttu-id="cf8aa-473">コピーした ps1 スクリプトを選択します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-473">Select the ps1 script you just copied.</span></span>

7.  <span data-ttu-id="cf8aa-474">:::no-loc text="Microsoft Teams Rooms":::デバイスは、2回目:::no-loc text="Microsoft Monitoring":::の再起動でエージェントをインストールして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-474">:::no-loc text="Microsoft Teams Rooms"::: devices should install and configure the :::no-loc text="Microsoft Monitoring"::: agent with the second reboot.</span></span>

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
> <span data-ttu-id="cf8aa-475">エージェントの再構成、別のワークスペースへの移動、または最初のインストール後のプロキシ設定の変更を行う必要がある場合は、「[エージェントの:::no-loc text="Log Analytics":::管理と保守](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-475">You can refer to the article [Managing and maintaining the :::no-loc text="Log Analytics"::: agent](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) when you need to reconfigure an agent, move it to a different workspace, or modify proxy settings after the initial installation.</span></span>

## <a name="additional-solutions"></a><span data-ttu-id="cf8aa-476">その他の解決策</span><span class="sxs-lookup"><span data-stu-id="cf8aa-476">Additional Solutions</span></span>
<span data-ttu-id="cf8aa-477"><a name="Solutions"> </a></span><span class="sxs-lookup"><span data-stu-id="cf8aa-477"><a name="Solutions"> </a></span></span>

<span data-ttu-id="cf8aa-478">:::no-loc text="Azure Monitor":::[ソリューションギャラリー](https://docs.microsoft.com/azure/azure-monitor/insights/solutions)を通じて、お客様の環境を監視するための組み込みの管理ソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-478">:::no-loc text="Azure Monitor"::: provides built-in management solutions through its [solution gallery](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) to further help you monitor your environment.</span></span> <span data-ttu-id="cf8aa-479">[通知管理](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution)と[ :::no-loc text="Azure Log Analytics":::エージェントの正常性](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth)の解決策もワークスペースに追加することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-479">We highly recommend that you add [Alert Management](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) and [:::no-loc text="Azure Log Analytics"::: Agent Health](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) solutions to your workspace as well.</span></span>

> [!NOTE]
> <span data-ttu-id="cf8aa-480">エージェント正常性ソリューションは、環境内の古いまた:::no-loc text="Microsoft Monitoring":::は破損したエージェントを特定するのに役立ちます。また、アラート管理ソリューションは、一定の期間内に発生した警告に関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="cf8aa-480">The Agent Health solution can help you identify outdated or broken :::no-loc text="Microsoft Monitoring"::: agents within your environment, and the Alert Management solution provides details about the alerts that have been raised within a given period.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf8aa-481">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf8aa-481">See also</span></span>

[<span data-ttu-id="cf8aa-482">計画:::no-loc text="Microsoft Teams Rooms":::管理:::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="cf8aa-482">Plan :::no-loc text="Microsoft Teams Rooms"::: management with :::no-loc text="Azure Monitor":::</span></span>](azure-monitor-plan.md)

[<span data-ttu-id="cf8aa-483">デバイス:::no-loc text="Microsoft Teams Rooms":::の管理:::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="cf8aa-483">Manage :::no-loc text="Microsoft Teams Rooms"::: devices with :::no-loc text="Azure Monitor":::</span></span>](azure-monitor-manage.md)
