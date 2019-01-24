---
title: Azure のモニターを使用して Skype ルーム システム v2 の管理を展開します。
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: この資料では、Azure のモニターを使用して、エンド ・ ツー ・ エンドの統合された方法で Skype ルーム システム v2 のデバイスの管理を展開する方法について説明します。
ms.openlocfilehash: 6a90f5b1dcbbdbab9c4149717e16a01c3a5f5ba1
ms.sourcegitcommit: 09fcd68e30e7f83110f98172382c74f970b339a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2019
ms.locfileid: "29448482"
---
# <a name="deploy-skype-room-systems-v2-management-with-azure-monitor"></a><span data-ttu-id="fdbd4-103">Azure のモニターを使用して Skype ルーム システム v2 の管理を展開します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-103">Deploy Skype Room Systems v2 management with Azure Monitor</span></span>

<span data-ttu-id="fdbd4-104">この資料を設定し、Azure のモニターを使用して Skype ルーム システム v2 のデバイスの統合された、エンド ・ ツー ・ エンドの管理を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-104">This article discusses how to set up and deploy integrated, end-to-end management of Skype Room Systems v2 devices by using Azure Monitor.</span></span>

<span data-ttu-id="fdbd4-105">基本的な遠隔測定を提供する Azure モニター内でのログの分析を構成することができ、警告するためは、Skype の会議室のデバイスを管理します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-105">You can configure Log Analytics within Azure Monitor to provide basic telemetry and alerts that will help you manage Skype meeting room devices.</span></span> <span data-ttu-id="fdbd4-106">管理ソリューションが完成に近づくにつれて、追加のデータとデバイスの可用性とパフォーマンスの詳細なビューを作成する管理機能を導入することができます。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-106">As your management solution matures, you might decide to deploy additional data and management capabilities to create a more detailed view of device availability and performance.</span></span>

<span data-ttu-id="fdbd4-107">によって、このガイドに従うと、デバイスの可用性、アプリケーションとハードウェアの健康状態、および Skype ルーム システム v2 アプリケーションおよびオペレーティング システムのバージョンの配布用のレポート、詳細なステータスを取得するのに例を次のようなダッシュ ボードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-107">By following this guide, you can use a dashboard like the following example to get detailed status reporting for device availability, application and hardware health, and Skype Room Systems v2 application and operating system version distribution.</span></span>

<span data-ttu-id="fdbd4-108">![SRS v2 のサンプル ログ分析の表示](../../media/Deploy-Azure-Monitor-1.png "SRS v2 のサンプル ログ分析の表示")</span><span class="sxs-lookup"><span data-stu-id="fdbd4-108">![Sample Log Analytics view for SRS v2](../../media/Deploy-Azure-Monitor-1.png "Sample Log Analytics view for SRS v2")</span></span>

<span data-ttu-id="fdbd4-109">高いレベルでは、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-109">At a high level, you need to perform the following tasks:</span></span>


