---
title: Azure のモニターを使用して Microsoft チームの会議室の管理を展開します。
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
- M365-voice
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: この資料では、Azure のモニターを使用して、統合されたエンド ・ ツー ・ エンドの方法でマイクロソフト チームの会議室のデバイスの管理を展開する方法について説明します。
ms.openlocfilehash: c9808e03a9f72ce016e4e16b06a277377832122b
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362914"
---
# <a name="deploy-microsoft-teams-rooms-management-with-azure-monitor"></a><span data-ttu-id="3cf6a-103">Azure のモニターを使用して Microsoft チームの会議室の管理を展開します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-103">Deploy Microsoft Teams Rooms management with Azure Monitor</span></span>

<span data-ttu-id="3cf6a-104">この資料を設定し、Azure のモニターを使用して Microsoft チームの会議室のデバイスの統合された、エンド ・ ツー ・ エンドの管理を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-104">This article discusses how to set up and deploy integrated, end-to-end management of Microsoft Teams Rooms devices by using Azure Monitor.</span></span>

<span data-ttu-id="3cf6a-105">基本的な遠隔測定を提供する Azure モニター内でのログの分析を構成することができ、警告するのに役立つマイクロソフト チームの会議室の会議室のデバイスを管理します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-105">You can configure Log Analytics within Azure Monitor to provide basic telemetry and alerts that will help you manage Microsoft Teams Rooms meeting room devices.</span></span> <span data-ttu-id="3cf6a-106">管理ソリューションが完成に近づくにつれて、追加のデータとデバイスの可用性とパフォーマンスの詳細なビューを作成する管理機能を導入することができます。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-106">As your management solution matures, you might decide to deploy additional data and management capabilities to create a more detailed view of device availability and performance.</span></span>

<span data-ttu-id="3cf6a-107">によって、このガイドに従うと、デバイスの可用性、アプリケーションとハードウェアの健康状態、およびマイクロソフト チームの会議室のアプリケーションおよびオペレーティング システムのバージョンの配布のレポート、詳細なステータスを取得するのに例を次のようなダッシュ ボードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-107">By following this guide, you can use a dashboard like the following example to get detailed status reporting for device availability, application and hardware health, and Microsoft Teams Rooms application and operating system version distribution.</span></span>

<span data-ttu-id="3cf6a-108">![マイクロソフト チームの会議室のログ分析のサンプルの表示](../media/Deploy-Azure-Monitor-1.png "マイクロソフト チームの会議室のログ分析のサンプルの表示")</span><span class="sxs-lookup"><span data-stu-id="3cf6a-108">![Sample Log Analytics view for Microsoft Teams Rooms](../media/Deploy-Azure-Monitor-1.png "Sample Log Analytics view for Microsoft Teams Rooms")</span></span>

<span data-ttu-id="3cf6a-109">高いレベルでは、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-109">At a high level, you need to perform the following tasks:</span></span>