1.  [<span data-ttu-id="fdbd4-110">ログ分析の構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-110">Validate Log Analytics configuration</span></span>](azure-monitor.md#validate_LogAnalytics)
2.  [<span data-ttu-id="fdbd4-111">管理セットアップのログ分析機能のテスト デバイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-111">Configure test devices for Log Analytics management setup</span></span>](azure-monitor.md#configure_test_devices)
3.  [<span data-ttu-id="fdbd4-112">カスタム フィールドをマップする</span><span class="sxs-lookup"><span data-stu-id="fdbd4-112">Map custom fields</span></span>](azure-monitor.md#Custom_fields)
4.  [<span data-ttu-id="fdbd4-113">ログ分析で Skype ルーム システム v2 ビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-113">Define the Skype Room Systems v2 views in Log Analytics</span></span>](azure-monitor.md#Define_Views)
5.  [<span data-ttu-id="fdbd4-114">警告を定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-114">Define alerts</span></span>](azure-monitor.md#Alerts)
6.  [<span data-ttu-id="fdbd4-115">監視のすべてのデバイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-115">Configure all devices for Monitoring</span></span>](azure-monitor.md#configure_all_devices)
7.  [<span data-ttu-id="fdbd4-116">Azure のモニターの追加のソリューションを構成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-116">Configure additional Azure Monitor solutions</span></span>](azure-monitor.md#Solutions)

> [!IMPORTANT]
> <span data-ttu-id="fdbd4-117">Skype ルームのすべてのシステムにエージェントの展開を開始する前に実行する必要があるいくつかの Skype ルーム システム v2 固有の手順はまだありますが、最小限の構成では、Azure 監視ログ分析機能は、Windows オペレーティング システムを実行するコンピューターを監視できます、デバイスです。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-117">Although with minimal configuration, Azure Monitor Log Analytics can monitor a computer running a Windows operating system, there are still some Skype Room Systems v2–specific steps that you need to take before you start deploying agents to all Skype Room Systems devices.</span></span>
> <span data-ttu-id="fdbd4-118">したがって、コントロールのセットアップと構成の正しい順序ですべての構成手順を実行するを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-118">Therefore, we highly recommend you perform all configuration steps in the right order for a controlled setup and configuration.</span></span> <span data-ttu-id="fdbd4-119">最終結果の品質は、初期構成の品質に非常に依存します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-119">The quality of the end result very much depends on the quality of the initial configuration.</span></span>

## <a name="validate-log-analytics-configuration"></a><span data-ttu-id="fdbd4-120">ログ分析の構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-120">Validate Log Analytics configuration</span></span>
<span data-ttu-id="fdbd4-121"><a name="validate_LogAnalytics"> </a></span><span class="sxs-lookup"><span data-stu-id="fdbd4-121"></span></span>

<span data-ttu-id="fdbd4-122">Skype ルーム システム v2 のデバイスからのログの収集を開始するログ分析機能のワークスペースが必要です。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-122">You need to have a Log Analytics workspace to start collecting logs from Skype Room Systems v2 devices.</span></span> <span data-ttu-id="fdbd4-123">ワークスペースは、独自のデータ リポジトリ、データ ソース、およびソリューションの一意なログ分析環境です。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-123">A workspace is a unique Log Analytics environment with its own data repository, data sources, and solutions.</span></span> <span data-ttu-id="fdbd4-124">既にした場合、既存のログ分析機能のワークスペース、Skype ルーム システム v2 配置を監視するために使用可能性があります代わりを作成したりできます、専用のログ分析機能のワークスペース特定 Skype ルーム システム v2 の監視ニーズにします。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-124">If you already have an existing Log Analytics workspace, you might use it to monitor your Skype Room Systems v2 deployment or alternatively, you can create a dedicated Log Analytics workspace specific to your Skype Room Systems v2 monitoring needs.</span></span>

<span data-ttu-id="fdbd4-125">[Azure ポータルでのログの分析機能のワークスペースを作成する](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)この資料の指示に従って、新しいログの分析機能のワークスペースを作成する場合は、</span><span class="sxs-lookup"><span data-stu-id="fdbd4-125">If you need to create a new Log Analytics workspace, follow the instructions in the article [Create a Log Analytics workspace in the Azure portal](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)</span></span>

> [!NOTE]
> <span data-ttu-id="fdbd4-126">ログ分析機能を使用して、Azure のモニターでは、Azure サブスクリプションはアクティブにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-126">To use Log Analytics with Azure Monitor, you need to have an active Azure subscription.</span></span> <span data-ttu-id="fdbd4-127">Azure サブスクリプションをお持ちでない場合は、開始点として[無料の試用版サブスクリプション](https://azure.microsoft.com/free)を作成できます。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-127">If you don’t have an Azure subscription, you can create [a free trial subscription](https://azure.microsoft.com/free) as a starting point.</span></span>

### <a name="configure-log-analytics-to-collect-skype-room-systems-v2-event-logs"></a><span data-ttu-id="fdbd4-128">Skype ルーム システム v2 のイベント ログを収集するログの分析を構成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-128">Configure Log Analytics to collect Skype Room Systems v2 event logs</span></span>

<span data-ttu-id="fdbd4-129">のみ、ログ分析機能は、設定で指定されている Windows のイベント ログからイベントを収集します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-129">Log Analytics only collects events from the Windows event logs that are specified in the settings.</span></span> <span data-ttu-id="fdbd4-130">各ログには、選択した重大度のレベルのイベントのみが収集されます。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-130">For each log, only the events with the selected severities are collected.</span></span>

<span data-ttu-id="fdbd4-131">Skype ルーム システム v2 のデバイスとアプリケーションの状態を監視するために必要なログを収集するログの分析を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-131">You need to configure Log Analytics to collect the logs required to monitor Skype Room Systems v2 device and application status.</span></span> <span data-ttu-id="fdbd4-132">Skype ルーム システム v2 のデバイスでは、 **Skype の部屋のシステム**イベント ログを使用します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-132">Skype Room Systems v2 devices use the **Skype Room System** event log.</span></span>

<span data-ttu-id="fdbd4-133">Skype ルーム システム v2 のイベントを収集するログの分析を構成するには、 [Azure のモニターでは、Windows イベント ログ データ ソース](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-133">To configure Log Analytics to collect the Skype Room Systems v2 events, see [Windows event log data sources in Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)</span></span>

<span data-ttu-id="fdbd4-134">![イベント ログの設定](../../media/Deploy-Azure-Monitor-2.png "イベント ログの設定")</span><span class="sxs-lookup"><span data-stu-id="fdbd4-134">![Event log settings](../../media/Deploy-Azure-Monitor-2.png "Event log settings")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fdbd4-135">Windows イベント ログ設定を構成および**Skype ルーム システム**を入力して、イベント ログの名前と、**エラー**、**警告**、および**情報**のチェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-135">Configure Windows Event Log settings and enter **Skype Room System** as event log name, and then select the **Error**, **Warning**, and **Information** check boxes.</span></span>

## <a name="configure-test-devices-for-azure-monitoring"></a><span data-ttu-id="fdbd4-136">Azure を監視するためのテスト デバイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-136">Configure test devices for Azure Monitoring</span></span>
<span data-ttu-id="fdbd4-137"><a name="configure_test_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="fdbd4-137"></span></span>

<span data-ttu-id="fdbd4-138">Skype ルーム システム v2 に関連するイベントを監視することができるログの分析を準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-138">You need to prepare Log Analytics to be able to monitor Skype Room Systems v2–related events.</span></span> <span data-ttu-id="fdbd4-139">開始する物理的なアクセス権を持つ、1 つか 2 つの Skype ルーム システム v2 デバイスに Microsoft の監視エージェントを展開し、それらを取得する必要がありますテスト デバイスは、いくつかのデータを生成し、ログ分析機能のワークスペースに押し込みます。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-139">To start with, you need to deploy Microsoft Monitoring agents to just one or two Skype Room Systems v2 devices that you have physical access to, and get those test devices generate some data and push it to the Log Analytics workspace.</span></span>

### <a name="install-microsoft-monitoring-agents-to-test-devices"></a><span data-ttu-id="fdbd4-140">デバイスをテストするのには Microsoft の監視エージェントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-140">Install Microsoft Monitoring agents to test devices</span></span>

<span data-ttu-id="fdbd4-141">テスト デバイスに[接続の Windows コンピューター](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)で提供されている手順を使用して Microsoft の監視エージェントを展開します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-141">Deploy the Microsoft Monitoring agent to the test devices by using the instructions provided in [Connect Windows computers to the Log Analytics service in Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows).</span></span> <span data-ttu-id="fdbd4-142">この資料には、監視エージェントの Windows を展開するための手順に関する詳細情報が用意されています、Skype ルーム システム v2 のデバイスを取得するログ分析機能の***ワークスペース ID***と***プライマリ ・ キー***を取得するための手順に接続されています。Azure のモニターの配置とログ分析のインスタンスへのエージェント接続を確認する手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-142">This article provides detailed information about the steps for deploying Microsoft Monitoring Agent for Windows, instructions for obtaining the Log Analytics ***Workspace ID*** and the ***primary key*** to get Skype Room Systems v2 devices connected to your Azure Monitor deployment, and steps to verify agent connectivity to Log Analytics instance.</span></span>

### <a name="generate-sample-skype-room-systems-events"></a><span data-ttu-id="fdbd4-143">サンプル Skype ルームのシステム イベントを生成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-143">Generate sample Skype Room Systems events</span></span>

<span data-ttu-id="fdbd4-144">Microsoft の監視エージェントがテストのデバイス上に配置されると、Azure のモニターを使用して必要なイベント ログ データを収集することを確認します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-144">After the Microsoft Monitoring agent is deployed onto the test devices, verify that the required event log data is collected by Azure Monitor.</span></span>

> [!NOTE]
> <span data-ttu-id="fdbd4-145">、Microsoft の監視エージェントのインストール後、デバイスを再起動し、その Skype ルーム システム v2 の会議アプリケーションを起動すると、イベント ログに新しいイベントが生成されることができるようにします。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-145">Reboot the device after the installation of the Microsoft Monitoring agent, and make sure that Skype Room Systems v2 Meeting app is started, so that it can generate new events into the Event Log.</span></span>

1.  <span data-ttu-id="fdbd4-146">[Microsoft Azure ポータル](https://portal.azure.com)にサインインし、どうなるログの分析に新しいワークスペースを選択します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-146">Sign in to the [Microsoft Azure portal](https://portal.azure.com) and go to Log Analytics and select your workspace.</span></span>

2.  <span data-ttu-id="fdbd4-147">Skype ルーム システム v2 デバイスによって生成されたハートビート イベントを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-147">List the heartbeat events generated by a Skype Room Systems v2 device:</span></span>
    1.  <span data-ttu-id="fdbd4-148">ワークスペースを選択して**ログ**にしてどうなる SRS v2 のカスタム フィールドがあるハートビート レコードを取得するクエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-148">Select your workspace and go to **Logs** and use a query to retrieve the heartbeat records that will have the custom fields for SRS v2.</span></span>
    2.  <span data-ttu-id="fdbd4-149">サンプル クエリ。`Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="fdbd4-149">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3.  <span data-ttu-id="fdbd4-150">Skype ルーム システム v2 の会議アプリケーションによって生成されたイベントを含むログ レコードをクエリが返すことを確認します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-150">Make sure that the query returns log records that include events generated by the Skype Room Systems v2 meetings app.</span></span>

4.  <span data-ttu-id="fdbd4-151">ハードウェアの問題を生成し、Azure のログの分析に必要なイベントを記録することを検証します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-151">Generate a hardware issue, and validate that the required events are logged in Azure Log Analytics.</span></span>
    1.  <span data-ttu-id="fdbd4-152">Skype ルーム システム v2 のシステムのテストで周辺機器の 1 つを外します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-152">Unplug one of the peripheral devices on the test Skype Room Systems v2 system.</span></span> <span data-ttu-id="fdbd4-153">カメラ、スピーカー フォン、マイク、または部屋の前面表示可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-153">This could be the camera, speakerphone, microphone, or Front Room Display</span></span>
    2.  <span data-ttu-id="fdbd4-154">Azure のログ分析機能に設定するイベント ログの 10 分間待ちます。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-154">Wait 10 minutes for the event log to be populated in Azure Log Analytics.</span></span>
    3.  <span data-ttu-id="fdbd4-155">ハードウェア エラー イベントのリストにクエリを使用します。`Event | where Source == "SRS-App" and EventID == 3001`</span><span class="sxs-lookup"><span data-stu-id="fdbd4-155">Use a query to list hardware error events: `Event | where Source == "SRS-App" and EventID == 3001`</span></span>

5.  <span data-ttu-id="fdbd4-156">、アプリケーションの問題を生成し、必要なイベントを記録することを検証します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-156">Generate an application issue, and validate that the required events are logged.</span></span>
    1.  <span data-ttu-id="fdbd4-157">Skype ルーム システム v2 アプリケーションの構成を変更し、不正なセッション開始プロトコル (SIP) アドレスとパスワードのペアを入力します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-157">Modify Skype Room Systems v2 application configuration, and type an incorrect Session Initiation Protocol (SIP) address/password pair.</span></span>
    2.  <span data-ttu-id="fdbd4-158">Azure のログ分析機能に設定するイベント ログの 10 分間待ちます。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-158">Wait 10 minutes for the event log to be populated in Azure Log Analytics.</span></span>
    3.  <span data-ttu-id="fdbd4-159">アプリケーション エラー イベントのリストにクエリを使用します。`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span><span class="sxs-lookup"><span data-stu-id="fdbd4-159">Use a query to list application error events: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fdbd4-160">ユーザー設定フィールドを構成する前に、これらのサンプルのイベント ログが必要です。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-160">These sample event logs are required before custom fields can be configured.</span></span> <span data-ttu-id="fdbd4-161">必要なイベント ログを収集し終えるまで、次の手順を続行しません。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-161">Don’t proceed to the next step until you have collected the required event logs.</span></span>

## <a name="map-custom-fields"></a><span data-ttu-id="fdbd4-162">カスタム フィールドをマップする</span><span class="sxs-lookup"><span data-stu-id="fdbd4-162">Map custom fields</span></span>
<span data-ttu-id="fdbd4-163"><a name="Custom_fields"> </a></span><span class="sxs-lookup"><span data-stu-id="fdbd4-163"></span></span>

<span data-ttu-id="fdbd4-164">イベント ログから特定のデータを抽出するのにには、カスタム フィールドを使用します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-164">You use custom fields to extract specific data from the event logs.</span></span> <span data-ttu-id="fdbd4-165">タイル、ダッシュ ボードの表示、および警告の後で使用するカスタム フィールドを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-165">You need to define custom fields that will be used later with your tiles, dashboard views, and alerts.</span></span> <span data-ttu-id="fdbd4-166">[ログ分析でユーザー設定フィールド](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields)を参照してくださいし、カスタム フィールドの作成を開始する前に概念を理解します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-166">See [Custom fields in Log Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) and become familiar with the concepts before you start creating your custom fields.</span></span>

<span data-ttu-id="fdbd4-167">キャプチャしたイベント ログから、ユーザー設定のフィールドを抽出するには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-167">To extract your custom fields out of the captured event logs, follow these steps:</span></span>

1.  <span data-ttu-id="fdbd4-168">[Microsoft Azure ポータル](https://portal.azure.com)にサインインし、どうなるログの分析に新しいワークスペースを選択します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-168">Sign in to the [Microsoft Azure portal](https://portal.azure.com) and go to Log Analytics and select your workspace.</span></span>

2. <span data-ttu-id="fdbd4-169">Skype ルーム システム v2 デバイスによって生成されたイベントの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-169">List the events generated by a Skype Room Systems v2 device:</span></span>
   1.  <span data-ttu-id="fdbd4-170">**(クラシック) のログ**に移動し、ユーザー設定フィールドを持つレコードを取得するクエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-170">Go to **Logs (classic)** and use a query to retrieve the records that will have the custom field.</span></span>
   2.  <span data-ttu-id="fdbd4-171">サンプル クエリ。`Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="fdbd4-171">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3. <span data-ttu-id="fdbd4-172">レコードのいずれかを選択、左側にあるボタンを選択し、フィールドの展開ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-172">Select one of the records, select the button to the left, and start the field extraction wizard.</span></span>

   <span data-ttu-id="fdbd4-173">![フィールドの抽出ウィザード](../../media/Deploy-Azure-Monitor-3.png "フィールドの抽出ウィザード")</span><span class="sxs-lookup"><span data-stu-id="fdbd4-173">![Field extraction wizard](../../media/Deploy-Azure-Monitor-3.png "Field extraction wizard")</span></span>

4. <span data-ttu-id="fdbd4-174">RenderedDescription から抽出し、フィールドのタイトルを提供したいデータを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-174">Highlight the data you’d like to extract from the RenderedDescription and provide a Field Title.</span></span> <span data-ttu-id="fdbd4-175">表 1 には、使用するフィールド名が用意されています。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-175">The field names that you should use are provided in Table 1.</span></span>

   <span data-ttu-id="fdbd4-176">![ユーザー設定フィールドの定義](../../media/Deploy-Azure-Monitor-4.png "ユーザー設定フィールドの定義")</span><span class="sxs-lookup"><span data-stu-id="fdbd4-176">![Custom field definition](../../media/Deploy-Azure-Monitor-4.png "Custom field definition")</span></span>

5. <span data-ttu-id="fdbd4-177">*表 1*に示すようにマッピングを使用します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-177">Use the mappings shown in *Table 1*.</span></span> <span data-ttu-id="fdbd4-178">ログ分析機能が自動的に追加されます、 \*\* \_CF\*\*文字列の新しいフィールドを定義するとします。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-178">Log Analytics will automatically append the **\_CF** string when you define the new field.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fdbd4-179">JSON とログ分析のすべてのフィールドは大文字小文字を区別することを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-179">Remember that all JSON and Log Analytics fields are case-sensitive.</span></span>
> 
> <span data-ttu-id="fdbd4-180">次の表に各ユーザー設定のフィールドに必要なクエリに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-180">Pay attention to the queries required for each custom field in the table below.</span></span> <span data-ttu-id="fdbd4-181">ログ分析の適切なクエリを使用して、カスタム フィールドの値を正常に抽出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-181">You need to use the correct queries for Log Analytics to successfully extract custom field values.</span></span>
> 
 <span data-ttu-id="fdbd4-182">![ユーザー設定フィールドの定義](../../media/Deploy-Azure-Monitor-5.png "ユーザー設定フィールドの定義")</span><span class="sxs-lookup"><span data-stu-id="fdbd4-182">![Custom field definition](../../media/Deploy-Azure-Monitor-5.png "Custom field definition")</span></span>

<span data-ttu-id="fdbd4-183">表 1.</span><span class="sxs-lookup"><span data-stu-id="fdbd4-183">**Table 1**</span></span>

| <span data-ttu-id="fdbd4-184">JSON フィールド</span><span class="sxs-lookup"><span data-stu-id="fdbd4-184">**JSON field**</span></span>                   | <span data-ttu-id="fdbd4-185">**ログ分析機能のユーザー設定フィールド**</span><span class="sxs-lookup"><span data-stu-id="fdbd4-185">**Log Analytics custom field**</span></span> | <span data-ttu-id="fdbd4-186">イベント ID</span><span class="sxs-lookup"><span data-stu-id="fdbd4-186">**Event ID**</span></span> | <span data-ttu-id="fdbd4-187">**抽出に使用するクエリ**</span><span class="sxs-lookup"><span data-stu-id="fdbd4-187">**Query to use with the extraction**</span></span>                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| <span data-ttu-id="fdbd4-188">説明</span><span class="sxs-lookup"><span data-stu-id="fdbd4-188">Description</span></span>                      | <span data-ttu-id="fdbd4-189">SRSEventDescription</span><span class="sxs-lookup"><span data-stu-id="fdbd4-189">SRSEventDescription</span></span>         | <span data-ttu-id="fdbd4-190">$2,000</span><span class="sxs-lookup"><span data-stu-id="fdbd4-190">**2000**</span></span>     | <span data-ttu-id="fdbd4-191">イベント\|、実際のソース"SRS App"とイベント Id = = = 2000</span><span class="sxs-lookup"><span data-stu-id="fdbd4-191">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="fdbd4-192">ResourceState</span><span class="sxs-lookup"><span data-stu-id="fdbd4-192">ResourceState</span></span>                    | <span data-ttu-id="fdbd4-193">SRSResourceState</span><span class="sxs-lookup"><span data-stu-id="fdbd4-193">SRSResourceState</span></span>            | <span data-ttu-id="fdbd4-194">$2,000</span><span class="sxs-lookup"><span data-stu-id="fdbd4-194">**2000**</span></span>     | <span data-ttu-id="fdbd4-195">イベント\|、実際のソース"SRS App"とイベント Id = = = 2000</span><span class="sxs-lookup"><span data-stu-id="fdbd4-195">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="fdbd4-196">OperationName</span><span class="sxs-lookup"><span data-stu-id="fdbd4-196">OperationName</span></span>                    | <span data-ttu-id="fdbd4-197">SRSOperationName</span><span class="sxs-lookup"><span data-stu-id="fdbd4-197">SRSOperationName</span></span>            | <span data-ttu-id="fdbd4-198">$2,000</span><span class="sxs-lookup"><span data-stu-id="fdbd4-198">**2000**</span></span>     | <span data-ttu-id="fdbd4-199">イベント\|、実際のソース"SRS App"とイベント Id = = = 2000</span><span class="sxs-lookup"><span data-stu-id="fdbd4-199">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="fdbd4-200">OperationResult</span><span class="sxs-lookup"><span data-stu-id="fdbd4-200">OperationResult</span></span>                  | <span data-ttu-id="fdbd4-201">SRSOperationResult</span><span class="sxs-lookup"><span data-stu-id="fdbd4-201">SRSOperationResult</span></span>          | <span data-ttu-id="fdbd4-202">$2,000</span><span class="sxs-lookup"><span data-stu-id="fdbd4-202">**2000**</span></span>     | <span data-ttu-id="fdbd4-203">イベント\|、実際のソース"SRS App"とイベント Id = = = 2000</span><span class="sxs-lookup"><span data-stu-id="fdbd4-203">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="fdbd4-204">OS</span><span class="sxs-lookup"><span data-stu-id="fdbd4-204">OS</span></span>                               | <span data-ttu-id="fdbd4-205">SRSOSVersion</span><span class="sxs-lookup"><span data-stu-id="fdbd4-205">SRSOSVersion</span></span>                | <span data-ttu-id="fdbd4-206">$2,000</span><span class="sxs-lookup"><span data-stu-id="fdbd4-206">**2000**</span></span>     | <span data-ttu-id="fdbd4-207">イベント\|、実際のソース"SRS App"とイベント Id = = = 2000</span><span class="sxs-lookup"><span data-stu-id="fdbd4-207">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="fdbd4-208">OSVersion</span><span class="sxs-lookup"><span data-stu-id="fdbd4-208">OSVersion</span></span>                        | <span data-ttu-id="fdbd4-209">SRSOSLongVersion</span><span class="sxs-lookup"><span data-stu-id="fdbd4-209">SRSOSLongVersion</span></span>            | <span data-ttu-id="fdbd4-210">$2,000</span><span class="sxs-lookup"><span data-stu-id="fdbd4-210">**2000**</span></span>     | <span data-ttu-id="fdbd4-211">イベント\|、実際のソース"SRS App"とイベント Id = = = 2000</span><span class="sxs-lookup"><span data-stu-id="fdbd4-211">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="fdbd4-212">Alias</span><span class="sxs-lookup"><span data-stu-id="fdbd4-212">Alias</span></span>                            | <span data-ttu-id="fdbd4-213">SRSAlias</span><span class="sxs-lookup"><span data-stu-id="fdbd4-213">SRSAlias</span></span>                    | <span data-ttu-id="fdbd4-214">$2,000</span><span class="sxs-lookup"><span data-stu-id="fdbd4-214">**2000**</span></span>     | <span data-ttu-id="fdbd4-215">イベント\|、実際のソース"SRS App"とイベント Id = = = 2000</span><span class="sxs-lookup"><span data-stu-id="fdbd4-215">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="fdbd4-216">DisplayName</span><span class="sxs-lookup"><span data-stu-id="fdbd4-216">DisplayName</span></span>                      | <span data-ttu-id="fdbd4-217">SRSDisplayName</span><span class="sxs-lookup"><span data-stu-id="fdbd4-217">SRSDisplayName</span></span>              | <span data-ttu-id="fdbd4-218">$2,000</span><span class="sxs-lookup"><span data-stu-id="fdbd4-218">**2000**</span></span>     | <span data-ttu-id="fdbd4-219">イベント\|、実際のソース"SRS App"とイベント Id = = = 2000</span><span class="sxs-lookup"><span data-stu-id="fdbd4-219">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="fdbd4-220">AppVersion</span><span class="sxs-lookup"><span data-stu-id="fdbd4-220">AppVersion</span></span>                       | <span data-ttu-id="fdbd4-221">SRSAppVersion</span><span class="sxs-lookup"><span data-stu-id="fdbd4-221">SRSAppVersion</span></span>               | <span data-ttu-id="fdbd4-222">$2,000</span><span class="sxs-lookup"><span data-stu-id="fdbd4-222">**2000**</span></span>     | <span data-ttu-id="fdbd4-223">イベント\|、実際のソース"SRS App"とイベント Id = = = 2000</span><span class="sxs-lookup"><span data-stu-id="fdbd4-223">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="fdbd4-224">IPv4Address</span><span class="sxs-lookup"><span data-stu-id="fdbd4-224">IPv4Address</span></span>                      | <span data-ttu-id="fdbd4-225">SRSIPv4Address</span><span class="sxs-lookup"><span data-stu-id="fdbd4-225">SRSIPv4Address</span></span>              | <span data-ttu-id="fdbd4-226">$2,000</span><span class="sxs-lookup"><span data-stu-id="fdbd4-226">**2000**</span></span>     | <span data-ttu-id="fdbd4-227">イベント\|、実際のソース"SRS App"とイベント Id = = = 2000</span><span class="sxs-lookup"><span data-stu-id="fdbd4-227">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="fdbd4-228">IPv6Address</span><span class="sxs-lookup"><span data-stu-id="fdbd4-228">IPv6Address</span></span>                      | <span data-ttu-id="fdbd4-229">SRSIPv6Address</span><span class="sxs-lookup"><span data-stu-id="fdbd4-229">SRSIPv6Address</span></span>              | <span data-ttu-id="fdbd4-230">$2,000</span><span class="sxs-lookup"><span data-stu-id="fdbd4-230">**2000**</span></span>     | <span data-ttu-id="fdbd4-231">イベント\|、実際のソース"SRS App"とイベント Id = = = 2000</span><span class="sxs-lookup"><span data-stu-id="fdbd4-231">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="fdbd4-232">会議マイクの状態</span><span class="sxs-lookup"><span data-stu-id="fdbd4-232">Conference Microphone status</span></span>     | <span data-ttu-id="fdbd4-233">SRSConfMicrophoneStatus</span><span class="sxs-lookup"><span data-stu-id="fdbd4-233">SRSConfMicrophoneStatus</span></span>     | <span data-ttu-id="fdbd4-234">**3001**</span><span class="sxs-lookup"><span data-stu-id="fdbd4-234">**3001**</span></span>     | <span data-ttu-id="fdbd4-235">イベント\|、実際のソース"SRS App"とイベント Id = = = = の 3001</span><span class="sxs-lookup"><span data-stu-id="fdbd4-235">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="fdbd4-236">会議の発表者のステータス</span><span class="sxs-lookup"><span data-stu-id="fdbd4-236">Conference Speaker status</span></span>        | <span data-ttu-id="fdbd4-237">SRSConfSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="fdbd4-237">SRSConfSpeakerStatus</span></span>        | <span data-ttu-id="fdbd4-238">**3001**</span><span class="sxs-lookup"><span data-stu-id="fdbd4-238">**3001**</span></span>     | <span data-ttu-id="fdbd4-239">イベント\|、実際のソース"SRS App"とイベント Id = = = = の 3001</span><span class="sxs-lookup"><span data-stu-id="fdbd4-239">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="fdbd4-240">スピーカーの既定の状態</span><span class="sxs-lookup"><span data-stu-id="fdbd4-240">Default Speaker status</span></span>           | <span data-ttu-id="fdbd4-241">SRSDefaultSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="fdbd4-241">SRSDefaultSpeakerStatus</span></span>     | <span data-ttu-id="fdbd4-242">**3001**</span><span class="sxs-lookup"><span data-stu-id="fdbd4-242">**3001**</span></span>     | <span data-ttu-id="fdbd4-243">イベント\|、実際のソース"SRS App"とイベント Id = = = = の 3001</span><span class="sxs-lookup"><span data-stu-id="fdbd4-243">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="fdbd4-244">カメラの状態</span><span class="sxs-lookup"><span data-stu-id="fdbd4-244">Camera status</span></span>                    | <span data-ttu-id="fdbd4-245">SRSCameraStatus</span><span class="sxs-lookup"><span data-stu-id="fdbd4-245">SRSCameraStatus</span></span>             | <span data-ttu-id="fdbd4-246">**3001**</span><span class="sxs-lookup"><span data-stu-id="fdbd4-246">**3001**</span></span>     | <span data-ttu-id="fdbd4-247">イベント\|、実際のソース"SRS App"とイベント Id = = = = の 3001</span><span class="sxs-lookup"><span data-stu-id="fdbd4-247">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="fdbd4-248">ルームの表示状態の前面</span><span class="sxs-lookup"><span data-stu-id="fdbd4-248">Front of Room Display status</span></span>     | <span data-ttu-id="fdbd4-249">SRSFORDStatus</span><span class="sxs-lookup"><span data-stu-id="fdbd4-249">SRSFORDStatus</span></span>               | <span data-ttu-id="fdbd4-250">**3001**</span><span class="sxs-lookup"><span data-stu-id="fdbd4-250">**3001**</span></span>     | <span data-ttu-id="fdbd4-251">イベント\|、実際のソース"SRS App"とイベント Id = = = = の 3001</span><span class="sxs-lookup"><span data-stu-id="fdbd4-251">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="fdbd4-252">モーション センサーのステータス</span><span class="sxs-lookup"><span data-stu-id="fdbd4-252">Motion Sensor status</span></span>             | <span data-ttu-id="fdbd4-253">SRSMotionSensorStatus</span><span class="sxs-lookup"><span data-stu-id="fdbd4-253">SRSMotionSensorStatus</span></span>       | <span data-ttu-id="fdbd4-254">**3001**</span><span class="sxs-lookup"><span data-stu-id="fdbd4-254">**3001**</span></span>     | <span data-ttu-id="fdbd4-255">イベント\|、実際のソース"SRS App"とイベント Id = = = = の 3001</span><span class="sxs-lookup"><span data-stu-id="fdbd4-255">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="fdbd4-256">HDMI 取り込みの状態</span><span class="sxs-lookup"><span data-stu-id="fdbd4-256">HDMI Ingest status</span></span>               | <span data-ttu-id="fdbd4-257">SRSHDMIIngestStatus</span><span class="sxs-lookup"><span data-stu-id="fdbd4-257">SRSHDMIIngestStatus</span></span>         | <span data-ttu-id="fdbd4-258">**3001**</span><span class="sxs-lookup"><span data-stu-id="fdbd4-258">**3001**</span></span>     | <span data-ttu-id="fdbd4-259">イベント\|、実際のソース"SRS App"とイベント Id = = = = の 3001</span><span class="sxs-lookup"><span data-stu-id="fdbd4-259">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |


## <a name="define-the-skype-room-systems-v2-views-in-log-analytics"></a><span data-ttu-id="fdbd4-260">ログ分析で Skype ルーム システム v2 ビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-260">Define the Skype Room Systems v2 views in Log Analytics</span></span>
<span data-ttu-id="fdbd4-261"><a name="Define_Views"> </a></span><span class="sxs-lookup"><span data-stu-id="fdbd4-261"></span></span>

<span data-ttu-id="fdbd4-262">データが収集され、ユーザー設定フィールドがマップされている後、は、Skype ルーム システム v2 のイベントを監視するためのさまざまなタイルを含むダッシュ ボードを開発するのにデザイナーの表示を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-262">After data is collected and custom fields are mapped, you can use View Designer to develop a dashboard containing various tiles to monitor Skype Room Systems v2 events.</span></span> <span data-ttu-id="fdbd4-263">ビュー デザイナーを使用して、次のファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-263">Use View Designer to create the following tiles.</span></span> <span data-ttu-id="fdbd4-264">詳細については、[ログの分析で、ビュー デザイナーを使用してカスタム ビューを作成する](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-264">For more information, see [Create custom views by using View Designer in Log Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)</span></span>

> [!NOTE]
> <span data-ttu-id="fdbd4-265">正常に動作するダッシュ ボードのタイルのこのガイドで前の手順への接続が完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-265">Previous steps in this guide should have been completed for the dashboard tiles to work properly.</span></span>

### <a name="create-a-skype-room-systems-v2-dashboard-by-using-the-import-method"></a><span data-ttu-id="fdbd4-266">インポート メソッドを使用して、Skype ルーム システム v2 のダッシュ ボードを作成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-266">Create a Skype Room Systems v2 dashboard by using the import method</span></span>

<span data-ttu-id="fdbd4-267">Skype ルーム システム v2 のダッシュ ボードにインポートし、デバイスを簡単に監視を開始できます。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-267">You can import an Skype Room Systems v2 dashboard and start monitoring your devices quickly.</span></span> <span data-ttu-id="fdbd4-268">ダッシュ ボードにインポートするのには以下の手順を実行するには。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-268">Take the following steps to import the dashboard:</span></span>

1.  <span data-ttu-id="fdbd4-269">[SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675)ダッシュ ボード ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-269">Get the [SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675) dashboard file.</span></span>
2.  <span data-ttu-id="fdbd4-270">[Microsoft Azure ポータル](https://portal.azure.com)にサインインし、どうなるログの分析に新しいワークスペースを選択します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-270">Sign in to the [Microsoft Azure portal](https://portal.azure.com) and go to Log Analytics and select your workspace.</span></span>
3.  <span data-ttu-id="fdbd4-271">**ビュー デザイナー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-271">Open **View Designer**.</span></span>
4.  <span data-ttu-id="fdbd4-272">**インポート**] を選択し、 **SkypeRoomSystems_v2.omsview**ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-272">Select **Import**, and then select the **SkypeRoomSystems_v2.omsview** file.</span></span>
5.  <span data-ttu-id="fdbd4-273">**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-273">Select **Save**.</span></span>

### <a name="create-a-skype-room-systems-v2-dashboard-manually"></a><span data-ttu-id="fdbd4-274">Skype ルーム システム v2 のダッシュ ボードを手動で作成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-274">Create a Skype Room Systems v2 dashboard manually</span></span>

<span data-ttu-id="fdbd4-275">または、独自のダッシュ ボードを作成し、監視対象のタイルのみを追加できます。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-275">Alternatively, you can create your own dashboard and add only the tiles that you wish to monitor.</span></span>

#### <a name="configure-the-overview-tile"></a><span data-ttu-id="fdbd4-276">概要タイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-276">Configure the Overview Tile</span></span>

1.  <span data-ttu-id="fdbd4-277">**ビュー デザイナー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-277">Open **View Designer**.</span></span>
2.  <span data-ttu-id="fdbd4-278">**概要タイル**を選択し、ギャラリーから**2 つの数値**を選択します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-278">Select **Overview Tile**, and then select **Two numbers** from the gallery.</span></span>
3.  <span data-ttu-id="fdbd4-279">**Skype ルーム システム v2**のタイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-279">Name the tile **Skype Room Systems v2**.</span></span>
4.  <span data-ttu-id="fdbd4-280">**最初のタイル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-280">Define the **First Tile**:</span></span><br>
    <span data-ttu-id="fdbd4-281">**凡例:** 最後の月以内にハートビートを送信するデバイス</span><span class="sxs-lookup"><span data-stu-id="fdbd4-281">**Legend:** Devices that sent a heartbeat at least once within the last month</span></span><br>
    <span data-ttu-id="fdbd4-282">**クエリ:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="fdbd4-282">**Query:** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
5.  <span data-ttu-id="fdbd4-283">**2 つ目のタイル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-283">Define the **Second Tile**:</span></span><br>
    <span data-ttu-id="fdbd4-284">**凡例:** 最後の時間内にハートビートを送信するアクティブなデバイス</span><span class="sxs-lookup"><span data-stu-id="fdbd4-284">**Legend:** Active devices that sent a heartbeat within the last hour</span></span><br>
    <span data-ttu-id="fdbd4-285">**クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="fdbd4-285">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
6.  <span data-ttu-id="fdbd4-286">**適用**を選択します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-286">Select **Apply**.</span></span>

### <a name="create-a-tile-that-displays-active-devices"></a><span data-ttu-id="fdbd4-287">アクティブなデバイスを表示するタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-287">Create a tile that displays active devices</span></span>

1.  <span data-ttu-id="fdbd4-288">タイルを追加する**ダッシュ ボードのビュー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-288">Select **View Dashboard** to start adding your tiles.</span></span>
2.  <span data-ttu-id="fdbd4-289">**_AMP_ リストに番号**を選択して、ギャラリーから</span><span class="sxs-lookup"><span data-stu-id="fdbd4-289">Select **Number & list** from the gallery</span></span>
3.  <span data-ttu-id="fdbd4-290">**全般**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-290">Define the **General** properties:</span></span><br>
    <span data-ttu-id="fdbd4-291">**グループ タイトル:** ハートビートの状態</span><span class="sxs-lookup"><span data-stu-id="fdbd4-291">**Group Title:** Heartbeat Status</span></span><br>
    <span data-ttu-id="fdbd4-292">**新しいグループ:** 選択</span><span class="sxs-lookup"><span data-stu-id="fdbd4-292">**New Group:** Selected</span></span>
4.  <span data-ttu-id="fdbd4-293">**タイル**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-293">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="fdbd4-294">**凡例:** アクティブなデバイス (ハートビートの最後の 20 分間で送信されます)</span><span class="sxs-lookup"><span data-stu-id="fdbd4-294">**Legend:** Active devices (heartbeat sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="fdbd4-295">タイルのクエリ: </span><span class="sxs-lookup"><span data-stu-id="fdbd4-295">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span></span>
5.  <span data-ttu-id="fdbd4-296">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-296">Define the **List** properties:</span></span><br>
    <span data-ttu-id="fdbd4-297">リストのクエリ: </span><span class="sxs-lookup"><span data-stu-id="fdbd4-297">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
6.  <span data-ttu-id="fdbd4-298">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-298">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="fdbd4-299">**名:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="fdbd4-299">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="fdbd4-300">**値:** 最後のハートビート</span><span class="sxs-lookup"><span data-stu-id="fdbd4-300">**Value:** Last Heartbeat</span></span>
7.  <span data-ttu-id="fdbd4-301">**ナビゲーション クエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-301">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="fdbd4-302">**適用**され、し、**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-302">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a><span data-ttu-id="fdbd4-303">接続の問題のあるデバイスを表示するタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-303">Create a tile that displays devices that have connectivity issues</span></span>

1.  <span data-ttu-id="fdbd4-304">ギャラリーから、[ **&] ボックスの一覧の番号**を選択し、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-304">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="fdbd4-305">**全般**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-305">Define the **General** properties:</span></span><br>
    <span data-ttu-id="fdbd4-306">**グループ タイトル:** 空のままに</span><span class="sxs-lookup"><span data-stu-id="fdbd4-306">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="fdbd4-307">**新しいグループ:** 選択されていません。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-307">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="fdbd4-308">**タイル**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-308">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="fdbd4-309">**凡例:** 非アクティブなデバイス (ハートビート メッセージは最後の 20 分間で送信されます)</span><span class="sxs-lookup"><span data-stu-id="fdbd4-309">**Legend:** Inactive Devices (no heartbeat message sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="fdbd4-310">タイルのクエリ: </span><span class="sxs-lookup"><span data-stu-id="fdbd4-310">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span></span>
4.  <span data-ttu-id="fdbd4-311">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-311">Define the **List** properties:</span></span><br>
    <span data-ttu-id="fdbd4-312">リストのクエリ: </span><span class="sxs-lookup"><span data-stu-id="fdbd4-312">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="fdbd4-313">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-313">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="fdbd4-314">**名:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="fdbd4-314">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="fdbd4-315">**値:** 最後のハートビート</span><span class="sxs-lookup"><span data-stu-id="fdbd4-315">**Value:** Last Heartbeat</span></span>
6.  <span data-ttu-id="fdbd4-316">**ナビゲーション クエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-316">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="fdbd4-317">**適用**され、し、**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-317">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a><span data-ttu-id="fdbd4-318">ハードウェア エラーのあるデバイスを表示するタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-318">Create a tile that displays devices that have a hardware error</span></span>

1.  <span data-ttu-id="fdbd4-319">ギャラリーから、[ **&] ボックスの一覧の番号**を選択し、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-319">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="fdbd4-320">**全般**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-320">Define the **General** properties:</span></span><br>
    <span data-ttu-id="fdbd4-321">**グループ タイトル:** ハードウェアのステータス</span><span class="sxs-lookup"><span data-stu-id="fdbd4-321">**Group Title:** Hardware Status</span></span><br>
    <span data-ttu-id="fdbd4-322">**新しいグループ:** 選択</span><span class="sxs-lookup"><span data-stu-id="fdbd4-322">**New Group:** Selected</span></span>
3.  <span data-ttu-id="fdbd4-323">**タイル**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-323">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="fdbd4-324">**凡例:** 最後の 1 時間以内にハードウェア エラーが発生したデバイス</span><span class="sxs-lookup"><span data-stu-id="fdbd4-324">**Legend:** Devices that experienced a hardware error in the last hour</span></span><br>
    <span data-ttu-id="fdbd4-325">タイルのクエリ: </span><span class="sxs-lookup"><span data-stu-id="fdbd4-325">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="fdbd4-326">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-326">Define the **List** properties:</span></span><br>
    <span data-ttu-id="fdbd4-327">リストのクエリ: </span><span class="sxs-lookup"><span data-stu-id="fdbd4-327">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="fdbd4-328">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-328">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="fdbd4-329">**名:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="fdbd4-329">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="fdbd4-330">**値:** 最後のエラー</span><span class="sxs-lookup"><span data-stu-id="fdbd4-330">**Value:** Last Error</span></span>
6.  <span data-ttu-id="fdbd4-331">**ナビゲーション クエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-331">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="fdbd4-332">**適用**され、し、**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-332">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-skype-room-systems-v2-operating-system-versions"></a><span data-ttu-id="fdbd4-333">Skype ルーム システム v2 バージョンのオペレーティング システムを表示するタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-333">Create a tile that displays Skype Room Systems v2 Operating System versions</span></span>

1.  <span data-ttu-id="fdbd4-334">ギャラリーから、**ドーナツ & リスト**を選択し、新たにコピーします。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-334">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="fdbd4-335">**全般**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-335">Define the **General** properties:</span></span><br>
    <span data-ttu-id="fdbd4-336">**グループ タイトル:** オペレーティング システムの詳細</span><span class="sxs-lookup"><span data-stu-id="fdbd4-336">**Group Title:** Operating System details</span></span><br>
    <span data-ttu-id="fdbd4-337">**新しいグループ:** 選択</span><span class="sxs-lookup"><span data-stu-id="fdbd4-337">**New Group:** Selected</span></span>
3.  <span data-ttu-id="fdbd4-338">**ヘッダー**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-338">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="fdbd4-339">**タイトル:** オペレーティング システムのバージョン</span><span class="sxs-lookup"><span data-stu-id="fdbd4-339">**Title:** Operating System versions</span></span><br>
    <span data-ttu-id="fdbd4-340">**サブタイトル:** 特定の OS バージョンを実行しているデバイス</span><span class="sxs-lookup"><span data-stu-id="fdbd4-340">**Subtitle:** Devices running specific OS versions</span></span>
4.  <span data-ttu-id="fdbd4-341">**ドーナツ**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-341">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="fdbd4-342">**クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span><span class="sxs-lookup"><span data-stu-id="fdbd4-342">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span></span><br>
    <span data-ttu-id="fdbd4-343">**テキストを中央揃え:** デバイス</span><span class="sxs-lookup"><span data-stu-id="fdbd4-343">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="fdbd4-344">**操作:** 合計</span><span class="sxs-lookup"><span data-stu-id="fdbd4-344">**Operation:** Sum</span></span>
5.  <span data-ttu-id="fdbd4-345">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-345">Define the **List** properties.</span></span><br>
    <span data-ttu-id="fdbd4-346">リストのクエリ: </span><span class="sxs-lookup"><span data-stu-id="fdbd4-346">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="fdbd4-347">**グラフを非表示にする:** 選択</span><span class="sxs-lookup"><span data-stu-id="fdbd4-347">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="fdbd4-348">**スパーク ラインを有効にする:** 選択されていません。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-348">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="fdbd4-349">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-349">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="fdbd4-350">**名:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="fdbd4-350">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="fdbd4-351">**値:** 空のままに</span><span class="sxs-lookup"><span data-stu-id="fdbd4-351">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="fdbd4-352">**ナビゲーション クエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-352">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="fdbd4-353">**適用**し、[**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-353">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-skype-room-systems-v2-application-versions"></a><span data-ttu-id="fdbd4-354">Skype ルーム システム v2 のアプリケーションのバージョンを表示するタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-354">Create a tile that displays Skype Room Systems v2 application versions</span></span>

1.  <span data-ttu-id="fdbd4-355">ギャラリーから、**ドーナツ & リスト**を選択し、新たにコピーします。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-355">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="fdbd4-356">**全般**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-356">Define the **General** properties:</span></span><br>
    <span data-ttu-id="fdbd4-357">**グループ タイトル:** Skype ルーム システム v2 のアプリケーションの詳細</span><span class="sxs-lookup"><span data-stu-id="fdbd4-357">**Group Title:** Skype Room Systems v2 application details</span></span><br>
    <span data-ttu-id="fdbd4-358">**新しいグループ:** 選択</span><span class="sxs-lookup"><span data-stu-id="fdbd4-358">**New Group:** Selected</span></span>
3.  <span data-ttu-id="fdbd4-359">**ヘッダー**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-359">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="fdbd4-360">**タイトル:** アプリケーションのバージョン</span><span class="sxs-lookup"><span data-stu-id="fdbd4-360">**Title:** Application versions</span></span><br>
    <span data-ttu-id="fdbd4-361">**サブタイトル:** 特定のアプリケーションのバージョンを実行しているデバイス</span><span class="sxs-lookup"><span data-stu-id="fdbd4-361">**Subtitle:** Devices running specific application versions</span></span>
4.  <span data-ttu-id="fdbd4-362">**ドーナツ**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-362">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="fdbd4-363">**クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span><span class="sxs-lookup"><span data-stu-id="fdbd4-363">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span></span><br>
    <span data-ttu-id="fdbd4-364">**テキストを中央揃え:** デバイス</span><span class="sxs-lookup"><span data-stu-id="fdbd4-364">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="fdbd4-365">**操作:** 合計</span><span class="sxs-lookup"><span data-stu-id="fdbd4-365">**Operation:** Sum</span></span>
5.  <span data-ttu-id="fdbd4-366">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-366">Define the **List** properties.</span></span><br>
    <span data-ttu-id="fdbd4-367">リストのクエリ: </span><span class="sxs-lookup"><span data-stu-id="fdbd4-367">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="fdbd4-368">**グラフを非表示にする:** 選択</span><span class="sxs-lookup"><span data-stu-id="fdbd4-368">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="fdbd4-369">**スパーク ラインを有効にする:** 選択されていません。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-369">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="fdbd4-370">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-370">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="fdbd4-371">**名:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="fdbd4-371">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="fdbd4-372">**値:** 空のままに</span><span class="sxs-lookup"><span data-stu-id="fdbd4-372">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="fdbd4-373">**ナビゲーション クエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-373">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="fdbd4-374">**適用**し、[**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-374">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a><span data-ttu-id="fdbd4-375">アプリケーション エラーのあるデバイスを表示するタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-375">Create a tile that displays devices that have an application error</span></span>

1.  <span data-ttu-id="fdbd4-376">ギャラリーから、[ **&] ボックスの一覧の番号**を選択し、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-376">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="fdbd4-377">**全般**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-377">Define the **General** properties.</span></span><br>
    <span data-ttu-id="fdbd4-378">**グループ タイトル:** 空のままに</span><span class="sxs-lookup"><span data-stu-id="fdbd4-378">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="fdbd4-379">**新しいグループ:** 選択されていません。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-379">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="fdbd4-380">**タイル**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-380">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="fdbd4-381">**凡例:** 最後の時間でアプリケーション エラーが発生したデバイス</span><span class="sxs-lookup"><span data-stu-id="fdbd4-381">**Legend:** Devices that experienced an application error in the last hour</span></span><br>
    <span data-ttu-id="fdbd4-382">タイルのクエリ: </span><span class="sxs-lookup"><span data-stu-id="fdbd4-382">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="fdbd4-383">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-383">Define the **List** properties.</span></span><br>
    <span data-ttu-id="fdbd4-384">リストのクエリ: </span><span class="sxs-lookup"><span data-stu-id="fdbd4-384">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="fdbd4-385">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-385">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="fdbd4-386">**名:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="fdbd4-386">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="fdbd4-387">**値:** 最後のエラー</span><span class="sxs-lookup"><span data-stu-id="fdbd4-387">**Value:** Last Error</span></span>
6.  <span data-ttu-id="fdbd4-388">**ナビゲーション クエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-388">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="fdbd4-389">**適用**し、[**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-389">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a><span data-ttu-id="fdbd4-390">再起動されているデバイスを表示するタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-390">Create a tile that displays devices that have been restarted</span></span>

1.  <span data-ttu-id="fdbd4-391">ギャラリーから、[ **&] ボックスの一覧の番号**を選択し、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-391">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="fdbd4-392">**全般**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-392">Define the **General** properties.</span></span><br>
    <span data-ttu-id="fdbd4-393">**グループ タイトル:** 空のままに</span><span class="sxs-lookup"><span data-stu-id="fdbd4-393">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="fdbd4-394">**新しいグループ:** 選択されていません。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-394">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="fdbd4-395">**タイル**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-395">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="fdbd4-396">**凡例:** デバイスのアプリケーションの再起動では、最後の 24 時間、および再起動の回数</span><span class="sxs-lookup"><span data-stu-id="fdbd4-396">**Legend:** Devices where the application was restarted in the last 24 hours, and number of restarts</span></span><br>
    <span data-ttu-id="fdbd4-397">タイルのクエリ: </span><span class="sxs-lookup"><span data-stu-id="fdbd4-397">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="fdbd4-398">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-398">Define the **List** properties.</span></span><br>
    <span data-ttu-id="fdbd4-399">リストのクエリ: </span><span class="sxs-lookup"><span data-stu-id="fdbd4-399">**List Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span></span>
5.  <span data-ttu-id="fdbd4-400">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-400">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="fdbd4-401">**名:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="fdbd4-401">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="fdbd4-402">**値:** 再起動の回数</span><span class="sxs-lookup"><span data-stu-id="fdbd4-402">**Value:** Number of Restarts</span></span>
6.  <span data-ttu-id="fdbd4-403">**ナビゲーション クエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-403">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="fdbd4-404">**適用**し、[**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-404">Select **Apply** and then **Close**.</span></span>
8.  <span data-ttu-id="fdbd4-405">ダッシュ ボードを保存する**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-405">Select **Save** to save your dashboard.</span></span>

<span data-ttu-id="fdbd4-406">ここで、ビューの作成が完了しました。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-406">Now you’ve completed creating your views.</span></span>

## <a name="configure-alerts-in-azure-monitor"></a><span data-ttu-id="fdbd4-407">Azure のモニターで警告を構成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-407">Configure Alerts in Azure Monitor</span></span>
<span data-ttu-id="fdbd4-408"><a name="Alerts"> </a></span><span class="sxs-lookup"><span data-stu-id="fdbd4-408"></span></span>

<span data-ttu-id="fdbd4-409">Azure のモニターには、Skype ルーム システム v2 のコンソールに問題が発生した場合、管理者に通知するアラートを発生できます。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-409">Azure Monitor can raise alerts to notify the administrators, when a Skype Room Systems v2 console encounters an issue.</span></span>

<span data-ttu-id="fdbd4-410">Azure のモニターには、定期的にスケジュールされたログの検索を実行する組み込みの警告メカニズムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-410">Azure Monitor includes a built-in alerting mechanism that runs through scheduled log searches at regular intervals.</span></span> <span data-ttu-id="fdbd4-411">ログの検索の結果には、いくつか特定の条件が一致する場合は、アラートのレコードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-411">If the results of the log search match some particular criteria, an alert record is created.</span></span>

<span data-ttu-id="fdbd4-412">自動的に、ルールでは、事前に警告を通知または別のプロセスを起動する 1 つまたは複数のアクションを実行できるし。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-412">The rule can then automatically run one or more actions to proactively notify you of the alert or invoke another process.</span></span> <span data-ttu-id="fdbd4-413">アラートを使用可能なオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-413">The possible options with alerts are:</span></span>
-   <span data-ttu-id="fdbd4-414">電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-414">Sending an email</span></span>
-   <span data-ttu-id="fdbd4-415">HTTP POST 要求を外部プロセスを起動します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-415">Invoking an external process through an HTTP POST request</span></span>
-   <span data-ttu-id="fdbd4-416">Runbook を Azure のオートメーション サービスの開始</span><span class="sxs-lookup"><span data-stu-id="fdbd4-416">Starting a runbook in Azure Automation service</span></span>

<span data-ttu-id="fdbd4-417">Azure モニターの警告に関する詳細については、 [Azure のモニターで警告をログに記録](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-417">See [Log alerts in Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) to learn more about the alerts in Azure Monitor.</span></span>

> [!NOTE]
> <span data-ttu-id="fdbd4-418">次の例は、Skype ルーム システム v2 デバイスは、ハードウェアまたはアプリケーション エラーを生成する場合に電子メール警告を送信します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-418">The following examples send email alerts when a Skype Room Systems v2 device generates a hardware or an application error.</span></span>

### <a name="configure-an-email-alert-for-skype-room-systems-v2-hardware-issues"></a><span data-ttu-id="fdbd4-419">Skype ルーム システム v2 のハードウェアの問題に関する電子メール通知を構成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-419">Configure an email alert for Skype Room Systems v2 hardware issues</span></span>

<span data-ttu-id="fdbd4-420">最後の時間内でハードウェアの問題が発生している Skype ルーム システム v2 のデバイスを確認する警告ルールを構成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-420">Configure an alert rule that checks for Skype Room Systems v2 devices that have encountered hardware issues within the last hour.</span></span>
1.  <span data-ttu-id="fdbd4-421">[Microsoft Azure ポータル](https://portal.azure.com)にサインインし、どうなるログの分析に新しいワークスペースを選択します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-421">Sign in to the [Microsoft Azure portal](https://portal.azure.com) and go to Log Analytics and select your workspace.</span></span>

2. <span data-ttu-id="fdbd4-422">ログの分析機能のワークスペースに移動し**アラート**を選択し、**新しいアラート ルール**を選択し、</span><span class="sxs-lookup"><span data-stu-id="fdbd4-422">Navigate to your Log Analytics workspace and select **Alerts** and then select **New alert rule**</span></span>

3. <span data-ttu-id="fdbd4-423">[**条件の追加**し、[**カスタム ログの検索**</span><span class="sxs-lookup"><span data-stu-id="fdbd4-423">Select **Add condition** and then **Custom log search**</span></span>

4.  <span data-ttu-id="fdbd4-424">検索クエリのテキスト ボックスに次のクエリを入力します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-424">Enter the following query to the Search query text box.</span></span><br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  <span data-ttu-id="fdbd4-425">警告のロジックの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-425">Configure the Alert logic settings:</span></span><br>
    <span data-ttu-id="fdbd4-426">**に基づく:** 結果の数</span><span class="sxs-lookup"><span data-stu-id="fdbd4-426">**Based on:** Number of results</span></span><br>
    <span data-ttu-id="fdbd4-427">**条件:** 大きいし、</span><span class="sxs-lookup"><span data-stu-id="fdbd4-427">**Condition:** Greater then</span></span><br>
    <span data-ttu-id="fdbd4-428">**しきい値:** 0</span><span class="sxs-lookup"><span data-stu-id="fdbd4-428">**Treshold:** 0</span></span><br>

6. <span data-ttu-id="fdbd4-429">評価の設定を構成し、**実行**を選択します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-429">Configure Evaluation settings and select **Done**:</span></span> <br>
    <span data-ttu-id="fdbd4-430">**時間 (分単位):** 60</span><span class="sxs-lookup"><span data-stu-id="fdbd4-430">**Period (in minutes):** 60</span></span><br>
    <span data-ttu-id="fdbd4-431">**頻度 (分):** 60</span><span class="sxs-lookup"><span data-stu-id="fdbd4-431">**Frequency (in minutes):** 60</span></span><br>

7. <span data-ttu-id="fdbd4-432">アクションのグループを構成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-432">Configure action groups:</span></span>
    1.  <span data-ttu-id="fdbd4-433">**新規作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-433">Select **Create New**</span></span>
    2.  <span data-ttu-id="fdbd4-434">*アクション グループの名前*と*短い名前*のフィールドに適切な名前を提供します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-434">Provide suitable names for the *Action group name* and *Short Name* fields.</span></span>
    3.  <span data-ttu-id="fdbd4-435">固有の*アクション名*を指定、**電子メール、SMS、プッシュ/音声**を選択し、[**詳細の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-435">Specify a unique *Action Name* and select **Email/SMS/Push/Voice**, and then select **Edit details**.</span></span>
    4.  <span data-ttu-id="fdbd4-436">電子メール] チェック ボックスを選択しのユーザーまたはグループのアラートを受信する電子メール アドレスを提供します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-436">Select the Email checkbox and provide the email address of the person or group that will recieve the alerts.</span></span>
    5.  <span data-ttu-id="fdbd4-437">SMS、音声通話、またはその両方を使用して通知を受け取るため、電話番号を入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-437">You may also provide your phone number to get notified with SMS, a voice call or both.</span></span>
    6. <span data-ttu-id="fdbd4-438">**[Ok]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-438">Select **OK**.</span></span>

8. <span data-ttu-id="fdbd4-439">**アクションをカスタマイズする**警告の電子メールの件名行をオーバーライドする場合です。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-439">**Customize Actions** if you like to override the subject line of the alert emails.</span></span>

9. <span data-ttu-id="fdbd4-440">ルールの名前と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-440">Specify a rule name and description.</span></span><br>
    <span data-ttu-id="fdbd4-441">**ルールの名前:** Skype ルーム システム v2 ハードウェア障害の警告</span><span class="sxs-lookup"><span data-stu-id="fdbd4-441">**Rule Name:** Skype Room Systems v2 Hardware Failure Alert</span></span><br>
    <span data-ttu-id="fdbd4-442">**説明:** 最後の時間内でハードウェアの問題が発生したデバイスの一覧</span><span class="sxs-lookup"><span data-stu-id="fdbd4-442">**Description:** List of devices that encountered a hardware issue within the last hour</span></span><br>

10. <span data-ttu-id="fdbd4-443">目的の重要度を選択し、ルールが有効になっているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-443">Select the intended severity and make sure the rule is enabled.</span></span>

11. <span data-ttu-id="fdbd4-444">**警告ルールを作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-444">Select **Create alert rule**.</span></span>

### <a name="configure-an-email-alert-for-skype-room-systems-v2-application-issues"></a><span data-ttu-id="fdbd4-445">Skype ルーム システム v2 のアプリケーションの問題に関する電子メール通知を構成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-445">Configure an email alert for Skype Room Systems v2 application issues</span></span>

<span data-ttu-id="fdbd4-446">同じ手順を繰り返しますが、最後の時間内でアプリケーションの問題が発生しているデバイスの一覧表示するには、次のクエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-446">Repeat the same procedure but use the following query to list devices that have encountered application issues within the last hour.</span></span>

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

<span data-ttu-id="fdbd4-447">警告の定義を完了しました。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-447">Now you’ve completed defining alerts.</span></span> <span data-ttu-id="fdbd4-448">上記の例を使用して、別のアラートを定義できます。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-448">You can define additional alerts by using the examples above.</span></span>

<span data-ttu-id="fdbd4-449">アラートが生成されると、最後の時間内で問題が発生しているデバイスを一覧表示する電子メールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-449">When an alert is generated, you’ll get an email that lists the devices that encountered an issue within the last hour.</span></span>

<span data-ttu-id="fdbd4-450">![サンプル Azure モニター警告の電子メール](../../media/Deploy-Azure-Monitor-6.png "サンプル Azure モニター警告の電子メール")</span><span class="sxs-lookup"><span data-stu-id="fdbd4-450">![Sample Azure Monitor alert email](../../media/Deploy-Azure-Monitor-6.png "Sample Azure Monitor alert email")</span></span>

## <a name="configure-all-devices-for-azure-monitoring"></a><span data-ttu-id="fdbd4-451">Azure を監視するためのすべてのデバイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-451">Configure all devices for Azure Monitoring</span></span>
<span data-ttu-id="fdbd4-452"><a name="configure_all_devices"></a>ダッシュ ボード、アラートを構成した後は、設定および監視、展開を完了するすべての Skype ルーム システム v2 デバイスで Microsoft の監視エージェントを構成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-452"><a name="configure_all_devices"> </a> After the dashboards and alerts are configured, you can set up and configure Microsoft Monitoring agent on all Skype Room Systems v2 devices to complete your monitoring deployment.</span></span>

<span data-ttu-id="fdbd4-453">インストールし、デバイスごとに、Microsoft の監視エージェントを手動で構成できますが、既存のソフトウェア展開ツールおよび方法を活用するを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-453">Although you can install and configure the Microsoft Monitoring agent manually on each device, we highly recommend you leverage existing software deployment tools and methods.</span></span>

<span data-ttu-id="fdbd4-454">最初に、Skype ルーム システム v2 のデバイスを作成する場合は、ビルド プロセスの一環としてマイクロソフトの監視エージェントのセットアップと構成の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-454">If you’re building your Skype Room Systems v2 devices for the first time, you might want to include the Microsoft Monitoring agent setup and configuration steps as part of your build process.</span></span> <span data-ttu-id="fdbd4-455">詳細については、[コマンド ・ ラインを使用してエージェントのインストール](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-455">For more information, see [Install the agent using the command line](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).</span></span>

### <a name="deploying-microsoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a><span data-ttu-id="fdbd4-456">グループ ポリシー オブジェクト (GPO) を使用して、Microsoft の監視エージェントを展開します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-456">Deploying Microsoft Monitoring agent by using a Group Policy Object (GPO)</span></span>

<span data-ttu-id="fdbd4-457">Azure の監視を実装する前に、Skype ルーム システム v2 デバイス既に展開されている場合を設定し、Active Directory グループ ポリシー オブジェクトを使用してエージェントを構成する提供されたスクリプトを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-457">If you already deployed your Skype Room Systems v2 devices before you implement Azure Monitoring, you can use the provided script to set up and configure the agents by using Active Directory group policy objects.</span></span>

1.  <span data-ttu-id="fdbd4-458">共有のネットワーク パスを作成し、**ドメイン コンピューター**グループに読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-458">Create a shared network path and grant read access to **Domain Computers** group.</span></span>

2.  <span data-ttu-id="fdbd4-459">監視エージェントの Windows からの 64 ビット バージョンをダウンロードします。<https://go.microsoft.com/fwlink/?LinkID=517476></span><span class="sxs-lookup"><span data-stu-id="fdbd4-459">Download the 64-bit version of the Microsoft Monitoring Agent for Windows from <https://go.microsoft.com/fwlink/?LinkID=517476></span></span>

3.  <span data-ttu-id="fdbd4-460">ネットワーク共有には、セットアップ パッケージの内容を抽出します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-460">Extract the contents of the setup package into the network share.</span></span>
    1.  <span data-ttu-id="fdbd4-461">コマンド プロンプト ウィンドウを開き、 **MMASetup AMD64.exe/c**を実行し、</span><span class="sxs-lookup"><span data-stu-id="fdbd4-461">Open a Command Prompt window, and then execute **MMASetup-AMD64.exe /c**</span></span>
    2.  <span data-ttu-id="fdbd4-462">作成した共有を指定し、コンテンツを抽出します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-462">Specify the share you just created, and extract the content.</span></span>

4.  <span data-ttu-id="fdbd4-463">新しいグループ ポリシー オブジェクトを作成し、Skype ルーム システム v2 のコンピューター アカウントが格納されている組織単位に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-463">Create a new Group Policy Object and assign it to the organizational unit where Skype Room Systems v2 machine accounts are located.</span></span>

5.  <span data-ttu-id="fdbd4-464">PowerShell 実行ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-464">Configure PowerShell execution policy:</span></span>
    1.  <span data-ttu-id="fdbd4-465">新しく作成したグループ ポリシー オブジェクトを編集し、コンピューターの構成に移動\\ポリシー\\管理用テンプレート\\Windows コンポーネントの\\Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fdbd4-465">Edit the newly created Group Policy Object and navigate to Computer Configuration \\ Policies \\ Administrative Templates \\ Windows Components \\ Windows PowerShell</span></span>
    2.  <span data-ttu-id="fdbd4-466">**スクリプトの実行を有効に**するを有効にして、**実行ポリシー**を**ローカルのスクリプトを許可する**に設定します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-466">Enable the **Turn on Script Execution** and set **Execution Policy** to **Allow Local Scripts**.</span></span>

6.  <span data-ttu-id="fdbd4-467">スタートアップ ・ スクリプトを構成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-467">Configure the startup script:</span></span>
    1.  <span data-ttu-id="fdbd4-468">次のスクリプトをコピーし、インストールを MMAgent.ps1 として保存します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-468">Copy the following script and save it as Install-MMAgent.ps1.</span></span>
    2.  <span data-ttu-id="fdbd4-469">構成に合わせて、WorkspaceId、WorkspaceKey、および SetupPath のパラメーターを変更します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-469">Modify WorkspaceId, WorkspaceKey, and SetupPath parameters to match your configuration.</span></span>
    3.  <span data-ttu-id="fdbd4-470">同じグループ ポリシー オブジェクトを編集し、コンピューターの構成に移動\\ポリシー \\ Windows の設定\\スクリプト (スタートアップ/シャット ダウン)</span><span class="sxs-lookup"><span data-stu-id="fdbd4-470">Edit the same Group Policy Object and navigate to Computer Configuration \\ Policies \\ Windows Settings \\ Scripts (Startup/Shutdown)</span></span>
    4.  <span data-ttu-id="fdbd4-471">ダブルクリックして**起動**を選択し、 **PowerShell スクリプト**します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-471">Double-click to select **Startup**, and then select **PowerShell Scripts**.</span></span>
    5.  <span data-ttu-id="fdbd4-472">**ファイルを表示**] を選択し、そのフォルダーに**インストールを MMAgent.ps1**ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-472">Select **Show Files**, and then copy the **Install-MMAgent.ps1** file to that folder.</span></span>
    6.  <span data-ttu-id="fdbd4-473">**追加**して、**参照**を選択します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-473">Select **Add**, and then **Browse**.</span></span>
    7.  <span data-ttu-id="fdbd4-474">コピーした ps1 スクリプトを選択します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-474">Select the ps1 script you just copied.</span></span>

7.  <span data-ttu-id="fdbd4-475">Skype ルーム システム v2 のデバイスがインストールされ、2 つ目の再起動で、Microsoft の監視エージェントを構成します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-475">Skype Room Systems v2 devices should install and configure the Microsoft Monitoring agent with the second reboot.</span></span>

```
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
> <span data-ttu-id="fdbd4-476">エージェントを再構成して、別のワークスペースに移動する、または最初のインストール後にプロキシの設定を変更する必要がある場合は、[エージェント ログの分析機能を維持して管理](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage)の資料を参照できます。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-476">You can refer to the article [Managing and maintaining the Log Analytics agent](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) when you need to reconfigure an agent, move it to a different workspace, or modify proxy settings after the initial installation.</span></span>

## <a name="additional-solutions"></a><span data-ttu-id="fdbd4-477">他のソリューション</span><span class="sxs-lookup"><span data-stu-id="fdbd4-477">Additional Solutions</span></span>
<span data-ttu-id="fdbd4-478"><a name="Solutions"> </a></span><span class="sxs-lookup"><span data-stu-id="fdbd4-478"></span></span>

<span data-ttu-id="fdbd4-479">Azure のモニターでは、お客様の環境を監視するため、[ソリューション ギャラリー](https://docs.microsoft.com/azure/azure-monitor/insights/solutions)からの組み込み管理ソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-479">Azure Monitor provides built-in management solutions through its [solution gallery](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) to further help you monitor your environment.</span></span> <span data-ttu-id="fdbd4-480">ワークスペースには、[警告の管理](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution)と[ログ分析エージェント稼働状態の Azure](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth)ソリューションを追加することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-480">We highly recommend that you add [Alert Management](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) and [Azure Log Analytics Agent Health](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) solutions to your workspace as well.</span></span>

> [!NOTE]
> <span data-ttu-id="fdbd4-481">エージェントの正常性のソリューションを使用して、環境内の古いか破損している Microsoft の監視エージェントを特定でき、アラート管理ソリューションには、一定期間内に発生して、アラートに関する詳細情報が用意されています。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-481">The Agent Health solution can help you identify outdated or broken Microsoft Monitoring agents within your environment, and the Alert Management solution provides details about the alerts that have been raised within a given period.</span></span>

## <a name="see-also"></a><span data-ttu-id="fdbd4-482">関連項目</span><span class="sxs-lookup"><span data-stu-id="fdbd4-482">See also</span></span>

[<span data-ttu-id="fdbd4-483">Azure のモニターを使用して Skype ルーム システム v2 の管理を計画します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-483">Plan Skype Room Systems v2 management with Azure Monitor</span></span>](../../plan-your-deployment/clients-and-devices/azure-monitor.md)

[<span data-ttu-id="fdbd4-484">Azure のモニターを使用して Skype ルーム システム v2 のデバイスを管理します。</span><span class="sxs-lookup"><span data-stu-id="fdbd4-484">Manage Skype Room Systems v2 devices with Azure Monitor</span></span>](../../manage/skype-room-systems-v2/azure-monitor.md)