1.  [<span data-ttu-id="3cf6a-110">ログ分析の構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-110">Validate Log Analytics configuration</span></span>](azure-monitor-deploy.md#validate_LogAnalytics)
2.  [<span data-ttu-id="3cf6a-111">管理セットアップのログ分析機能のテスト デバイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-111">Configure test devices for Log Analytics management setup</span></span>](azure-monitor-deploy.md#configure_test_devices)
3.  [<span data-ttu-id="3cf6a-112">カスタム フィールドをマップする</span><span class="sxs-lookup"><span data-stu-id="3cf6a-112">Map custom fields</span></span>](azure-monitor-deploy.md#Custom_fields)
4.  [<span data-ttu-id="3cf6a-113">ログ分析のマイクロソフト チーム室ビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-113">Define the Microsoft Teams Rooms views in Log Analytics</span></span>](azure-monitor-deploy.md#Define_Views)
5.  [<span data-ttu-id="3cf6a-114">警告を定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-114">Define alerts</span></span>](azure-monitor-deploy.md#Alerts)
6.  [<span data-ttu-id="3cf6a-115">監視のすべてのデバイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-115">Configure all devices for Monitoring</span></span>](azure-monitor-deploy.md#configure_all_devices)
7.  [<span data-ttu-id="3cf6a-116">Azure のモニターの追加のソリューションを構成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-116">Configure additional Azure Monitor solutions</span></span>](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> <span data-ttu-id="3cf6a-117">マイクロソフトのすべてのチームへのエージェントの展開を開始する前に実行する必要があるいくつかのマイクロソフト チーム ルーム – 特定の手順はまだありますが、最小限の構成では、Azure 監視ログ分析機能は、Windows オペレーティング システムを実行するコンピューターを監視できます、ルームのデバイスです。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-117">Although with minimal configuration, Azure Monitor Log Analytics can monitor a computer running a Windows operating system, there are still some Microsoft Teams Rooms–specific steps that you need to take before you start deploying agents to all Microsoft Teams Rooms devices.</span></span>
> <span data-ttu-id="3cf6a-118">したがって、コントロールのセットアップと構成の正しい順序ですべての構成手順を実行するを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-118">Therefore, we highly recommend you perform all configuration steps in the right order for a controlled setup and configuration.</span></span> <span data-ttu-id="3cf6a-119">最終結果の品質は、初期構成の品質に非常に依存します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-119">The quality of the end result very much depends on the quality of the initial configuration.</span></span>

## <a name="validate-log-analytics-configuration"></a><span data-ttu-id="3cf6a-120">ログ分析の構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-120">Validate Log Analytics configuration</span></span>
<span data-ttu-id="3cf6a-121"><a name="validate_LogAnalytics"> </a></span><span class="sxs-lookup"><span data-stu-id="3cf6a-121"></span></span>

<span data-ttu-id="3cf6a-122">マイクロソフト チームの会議室のデバイスからのログの収集を開始するログ分析機能のワークスペースが必要です。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-122">You need to have a Log Analytics workspace to start collecting logs from Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="3cf6a-123">ワークスペースは、独自のデータ リポジトリ、データ ソース、およびソリューションの一意なログ分析環境です。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-123">A workspace is a unique Log Analytics environment with its own data repository, data sources, and solutions.</span></span> <span data-ttu-id="3cf6a-124">既に既存のログ分析機能のワークスペースがある場合、か、マイクロソフト チームの会議室の展開を監視するために使用可能性があります代わりに、ワークスペースを作成できます、専用ログ分析特定のニーズを監視、マイクロソフト チームの会議室にします。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-124">If you already have an existing Log Analytics workspace, you might use it to monitor your Microsoft Teams Rooms deployment or alternatively, you can create a dedicated Log Analytics workspace specific to your Microsoft Teams Rooms monitoring needs.</span></span>

<span data-ttu-id="3cf6a-125">[Azure ポータルでのログの分析機能のワークスペースを作成する](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)この資料の指示に従って、新しいログの分析機能のワークスペースを作成する場合は、</span><span class="sxs-lookup"><span data-stu-id="3cf6a-125">If you need to create a new Log Analytics workspace, follow the instructions in the article [Create a Log Analytics workspace in the Azure portal](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)</span></span>

> [!NOTE]
> <span data-ttu-id="3cf6a-126">ログ分析機能を使用して、Azure のモニターでは、Azure サブスクリプションはアクティブにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-126">To use Log Analytics with Azure Monitor, you need to have an active Azure subscription.</span></span> <span data-ttu-id="3cf6a-127">Azure サブスクリプションをお持ちでない場合は、開始点として[無料の試用版サブスクリプション](https://azure.microsoft.com/free)を作成できます。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-127">If you don’t have an Azure subscription, you can create [a free trial subscription](https://azure.microsoft.com/free) as a starting point.</span></span>

### <a name="configure-log-analytics-to-collect-microsoft-teams-rooms-event-logs"></a><span data-ttu-id="3cf6a-128">マイクロソフト チームの会議室のイベント ログを収集するログの分析を構成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-128">Configure Log Analytics to collect Microsoft Teams Rooms event logs</span></span>

<span data-ttu-id="3cf6a-129">のみ、ログ分析機能は、設定で指定されている Windows のイベント ログからイベントを収集します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-129">Log Analytics only collects events from the Windows event logs that are specified in the settings.</span></span> <span data-ttu-id="3cf6a-130">各ログには、選択した重大度のレベルのイベントのみが収集されます。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-130">For each log, only the events with the selected severities are collected.</span></span>

<span data-ttu-id="3cf6a-131">マイクロソフト チームの会議室のデバイスとアプリケーションの状態を監視するために必要なログを収集するログの分析を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-131">You need to configure Log Analytics to collect the logs required to monitor Microsoft Teams Rooms device and application status.</span></span> <span data-ttu-id="3cf6a-132">マイクロソフト チームの会議室のデバイスでは、 **Skype の部屋のシステム**イベント ログを使用します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-132">Microsoft Teams Rooms devices use the **Skype Room System** event log.</span></span>

<span data-ttu-id="3cf6a-133">マイクロソフト チームの会議室のイベントを収集するログの分析を構成するには、 [Azure のモニターでは、Windows イベント ログ データ ソース](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-133">To configure Log Analytics to collect the Microsoft Teams Rooms events, see [Windows event log data sources in Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)</span></span>

<span data-ttu-id="3cf6a-134">![イベント ログの設定](../media/Deploy-Azure-Monitor-2.png "イベント ログの設定")</span><span class="sxs-lookup"><span data-stu-id="3cf6a-134">![Event log settings](../media/Deploy-Azure-Monitor-2.png "Event log settings")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3cf6a-135">Windows イベント ログ設定を構成および**Skype ルーム システム**を入力して、イベント ログの名前と、**エラー**、**警告**、および**情報**のチェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-135">Configure Windows Event Log settings and enter **Skype Room System** as event log name, and then select the **Error**, **Warning**, and **Information** check boxes.</span></span>

## <a name="configure-test-devices-for-azure-monitoring"></a><span data-ttu-id="3cf6a-136">Azure を監視するためのテスト デバイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-136">Configure test devices for Azure Monitoring</span></span>
<span data-ttu-id="3cf6a-137"><a name="configure_test_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="3cf6a-137"></span></span>

<span data-ttu-id="3cf6a-138">マイクロソフト チームの会議室に関連するイベントを監視することができるログの分析を準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-138">You need to prepare Log Analytics to be able to monitor Microsoft Teams Rooms–related events.</span></span> <span data-ttu-id="3cf6a-139">開始する物理的なアクセス権を持つ、1 つか 2 つのマイクロソフト チーム室デバイスに Microsoft の監視エージェントを展開し、それらを取得する必要がありますテスト デバイスは、いくつかのデータを生成し、ログ分析機能のワークスペースに押し込みます。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-139">To start with, you need to deploy Microsoft Monitoring agents to just one or two Microsoft Teams Rooms devices that you have physical access to, and get those test devices generate some data and push it to the Log Analytics workspace.</span></span>

### <a name="install-microsoft-monitoring-agents-to-test-devices"></a><span data-ttu-id="3cf6a-140">デバイスをテストするのには Microsoft の監視エージェントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-140">Install Microsoft Monitoring agents to test devices</span></span>

<span data-ttu-id="3cf6a-141">テスト デバイスに[接続の Windows コンピューター](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)で提供されている手順を使用して Microsoft の監視エージェントを展開します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-141">Deploy the Microsoft Monitoring agent to the test devices by using the instructions provided in [Connect Windows computers to the Log Analytics service in Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows).</span></span> <span data-ttu-id="3cf6a-142">この資料には、監視エージェントの Windows を展開するための手順に関する詳細情報が用意されています、マイクロソフト チームの会議室のデバイスを取得するログ分析機能の***ワークスペース ID***と***プライマリ ・ キー***を取得するための手順に接続されています。Azure のモニターの配置とログ分析のインスタンスへのエージェント接続を確認する手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-142">This article provides detailed information about the steps for deploying Microsoft Monitoring Agent for Windows, instructions for obtaining the Log Analytics ***Workspace ID*** and the ***primary key*** to get Microsoft Teams Rooms devices connected to your Azure Monitor deployment, and steps to verify agent connectivity to Log Analytics instance.</span></span>

### <a name="generate-sample-microsoft-teams-rooms-events"></a><span data-ttu-id="3cf6a-143">サンプル Microsoft チームの会議室のイベントを生成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-143">Generate sample Microsoft Teams Rooms events</span></span>

<span data-ttu-id="3cf6a-144">Microsoft の監視エージェントがテストのデバイス上に配置されると、Azure のモニターを使用して必要なイベント ログ データを収集することを確認します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-144">After the Microsoft Monitoring agent is deployed onto the test devices, verify that the required event log data is collected by Azure Monitor.</span></span>

> [!NOTE]
> <span data-ttu-id="3cf6a-145">、Microsoft の監視エージェントのインストール後、デバイスを再起動し、マイクロソフト チームの会議室の会議アプリケーションを起動すると、イベント ログに新しいイベントが生成されることができるようにします。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-145">Reboot the device after the installation of the Microsoft Monitoring agent, and make sure that Microsoft Teams Rooms Meeting app is started, so that it can generate new events into the Event Log.</span></span>

1.  <span data-ttu-id="3cf6a-146">[Microsoft Azure ポータル](https://portal.azure.com)にサインインし、どうなるログの分析に新しいワークスペースを選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-146">Sign in to the [Microsoft Azure portal](https://portal.azure.com) and go to Log Analytics and select your workspace.</span></span>

2.  <span data-ttu-id="3cf6a-147">マイクロソフト チーム室デバイスによって生成されたハートビート イベントを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-147">List the heartbeat events generated by a Microsoft Teams Rooms device:</span></span>
    1.  <span data-ttu-id="3cf6a-148">ワークスペースを選択して**ログ**にしてどうなるマイクロソフト チームの会議室のユーザー設定フィールドを持つハートビート レコードを取得するクエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-148">Select your workspace and go to **Logs** and use a query to retrieve the heartbeat records that will have the custom fields for Microsoft Teams Rooms.</span></span>
    2.  <span data-ttu-id="3cf6a-149">サンプル クエリ。`Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="3cf6a-149">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3.  <span data-ttu-id="3cf6a-150">クエリがマイクロソフト チームの会議室の会議アプリケーションによって生成されたイベントを含むログ レコードを返すことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-150">Make sure that the query returns log records that include events generated by the Microsoft Teams Rooms meetings app.</span></span>

4.  <span data-ttu-id="3cf6a-151">ハードウェアの問題を生成し、Azure のログの分析に必要なイベントを記録することを検証します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-151">Generate a hardware issue, and validate that the required events are logged in Azure Log Analytics.</span></span>
    1.  <span data-ttu-id="3cf6a-152">テスト チームの会議室を Microsoft のシステム上の周辺機器の 1 つを外します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-152">Unplug one of the peripheral devices on the test Microsoft Teams Rooms system.</span></span> <span data-ttu-id="3cf6a-153">カメラ、スピーカー フォン、マイク、または部屋の前面表示可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-153">This could be the camera, speakerphone, microphone, or Front Room Display</span></span>
    2.  <span data-ttu-id="3cf6a-154">Azure のログ分析機能に設定するイベント ログの 10 分間待ちます。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-154">Wait 10 minutes for the event log to be populated in Azure Log Analytics.</span></span>
    3.  <span data-ttu-id="3cf6a-155">ハードウェア エラー イベントのリストにクエリを使用します。`Event | where Source == "SRS-App" and EventID == 3001`</span><span class="sxs-lookup"><span data-stu-id="3cf6a-155">Use a query to list hardware error events: `Event | where Source == "SRS-App" and EventID == 3001`</span></span>

5.  <span data-ttu-id="3cf6a-156">、アプリケーションの問題を生成し、必要なイベントを記録することを検証します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-156">Generate an application issue, and validate that the required events are logged.</span></span>
    1.  <span data-ttu-id="3cf6a-157">マイクロソフト チーム ルーム アプリケーションの構成を変更して、不正なセッション開始プロトコル (SIP) アドレスとパスワードのペアを入力します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-157">Modify Microsoft Teams Rooms application configuration, and type an incorrect Session Initiation Protocol (SIP) address/password pair.</span></span>
    2.  <span data-ttu-id="3cf6a-158">Azure のログ分析機能に設定するイベント ログの 10 分間待ちます。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-158">Wait 10 minutes for the event log to be populated in Azure Log Analytics.</span></span>
    3.  <span data-ttu-id="3cf6a-159">アプリケーション エラー イベントのリストにクエリを使用します。`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span><span class="sxs-lookup"><span data-stu-id="3cf6a-159">Use a query to list application error events: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3cf6a-160">ユーザー設定フィールドを構成する前に、これらのサンプルのイベント ログが必要です。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-160">These sample event logs are required before custom fields can be configured.</span></span> <span data-ttu-id="3cf6a-161">必要なイベント ログを収集し終えるまで、次の手順を続行しません。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-161">Don’t proceed to the next step until you have collected the required event logs.</span></span>

## <a name="map-custom-fields"></a><span data-ttu-id="3cf6a-162">カスタム フィールドをマップする</span><span class="sxs-lookup"><span data-stu-id="3cf6a-162">Map custom fields</span></span>
<span data-ttu-id="3cf6a-163"><a name="Custom_fields"> </a></span><span class="sxs-lookup"><span data-stu-id="3cf6a-163"></span></span>

<span data-ttu-id="3cf6a-164">イベント ログから特定のデータを抽出するのにには、カスタム フィールドを使用します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-164">You use custom fields to extract specific data from the event logs.</span></span> <span data-ttu-id="3cf6a-165">タイル、ダッシュ ボードの表示、および警告の後で使用するカスタム フィールドを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-165">You need to define custom fields that will be used later with your tiles, dashboard views, and alerts.</span></span> <span data-ttu-id="3cf6a-166">[ログ分析でユーザー設定フィールド](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields)を参照してくださいし、カスタム フィールドの作成を開始する前に概念を理解します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-166">See [Custom fields in Log Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) and become familiar with the concepts before you start creating your custom fields.</span></span>

<span data-ttu-id="3cf6a-167">キャプチャしたイベント ログから、ユーザー設定のフィールドを抽出するには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-167">To extract your custom fields out of the captured event logs, follow these steps:</span></span>

1.  <span data-ttu-id="3cf6a-168">[Microsoft Azure ポータル](https://portal.azure.com)にサインインし、どうなるログの分析に新しいワークスペースを選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-168">Sign in to the [Microsoft Azure portal](https://portal.azure.com) and go to Log Analytics and select your workspace.</span></span>

2. <span data-ttu-id="3cf6a-169">マイクロソフト チーム室デバイスによって生成されたイベントの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-169">List the events generated by a Microsoft Teams Rooms device:</span></span>
   1.  <span data-ttu-id="3cf6a-170">**ログ**に移動し、ユーザー設定フィールドを持つレコードを取得するクエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-170">Go to **Logs** and use a query to retrieve the records that will have the custom field.</span></span>
   2.  <span data-ttu-id="3cf6a-171">サンプル クエリ。`Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="3cf6a-171">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3. <span data-ttu-id="3cf6a-172">レコードのいずれかを選択、左側にあるボタンを選択し、フィールドの展開ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-172">Select one of the records, select the button to the left, and start the field extraction wizard.</span></span>
4. <span data-ttu-id="3cf6a-173">RenderedDescription から抽出し、フィールドのタイトルを提供したいデータを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-173">Highlight the data you’d like to extract from the RenderedDescription and provide a Field Title.</span></span> <span data-ttu-id="3cf6a-174">表 1 には、使用するフィールド名が用意されています。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-174">The field names that you should use are provided in Table 1.</span></span>

   <span data-ttu-id="3cf6a-175">![ユーザー設定フィールドの定義](../media/Deploy-Azure-Monitor-4.png "ユーザー設定フィールドの定義")</span><span class="sxs-lookup"><span data-stu-id="3cf6a-175">![Custom field definition](../media/Deploy-Azure-Monitor-4.png "Custom field definition")</span></span>

5. <span data-ttu-id="3cf6a-176">*表 1*に示すようにマッピングを使用します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-176">Use the mappings shown in *Table 1*.</span></span> <span data-ttu-id="3cf6a-177">ログ分析機能が自動的に追加されます、 \*\* \_CF\*\*文字列の新しいフィールドを定義するとします。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-177">Log Analytics will automatically append the **\_CF** string when you define the new field.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3cf6a-178">JSON とログ分析のすべてのフィールドは大文字小文字を区別することを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-178">Remember that all JSON and Log Analytics fields are case-sensitive.</span></span>
> 
> <span data-ttu-id="3cf6a-179">次の表に各ユーザー設定のフィールドに必要なクエリに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-179">Pay attention to the queries required for each custom field in the table below.</span></span> <span data-ttu-id="3cf6a-180">ログ分析の適切なクエリを使用して、カスタム フィールドの値を正常に抽出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-180">You need to use the correct queries for Log Analytics to successfully extract custom field values.</span></span>
> 
 <span data-ttu-id="3cf6a-181">![ユーザー設定フィールドの定義](../media/Deploy-Azure-Monitor-5.png "ユーザー設定フィールドの定義")</span><span class="sxs-lookup"><span data-stu-id="3cf6a-181">![Custom field definition](../media/Deploy-Azure-Monitor-5.png "Custom field definition")</span></span>

<span data-ttu-id="3cf6a-182">**表 1**</span><span class="sxs-lookup"><span data-stu-id="3cf6a-182">**Table 1**</span></span>

| <span data-ttu-id="3cf6a-183">**JSON フィールド**</span><span class="sxs-lookup"><span data-stu-id="3cf6a-183">**JSON field**</span></span>                   | <span data-ttu-id="3cf6a-184">**ログ分析機能のユーザー設定フィールド**</span><span class="sxs-lookup"><span data-stu-id="3cf6a-184">**Log Analytics custom field**</span></span> | <span data-ttu-id="3cf6a-185">**イベント ID**</span><span class="sxs-lookup"><span data-stu-id="3cf6a-185">**Event ID**</span></span> | <span data-ttu-id="3cf6a-186">**抽出に使用するクエリ**</span><span class="sxs-lookup"><span data-stu-id="3cf6a-186">**Query to use with the extraction**</span></span>                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| <span data-ttu-id="3cf6a-187">説明</span><span class="sxs-lookup"><span data-stu-id="3cf6a-187">Description</span></span>                      | <span data-ttu-id="3cf6a-188">SRSEventDescription</span><span class="sxs-lookup"><span data-stu-id="3cf6a-188">SRSEventDescription</span></span>         | <span data-ttu-id="3cf6a-189">**2000**</span><span class="sxs-lookup"><span data-stu-id="3cf6a-189">**2000**</span></span>     | <span data-ttu-id="3cf6a-190">イベント\|、実際のソース"SRS App"とイベント Id = = = 2000</span><span class="sxs-lookup"><span data-stu-id="3cf6a-190">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="3cf6a-191">ResourceState</span><span class="sxs-lookup"><span data-stu-id="3cf6a-191">ResourceState</span></span>                    | <span data-ttu-id="3cf6a-192">SRSResourceState</span><span class="sxs-lookup"><span data-stu-id="3cf6a-192">SRSResourceState</span></span>            | <span data-ttu-id="3cf6a-193">**2000**</span><span class="sxs-lookup"><span data-stu-id="3cf6a-193">**2000**</span></span>     | <span data-ttu-id="3cf6a-194">イベント\|、実際のソース"SRS App"とイベント Id = = = 2000</span><span class="sxs-lookup"><span data-stu-id="3cf6a-194">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="3cf6a-195">OperationName</span><span class="sxs-lookup"><span data-stu-id="3cf6a-195">OperationName</span></span>                    | <span data-ttu-id="3cf6a-196">SRSOperationName</span><span class="sxs-lookup"><span data-stu-id="3cf6a-196">SRSOperationName</span></span>            | <span data-ttu-id="3cf6a-197">**2000**</span><span class="sxs-lookup"><span data-stu-id="3cf6a-197">**2000**</span></span>     | <span data-ttu-id="3cf6a-198">イベント\|、実際のソース"SRS App"とイベント Id = = = 2000</span><span class="sxs-lookup"><span data-stu-id="3cf6a-198">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="3cf6a-199">OperationResult</span><span class="sxs-lookup"><span data-stu-id="3cf6a-199">OperationResult</span></span>                  | <span data-ttu-id="3cf6a-200">SRSOperationResult</span><span class="sxs-lookup"><span data-stu-id="3cf6a-200">SRSOperationResult</span></span>          | <span data-ttu-id="3cf6a-201">**2000**</span><span class="sxs-lookup"><span data-stu-id="3cf6a-201">**2000**</span></span>     | <span data-ttu-id="3cf6a-202">イベント\|、実際のソース"SRS App"とイベント Id = = = 2000</span><span class="sxs-lookup"><span data-stu-id="3cf6a-202">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="3cf6a-203">OS</span><span class="sxs-lookup"><span data-stu-id="3cf6a-203">OS</span></span>                               | <span data-ttu-id="3cf6a-204">SRSOSVersion</span><span class="sxs-lookup"><span data-stu-id="3cf6a-204">SRSOSVersion</span></span>                | <span data-ttu-id="3cf6a-205">**2000**</span><span class="sxs-lookup"><span data-stu-id="3cf6a-205">**2000**</span></span>     | <span data-ttu-id="3cf6a-206">イベント\|、実際のソース"SRS App"とイベント Id = = = 2000</span><span class="sxs-lookup"><span data-stu-id="3cf6a-206">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="3cf6a-207">OSVersion</span><span class="sxs-lookup"><span data-stu-id="3cf6a-207">OSVersion</span></span>                        | <span data-ttu-id="3cf6a-208">SRSOSLongVersion</span><span class="sxs-lookup"><span data-stu-id="3cf6a-208">SRSOSLongVersion</span></span>            | <span data-ttu-id="3cf6a-209">**2000**</span><span class="sxs-lookup"><span data-stu-id="3cf6a-209">**2000**</span></span>     | <span data-ttu-id="3cf6a-210">イベント\|、実際のソース"SRS App"とイベント Id = = = 2000</span><span class="sxs-lookup"><span data-stu-id="3cf6a-210">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="3cf6a-211">Alias</span><span class="sxs-lookup"><span data-stu-id="3cf6a-211">Alias</span></span>                            | <span data-ttu-id="3cf6a-212">SRSAlias</span><span class="sxs-lookup"><span data-stu-id="3cf6a-212">SRSAlias</span></span>                    | <span data-ttu-id="3cf6a-213">**2000**</span><span class="sxs-lookup"><span data-stu-id="3cf6a-213">**2000**</span></span>     | <span data-ttu-id="3cf6a-214">イベント\|、実際のソース"SRS App"とイベント Id = = = 2000</span><span class="sxs-lookup"><span data-stu-id="3cf6a-214">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="3cf6a-215">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3cf6a-215">DisplayName</span></span>                      | <span data-ttu-id="3cf6a-216">SRSDisplayName</span><span class="sxs-lookup"><span data-stu-id="3cf6a-216">SRSDisplayName</span></span>              | <span data-ttu-id="3cf6a-217">**2000**</span><span class="sxs-lookup"><span data-stu-id="3cf6a-217">**2000**</span></span>     | <span data-ttu-id="3cf6a-218">イベント\|、実際のソース"SRS App"とイベント Id = = = 2000</span><span class="sxs-lookup"><span data-stu-id="3cf6a-218">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="3cf6a-219">AppVersion</span><span class="sxs-lookup"><span data-stu-id="3cf6a-219">AppVersion</span></span>                       | <span data-ttu-id="3cf6a-220">SRSAppVersion</span><span class="sxs-lookup"><span data-stu-id="3cf6a-220">SRSAppVersion</span></span>               | <span data-ttu-id="3cf6a-221">**2000**</span><span class="sxs-lookup"><span data-stu-id="3cf6a-221">**2000**</span></span>     | <span data-ttu-id="3cf6a-222">イベント\|、実際のソース"SRS App"とイベント Id = = = 2000</span><span class="sxs-lookup"><span data-stu-id="3cf6a-222">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="3cf6a-223">IPv4Address</span><span class="sxs-lookup"><span data-stu-id="3cf6a-223">IPv4Address</span></span>                      | <span data-ttu-id="3cf6a-224">SRSIPv4Address</span><span class="sxs-lookup"><span data-stu-id="3cf6a-224">SRSIPv4Address</span></span>              | <span data-ttu-id="3cf6a-225">**2000**</span><span class="sxs-lookup"><span data-stu-id="3cf6a-225">**2000**</span></span>     | <span data-ttu-id="3cf6a-226">イベント\|、実際のソース"SRS App"とイベント Id = = = 2000</span><span class="sxs-lookup"><span data-stu-id="3cf6a-226">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="3cf6a-227">IPv6Address</span><span class="sxs-lookup"><span data-stu-id="3cf6a-227">IPv6Address</span></span>                      | <span data-ttu-id="3cf6a-228">SRSIPv6Address</span><span class="sxs-lookup"><span data-stu-id="3cf6a-228">SRSIPv6Address</span></span>              | <span data-ttu-id="3cf6a-229">**2000**</span><span class="sxs-lookup"><span data-stu-id="3cf6a-229">**2000**</span></span>     | <span data-ttu-id="3cf6a-230">イベント\|、実際のソース"SRS App"とイベント Id = = = 2000</span><span class="sxs-lookup"><span data-stu-id="3cf6a-230">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="3cf6a-231">会議マイクの状態</span><span class="sxs-lookup"><span data-stu-id="3cf6a-231">Conference Microphone status</span></span>     | <span data-ttu-id="3cf6a-232">SRSConfMicrophoneStatus</span><span class="sxs-lookup"><span data-stu-id="3cf6a-232">SRSConfMicrophoneStatus</span></span>     | <span data-ttu-id="3cf6a-233">**3001**</span><span class="sxs-lookup"><span data-stu-id="3cf6a-233">**3001**</span></span>     | <span data-ttu-id="3cf6a-234">イベント\|、実際のソース"SRS App"とイベント Id = = = = の 3001</span><span class="sxs-lookup"><span data-stu-id="3cf6a-234">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="3cf6a-235">会議の発表者のステータス</span><span class="sxs-lookup"><span data-stu-id="3cf6a-235">Conference Speaker status</span></span>        | <span data-ttu-id="3cf6a-236">SRSConfSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="3cf6a-236">SRSConfSpeakerStatus</span></span>        | <span data-ttu-id="3cf6a-237">**3001**</span><span class="sxs-lookup"><span data-stu-id="3cf6a-237">**3001**</span></span>     | <span data-ttu-id="3cf6a-238">イベント\|、実際のソース"SRS App"とイベント Id = = = = の 3001</span><span class="sxs-lookup"><span data-stu-id="3cf6a-238">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="3cf6a-239">スピーカーの既定の状態</span><span class="sxs-lookup"><span data-stu-id="3cf6a-239">Default Speaker status</span></span>           | <span data-ttu-id="3cf6a-240">SRSDefaultSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="3cf6a-240">SRSDefaultSpeakerStatus</span></span>     | <span data-ttu-id="3cf6a-241">**3001**</span><span class="sxs-lookup"><span data-stu-id="3cf6a-241">**3001**</span></span>     | <span data-ttu-id="3cf6a-242">イベント\|、実際のソース"SRS App"とイベント Id = = = = の 3001</span><span class="sxs-lookup"><span data-stu-id="3cf6a-242">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="3cf6a-243">カメラの状態</span><span class="sxs-lookup"><span data-stu-id="3cf6a-243">Camera status</span></span>                    | <span data-ttu-id="3cf6a-244">SRSCameraStatus</span><span class="sxs-lookup"><span data-stu-id="3cf6a-244">SRSCameraStatus</span></span>             | <span data-ttu-id="3cf6a-245">**3001**</span><span class="sxs-lookup"><span data-stu-id="3cf6a-245">**3001**</span></span>     | <span data-ttu-id="3cf6a-246">イベント\|、実際のソース"SRS App"とイベント Id = = = = の 3001</span><span class="sxs-lookup"><span data-stu-id="3cf6a-246">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="3cf6a-247">ルームの表示状態の前面</span><span class="sxs-lookup"><span data-stu-id="3cf6a-247">Front of Room Display status</span></span>     | <span data-ttu-id="3cf6a-248">SRSFORDStatus</span><span class="sxs-lookup"><span data-stu-id="3cf6a-248">SRSFORDStatus</span></span>               | <span data-ttu-id="3cf6a-249">**3001**</span><span class="sxs-lookup"><span data-stu-id="3cf6a-249">**3001**</span></span>     | <span data-ttu-id="3cf6a-250">イベント\|、実際のソース"SRS App"とイベント Id = = = = の 3001</span><span class="sxs-lookup"><span data-stu-id="3cf6a-250">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="3cf6a-251">モーション センサーのステータス</span><span class="sxs-lookup"><span data-stu-id="3cf6a-251">Motion Sensor status</span></span>             | <span data-ttu-id="3cf6a-252">SRSMotionSensorStatus</span><span class="sxs-lookup"><span data-stu-id="3cf6a-252">SRSMotionSensorStatus</span></span>       | <span data-ttu-id="3cf6a-253">**3001**</span><span class="sxs-lookup"><span data-stu-id="3cf6a-253">**3001**</span></span>     | <span data-ttu-id="3cf6a-254">イベント\|、実際のソース"SRS App"とイベント Id = = = = の 3001</span><span class="sxs-lookup"><span data-stu-id="3cf6a-254">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="3cf6a-255">HDMI 取り込みの状態</span><span class="sxs-lookup"><span data-stu-id="3cf6a-255">HDMI Ingest status</span></span>               | <span data-ttu-id="3cf6a-256">SRSHDMIIngestStatus</span><span class="sxs-lookup"><span data-stu-id="3cf6a-256">SRSHDMIIngestStatus</span></span>         | <span data-ttu-id="3cf6a-257">**3001**</span><span class="sxs-lookup"><span data-stu-id="3cf6a-257">**3001**</span></span>     | <span data-ttu-id="3cf6a-258">イベント\|、実際のソース"SRS App"とイベント Id = = = = の 3001</span><span class="sxs-lookup"><span data-stu-id="3cf6a-258">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |


## <a name="define-the-microsoft-teams-rooms-views-in-log-analytics"></a><span data-ttu-id="3cf6a-259">ログ分析のマイクロソフト チーム室ビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-259">Define the Microsoft Teams Rooms views in Log Analytics</span></span>
<span data-ttu-id="3cf6a-260"><a name="Define_Views"> </a></span><span class="sxs-lookup"><span data-stu-id="3cf6a-260"></span></span>

<span data-ttu-id="3cf6a-261">データが収集され、ユーザー設定フィールドがマップされている後、は、マイクロソフト チームの会議室のイベントを監視するためのさまざまなタイルを含むダッシュ ボードを開発するのにデザイナーの表示を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-261">After data is collected and custom fields are mapped, you can use View Designer to develop a dashboard containing various tiles to monitor Microsoft Teams Rooms events.</span></span> <span data-ttu-id="3cf6a-262">ビュー デザイナーを使用すると、次のタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-262">Use View Designer to create the following tiles.</span></span> <span data-ttu-id="3cf6a-263">詳細については、[ログの分析で、ビュー デザイナーを使用してカスタム ビューを作成する](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-263">For more information, see [Create custom views by using View Designer in Log Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)</span></span>

> [!NOTE]
> <span data-ttu-id="3cf6a-264">正常に動作するダッシュ ボードのタイルのこのガイドで前の手順への接続が完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-264">Previous steps in this guide should have been completed for the dashboard tiles to work properly.</span></span>

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a><span data-ttu-id="3cf6a-265">Import メソッドを使用して Microsoft チーム ルーム ダッシュ ボードを作成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-265">Create a Microsoft Teams Rooms dashboard by using the import method</span></span>

<span data-ttu-id="3cf6a-266">マイクロソフト チームの会議室のダッシュ ボードにインポートし、デバイスを簡単に監視を開始できます。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-266">You can import an Microsoft Teams Rooms dashboard and start monitoring your devices quickly.</span></span> <span data-ttu-id="3cf6a-267">ダッシュ ボードにインポートするのには以下の手順を実行するには。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-267">Take the following steps to import the dashboard:</span></span>

1.  <span data-ttu-id="3cf6a-268">[SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675)ダッシュ ボード ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-268">Get the [SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675) dashboard file.</span></span>
2.  <span data-ttu-id="3cf6a-269">[Microsoft Azure ポータル](https://portal.azure.com)にサインインし、どうなるログの分析に新しいワークスペースを選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-269">Sign in to the [Microsoft Azure portal](https://portal.azure.com) and go to Log Analytics and select your workspace.</span></span>
3.  <span data-ttu-id="3cf6a-270">**ビュー デザイナー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-270">Open **View Designer**.</span></span>
4.  <span data-ttu-id="3cf6a-271">**インポート**] を選択し、 **SkypeRoomSystems_v2.omsview**ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-271">Select **Import**, and then select the **SkypeRoomSystems_v2.omsview** file.</span></span>
5.  <span data-ttu-id="3cf6a-272">**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-272">Select **Save**.</span></span>

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a><span data-ttu-id="3cf6a-273">マイクロソフト チームの会議室のダッシュ ボードを手動で作成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-273">Create a Microsoft Teams Rooms dashboard manually</span></span>

<span data-ttu-id="3cf6a-274">または、独自のダッシュ ボードを作成し、監視対象のタイルのみを追加できます。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-274">Alternatively, you can create your own dashboard and add only the tiles that you wish to monitor.</span></span>

#### <a name="configure-the-overview-tile"></a><span data-ttu-id="3cf6a-275">概要タイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-275">Configure the Overview Tile</span></span>

1.  <span data-ttu-id="3cf6a-276">**ビュー デザイナー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-276">Open **View Designer**.</span></span>
2.  <span data-ttu-id="3cf6a-277">**概要タイル**を選択し、ギャラリーから**2 つの数値**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-277">Select **Overview Tile**, and then select **Two numbers** from the gallery.</span></span>
3.  <span data-ttu-id="3cf6a-278">**マイクロソフト チームの会議室**のタイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-278">Name the tile **Microsoft Teams Rooms**.</span></span>
4.  <span data-ttu-id="3cf6a-279">**最初のタイル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-279">Define the **First Tile**:</span></span><br>
    <span data-ttu-id="3cf6a-280">**凡例:** 最後の月以内にハートビートを送信するデバイス</span><span class="sxs-lookup"><span data-stu-id="3cf6a-280">**Legend:** Devices that sent a heartbeat at least once within the last month</span></span><br>
    <span data-ttu-id="3cf6a-281">**クエリ:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="3cf6a-281">**Query:** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
5.  <span data-ttu-id="3cf6a-282">**2 つ目のタイル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-282">Define the **Second Tile**:</span></span><br>
    <span data-ttu-id="3cf6a-283">**凡例:** 最後の時間内にハートビートを送信するアクティブなデバイス</span><span class="sxs-lookup"><span data-stu-id="3cf6a-283">**Legend:** Active devices that sent a heartbeat within the last hour</span></span><br>
    <span data-ttu-id="3cf6a-284">**クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="3cf6a-284">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
6.  <span data-ttu-id="3cf6a-285">**適用**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-285">Select **Apply**.</span></span>

### <a name="create-a-tile-that-displays-active-devices"></a><span data-ttu-id="3cf6a-286">アクティブなデバイスを表示するタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-286">Create a tile that displays active devices</span></span>

1.  <span data-ttu-id="3cf6a-287">タイルを追加する**ダッシュ ボードのビュー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-287">Select **View Dashboard** to start adding your tiles.</span></span>
2.  <span data-ttu-id="3cf6a-288">**_AMP_ リストに番号**を選択して、ギャラリーから</span><span class="sxs-lookup"><span data-stu-id="3cf6a-288">Select **Number & list** from the gallery</span></span>
3.  <span data-ttu-id="3cf6a-289">**全般**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-289">Define the **General** properties:</span></span><br>
    <span data-ttu-id="3cf6a-290">**グループ タイトル:** ハートビートの状態</span><span class="sxs-lookup"><span data-stu-id="3cf6a-290">**Group Title:** Heartbeat Status</span></span><br>
    <span data-ttu-id="3cf6a-291">**新しいグループ:** 選択</span><span class="sxs-lookup"><span data-stu-id="3cf6a-291">**New Group:** Selected</span></span>
4.  <span data-ttu-id="3cf6a-292">**タイル**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-292">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="3cf6a-293">**凡例:** アクティブなデバイス (ハートビートの最後の 20 分間で送信されます)</span><span class="sxs-lookup"><span data-stu-id="3cf6a-293">**Legend:** Active devices (heartbeat sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="3cf6a-294">\*\*タイルのクエリ: \*\* ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="3cf6a-294">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span></span>
5.  <span data-ttu-id="3cf6a-295">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-295">Define the **List** properties:</span></span><br>
    <span data-ttu-id="3cf6a-296">**クエリの一覧を表示:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="3cf6a-296">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
6.  <span data-ttu-id="3cf6a-297">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-297">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="3cf6a-298">**名:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="3cf6a-298">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="3cf6a-299">**値:** 最後のハートビート</span><span class="sxs-lookup"><span data-stu-id="3cf6a-299">**Value:** Last Heartbeat</span></span>
7.  <span data-ttu-id="3cf6a-300">**ナビゲーション クエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-300">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="3cf6a-301">**適用**され、し、**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-301">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a><span data-ttu-id="3cf6a-302">接続の問題のあるデバイスを表示するタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-302">Create a tile that displays devices that have connectivity issues</span></span>

1.  <span data-ttu-id="3cf6a-303">ギャラリーから、[ **&] ボックスの一覧の番号**を選択し、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-303">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="3cf6a-304">**全般**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-304">Define the **General** properties:</span></span><br>
    <span data-ttu-id="3cf6a-305">**グループ タイトル:** 空のままに</span><span class="sxs-lookup"><span data-stu-id="3cf6a-305">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="3cf6a-306">**新しいグループ:** 選択されていません。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-306">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="3cf6a-307">**タイル**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-307">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="3cf6a-308">**凡例:** 非アクティブなデバイス (ハートビート メッセージは最後の 20 分間で送信されます)</span><span class="sxs-lookup"><span data-stu-id="3cf6a-308">**Legend:** Inactive Devices (no heartbeat message sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="3cf6a-309">\*\*タイルのクエリ: \*\* ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span><span class="sxs-lookup"><span data-stu-id="3cf6a-309">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span></span>
4.  <span data-ttu-id="3cf6a-310">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-310">Define the **List** properties:</span></span><br>
    <span data-ttu-id="3cf6a-311">**クエリの一覧を表示:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="3cf6a-311">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="3cf6a-312">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-312">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="3cf6a-313">**名:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="3cf6a-313">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="3cf6a-314">**値:** 最後のハートビート</span><span class="sxs-lookup"><span data-stu-id="3cf6a-314">**Value:** Last Heartbeat</span></span>
6.  <span data-ttu-id="3cf6a-315">**ナビゲーション クエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-315">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="3cf6a-316">**適用**され、し、**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-316">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a><span data-ttu-id="3cf6a-317">ハードウェア エラーのあるデバイスを表示するタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-317">Create a tile that displays devices that have a hardware error</span></span>

1.  <span data-ttu-id="3cf6a-318">ギャラリーから、[ **&] ボックスの一覧の番号**を選択し、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-318">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="3cf6a-319">**全般**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-319">Define the **General** properties:</span></span><br>
    <span data-ttu-id="3cf6a-320">**グループ タイトル:** ハードウェアのステータス</span><span class="sxs-lookup"><span data-stu-id="3cf6a-320">**Group Title:** Hardware Status</span></span><br>
    <span data-ttu-id="3cf6a-321">**新しいグループ:** 選択</span><span class="sxs-lookup"><span data-stu-id="3cf6a-321">**New Group:** Selected</span></span>
3.  <span data-ttu-id="3cf6a-322">**タイル**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-322">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="3cf6a-323">**凡例:** 最後の 1 時間以内にハードウェア エラーが発生したデバイス</span><span class="sxs-lookup"><span data-stu-id="3cf6a-323">**Legend:** Devices that experienced a hardware error in the last hour</span></span><br>
    <span data-ttu-id="3cf6a-324">\*\*タイルのクエリ: \*\* ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="3cf6a-324">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="3cf6a-325">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-325">Define the **List** properties:</span></span><br>
    <span data-ttu-id="3cf6a-326">**クエリの一覧を表示:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="3cf6a-326">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="3cf6a-327">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-327">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="3cf6a-328">**名:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="3cf6a-328">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="3cf6a-329">**値:** 最後のエラー</span><span class="sxs-lookup"><span data-stu-id="3cf6a-329">**Value:** Last Error</span></span>
6.  <span data-ttu-id="3cf6a-330">**ナビゲーション クエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-330">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="3cf6a-331">**適用**され、し、**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-331">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-operating-system-versions"></a><span data-ttu-id="3cf6a-332">チーム会議室の Microsoft オペレーティング システムのバージョンを表示するタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-332">Create a tile that displays Microsoft Teams Rooms Operating System versions</span></span>

1.  <span data-ttu-id="3cf6a-333">ギャラリーから、**ドーナツ & リスト**を選択し、新たにコピーします。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-333">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="3cf6a-334">**全般**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-334">Define the **General** properties:</span></span><br>
    <span data-ttu-id="3cf6a-335">**グループ タイトル:** オペレーティング システムの詳細</span><span class="sxs-lookup"><span data-stu-id="3cf6a-335">**Group Title:** Operating System details</span></span><br>
    <span data-ttu-id="3cf6a-336">**新しいグループ:** 選択</span><span class="sxs-lookup"><span data-stu-id="3cf6a-336">**New Group:** Selected</span></span>
3.  <span data-ttu-id="3cf6a-337">**ヘッダー**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-337">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="3cf6a-338">**タイトル:** オペレーティング システムのバージョン</span><span class="sxs-lookup"><span data-stu-id="3cf6a-338">**Title:** Operating System versions</span></span><br>
    <span data-ttu-id="3cf6a-339">**サブタイトル:** 特定の OS バージョンを実行しているデバイス</span><span class="sxs-lookup"><span data-stu-id="3cf6a-339">**Subtitle:** Devices running specific OS versions</span></span>
4.  <span data-ttu-id="3cf6a-340">**ドーナツ**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-340">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="3cf6a-341">**クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span><span class="sxs-lookup"><span data-stu-id="3cf6a-341">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span></span><br>
    <span data-ttu-id="3cf6a-342">**テキストを中央揃え:** デバイス</span><span class="sxs-lookup"><span data-stu-id="3cf6a-342">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="3cf6a-343">**操作:** 合計</span><span class="sxs-lookup"><span data-stu-id="3cf6a-343">**Operation:** Sum</span></span>
5.  <span data-ttu-id="3cf6a-344">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-344">Define the **List** properties.</span></span><br>
    <span data-ttu-id="3cf6a-345">**クエリの一覧を表示:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span><span class="sxs-lookup"><span data-stu-id="3cf6a-345">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="3cf6a-346">**グラフを非表示にする:** 選択</span><span class="sxs-lookup"><span data-stu-id="3cf6a-346">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="3cf6a-347">**スパーク ラインを有効にする:** 選択されていません。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-347">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="3cf6a-348">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-348">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="3cf6a-349">**名:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="3cf6a-349">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="3cf6a-350">**値:** 空のままに</span><span class="sxs-lookup"><span data-stu-id="3cf6a-350">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="3cf6a-351">**ナビゲーション クエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-351">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="3cf6a-352">**適用**し、[**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-352">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-application-versions"></a><span data-ttu-id="3cf6a-353">チームの会議室を Microsoft アプリケーションのバージョンを表示するタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-353">Create a tile that displays Microsoft Teams Rooms application versions</span></span>

1.  <span data-ttu-id="3cf6a-354">ギャラリーから、**ドーナツ & リスト**を選択し、新たにコピーします。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-354">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="3cf6a-355">**全般**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-355">Define the **General** properties:</span></span><br>
    <span data-ttu-id="3cf6a-356">**グループ タイトル:** アプリケーションの詳細をマイクロソフト チームの会議室</span><span class="sxs-lookup"><span data-stu-id="3cf6a-356">**Group Title:** Microsoft Teams Rooms application details</span></span><br>
    <span data-ttu-id="3cf6a-357">**新しいグループ:** 選択</span><span class="sxs-lookup"><span data-stu-id="3cf6a-357">**New Group:** Selected</span></span>
3.  <span data-ttu-id="3cf6a-358">**ヘッダー**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-358">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="3cf6a-359">**タイトル:** アプリケーションのバージョン</span><span class="sxs-lookup"><span data-stu-id="3cf6a-359">**Title:** Application versions</span></span><br>
    <span data-ttu-id="3cf6a-360">**サブタイトル:** 特定のアプリケーションのバージョンを実行しているデバイス</span><span class="sxs-lookup"><span data-stu-id="3cf6a-360">**Subtitle:** Devices running specific application versions</span></span>
4.  <span data-ttu-id="3cf6a-361">**ドーナツ**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-361">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="3cf6a-362">**クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span><span class="sxs-lookup"><span data-stu-id="3cf6a-362">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span></span><br>
    <span data-ttu-id="3cf6a-363">**テキストを中央揃え:** デバイス</span><span class="sxs-lookup"><span data-stu-id="3cf6a-363">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="3cf6a-364">**操作:** 合計</span><span class="sxs-lookup"><span data-stu-id="3cf6a-364">**Operation:** Sum</span></span>
5.  <span data-ttu-id="3cf6a-365">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-365">Define the **List** properties.</span></span><br>
    <span data-ttu-id="3cf6a-366">**クエリの一覧を表示:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span><span class="sxs-lookup"><span data-stu-id="3cf6a-366">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="3cf6a-367">**グラフを非表示にする:** 選択</span><span class="sxs-lookup"><span data-stu-id="3cf6a-367">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="3cf6a-368">**スパーク ラインを有効にする:** 選択されていません。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-368">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="3cf6a-369">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-369">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="3cf6a-370">**名:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="3cf6a-370">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="3cf6a-371">**値:** 空のままに</span><span class="sxs-lookup"><span data-stu-id="3cf6a-371">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="3cf6a-372">**ナビゲーション クエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-372">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="3cf6a-373">**適用**し、[**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-373">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a><span data-ttu-id="3cf6a-374">アプリケーション エラーのあるデバイスを表示するタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-374">Create a tile that displays devices that have an application error</span></span>

1.  <span data-ttu-id="3cf6a-375">ギャラリーから、[ **&] ボックスの一覧の番号**を選択し、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-375">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="3cf6a-376">**全般**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-376">Define the **General** properties.</span></span><br>
    <span data-ttu-id="3cf6a-377">**グループ タイトル:** 空のままに</span><span class="sxs-lookup"><span data-stu-id="3cf6a-377">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="3cf6a-378">**新しいグループ:** 選択されていません。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-378">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="3cf6a-379">**タイル**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-379">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="3cf6a-380">**凡例:** 最後の時間でアプリケーション エラーが発生したデバイス</span><span class="sxs-lookup"><span data-stu-id="3cf6a-380">**Legend:** Devices that experienced an application error in the last hour</span></span><br>
    <span data-ttu-id="3cf6a-381">\*\*タイルのクエリ: \*\* ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="3cf6a-381">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="3cf6a-382">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-382">Define the **List** properties.</span></span><br>
    <span data-ttu-id="3cf6a-383">**クエリの一覧を表示:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="3cf6a-383">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="3cf6a-384">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-384">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="3cf6a-385">**名:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="3cf6a-385">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="3cf6a-386">**値:** 最後のエラー</span><span class="sxs-lookup"><span data-stu-id="3cf6a-386">**Value:** Last Error</span></span>
6.  <span data-ttu-id="3cf6a-387">**ナビゲーション クエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-387">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="3cf6a-388">**適用**し、[**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-388">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a><span data-ttu-id="3cf6a-389">再起動されているデバイスを表示するタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-389">Create a tile that displays devices that have been restarted</span></span>

1.  <span data-ttu-id="3cf6a-390">ギャラリーから、[ **&] ボックスの一覧の番号**を選択し、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-390">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="3cf6a-391">**全般**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-391">Define the **General** properties.</span></span><br>
    <span data-ttu-id="3cf6a-392">**グループ タイトル:** 空のままに</span><span class="sxs-lookup"><span data-stu-id="3cf6a-392">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="3cf6a-393">**新しいグループ:** 選択されていません。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-393">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="3cf6a-394">**タイル**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-394">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="3cf6a-395">**凡例:** デバイスのアプリケーションの再起動では、最後の 24 時間、および再起動の回数</span><span class="sxs-lookup"><span data-stu-id="3cf6a-395">**Legend:** Devices where the application was restarted in the last 24 hours, and number of restarts</span></span><br>
    <span data-ttu-id="3cf6a-396">\*\*タイルのクエリ: \*\* ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="3cf6a-396">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="3cf6a-397">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-397">Define the **List** properties.</span></span><br>
    <span data-ttu-id="3cf6a-398">**クエリの一覧を表示:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span><span class="sxs-lookup"><span data-stu-id="3cf6a-398">**List Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span></span>
5.  <span data-ttu-id="3cf6a-399">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-399">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="3cf6a-400">**名:** コンピューター名</span><span class="sxs-lookup"><span data-stu-id="3cf6a-400">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="3cf6a-401">**値:** 再起動の回数</span><span class="sxs-lookup"><span data-stu-id="3cf6a-401">**Value:** Number of Restarts</span></span>
6.  <span data-ttu-id="3cf6a-402">**ナビゲーション クエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-402">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="3cf6a-403">**適用**し、[**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-403">Select **Apply** and then **Close**.</span></span>
8.  <span data-ttu-id="3cf6a-404">ダッシュ ボードを保存する**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-404">Select **Save** to save your dashboard.</span></span>

<span data-ttu-id="3cf6a-405">ここで、ビューの作成が完了しました。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-405">Now you’ve completed creating your views.</span></span>

## <a name="configure-alerts-in-azure-monitor"></a><span data-ttu-id="3cf6a-406">Azure のモニターで警告を構成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-406">Configure Alerts in Azure Monitor</span></span>
<span data-ttu-id="3cf6a-407"><a name="Alerts"> </a></span><span class="sxs-lookup"><span data-stu-id="3cf6a-407"></span></span>

<span data-ttu-id="3cf6a-408">Azure のモニターには、マイクロソフト チームの会議室のコンソールに問題が発生した場合、管理者に通知するアラートを発生できます。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-408">Azure Monitor can raise alerts to notify the administrators, when a Microsoft Teams Rooms console encounters an issue.</span></span>

<span data-ttu-id="3cf6a-409">Azure のモニターには、定期的にスケジュールされたログの検索を実行する組み込みの警告メカニズムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-409">Azure Monitor includes a built-in alerting mechanism that runs through scheduled log searches at regular intervals.</span></span> <span data-ttu-id="3cf6a-410">ログの検索の結果には、いくつか特定の条件が一致する場合は、アラートのレコードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-410">If the results of the log search match some particular criteria, an alert record is created.</span></span>

<span data-ttu-id="3cf6a-411">自動的に、ルールでは、事前に警告を通知または別のプロセスを起動する 1 つまたは複数のアクションを実行できるし。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-411">The rule can then automatically run one or more actions to proactively notify you of the alert or invoke another process.</span></span> <span data-ttu-id="3cf6a-412">アラートを使用可能なオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-412">The possible options with alerts are:</span></span>
-   <span data-ttu-id="3cf6a-413">電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-413">Sending an email</span></span>
-   <span data-ttu-id="3cf6a-414">HTTP POST 要求を外部プロセスを起動します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-414">Invoking an external process through an HTTP POST request</span></span>
-   <span data-ttu-id="3cf6a-415">Runbook を Azure のオートメーション サービスの開始</span><span class="sxs-lookup"><span data-stu-id="3cf6a-415">Starting a runbook in Azure Automation service</span></span>

<span data-ttu-id="3cf6a-416">Azure モニターの警告に関する詳細については、 [Azure のモニターで警告をログに記録](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-416">See [Log alerts in Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) to learn more about the alerts in Azure Monitor.</span></span>

> [!NOTE]
> <span data-ttu-id="3cf6a-417">次の例は、マイクロソフト チームの会議室のデバイスがハードウェアまたはアプリケーション エラーを生成する場合電子メール警告を送信します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-417">The following examples send email alerts when a Microsoft Teams Rooms device generates a hardware or an application error.</span></span>

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-hardware-issues"></a><span data-ttu-id="3cf6a-418">ハードウェアの問題をマイクロソフト チームの会議室のメール ・ アラートを構成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-418">Configure an email alert for Microsoft Teams Rooms hardware issues</span></span>

<span data-ttu-id="3cf6a-419">最後の時間内でハードウェアの問題が発生しているマイクロソフト チームの会議室のデバイスを確認する警告ルールを構成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-419">Configure an alert rule that checks for Microsoft Teams Rooms devices that have encountered hardware issues within the last hour.</span></span>
1.  <span data-ttu-id="3cf6a-420">[Microsoft Azure ポータル](https://portal.azure.com)にサインインし、どうなるログの分析に新しいワークスペースを選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-420">Sign in to the [Microsoft Azure portal](https://portal.azure.com) and go to Log Analytics and select your workspace.</span></span>

2. <span data-ttu-id="3cf6a-421">ログの分析機能のワークスペースに移動し**アラート**を選択し、**新しいアラート ルール**を選択し、</span><span class="sxs-lookup"><span data-stu-id="3cf6a-421">Navigate to your Log Analytics workspace and select **Alerts** and then select **New alert rule**</span></span>

3. <span data-ttu-id="3cf6a-422">[**条件の追加**し、[**カスタム ログの検索**</span><span class="sxs-lookup"><span data-stu-id="3cf6a-422">Select **Add condition** and then **Custom log search**</span></span>

4.  <span data-ttu-id="3cf6a-423">検索クエリのテキスト ボックスに次のクエリを入力します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-423">Enter the following query to the Search query text box.</span></span><br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  <span data-ttu-id="3cf6a-424">警告のロジックの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-424">Configure the Alert logic settings:</span></span><br>
    <span data-ttu-id="3cf6a-425">**に基づく:** 結果の数</span><span class="sxs-lookup"><span data-stu-id="3cf6a-425">**Based on:** Number of results</span></span><br>
    <span data-ttu-id="3cf6a-426">**条件:** 大きいし、</span><span class="sxs-lookup"><span data-stu-id="3cf6a-426">**Condition:** Greater then</span></span><br>
    <span data-ttu-id="3cf6a-427">**しきい値:** 0</span><span class="sxs-lookup"><span data-stu-id="3cf6a-427">**Treshold:** 0</span></span><br>

6. <span data-ttu-id="3cf6a-428">評価の設定を構成し、**実行**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-428">Configure Evaluation settings and select **Done**:</span></span> <br>
    <span data-ttu-id="3cf6a-429">**時間 (分単位):** 60</span><span class="sxs-lookup"><span data-stu-id="3cf6a-429">**Period (in minutes):** 60</span></span><br>
    <span data-ttu-id="3cf6a-430">**頻度 (分):** 60</span><span class="sxs-lookup"><span data-stu-id="3cf6a-430">**Frequency (in minutes):** 60</span></span><br>

7. <span data-ttu-id="3cf6a-431">アクションのグループを構成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-431">Configure action groups:</span></span>
    1.  <span data-ttu-id="3cf6a-432">**新規作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-432">Select **Create New**</span></span>
    2.  <span data-ttu-id="3cf6a-433">*アクション グループの名前*と*短い名前*のフィールドに適切な名前を提供します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-433">Provide suitable names for the *Action group name* and *Short Name* fields.</span></span>
    3.  <span data-ttu-id="3cf6a-434">固有の*アクション名*を指定、**電子メール、SMS、プッシュ/音声**を選択し、[**詳細の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-434">Specify a unique *Action Name* and select **Email/SMS/Push/Voice**, and then select **Edit details**.</span></span>
    4.  <span data-ttu-id="3cf6a-435">電子メール] チェック ボックスを選択しのユーザーまたはグループのアラートを受信する電子メール アドレスを提供します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-435">Select the Email checkbox and provide the email address of the person or group that will recieve the alerts.</span></span>
    5.  <span data-ttu-id="3cf6a-436">SMS、音声通話、またはその両方を使用して通知を受け取るため、電話番号を入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-436">You may also provide your phone number to get notified with SMS, a voice call or both.</span></span>
    6. <span data-ttu-id="3cf6a-437">**[Ok]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-437">Select **OK**.</span></span>

8. <span data-ttu-id="3cf6a-438">**アクションをカスタマイズする**警告の電子メールの件名行をオーバーライドする場合です。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-438">**Customize Actions** if you like to override the subject line of the alert emails.</span></span>

9. <span data-ttu-id="3cf6a-439">ルールの名前と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-439">Specify a rule name and description.</span></span><br>
    <span data-ttu-id="3cf6a-440">**ルールの名前:** マイクロソフト チーム ルームのハードウェア障害の警告</span><span class="sxs-lookup"><span data-stu-id="3cf6a-440">**Rule Name:** Microsoft Teams Rooms Hardware Failure Alert</span></span><br>
    <span data-ttu-id="3cf6a-441">**説明:** 最後の時間内でハードウェアの問題が発生したデバイスの一覧</span><span class="sxs-lookup"><span data-stu-id="3cf6a-441">**Description:** List of devices that encountered a hardware issue within the last hour</span></span><br>

10. <span data-ttu-id="3cf6a-442">目的の重要度を選択し、ルールが有効になっているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-442">Select the intended severity and make sure the rule is enabled.</span></span>

11. <span data-ttu-id="3cf6a-443">**警告ルールを作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-443">Select **Create alert rule**.</span></span>

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-application-issues"></a><span data-ttu-id="3cf6a-444">アプリケーションの問題をマイクロソフト チームの会議室の電子メール通知を構成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-444">Configure an email alert for Microsoft Teams Rooms application issues</span></span>

<span data-ttu-id="3cf6a-445">同じ手順を繰り返しますが、最後の時間内でアプリケーションの問題が発生しているデバイスの一覧表示するには、次のクエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-445">Repeat the same procedure but use the following query to list devices that have encountered application issues within the last hour.</span></span>

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

<span data-ttu-id="3cf6a-446">警告の定義を完了しました。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-446">Now you’ve completed defining alerts.</span></span> <span data-ttu-id="3cf6a-447">上記の例を使用して、別のアラートを定義できます。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-447">You can define additional alerts by using the examples above.</span></span>

<span data-ttu-id="3cf6a-448">アラートが生成されると、最後の時間内で問題が発生しているデバイスを一覧表示する電子メールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-448">When an alert is generated, you’ll get an email that lists the devices that encountered an issue within the last hour.</span></span>

<span data-ttu-id="3cf6a-449">![サンプル Azure モニター警告の電子メール](../media/Deploy-Azure-Monitor-6.png "サンプル Azure モニター警告の電子メール")</span><span class="sxs-lookup"><span data-stu-id="3cf6a-449">![Sample Azure Monitor alert email](../media/Deploy-Azure-Monitor-6.png "Sample Azure Monitor alert email")</span></span>

## <a name="configure-all-devices-for-azure-monitoring"></a><span data-ttu-id="3cf6a-450">Azure を監視するためのすべてのデバイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-450">Configure all devices for Azure Monitoring</span></span>
<span data-ttu-id="3cf6a-451"><a name="configure_all_devices"></a>ダッシュ ボード、アラートを構成した後は、設定および監視、展開を完了するすべてのマイクロソフト チーム室デバイスで Microsoft の監視エージェントを構成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-451"><a name="configure_all_devices"> </a> After the dashboards and alerts are configured, you can set up and configure Microsoft Monitoring agent on all Microsoft Teams Rooms devices to complete your monitoring deployment.</span></span>

<span data-ttu-id="3cf6a-452">インストールし、デバイスごとに、Microsoft の監視エージェントを手動で構成できますが、既存のソフトウェア展開ツールおよび方法を活用するを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-452">Although you can install and configure the Microsoft Monitoring agent manually on each device, we highly recommend you leverage existing software deployment tools and methods.</span></span>

<span data-ttu-id="3cf6a-453">最初に、マイクロソフト チームの会議室のデバイスを作成する場合は、ビルド プロセスの一環としてマイクロソフトの監視エージェントのセットアップと構成の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-453">If you’re building your Microsoft Teams Rooms devices for the first time, you might want to include the Microsoft Monitoring agent setup and configuration steps as part of your build process.</span></span> <span data-ttu-id="3cf6a-454">詳細については、[コマンド ・ ラインを使用してエージェントのインストール](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-454">For more information, see [Install the agent using the command line](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).</span></span>

### <a name="deploying-microsoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a><span data-ttu-id="3cf6a-455">グループ ポリシー オブジェクト (GPO) を使用して、Microsoft の監視エージェントを展開します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-455">Deploying Microsoft Monitoring agent by using a Group Policy Object (GPO)</span></span>

<span data-ttu-id="3cf6a-456">Azure の監視を実装する前に、マイクロソフトのチーム会議室デバイス既に展開されている場合を設定し、Active Directory グループ ポリシー オブジェクトを使用してエージェントを構成する提供されたスクリプトを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-456">If you already deployed your Microsoft Teams Rooms devices before you implement Azure Monitoring, you can use the provided script to set up and configure the agents by using Active Directory group policy objects.</span></span>

1.  <span data-ttu-id="3cf6a-457">共有のネットワーク パスを作成し、**ドメイン コンピューター**グループに読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-457">Create a shared network path and grant read access to **Domain Computers** group.</span></span>

2.  <span data-ttu-id="3cf6a-458">監視エージェントの Windows からの 64 ビット バージョンをダウンロードします。<https://go.microsoft.com/fwlink/?LinkID=517476></span><span class="sxs-lookup"><span data-stu-id="3cf6a-458">Download the 64-bit version of the Microsoft Monitoring Agent for Windows from <https://go.microsoft.com/fwlink/?LinkID=517476></span></span>

3.  <span data-ttu-id="3cf6a-459">ネットワーク共有には、セットアップ パッケージの内容を抽出します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-459">Extract the contents of the setup package into the network share.</span></span>
    1.  <span data-ttu-id="3cf6a-460">コマンド プロンプト ウィンドウを開き、 **MMASetup AMD64.exe/c**を実行し、</span><span class="sxs-lookup"><span data-stu-id="3cf6a-460">Open a Command Prompt window, and then execute **MMASetup-AMD64.exe /c**</span></span>
    2.  <span data-ttu-id="3cf6a-461">作成した共有を指定し、コンテンツを抽出します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-461">Specify the share you just created, and extract the content.</span></span>

4.  <span data-ttu-id="3cf6a-462">新しいグループ ポリシー オブジェクトを作成し、マイクロソフト チームの会議室のコンピューター アカウントが格納されている組織単位に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-462">Create a new Group Policy Object and assign it to the organizational unit where Microsoft Teams Rooms machine accounts are located.</span></span>

5.  <span data-ttu-id="3cf6a-463">PowerShell 実行ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-463">Configure PowerShell execution policy:</span></span>
    1.  <span data-ttu-id="3cf6a-464">新しく作成したグループ ポリシー オブジェクトを編集し、コンピューターの構成に移動\\ポリシー\\管理用テンプレート\\Windows コンポーネントの\\Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3cf6a-464">Edit the newly created Group Policy Object and navigate to Computer Configuration \\ Policies \\ Administrative Templates \\ Windows Components \\ Windows PowerShell</span></span>
    2.  <span data-ttu-id="3cf6a-465">**スクリプトの実行を有効に**するを有効にして、**実行ポリシー**を**ローカルのスクリプトを許可する**に設定します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-465">Enable the **Turn on Script Execution** and set **Execution Policy** to **Allow Local Scripts**.</span></span>

6.  <span data-ttu-id="3cf6a-466">スタートアップ ・ スクリプトを構成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-466">Configure the startup script:</span></span>
    1.  <span data-ttu-id="3cf6a-467">次のスクリプトをコピーし、インストールを MMAgent.ps1 として保存します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-467">Copy the following script and save it as Install-MMAgent.ps1.</span></span>
    2.  <span data-ttu-id="3cf6a-468">構成に合わせて、WorkspaceId、WorkspaceKey、および SetupPath のパラメーターを変更します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-468">Modify WorkspaceId, WorkspaceKey, and SetupPath parameters to match your configuration.</span></span>
    3.  <span data-ttu-id="3cf6a-469">同じグループ ポリシー オブジェクトを編集し、コンピューターの構成に移動\\ポリシー \\ Windows の設定\\スクリプト (スタートアップ/シャット ダウン)</span><span class="sxs-lookup"><span data-stu-id="3cf6a-469">Edit the same Group Policy Object and navigate to Computer Configuration \\ Policies \\ Windows Settings \\ Scripts (Startup/Shutdown)</span></span>
    4.  <span data-ttu-id="3cf6a-470">ダブルクリックして**起動**を選択し、 **PowerShell スクリプト**します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-470">Double-click to select **Startup**, and then select **PowerShell Scripts**.</span></span>
    5.  <span data-ttu-id="3cf6a-471">**ファイルを表示**] を選択し、そのフォルダーに**インストールを MMAgent.ps1**ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-471">Select **Show Files**, and then copy the **Install-MMAgent.ps1** file to that folder.</span></span>
    6.  <span data-ttu-id="3cf6a-472">**追加**して、**参照**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-472">Select **Add**, and then **Browse**.</span></span>
    7.  <span data-ttu-id="3cf6a-473">コピーした ps1 スクリプトを選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-473">Select the ps1 script you just copied.</span></span>

7.  <span data-ttu-id="3cf6a-474">マイクロソフト チームの会議室のデバイスがインストールされ、2 つ目の再起動で、Microsoft の監視エージェントを構成します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-474">Microsoft Teams Rooms devices should install and configure the Microsoft Monitoring agent with the second reboot.</span></span>

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
> <span data-ttu-id="3cf6a-475">エージェントを再構成して、別のワークスペースに移動する、または最初のインストール後にプロキシの設定を変更する必要がある場合は、[エージェント ログの分析機能を維持して管理](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage)の資料を参照できます。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-475">You can refer to the article [Managing and maintaining the Log Analytics agent](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) when you need to reconfigure an agent, move it to a different workspace, or modify proxy settings after the initial installation.</span></span>

## <a name="additional-solutions"></a><span data-ttu-id="3cf6a-476">他のソリューション</span><span class="sxs-lookup"><span data-stu-id="3cf6a-476">Additional Solutions</span></span>
<span data-ttu-id="3cf6a-477"><a name="Solutions"> </a></span><span class="sxs-lookup"><span data-stu-id="3cf6a-477"></span></span>

<span data-ttu-id="3cf6a-478">Azure のモニターでは、お客様の環境を監視するため、[ソリューション ギャラリー](https://docs.microsoft.com/azure/azure-monitor/insights/solutions)からの組み込み管理ソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-478">Azure Monitor provides built-in management solutions through its [solution gallery](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) to further help you monitor your environment.</span></span> <span data-ttu-id="3cf6a-479">ワークスペースには、[警告の管理](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution)と[ログ分析エージェント稼働状態の Azure](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth)ソリューションを追加することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-479">We highly recommend that you add [Alert Management](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) and [Azure Log Analytics Agent Health](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) solutions to your workspace as well.</span></span>

> [!NOTE]
> <span data-ttu-id="3cf6a-480">エージェントの正常性のソリューションを使用して、環境内の古いか破損している Microsoft の監視エージェントを特定でき、アラート管理ソリューションには、一定期間内に発生して、アラートに関する詳細情報が用意されています。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-480">The Agent Health solution can help you identify outdated or broken Microsoft Monitoring agents within your environment, and the Alert Management solution provides details about the alerts that have been raised within a given period.</span></span>

## <a name="see-also"></a><span data-ttu-id="3cf6a-481">関連項目</span><span class="sxs-lookup"><span data-stu-id="3cf6a-481">See also</span></span>

[<span data-ttu-id="3cf6a-482">Azure のモニターを使用して Microsoft チームの会議室の管理を計画します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-482">Plan Microsoft Teams Rooms management with Azure Monitor</span></span>](azure-monitor-plan.md)

[<span data-ttu-id="3cf6a-483">Azure のモニターを使用して Microsoft チームの会議室のデバイスを管理します。</span><span class="sxs-lookup"><span data-stu-id="3cf6a-483">Manage Microsoft Teams Rooms devices with Azure Monitor</span></span>](azure-monitor-manage.md)