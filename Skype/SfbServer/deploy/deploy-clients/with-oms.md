---
title: OMS を使用した Skype Room Systems バージョン 2 の管理を展開する
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
description: この資料では、マイクロソフトの運用管理スイートを使用して、エンド ・ ツー ・ エンドの統合された方法で Skype ルーム システム v2 のデバイスの管理を展開する方法について説明します。
ms.openlocfilehash: 9a55238296452119679ff3c07147961fcec3eb7a
ms.sourcegitcommit: 0fcca2d8303da82cc00a504f4183bee50ab23eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2019
ms.locfileid: "28328279"
---
# <a name="deploy-skype-room-systems-v2-management-with-oms"></a><span data-ttu-id="da8ad-103">OMS を使用した Skype Room Systems バージョン 2 の管理を展開する</span><span class="sxs-lookup"><span data-stu-id="da8ad-103">Deploy Skype Room Systems v2 management with OMS</span></span>

<span data-ttu-id="da8ad-104">この資料では、設定およびマイクロソフトの運用管理スイートを使用して、Skype ルーム システム v2 のデバイスの統合された、エンド ・ ツー ・ エンドの管理を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-104">This article discusses how to set up and deploy integrated, end-to-end management of Skype Room Systems v2 devices by using Microsoft Operations Management Suite.</span></span>

<span data-ttu-id="da8ad-105">基本的な遠隔測定を提供するマイクロソフトの運用管理スイートを構成することができ、警告するためは、Skype の会議室のデバイスを管理します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-105">You can configure Microsoft Operations Management Suite to provide basic telemetry and alerts that will help you manage Skype meeting room devices.</span></span> <span data-ttu-id="da8ad-106">管理ソリューションが完成に近づくにつれて、追加のデータとデバイスの可用性とパフォーマンスの詳細なビューを作成する管理機能を導入することができます。</span><span class="sxs-lookup"><span data-stu-id="da8ad-106">As your management solution matures, you might decide to deploy additional data and management capabilities to create a more detailed view of device availability and performance.</span></span>

<span data-ttu-id="da8ad-107">によって、このガイドに従うと、デバイスの可用性、アプリケーションおよびハードウェアの健康状態、および Skype ルーム システム v2 のアプリケーションのバージョンの配布のレポート、詳細なステータスを取得するのに例を次のようなダッシュ ボードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="da8ad-107">By following this guide, you can use a dashboard like the following example to get detailed status reporting for device availability, application and hardware health, and Skype Room Systems v2 application version distribution.</span></span>

<span data-ttu-id="da8ad-108">![SRS v2 の OMS のサンプルの表示](../../media/Deploy_OMS_1.png "SRS v2 の OMS のサンプルの表示")</span><span class="sxs-lookup"><span data-stu-id="da8ad-108">![Sample OMS view for SRS v2](../../media/Deploy_OMS_1.png "Sample OMS view for SRS v2")</span></span>

<span data-ttu-id="da8ad-109">高いレベルでは、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da8ad-109">At a high level, you need to perform the following tasks:</span></span>


1.  [<span data-ttu-id="da8ad-110">操作の管理スイートの構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-110">Validate Operations Management Suite configuration</span></span>](with-oms.md#validate_OMS)
2.  [<span data-ttu-id="da8ad-111">管理セットアップの操作の管理スイートのテスト デバイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-111">Configure test devices for Operations Management Suite management setup</span></span>](with-oms.md#configure_test_devices)
3.  [<span data-ttu-id="da8ad-112">カスタム フィールドをマップする</span><span class="sxs-lookup"><span data-stu-id="da8ad-112">Map custom fields</span></span>](with-oms.md#Custom_fields)
4.  [<span data-ttu-id="da8ad-113">運用管理スイートで Skype ルーム システム v2 ビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-113">Define the Skype Room Systems v2 views in Operations Management Suite</span></span>](with-oms.md#Define_Views)
5.  [<span data-ttu-id="da8ad-114">警告を定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-114">Define alerts</span></span>](with-oms.md#Alerts)
6.  [<span data-ttu-id="da8ad-115">操作の管理スイートのすべてのデバイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-115">Configure all devices for Operations Management Suite</span></span>](with-oms.md#configure_all_devices)
7.  [<span data-ttu-id="da8ad-116">追加の運用管理ソフトウェア ・ パッケージ ・ ソリューションを構成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-116">Configure additional Operations Management Suite solutions</span></span>](with-oms.md#Solutions)

> [!IMPORTANT]
> <span data-ttu-id="da8ad-117">Skype のすべてのルームにエージェントの展開を開始する前に実行する必要があるいくつかの Skype ルーム システム v2 固有の手順はまだありますが、最小限の構成では、操作の管理スイートは、Windows オペレーティング システムを実行するコンピューターを監視できます、システム デバイス。</span><span class="sxs-lookup"><span data-stu-id="da8ad-117">Although with minimal configuration, the Operations Management Suite can monitor a computer running a Windows operating system, there are still some Skype Room Systems v2–specific steps that you need to take before you start deploying agents to all Skype Room Systems devices.</span></span>
> <span data-ttu-id="da8ad-118">したがって、コントロールのセットアップと構成の正しい順序ですべての構成手順を実行するを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="da8ad-118">Therefore, we highly recommend you perform all configuration steps in the right order for a controlled setup and configuration.</span></span> <span data-ttu-id="da8ad-119">最終結果の品質は、初期構成の品質に非常に依存します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-119">The quality of the end result very much depends on the quality of the initial configuration.</span></span>

## <a name="validate-operations-management-suite-configuration"></a><span data-ttu-id="da8ad-120">操作の管理スイートの構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-120">Validate Operations Management Suite configuration</span></span>
<span data-ttu-id="da8ad-121"><a name="validate_OMS"> </a></span><span class="sxs-lookup"><span data-stu-id="da8ad-121"></span></span>

<span data-ttu-id="da8ad-122">Skype ルーム システム v2 のデバイスからのログの収集を開始するのには、操作管理スイートのワークスペースが必要です。</span><span class="sxs-lookup"><span data-stu-id="da8ad-122">You need to have an Operations Management Suite workspace to start collecting logs from Skype Room Systems v2 devices.</span></span> <span data-ttu-id="da8ad-123">ワークスペースは、独自のデータ リポジトリ、データ ソース、およびソリューションの一意なログ分析環境です。</span><span class="sxs-lookup"><span data-stu-id="da8ad-123">A workspace is a unique Log Analytics environment with its own data repository, data sources, and solutions.</span></span> <span data-ttu-id="da8ad-124">既に既存のログ分析機能のワークスペースがある場合、Skype ルーム システム v2 配置を監視するために使用可能性がありますまたは作成することができます Skype ルーム システム v2 の監視に専用のログ分析ワークスペースが必要です。</span><span class="sxs-lookup"><span data-stu-id="da8ad-124">If you already have an existing Log Analytics workspace, you might use it to monitor your Skype Room Systems v2 deployment or you can create a dedicated Log Analytics workspace specific to your Skype Room Systems v2 monitoring needs.</span></span>

<span data-ttu-id="da8ad-125">[Azure ポータルでのログの分析機能のワークスペースを作成する](https://docs.microsoft.com/azure/log-analytics/log-analytics-quick-create-workspace)この資料の指示に従って、新しいログの分析機能のワークスペースを作成する場合は、</span><span class="sxs-lookup"><span data-stu-id="da8ad-125">If you need to create a new Log Analytics workspace, follow the instructions in the article [Create a Log Analytics workspace in the Azure portal](https://docs.microsoft.com/azure/log-analytics/log-analytics-quick-create-workspace)</span></span>

> [!NOTE]
> <span data-ttu-id="da8ad-126">ログ分析機能を使用して、オペレーションの管理スイートで、Azure サブスクリプションはアクティブにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="da8ad-126">To use Log Analytics with Operations Management Suite, you need to have an active Azure subscription.</span></span> <span data-ttu-id="da8ad-127">Azure サブスクリプションをお持ちでない場合は、開始点として[無料の試用版サブスクリプション](https://azure.microsoft.com/free)を作成できます。</span><span class="sxs-lookup"><span data-stu-id="da8ad-127">If you don’t have an Azure subscription, you can create [a free trial subscription](https://azure.microsoft.com/free) as a starting point.</span></span>


### <a name="configure-operations-management-suite-to-collect-skype-room-systems-v2-event-logs"></a><span data-ttu-id="da8ad-128">Skype ルーム システム v2 のイベント ログを収集するための運用管理スイートを構成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-128">Configure Operations Management Suite to collect Skype Room Systems v2 event logs</span></span>

<span data-ttu-id="da8ad-129">のみ、ログ分析機能は、設定で指定されている Windows のイベント ログからイベントを収集します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-129">Log Analytics only collects events from the Windows event logs that are specified in the settings.</span></span> <span data-ttu-id="da8ad-130">各ログには、選択した重大度のレベルのイベントのみが収集されます。</span><span class="sxs-lookup"><span data-stu-id="da8ad-130">For each log, only the events with the selected severities are collected.</span></span>

<span data-ttu-id="da8ad-131">Skype ルーム システム v2 のデバイスとアプリケーションの状態を監視するために必要なログを収集するための運用管理スイートを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da8ad-131">You need to configure Operations Management Suite to collect the logs required to monitor Skype Room Systems v2 device and application status.</span></span> <span data-ttu-id="da8ad-132">Skype ルーム システム v2 のデバイスでは、 **Skype の部屋のシステム**イベント ログを使用します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-132">Skype Room Systems v2 devices use the **Skype Room System** event log.</span></span>

<span data-ttu-id="da8ad-133">Skype ルーム システム v2 のイベントを収集する運用管理ソフトウェア ・ パッケージを構成するには、[ログ分析では、Windows イベント ログ データ ソース](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da8ad-133">To configure Operations Management Suite to collect the Skype Room Systems v2 events, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

<span data-ttu-id="da8ad-134">![イベント ログの設定](../../media/Deploy_OMS_2.png "イベント ログの設定")</span><span class="sxs-lookup"><span data-stu-id="da8ad-134">![Event log settings](../../media/Deploy_OMS_2.png "Event log settings")</span></span>


> [!IMPORTANT]
> <span data-ttu-id="da8ad-135">**Skype ルームのシステム**イベント ログを選択し、**エラー**、**警告**、および**情報**のチェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="da8ad-135">Select the **Skype Room System** event log, and then select the **Error**, **Warning**, and **Information** check boxes.</span></span>

## <a name="configure-test-devices-for-operations-management-suite-setup"></a><span data-ttu-id="da8ad-136">操作の管理スイートのセットアップのテスト デバイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-136">Configure test devices for Operations Management Suite setup</span></span>
<span data-ttu-id="da8ad-137"><a name="configure_test_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="da8ad-137"></span></span>

<span data-ttu-id="da8ad-138">Skype ルーム システム v2 に関連するイベントを監視することができる運用管理ソフトウェア ・ パッケージを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da8ad-138">You need to prepare Operations Management Suite to be able to monitor Skype Room Systems v2–related events.</span></span> <span data-ttu-id="da8ad-139">エージェントの操作の管理スイートを 1 つか 2 つ Skype ルーム システム v2 ・ デバイスに物理的にアクセスしているものがあるに配置する必要がありますから開始して、テスト デバイスは、いくつかのデータを生成し、ログ分析機能のワークスペースに押し込みます。</span><span class="sxs-lookup"><span data-stu-id="da8ad-139">To start with, you need to deploy Operations Management Suite agents to just one or two Skype Room Systems v2 devices that you have physical access to and have those test devices generate some data and push it to the Log Analytics workspace.</span></span>

### <a name="install-operations-management-suite-agents-to-test-devices"></a><span data-ttu-id="da8ad-140">デバイスをテストするのには操作の管理スイートのエージェントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="da8ad-140">Install Operations Management Suite agents to test devices</span></span>

<span data-ttu-id="da8ad-141">テスト デバイスに[接続の Windows コンピューター](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-windows)で提供されている手順を使用して操作管理スイート エージェントを展開します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-141">Deploy the Operations Management Suite agent to the test devices by using the instructions provided in [Connect Windows computers to the Log Analytics service in Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-windows).</span></span> <span data-ttu-id="da8ad-142">この記事は、監視エージェントの Windows、Skype ルーム システム v2 のデバイスを取得する操作管理スイート*ワークスペース ID*と*プライマリ ・ キー*を取得するための手順を展開するための手順に関する詳細情報を提供します。ログ分析へのエージェント接続を確認する手順、運用管理ソフトウェア ・ パッケージの展開に接続されています。</span><span class="sxs-lookup"><span data-stu-id="da8ad-142">This article gives detailed information about the steps for deploying Microsoft Monitoring Agent for Windows, instructions for obtaining the Operations Management Suite *Workspace ID* and the *primary key* to get Skype Room Systems v2 devices connected to your Operations Management Suite deployment, and steps to verify agent connectivity to Log Analytics.</span></span>

### <a name="generate-sample-skype-room-systems-events"></a><span data-ttu-id="da8ad-143">サンプル Skype ルームのシステム イベントを生成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-143">Generate sample Skype Room Systems events</span></span>

<span data-ttu-id="da8ad-144">操作の管理スイートのエージェントがテストのデバイス上に配置されると、ログ分析機能が必要なイベント ログ データを収集することを確認します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-144">After the Operations Management Suite agent is deployed onto the test devices, verify that the required event log data is collected by Log Analytics.</span></span>

1.  <span data-ttu-id="da8ad-145">[マイクロソフトの運用管理スイートのポータル](https://aka.ms/omsportal)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="da8ad-145">Sign in to the [Microsoft Operations Management Suite portal](https://aka.ms/omsportal).</span></span>

2.  <span data-ttu-id="da8ad-146">Skype ルーム システム v2 デバイスによって生成されたイベントの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-146">List the events generated by a Skype Room Systems v2 device:</span></span>
    1.  <span data-ttu-id="da8ad-147">**ログの検索**に移動し、ユーザー設定フィールドを持つレコードを取得するクエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-147">Go to **Log Search** and use a query to retrieve the records that will have the custom field.</span></span>
    2.  <span data-ttu-id="da8ad-148">サンプル クエリ。`Event | where Source == "SRS-App"`</span><span class="sxs-lookup"><span data-stu-id="da8ad-148">Sample query: `Event | where Source == "SRS-App"`</span></span>

3.  <span data-ttu-id="da8ad-149">クエリが正常なハートビート イベントを含むログ レコードを返すことを確認します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-149">Make sure that the query returns log records that include successful heartbeat events.</span></span>

4.  <span data-ttu-id="da8ad-150">ハードウェアの問題を生成し、運用管理ソフトウェア ・ パッケージに必要なイベントを記録することを検証します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-150">Generate a hardware issue, and validate that the required events are logged in Operations Management Suite.</span></span>
    1.  <span data-ttu-id="da8ad-151">Skype ルーム システム v2 のシステムのテストで周辺機器の 1 つを外します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-151">Unplug one of the peripheral devices on the test Skype Room Systems v2 system.</span></span> <span data-ttu-id="da8ad-152">カメラ、スピーカー フォン、マイク、または部屋の前面表示可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da8ad-152">This could be the camera, speakerphone, microphone, or Front Room Display</span></span>
    2.  <span data-ttu-id="da8ad-153">運用管理スイートで事前に設定するイベント ログの 10 分間待ちます。</span><span class="sxs-lookup"><span data-stu-id="da8ad-153">Wait 10 minutes for the event log to be populated in Operations Management Suite.</span></span>
    3.  <span data-ttu-id="da8ad-154">ハードウェア エラー イベントのリストにクエリを使用します。`Event | where EventID == 3001`</span><span class="sxs-lookup"><span data-stu-id="da8ad-154">Use a query to list hardware error events: `Event | where EventID == 3001`</span></span>

5.  <span data-ttu-id="da8ad-155">、アプリケーションの問題を生成し、必要なイベントを記録することを検証します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-155">Generate an application issue, and validate that the required events are logged.</span></span>
    1.  <span data-ttu-id="da8ad-156">Skype ルーム システム v2 アプリケーションの構成を変更し、不正なセッション開始プロトコル (SIP) アドレスとパスワードのペアを入力します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-156">Modify Skype Room Systems v2 application configuration, and type an incorrect Session Initiation Protocol (SIP) address/password pair.</span></span>
    2.  <span data-ttu-id="da8ad-157">運用管理スイートで事前に設定するイベント ログの 10 分間待ちます。</span><span class="sxs-lookup"><span data-stu-id="da8ad-157">Wait 10 minutes for the event log to be populated in Operations Management Suite.</span></span>
    3.  <span data-ttu-id="da8ad-158">アプリケーション エラー イベントのリストにクエリを使用します。`Event | where EventID == 2001`</span><span class="sxs-lookup"><span data-stu-id="da8ad-158">Use a query to list application error events: `Event | where EventID == 2001`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="da8ad-159">ユーザー設定フィールドを構成する前に、これらのサンプルのイベント ログが必要です。</span><span class="sxs-lookup"><span data-stu-id="da8ad-159">These sample event logs are required before custom fields can be configured.</span></span> <span data-ttu-id="da8ad-160">必要なイベント ログを収集し終えるまで、次の手順を続行しません。</span><span class="sxs-lookup"><span data-stu-id="da8ad-160">Don’t proceed to the next step until you have collected the required event logs.</span></span>

## <a name="map-custom-fields"></a><span data-ttu-id="da8ad-161">カスタム フィールドをマップする</span><span class="sxs-lookup"><span data-stu-id="da8ad-161">Map custom fields</span></span>
<span data-ttu-id="da8ad-162"><a name="Custom_fields"> </a></span><span class="sxs-lookup"><span data-stu-id="da8ad-162"></span></span>

<span data-ttu-id="da8ad-163">イベント ログから特定のデータを抽出するのにには、カスタム フィールドを使用します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-163">You use custom fields to extract specific data from the event logs.</span></span> <span data-ttu-id="da8ad-164">タイル、ダッシュ ボードの表示、および警告の後で使用するカスタム フィールドを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da8ad-164">You need to define custom fields that will be used later with your tiles, dashboard views, and alerts.</span></span> <span data-ttu-id="da8ad-165">[ログ分析でユーザー設定フィールド](https://docs.microsoft.com/azure/log-analytics/log-analytics-custom-fields)を参照してくださいし、カスタム フィールドの作成を開始する前に概念を理解します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-165">See [Custom fields in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-custom-fields) and become familiar with the concepts before you start creating your custom fields.</span></span>

<span data-ttu-id="da8ad-166">キャプチャしたイベント ログから、ユーザー設定のフィールドを抽出するには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-166">To extract your custom fields out of the captured event logs, follow these steps:</span></span>

1. <span data-ttu-id="da8ad-167">[マイクロソフトの運用管理スイートのポータル](https://aka.ms/omsportal)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="da8ad-167">Sign in to the [Microsoft Operations Management Suite portal](https://aka.ms/omsportal).</span></span>

2. <span data-ttu-id="da8ad-168">Skype ルーム システム v2 デバイスによって生成されたイベントの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-168">List the events generated by a Skype Room Systems v2 device:</span></span>
   1.  <span data-ttu-id="da8ad-169">**ログの検索**に移動し、ユーザー設定フィールドを持つレコードを取得するクエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-169">Go to **Log Search** and use a query to retrieve the records that will have the custom field.</span></span>
   2.  <span data-ttu-id="da8ad-170">サンプル クエリ。`Event | where Source == "SRS-App"`</span><span class="sxs-lookup"><span data-stu-id="da8ad-170">Sample query: `Event | where Source == "SRS-App"`</span></span>

3. <span data-ttu-id="da8ad-171">レコードのいずれかを選択、左側にあるボタンを選択し、フィールドの展開ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-171">Select one of the records, select the button to the left, and start the field extraction wizard.</span></span>

   <span data-ttu-id="da8ad-172">![フィールドの抽出ウィザード](../../media/Deploy_OMS_3.png "フィールドの抽出ウィザード")</span><span class="sxs-lookup"><span data-stu-id="da8ad-172">![Field extraction wizard](../../media/Deploy_OMS_3.png "Field extraction wizard")</span></span>

4. <span data-ttu-id="da8ad-173">RenderedDescription から抽出し、フィールドのタイトルを提供したいデータを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-173">Highlight the data you’d like to extract from the RenderedDescription and provide a Field Title.</span></span> <span data-ttu-id="da8ad-174">表 1 には、使用するフィールド名が用意されています。</span><span class="sxs-lookup"><span data-stu-id="da8ad-174">The field names that you should use are provided in Table 1.</span></span>

   <span data-ttu-id="da8ad-175">![ユーザー設定フィールドの定義](../../media/Deploy_OMS_4.png "ユーザー設定フィールドの定義")</span><span class="sxs-lookup"><span data-stu-id="da8ad-175">![Custom field definition](../../media/Deploy_OMS_4.png "Custom field definition")</span></span>

5. <span data-ttu-id="da8ad-176">*表 1*に示すようにマッピングを使用します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-176">Use the mappings shown in *Table 1*.</span></span> <span data-ttu-id="da8ad-177">運用管理スイートが自動的に追加、 \*\* \_CF\*\*文字列の新しいフィールドを定義するとき。</span><span class="sxs-lookup"><span data-stu-id="da8ad-177">Operations Management Suite will automatically add the **\_CF** string when you define the new field.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="da8ad-178">JSON との操作の管理スイートのすべてのフィールドは大文字小文字を区別することを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="da8ad-178">Remember that all JSON and Operations Management Suite fields are case-sensitive.</span></span>
> 
> <span data-ttu-id="da8ad-179">次の表に、[イベント Id] チェック ボックスをオンの状態に注意してください。</span><span class="sxs-lookup"><span data-stu-id="da8ad-179">Pay attention to the state of the EventID check box in the table below.</span></span> <span data-ttu-id="da8ad-180">カスタム フィールドの値を正常に抽出する操作の管理スイートの場合は、このチェック ボックスの状態を確認することを確認します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-180">Be sure you confirm the state of this check box for Operations Management Suite to successfully extract custom field values.</span></span>
> 
> <span data-ttu-id="da8ad-181">![ユーザー設定フィールドの定義](../../media/Deploy_OMS_5.png "ユーザー設定フィールドの定義")</span><span class="sxs-lookup"><span data-stu-id="da8ad-181">![Custom field definition](../../media/Deploy_OMS_5.png "Custom field definition")</span></span>

<span data-ttu-id="da8ad-182">**表 1**</span><span class="sxs-lookup"><span data-stu-id="da8ad-182">**Table 1**</span></span>

| <span data-ttu-id="da8ad-183">JSON フィールド</span><span class="sxs-lookup"><span data-stu-id="da8ad-183">JSON field</span></span>                   | <span data-ttu-id="da8ad-184">OMS カスタム フィールド</span><span class="sxs-lookup"><span data-stu-id="da8ad-184">OMS custom field</span></span>           | <span data-ttu-id="da8ad-185">イベント ID</span><span class="sxs-lookup"><span data-stu-id="da8ad-185">Event ID</span></span>        |
|:-----------------------------|:---------------------------|:----------------|
| <span data-ttu-id="da8ad-186">説明</span><span class="sxs-lookup"><span data-stu-id="da8ad-186">Description</span></span>                  | <span data-ttu-id="da8ad-187">SRSEventDescription_CF </span><span class="sxs-lookup"><span data-stu-id="da8ad-187">SRSEventDescription_CF</span></span>     | <span data-ttu-id="da8ad-188">選択されていません。</span><span class="sxs-lookup"><span data-stu-id="da8ad-188">Not selected</span></span>    |
| <span data-ttu-id="da8ad-189">ResourceState</span><span class="sxs-lookup"><span data-stu-id="da8ad-189">ResourceState</span></span>                | <span data-ttu-id="da8ad-190">SRSResourceState_CF</span><span class="sxs-lookup"><span data-stu-id="da8ad-190">SRSResourceState_CF</span></span>        | <span data-ttu-id="da8ad-191">選択されていません。</span><span class="sxs-lookup"><span data-stu-id="da8ad-191">Not selected</span></span>    |
| <span data-ttu-id="da8ad-192">OperationName</span><span class="sxs-lookup"><span data-stu-id="da8ad-192">OperationName</span></span>                | <span data-ttu-id="da8ad-193">SRSOperationName_CF</span><span class="sxs-lookup"><span data-stu-id="da8ad-193">SRSOperationName_CF</span></span>        | <span data-ttu-id="da8ad-194">選択されていません。</span><span class="sxs-lookup"><span data-stu-id="da8ad-194">Not selected</span></span>    |
| <span data-ttu-id="da8ad-195">OperationResult</span><span class="sxs-lookup"><span data-stu-id="da8ad-195">OperationResult</span></span>              | <span data-ttu-id="da8ad-196">SRSOperationResult_CF</span><span class="sxs-lookup"><span data-stu-id="da8ad-196">SRSOperationResult_CF</span></span>      | <span data-ttu-id="da8ad-197">選択されていません。</span><span class="sxs-lookup"><span data-stu-id="da8ad-197">Not selected</span></span>    |
| <span data-ttu-id="da8ad-198">OS</span><span class="sxs-lookup"><span data-stu-id="da8ad-198">OS</span></span>                           | <span data-ttu-id="da8ad-199">SRSOSVersion_CF</span><span class="sxs-lookup"><span data-stu-id="da8ad-199">SRSOSVersion_CF</span></span>            | <span data-ttu-id="da8ad-200">選択されていません。</span><span class="sxs-lookup"><span data-stu-id="da8ad-200">Not selected</span></span>    |
| <span data-ttu-id="da8ad-201">OSVersion</span><span class="sxs-lookup"><span data-stu-id="da8ad-201">OSVersion</span></span>                    | <span data-ttu-id="da8ad-202">SRSOSLongVersion_CF</span><span class="sxs-lookup"><span data-stu-id="da8ad-202">SRSOSLongVersion_CF</span></span>        | <span data-ttu-id="da8ad-203">選択されていません。</span><span class="sxs-lookup"><span data-stu-id="da8ad-203">Not selected</span></span>    |
| <span data-ttu-id="da8ad-204">Alias</span><span class="sxs-lookup"><span data-stu-id="da8ad-204">Alias</span></span>                        | <span data-ttu-id="da8ad-205">SRSAlias_CF</span><span class="sxs-lookup"><span data-stu-id="da8ad-205">SRSAlias_CF</span></span>                | <span data-ttu-id="da8ad-206">選択されていません。</span><span class="sxs-lookup"><span data-stu-id="da8ad-206">Not selected</span></span>    |
| <span data-ttu-id="da8ad-207">DisplayName</span><span class="sxs-lookup"><span data-stu-id="da8ad-207">DisplayName</span></span>                  | <span data-ttu-id="da8ad-208">SRSDisplayName_CF</span><span class="sxs-lookup"><span data-stu-id="da8ad-208">SRSDisplayName_CF</span></span>          | <span data-ttu-id="da8ad-209">選択されていません。</span><span class="sxs-lookup"><span data-stu-id="da8ad-209">Not selected</span></span>    |
| <span data-ttu-id="da8ad-210">AppVersion</span><span class="sxs-lookup"><span data-stu-id="da8ad-210">AppVersion</span></span>                   | <span data-ttu-id="da8ad-211">SRSAppVersion_CF</span><span class="sxs-lookup"><span data-stu-id="da8ad-211">SRSAppVersion_CF</span></span>           | <span data-ttu-id="da8ad-212">選択されていません。</span><span class="sxs-lookup"><span data-stu-id="da8ad-212">Not selected</span></span>    |
| <span data-ttu-id="da8ad-213">IPv4Address</span><span class="sxs-lookup"><span data-stu-id="da8ad-213">IPv4Address</span></span>                  | <span data-ttu-id="da8ad-214">SRSIPv4Address_CF</span><span class="sxs-lookup"><span data-stu-id="da8ad-214">SRSIPv4Address_CF</span></span>          | <span data-ttu-id="da8ad-215">選択されていません。</span><span class="sxs-lookup"><span data-stu-id="da8ad-215">Not selected</span></span>    |
| <span data-ttu-id="da8ad-216">IPv6Address</span><span class="sxs-lookup"><span data-stu-id="da8ad-216">IPv6Address</span></span>                  | <span data-ttu-id="da8ad-217">SRSIPv6Address_CF</span><span class="sxs-lookup"><span data-stu-id="da8ad-217">SRSIPv6Address_CF</span></span>          | <span data-ttu-id="da8ad-218">選択されていません。</span><span class="sxs-lookup"><span data-stu-id="da8ad-218">Not selected</span></span>    |
| <span data-ttu-id="da8ad-219">ルームの表示状態の前面</span><span class="sxs-lookup"><span data-stu-id="da8ad-219">Front of Room Display status</span></span> | <span data-ttu-id="da8ad-220">SRSFORDStatus_CF</span><span class="sxs-lookup"><span data-stu-id="da8ad-220">SRSFORDStatus_CF</span></span>           | <span data-ttu-id="da8ad-221">3001</span><span class="sxs-lookup"><span data-stu-id="da8ad-221">3001</span></span>            |
| <span data-ttu-id="da8ad-222">カメラの状態</span><span class="sxs-lookup"><span data-stu-id="da8ad-222">Camera status</span></span>                | <span data-ttu-id="da8ad-223">SRSCameraStatus_CF</span><span class="sxs-lookup"><span data-stu-id="da8ad-223">SRSCameraStatus_CF</span></span>         | <span data-ttu-id="da8ad-224">3001</span><span class="sxs-lookup"><span data-stu-id="da8ad-224">3001</span></span>            |
| <span data-ttu-id="da8ad-225">会議マイクの状態</span><span class="sxs-lookup"><span data-stu-id="da8ad-225">Conference Microphone status</span></span> | <span data-ttu-id="da8ad-226">SRSConfMicrophoneStatus_CF</span><span class="sxs-lookup"><span data-stu-id="da8ad-226">SRSConfMicrophoneStatus_CF</span></span> | <span data-ttu-id="da8ad-227">3001</span><span class="sxs-lookup"><span data-stu-id="da8ad-227">3001</span></span>            |
| <span data-ttu-id="da8ad-228">会議の発表者のステータス</span><span class="sxs-lookup"><span data-stu-id="da8ad-228">Conference Speaker status</span></span>    | <span data-ttu-id="da8ad-229">SRSConfSpeakerStatus_CF</span><span class="sxs-lookup"><span data-stu-id="da8ad-229">SRSConfSpeakerStatus_CF</span></span>    | <span data-ttu-id="da8ad-230">3001</span><span class="sxs-lookup"><span data-stu-id="da8ad-230">3001</span></span>            |
| <span data-ttu-id="da8ad-231">スピーカーの既定の状態</span><span class="sxs-lookup"><span data-stu-id="da8ad-231">Default Speaker status</span></span>       | <span data-ttu-id="da8ad-232">SRSDefaultSpeakerStatus_CF</span><span class="sxs-lookup"><span data-stu-id="da8ad-232">SRSDefaultSpeakerStatus_CF</span></span> | <span data-ttu-id="da8ad-233">3001</span><span class="sxs-lookup"><span data-stu-id="da8ad-233">3001</span></span>            |
| <span data-ttu-id="da8ad-234">モーション センサーのステータス</span><span class="sxs-lookup"><span data-stu-id="da8ad-234">Motion Sensor status</span></span>         | <span data-ttu-id="da8ad-235">SRSMotionSensorStatus_CF</span><span class="sxs-lookup"><span data-stu-id="da8ad-235">SRSMotionSensorStatus_CF</span></span>   | <span data-ttu-id="da8ad-236">3001</span><span class="sxs-lookup"><span data-stu-id="da8ad-236">3001</span></span>            |
| <span data-ttu-id="da8ad-237">HDMI 取り込みの状態</span><span class="sxs-lookup"><span data-stu-id="da8ad-237">HDMI Ingest status</span></span>           | <span data-ttu-id="da8ad-238">SRSHDMIIngestStatus_CF</span><span class="sxs-lookup"><span data-stu-id="da8ad-238">SRSHDMIIngestStatus_CF</span></span>     | <span data-ttu-id="da8ad-239">3001</span><span class="sxs-lookup"><span data-stu-id="da8ad-239">3001</span></span>            |


## <a name="define-the-skype-room-systems-v2-views-in-operations-management-suite"></a><span data-ttu-id="da8ad-240">運用管理スイートで Skype ルーム システム v2 ビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-240">Define the Skype Room Systems v2 views in Operations Management Suite</span></span>
<span data-ttu-id="da8ad-241"><a name="Define_Views"> </a></span><span class="sxs-lookup"><span data-stu-id="da8ad-241"></span></span>

<span data-ttu-id="da8ad-242">データが収集され、ユーザー設定フィールドがマップされている後、は、Skype ルーム システム v2 のイベントを監視するためのさまざまなタイルを含むダッシュ ボードを開発するのに管理スイート ビュー デザイナーの操作を使用できます。</span><span class="sxs-lookup"><span data-stu-id="da8ad-242">After data is collected and custom fields are mapped, you can use Operations Management Suite View Designer to develop a dashboard containing various tiles to monitor Skype Room Systems v2 events.</span></span> <span data-ttu-id="da8ad-243">ビュー デザイナーを使用して、次のファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-243">Use View Designer to create the following tiles.</span></span> <span data-ttu-id="da8ad-244">詳細については、[ログ分析機能でカスタム ビューを作成するビュー デザイナーの使用](https://docs.microsoft.com/azure/log-analytics/log-analytics-view-designer)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da8ad-244">For more information, see [Use View Designer to create custom views in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-view-designer)</span></span>

> [!NOTE]
> <span data-ttu-id="da8ad-245">正常に動作するダッシュ ボードのタイルのこのガイドで前述の手順への接続が完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da8ad-245">Earlier steps in this guide should have been completed for the dashboard tiles to work properly.</span></span>


### <a name="create-a-skype-room-systems-v2-dashboard-by-using-the-import-method"></a><span data-ttu-id="da8ad-246">インポート メソッドを使用して、Skype ルーム システム v2 のダッシュ ボードを作成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-246">Create a Skype Room Systems v2 dashboard by using the import method</span></span>

<span data-ttu-id="da8ad-247">操作の管理スイートのダッシュ ボードにインポートし、デバイスをすぐに監視を開始できます。</span><span class="sxs-lookup"><span data-stu-id="da8ad-247">You can import an Operations Management Suite dashboard and start monitoring your devices immediately.</span></span> <span data-ttu-id="da8ad-248">ダッシュ ボードにインポートするのには以下の手順を実行するには。</span><span class="sxs-lookup"><span data-stu-id="da8ad-248">Take the following steps to import the dashboard:</span></span>

1.  <span data-ttu-id="da8ad-249">[SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675)ダッシュ ボード ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-249">Get the [SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675) dashboard file.</span></span>
2.  <span data-ttu-id="da8ad-250">[マイクロソフトの運用管理スイートのポータル](https://aka.ms/omsportal)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="da8ad-250">Sign in to the [Microsoft Operations Management Suite portal](https://aka.ms/omsportal).</span></span>
3.  <span data-ttu-id="da8ad-251">**ビュー デザイナー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="da8ad-251">Open **View Designer**.</span></span>
4.  <span data-ttu-id="da8ad-252">**インポート**] を選択し、 **SkypeRoomSystems_v2.omsview**ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-252">Select **Import**, and then select the **SkypeRoomSystems_v2.omsview** file.</span></span>
5.  <span data-ttu-id="da8ad-253">**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-253">Select **Save**.</span></span>

### <a name="create-a-skype-room-systems-v2-dashboard-manually"></a><span data-ttu-id="da8ad-254">Skype ルーム システム v2 のダッシュ ボードを手動で作成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-254">Create a Skype Room Systems v2 dashboard manually</span></span>

<span data-ttu-id="da8ad-255">または、独自のダッシュ ボードを作成し、監視対象のタイルのみを追加できます。</span><span class="sxs-lookup"><span data-stu-id="da8ad-255">Alternatively, you can create your own dashboard and add only the tiles that you wish to monitor.</span></span>

#### <a name="configure-the-overview-tile"></a><span data-ttu-id="da8ad-256">概要タイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-256">Configure the Overview Tile</span></span>
1.  <span data-ttu-id="da8ad-257">**ビュー デザイナー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="da8ad-257">Open **View Designer**.</span></span>
2.  <span data-ttu-id="da8ad-258">**概要タイル**を選択し、ギャラリーから**2 つの数値**を選択します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-258">Select **Overview Tile**, and then select **Two numbers** from the gallery.</span></span>
3.  <span data-ttu-id="da8ad-259">**Skype ルーム システム v2**のタイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-259">Name the tile **Skype Room Systems v2**.</span></span>
4.  <span data-ttu-id="da8ad-260">**最初のタイル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-260">Define the **First Tile**:</span></span><br>
    <span data-ttu-id="da8ad-261">**凡例:** 最後の月以内にハートビートを送信するデバイス</span><span class="sxs-lookup"><span data-stu-id="da8ad-261">**Legend:** Devices that sent a heartbeat at least once within the last month</span></span><br>
    <span data-ttu-id="da8ad-262">**クエリ:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="da8ad-262">**Query:** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
5.  <span data-ttu-id="da8ad-263">**2 つ目のタイル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-263">Define the **Second Tile**:</span></span><br>
    <span data-ttu-id="da8ad-264">**凡例:** 最後の時間内にハートビートを送信するアクティブなデバイス</span><span class="sxs-lookup"><span data-stu-id="da8ad-264">**Legend:** Active devices that sent a heartbeat within the last hour</span></span><br>
    <span data-ttu-id="da8ad-265">**クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="da8ad-265">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
6.  <span data-ttu-id="da8ad-266">**適用**を選択します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-266">Select **Apply**.</span></span>

### <a name="create-a-tile-that-displays-active-devices"></a><span data-ttu-id="da8ad-267">アクティブなデバイスを表示するタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-267">Create a tile that displays active devices</span></span>
1.  <span data-ttu-id="da8ad-268">タイルを追加する**ダッシュ ボードのビュー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-268">Select **View Dashboard** to start adding your tiles.</span></span>
2.  <span data-ttu-id="da8ad-269">**_AMP_ リストに番号**を選択して、ギャラリーから</span><span class="sxs-lookup"><span data-stu-id="da8ad-269">Select **Number & list** from the gallery</span></span>
3.  <span data-ttu-id="da8ad-270">**全般**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-270">Define the **General** properties:</span></span><br>
    <span data-ttu-id="da8ad-271">**グループ タイトル:** ハートビートの状態</span><span class="sxs-lookup"><span data-stu-id="da8ad-271">**Group Title:** Heartbeat Status</span></span><br>
    <span data-ttu-id="da8ad-272">**新しいグループ:** 選択</span><span class="sxs-lookup"><span data-stu-id="da8ad-272">**New Group:** Selected</span></span>
4.  <span data-ttu-id="da8ad-273">**タイル**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-273">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="da8ad-274">**凡例:** アクティブなデバイス (ハートビートの最後の 20 分間で送信されます)</span><span class="sxs-lookup"><span data-stu-id="da8ad-274">**Legend:** Active devices (heartbeat sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="da8ad-275">\*\*タイルのクエリ: \*\* ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="da8ad-275">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span></span>
5.  <span data-ttu-id="da8ad-276">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-276">Define the **List** properties:</span></span><br>
    <span data-ttu-id="da8ad-277">**クエリの一覧を表示:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="da8ad-277">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
6.  <span data-ttu-id="da8ad-278">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-278">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="da8ad-279">**名:** 表示名</span><span class="sxs-lookup"><span data-stu-id="da8ad-279">**Name:** Display Name</span></span><br>
    <span data-ttu-id="da8ad-280">**値:** 最後のハートビート</span><span class="sxs-lookup"><span data-stu-id="da8ad-280">**Value:** Last Heartbeat</span></span>
7.  <span data-ttu-id="da8ad-281">**ナビゲーション クエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-281">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="da8ad-282">**適用**され、し、**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-282">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a><span data-ttu-id="da8ad-283">接続の問題のあるデバイスを表示するタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-283">Create a tile that displays devices that have connectivity issues</span></span>
1.  <span data-ttu-id="da8ad-284">ギャラリーから、[ **&] ボックスの一覧の番号**を選択し、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-284">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="da8ad-285">**全般**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-285">Define the **General** properties:</span></span><br>
    <span data-ttu-id="da8ad-286">**グループ タイトル:** 空のままに</span><span class="sxs-lookup"><span data-stu-id="da8ad-286">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="da8ad-287">**新しいグループ:** 選択されていません。</span><span class="sxs-lookup"><span data-stu-id="da8ad-287">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="da8ad-288">**タイル**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-288">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="da8ad-289">**凡例:** 非アクティブなデバイス (ハートビート メッセージは最後の 20 分間で送信されます)</span><span class="sxs-lookup"><span data-stu-id="da8ad-289">**Legend:** Inactive Devices (no heartbeat message sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="da8ad-290">\*\*タイルのクエリ: \*\* ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span><span class="sxs-lookup"><span data-stu-id="da8ad-290">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span></span>
4.  <span data-ttu-id="da8ad-291">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-291">Define the **List** properties:</span></span><br>
    <span data-ttu-id="da8ad-292">**クエリの一覧を表示:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="da8ad-292">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="da8ad-293">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-293">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="da8ad-294">**名:** 表示名</span><span class="sxs-lookup"><span data-stu-id="da8ad-294">**Name:** Display Name</span></span><br>
    <span data-ttu-id="da8ad-295">**値:** 最後のハートビート</span><span class="sxs-lookup"><span data-stu-id="da8ad-295">**Value:** Last Heartbeat</span></span>
6.  <span data-ttu-id="da8ad-296">**ナビゲーション クエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-296">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="da8ad-297">**適用**され、し、**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-297">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a><span data-ttu-id="da8ad-298">ハードウェア エラーのあるデバイスを表示するタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-298">Create a tile that displays devices that have a hardware error</span></span>

1.  <span data-ttu-id="da8ad-299">ギャラリーから、[ **&] ボックスの一覧の番号**を選択し、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-299">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="da8ad-300">**全般**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-300">Define the **General** properties:</span></span><br>
    <span data-ttu-id="da8ad-301">**グループ タイトル:** ハードウェアのステータス</span><span class="sxs-lookup"><span data-stu-id="da8ad-301">**Group Title:** Hardware Status</span></span><br>
    <span data-ttu-id="da8ad-302">**新しいグループ:** 選択</span><span class="sxs-lookup"><span data-stu-id="da8ad-302">**New Group:** Selected</span></span>
3.  <span data-ttu-id="da8ad-303">**タイル**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-303">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="da8ad-304">**凡例:** 最後の 1 時間以内にハードウェア エラーが発生したデバイス</span><span class="sxs-lookup"><span data-stu-id="da8ad-304">**Legend:** Devices that experienced a hardware error in the last hour</span></span> <br>
    <span data-ttu-id="da8ad-305">\*\*タイルのクエリ: \*\* ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="da8ad-305">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="da8ad-306">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-306">Define the **List** properties:</span></span><br>
    <span data-ttu-id="da8ad-307">**クエリの一覧を表示:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer```</span><span class="sxs-lookup"><span data-stu-id="da8ad-307">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer```</span></span>
5.  <span data-ttu-id="da8ad-308">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-308">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="da8ad-309">**名:** 表示名</span><span class="sxs-lookup"><span data-stu-id="da8ad-309">**Name:** Display Name</span></span><br>
    <span data-ttu-id="da8ad-310">**値:** 最後のエラー</span><span class="sxs-lookup"><span data-stu-id="da8ad-310">**Value:** Last Error</span></span>
6.  <span data-ttu-id="da8ad-311">**ナビゲーション クエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-311">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="da8ad-312">**適用**され、し、**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-312">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-skype-room-systems-v2-operating-system-versions"></a><span data-ttu-id="da8ad-313">Skype ルーム システム v2 バージョンのオペレーティング システムを表示するタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-313">Create a tile that displays Skype Room Systems v2 Operating System versions</span></span>

1.  <span data-ttu-id="da8ad-314">ギャラリーから、**ドーナツ & リスト**を選択し、新たにコピーします。</span><span class="sxs-lookup"><span data-stu-id="da8ad-314">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="da8ad-315">**全般**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-315">Define the **General** properties:</span></span><br>
    <span data-ttu-id="da8ad-316">**グループ タイトル:** Syetem の動作の詳細</span><span class="sxs-lookup"><span data-stu-id="da8ad-316">**Group Title:** Operating Syetem details</span></span> <br>
    <span data-ttu-id="da8ad-317">**新しいグループ:** 選択</span><span class="sxs-lookup"><span data-stu-id="da8ad-317">**New Group:** Selected</span></span>
3.  <span data-ttu-id="da8ad-318">**ヘッダー**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-318">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="da8ad-319">**タイトル:** オペレーティング システムのバージョン</span><span class="sxs-lookup"><span data-stu-id="da8ad-319">**Title:** Operating System versions</span></span><br>
    <span data-ttu-id="da8ad-320">**サブタイトル:** 特定の OS バージョンを実行しているデバイス</span><span class="sxs-lookup"><span data-stu-id="da8ad-320">**Subtitle:** Devices running specific OS versions</span></span>
4.  <span data-ttu-id="da8ad-321">**ドーナツ**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-321">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="da8ad-322">**クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span><span class="sxs-lookup"><span data-stu-id="da8ad-322">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span></span><br>
    <span data-ttu-id="da8ad-323">**テキストを中央揃え:** デバイス</span><span class="sxs-lookup"><span data-stu-id="da8ad-323">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="da8ad-324">**操作:** 合計</span><span class="sxs-lookup"><span data-stu-id="da8ad-324">**Operation:** Sum</span></span>
5.  <span data-ttu-id="da8ad-325">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-325">Define the **List** properties.</span></span><br>
    <span data-ttu-id="da8ad-326">**クエリの一覧を表示:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span><span class="sxs-lookup"><span data-stu-id="da8ad-326">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="da8ad-327">**グラフを非表示にする:** 選択</span><span class="sxs-lookup"><span data-stu-id="da8ad-327">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="da8ad-328">**スパーク ラインを有効にする:** 選択されていません。</span><span class="sxs-lookup"><span data-stu-id="da8ad-328">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="da8ad-329">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-329">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="da8ad-330">**名:** 表示名</span><span class="sxs-lookup"><span data-stu-id="da8ad-330">**Name:** Display Name</span></span><br>
    <span data-ttu-id="da8ad-331">**値:** 空のままに</span><span class="sxs-lookup"><span data-stu-id="da8ad-331">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="da8ad-332">**ナビゲーション クエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-332">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="da8ad-333">**適用**し、[**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-333">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-skype-room-systems-v2-application-versions"></a><span data-ttu-id="da8ad-334">Skype ルーム システム v2 のアプリケーションのバージョンを表示するタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-334">Create a tile that displays Skype Room Systems v2 application versions</span></span>

1.  <span data-ttu-id="da8ad-335">ギャラリーから、**ドーナツ & リスト**を選択し、新たにコピーします。</span><span class="sxs-lookup"><span data-stu-id="da8ad-335">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="da8ad-336">**全般**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-336">Define the **General** properties:</span></span><br>
    <span data-ttu-id="da8ad-337">**グループ タイトル:** Skype ルーム システム v2 のアプリケーションの詳細</span><span class="sxs-lookup"><span data-stu-id="da8ad-337">**Group Title:** Skype Room Systems v2 application details</span></span> <br>
    <span data-ttu-id="da8ad-338">**新しいグループ:** 選択</span><span class="sxs-lookup"><span data-stu-id="da8ad-338">**New Group:** Selected</span></span>
3.  <span data-ttu-id="da8ad-339">**ヘッダー**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-339">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="da8ad-340">**タイトル:** アプリケーションのバージョン</span><span class="sxs-lookup"><span data-stu-id="da8ad-340">**Title:** Application versions</span></span><br>
    <span data-ttu-id="da8ad-341">**サブタイトル:** 特定のアプリケーションのバージョンを実行しているデバイス</span><span class="sxs-lookup"><span data-stu-id="da8ad-341">**Subtitle:** Devices running specific application versions</span></span>
4.  <span data-ttu-id="da8ad-342">**ドーナツ**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-342">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="da8ad-343">**クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span><span class="sxs-lookup"><span data-stu-id="da8ad-343">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span></span><br>
    <span data-ttu-id="da8ad-344">**テキストを中央揃え:** デバイス</span><span class="sxs-lookup"><span data-stu-id="da8ad-344">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="da8ad-345">**操作:** 合計</span><span class="sxs-lookup"><span data-stu-id="da8ad-345">**Operation:** Sum</span></span>
5.  <span data-ttu-id="da8ad-346">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-346">Define the **List** properties.</span></span><br>
    <span data-ttu-id="da8ad-347">**クエリの一覧を表示:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span><span class="sxs-lookup"><span data-stu-id="da8ad-347">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="da8ad-348">**グラフを非表示にする:** 選択</span><span class="sxs-lookup"><span data-stu-id="da8ad-348">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="da8ad-349">**スパーク ラインを有効にする:** 選択されていません。</span><span class="sxs-lookup"><span data-stu-id="da8ad-349">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="da8ad-350">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-350">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="da8ad-351">**名:** 表示名</span><span class="sxs-lookup"><span data-stu-id="da8ad-351">**Name:** Display Name</span></span><br>
    <span data-ttu-id="da8ad-352">**値:** 空のままに</span><span class="sxs-lookup"><span data-stu-id="da8ad-352">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="da8ad-353">**ナビゲーション クエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-353">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="da8ad-354">**適用**し、[**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-354">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a><span data-ttu-id="da8ad-355">アプリケーション エラーのあるデバイスを表示するタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-355">Create a tile that displays devices that have an application error</span></span>

1.  <span data-ttu-id="da8ad-356">ギャラリーから、[ **&] ボックスの一覧の番号**を選択し、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-356">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="da8ad-357">**全般**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-357">Define the **General** properties.</span></span><br>
    <span data-ttu-id="da8ad-358">**グループ タイトル:** 空のままに</span><span class="sxs-lookup"><span data-stu-id="da8ad-358">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="da8ad-359">**新しいグループ:** 選択されていません。</span><span class="sxs-lookup"><span data-stu-id="da8ad-359">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="da8ad-360">**タイル**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-360">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="da8ad-361">**凡例:** 最後の時間でアプリケーション エラーが発生したデバイス</span><span class="sxs-lookup"><span data-stu-id="da8ad-361">**Legend:** Devices that experienced an application error in the last hour</span></span><br>
    <span data-ttu-id="da8ad-362">\*\*タイルのクエリ: \*\* ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="da8ad-362">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="da8ad-363">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-363">Define the **List** properties.</span></span><br>
    <span data-ttu-id="da8ad-364">**クエリの一覧を表示:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="da8ad-364">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="da8ad-365">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-365">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="da8ad-366">**名:** 表示名</span><span class="sxs-lookup"><span data-stu-id="da8ad-366">**Name:** Display Name</span></span><br>
    <span data-ttu-id="da8ad-367">**値:** 最後のエラー</span><span class="sxs-lookup"><span data-stu-id="da8ad-367">**Value:** Last Error</span></span>
6.  <span data-ttu-id="da8ad-368">**ナビゲーション クエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-368">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="da8ad-369">**適用**し、[**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-369">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a><span data-ttu-id="da8ad-370">再起動されているデバイスを表示するタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-370">Create a tile that displays devices that have been restarted</span></span>

1.  <span data-ttu-id="da8ad-371">ギャラリーから、[ **&] ボックスの一覧の番号**を選択し、新しいタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-371">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="da8ad-372">**全般**プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-372">Define the **General** properties.</span></span><br>
    <span data-ttu-id="da8ad-373">**グループ タイトル:** 空のままに</span><span class="sxs-lookup"><span data-stu-id="da8ad-373">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="da8ad-374">**新しいグループ:** 選択されていません。</span><span class="sxs-lookup"><span data-stu-id="da8ad-374">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="da8ad-375">**タイル**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-375">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="da8ad-376">**凡例:** デバイスのアプリケーションの再起動では、最後の 24 時間、および再起動の回数</span><span class="sxs-lookup"><span data-stu-id="da8ad-376">**Legend:** Devices where the application was restarted in the last 24 hours, and number of restarts</span></span><br>
    <span data-ttu-id="da8ad-377">\*\*タイルのクエリ: \*\* ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="da8ad-377">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="da8ad-378">**リスト**のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-378">Define the **List** properties.</span></span><br>
    <span data-ttu-id="da8ad-379">**クエリの一覧を表示:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span><span class="sxs-lookup"><span data-stu-id="da8ad-379">**List Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span></span>
5.  <span data-ttu-id="da8ad-380">**列のタイトル**を定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-380">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="da8ad-381">**名:** 表示名</span><span class="sxs-lookup"><span data-stu-id="da8ad-381">**Name:** Display Name</span></span><br>
    <span data-ttu-id="da8ad-382">**値:** 再起動の回数</span><span class="sxs-lookup"><span data-stu-id="da8ad-382">**Value:** Number of Restarts</span></span>
6.  <span data-ttu-id="da8ad-383">**ナビゲーション クエリ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-383">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="da8ad-384">**適用**し、[**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-384">Select **Apply** and then **Close**.</span></span>
8.  <span data-ttu-id="da8ad-385">ダッシュ ボードを保存する**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-385">Select **Save** to save your dashboard.</span></span>

<span data-ttu-id="da8ad-386">ここで、ビューの作成が完了しました。</span><span class="sxs-lookup"><span data-stu-id="da8ad-386">Now you’ve completed creating your views.</span></span>

<span data-ttu-id="da8ad-387">マイクロソフトの運用管理スイートのポータルまたは操作の管理スイートのモバイル クライアントの[Windows Phone を](https://www.microsoft.com/en-us/store/p/microsoft-operations-management-suite/9wzdncrfjz2r)、 [iOS](https://itunes.apple.com/us/app/microsoft-operations-management-suite/id1042424859)、 [Android](https://play.google.com/store/apps/details?id=com.microsoft.operations.AndroidPhone)を使用するには、ビューにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="da8ad-387">You can use the Microsoft Operations Management Suite portal or Operations Management Suite mobile clients for [Windows Phone](https://www.microsoft.com/en-us/store/p/microsoft-operations-management-suite/9wzdncrfjz2r), [iOS](https://itunes.apple.com/us/app/microsoft-operations-management-suite/id1042424859), or [Android](https://play.google.com/store/apps/details?id=com.microsoft.operations.AndroidPhone) to access your views.</span></span>

## <a name="configure-alerts-in-operations-management-suite"></a><span data-ttu-id="da8ad-388">運用管理スイートで警告を構成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-388">Configure Alerts in Operations Management Suite</span></span>
<span data-ttu-id="da8ad-389"><a name="Alerts"></a> 、Skype ルーム システムとバージョン 2 のデバイスが問題を検出すると、マイクロソフトの運用管理スイートは、問題の詳細を管理者に通知するアラートを発生させることもできます。</span><span class="sxs-lookup"><span data-stu-id="da8ad-389"><a name="Alerts"> </a> When a Skype Room Systems v2 device encounters an issue, Microsoft Operations Management Suite can raise alerts to notify the administrators with the details of the issue.</span></span>

<span data-ttu-id="da8ad-390">運用管理スイートには、定期的にスケジュールされたログの検索を実行する組み込みの警告メカニズムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="da8ad-390">Operations Management Suite includes a built-in alerting mechanism that runs through scheduled log searches at regular intervals.</span></span> <span data-ttu-id="da8ad-391">ログの検索の結果には、いくつか特定の条件が一致する場合は、アラートのレコードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="da8ad-391">If the results of the log search match some particular criteria, an alert record is created.</span></span>

<span data-ttu-id="da8ad-392">![OMS は警告メカニズム](../../media/Deploy_OMS_6.png "OMS は警告メカニズム")</span><span class="sxs-lookup"><span data-stu-id="da8ad-392">![OMS alert mechanism](../../media/Deploy_OMS_6.png "OMS alert mechanism")</span></span>

<span data-ttu-id="da8ad-393">自動的に、ルールでは、事前に警告を通知または別のプロセスを起動する 1 つまたは複数のアクションを実行できるし。</span><span class="sxs-lookup"><span data-stu-id="da8ad-393">The rule can then automatically run one or more actions to proactively notify you of the alert or invoke another process.</span></span> <span data-ttu-id="da8ad-394">操作の管理スイートのアラートを使用可能なオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="da8ad-394">The possible options with Operations Management Suite alerts are:</span></span>
-   <span data-ttu-id="da8ad-395">電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-395">Sending an email</span></span>
-   <span data-ttu-id="da8ad-396">HTTP POST 要求を外部プロセスを起動します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-396">Invoking an external process through an HTTP POST request</span></span>
-   <span data-ttu-id="da8ad-397">Runbook を Azure のオートメーション サービスの開始</span><span class="sxs-lookup"><span data-stu-id="da8ad-397">Starting a runbook in Azure Automation service</span></span>

<span data-ttu-id="da8ad-398">運用管理スイートでのアラートの詳細については、[ログ分析機能で通知を理解する](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da8ad-398">See [Understanding alerts in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts) to learn more about the alerts in Operations Management Suite.</span></span>

> [!NOTE]
> <span data-ttu-id="da8ad-399">次の例は、Skype ルーム システム v2 デバイスは、ハードウェアまたはアプリケーション エラーを生成する場合に電子メール警告を送信します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-399">The following examples send email alerts when a Skype Room Systems v2 device generates a hardware or an application error.</span></span>


### <a name="configure-an-email-alert-for-skype-room-systems-v2-hardware-issues"></a><span data-ttu-id="da8ad-400">Skype ルーム システム v2 のハードウェアの問題に関する電子メール通知を構成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-400">Configure an email alert for Skype Room Systems v2 hardware issues</span></span>

<span data-ttu-id="da8ad-401">最後の時間内でハードウェアの問題があった Skype ルーム システム v2 のデバイスを確認する警告ルールを構成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-401">Configure an alert rule that checks for Skype Room Systems v2 devices that have had hardware issues within the last hour.</span></span>
1.  <span data-ttu-id="da8ad-402">[マイクロソフトの運用管理スイートのポータル](https://aka.ms/omsportal)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="da8ad-402">Sign in to the [Microsoft Operations Management Suite portal](https://aka.ms/omsportal).</span></span>

2.  <span data-ttu-id="da8ad-403">**ログの検索対象**を選択します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-403">Select **Log Search**.</span></span>

3.  <span data-ttu-id="da8ad-404">次のクエリを入力し、し、[**実行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-404">Enter the following query, and then select **Run**.</span></span><br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

4.  <span data-ttu-id="da8ad-405">クエリを実行すると、**アラート**を選択します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-405">After the query is executed, select **Alert**.</span></span> <span data-ttu-id="da8ad-406">**警告ルールの追加**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da8ad-406">This will open the **Add Alert Rule** page.</span></span>

5.  <span data-ttu-id="da8ad-407">以下の情報を使用して通知設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-407">Configure alert settings by using the information below:</span></span><br>
    <span data-ttu-id="da8ad-408">**ルールの名前:** Skype ルーム システム v2 ハードウェア障害の警告</span><span class="sxs-lookup"><span data-stu-id="da8ad-408">**Rule Name:** Skype Room Systems v2 Hardware Failure Alert</span></span><br>
    <span data-ttu-id="da8ad-409">**説明:** 最後の時間内でハードウェアの問題が発生したデバイスの一覧</span><span class="sxs-lookup"><span data-stu-id="da8ad-409">**Description:** List of devices that encountered a hardware issue within the last hour</span></span><br>
    <span data-ttu-id="da8ad-410">**重要度:** 重要です</span><span class="sxs-lookup"><span data-stu-id="da8ad-410">**Severity:** Critical</span></span><br>
    <span data-ttu-id="da8ad-411">**クエリ:** 事前設定の検索クエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-411">**Query:** Use the prepopulated search query</span></span><br>
    <span data-ttu-id="da8ad-412">**時間:** 1 時間</span><span class="sxs-lookup"><span data-stu-id="da8ad-412">**Time Window:** 1 hour</span></span><br>
    <span data-ttu-id="da8ad-413">**通知の頻度:** 1 時間</span><span class="sxs-lookup"><span data-stu-id="da8ad-413">**Alert Frequency:** 1 hour</span></span><br>
    <span data-ttu-id="da8ad-414">**結果の数:** 0 より大きい</span><span class="sxs-lookup"><span data-stu-id="da8ad-414">**Number of results:** Greater than 0</span></span><br>
    <span data-ttu-id="da8ad-415">**電子メールの件名:** Skype ルーム システム v2 ハードウェア障害の警告</span><span class="sxs-lookup"><span data-stu-id="da8ad-415">**Email Subject:** Skype Room Systems v2 Hardware Failure Alert</span></span><br>
    <span data-ttu-id="da8ad-416">**受信者:** 区切り記号としてセミコロンを使用して、電子メール アドレスが含まれます</span><span class="sxs-lookup"><span data-stu-id="da8ad-416">**Recipients:** Include the email addresses, using semicolons as separators</span></span><br>

6.  <span data-ttu-id="da8ad-417">**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-417">Select **Save**.</span></span>

### <a name="configure-an-email-alert-for-skype-room-systems-v2-application-issues"></a><span data-ttu-id="da8ad-418">Skype ルーム システム v2 のアプリケーションの問題に関する電子メール通知を構成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-418">Configure an email alert for Skype Room Systems v2 application issues</span></span>

<span data-ttu-id="da8ad-419">Skype ルーム システムの最後の時間内でアプリケーションの問題があった v2 デバイスを確認する警告のルールを構成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-419">Configure an alert rule, that checks for Skype Room Systems v2 devices that have had application issues within the last hour.</span></span>
1.  <span data-ttu-id="da8ad-420">**ログの検索対象**を選択します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-420">Select **Log Search**.</span></span>

2.  <span data-ttu-id="da8ad-421">次のクエリを入力し、し、[**実行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-421">Enter the following query, and then select **Run**.</span></span><br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

3.  <span data-ttu-id="da8ad-422">クエリを実行すると、**アラート**を選択します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-422">After the query is executed, select **Alert**.</span></span> <span data-ttu-id="da8ad-423">**警告ルールの追加**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da8ad-423">This will open the **Add Alert Rule** page.</span></span>

4.  <span data-ttu-id="da8ad-424">以下の情報を使用して通知設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-424">Configure alert settings by using the information below:</span></span><br>
    <span data-ttu-id="da8ad-425">**ルールの名前:** Skype ルーム システム v2 アプリケーション エラー アラート</span><span class="sxs-lookup"><span data-stu-id="da8ad-425">**Rule Name:** Skype Room Systems v2 Application Failure Alert</span></span><br>
    <span data-ttu-id="da8ad-426">**説明:** 最後の時間内でアプリケーションの問題が発生したデバイスの一覧</span><span class="sxs-lookup"><span data-stu-id="da8ad-426">**Description:** List of devices that encountered an application issue within the last hour</span></span><br>
    <span data-ttu-id="da8ad-427">**重要度:** 重要です</span><span class="sxs-lookup"><span data-stu-id="da8ad-427">**Severity:** Critical</span></span><br>
    <span data-ttu-id="da8ad-428">**クエリ:** 事前設定の検索クエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-428">**Query:** Use the prepopulated search query</span></span><br>
    <span data-ttu-id="da8ad-429">**時間:** 1 時間</span><span class="sxs-lookup"><span data-stu-id="da8ad-429">**Time Window:** 1 hour</span></span><br>
    <span data-ttu-id="da8ad-430">**通知の頻度:** 1 時間</span><span class="sxs-lookup"><span data-stu-id="da8ad-430">**Alert Frequency:** 1 hour</span></span><br>
    <span data-ttu-id="da8ad-431">**結果の数:** 0 より大きい</span><span class="sxs-lookup"><span data-stu-id="da8ad-431">**Number of results:** Greater than 0</span></span><br>
    <span data-ttu-id="da8ad-432">**電子メールの件名:** Skype ルーム システム v2 アプリケーション エラー アラート</span><span class="sxs-lookup"><span data-stu-id="da8ad-432">**Email Subject:** Skype Room Systems v2 Application Failure Alert</span></span><br>
    <span data-ttu-id="da8ad-433">**受信者:** 区切り記号としてセミコロンを使用して、電子メール アドレスが含まれます</span><span class="sxs-lookup"><span data-stu-id="da8ad-433">**Recipients:** Include the email addresses, using semicolons as separators</span></span>

5.  <span data-ttu-id="da8ad-434">**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-434">Select **Save**.</span></span>

<span data-ttu-id="da8ad-435">警告の定義を完了しました。</span><span class="sxs-lookup"><span data-stu-id="da8ad-435">Now you’ve completed defining alerts.</span></span> <span data-ttu-id="da8ad-436">上記の例を使用して、別のアラートを定義できます。</span><span class="sxs-lookup"><span data-stu-id="da8ad-436">You can define additional alerts by using the examples above.</span></span>

<span data-ttu-id="da8ad-437">アラートが生成されると、最後の時間内で問題が発生しているデバイスを一覧表示する電子メールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da8ad-437">When an alert is generated, you’ll get an email that lists the devices that encountered an issue within the last hour.</span></span>

<span data-ttu-id="da8ad-438">![サンプル OMS のアラートの電子メール](../../media/Deploy_OMS_7.png "サンプル OMS のアラートの電子メール")</span><span class="sxs-lookup"><span data-stu-id="da8ad-438">![Sample OMS alert email](../../media/Deploy_OMS_7.png "Sample OMS alert email")</span></span>

<span data-ttu-id="da8ad-439">ページを使用して、警告の設定、既存の警告の構成を変更するのにはまたはを無効にするか、警告を削除します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-439">You use an alert settings page to modify an existing alert configuration, or to disable or remove an alert.</span></span>

<span data-ttu-id="da8ad-440">![OMS の警告の設定](../../media/Deploy_OMS_8.png "OMS の警告の設定")</span><span class="sxs-lookup"><span data-stu-id="da8ad-440">![OMS alert settings](../../media/Deploy_OMS_8.png "OMS alert settings")</span></span>

> [!NOTE]
> <span data-ttu-id="da8ad-441">Azure ポータルを使用して追加または、Azure に操作の管理スイートの警告を拡張するため、操作の管理スイートのワークスペースが設定されている場合、操作の管理スイートのアラートを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da8ad-441">You might need to use the Azure portal to add or modify Operations Management Suite alerts if your Operations Management Suite workspace is configured to extend the Operations Management Suite alerts into Azure.</span></span> <span data-ttu-id="da8ad-442">詳細については、 [Azure に OMS のポータルから移動できるようにする通知](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-alerts-extend)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da8ad-442">For more details, see [Extend alerts from OMS portal into Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-alerts-extend).</span></span>

## <a name="configure-all-devices-for-operations-management-suite"></a><span data-ttu-id="da8ad-443">操作の管理スイートのすべてのデバイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-443">Configure all devices for Operations Management Suite</span></span>
<span data-ttu-id="da8ad-444"><a name="configure_all_devices"></a>ダッシュ ボード、アラートを構成した後を設定し、監視の展開を完了するすべての Skype ルーム システム v2 のデバイスでの操作の管理スイートのエージェントを構成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-444"><a name="configure_all_devices"> </a> After the dashboards and alerts are configured, you can set up and configure Operations Management Suite agents on all Skype Room Systems v2 devices to complete your monitoring deployment.</span></span>

<span data-ttu-id="da8ad-445">インストールし、各デバイス上の操作の管理スイートのエージェントを手動で構成できますが、既存のソフトウェア展開ツールおよび方法を活用するを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="da8ad-445">Although you can install and configure the Operations Management Suite agents manually on each device, we highly recommend you leverage existing software deployment tools and methods.</span></span>

<span data-ttu-id="da8ad-446">最初に、Skype ルーム システム v2 のデバイスを作成する場合は、ビルド処理の一部として操作の管理スイートのエージェントのセットアップと構成手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="da8ad-446">If you’re building your Skype Room Systems v2 devices for the first time, you might want to include the Operations Management Suite agent setup and configuration steps as part of your build process.</span></span> <span data-ttu-id="da8ad-447">詳細については、[コマンド ・ ラインを使用してエージェントのインストール](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-windows#install-the-agent-using-the-command-line)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da8ad-447">For more information, see [Install the agent using the command line](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-windows#install-the-agent-using-the-command-line).</span></span>

### <a name="deploying-operations-management-suite-agents-by-using-a-group-policy-object"></a><span data-ttu-id="da8ad-448">グループ ポリシー オブジェクトを使用して、オペレーションの管理スイートのエージェントを展開します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-448">Deploying Operations Management Suite agents by using a Group Policy Object</span></span>

<span data-ttu-id="da8ad-449">既にを展開した場合、Skype ルーム システム v2 のデバイス管理ソフトウェア ・ パッケージの操作を実装する前を設定し、Active Directory グループ ポリシーを使用してエージェントを構成するのに提供されているスクリプトを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="da8ad-449">If you already deployed your Skype Room Systems v2 devices before you implement Operations Management Suite, you can use the provided script to set up and configure the agents by using Active Directory group policies.</span></span>

1.  <span data-ttu-id="da8ad-450">共有のネットワーク パスを作成し、**ドメイン コンピューター**グループに読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-450">Create a shared network path and grant read access to **Domain Computers** group.</span></span>

2.  <span data-ttu-id="da8ad-451">運用管理スイート エージェントの Windows からの 64 ビット バージョンをダウンロードします。<https://go.microsoft.com/fwlink/?LinkID=517476></span><span class="sxs-lookup"><span data-stu-id="da8ad-451">Download the 64-bit version of the Operations Management Suite Agent for Windows from <https://go.microsoft.com/fwlink/?LinkID=517476></span></span>

3.  <span data-ttu-id="da8ad-452">ネットワーク共有には、セットアップ パッケージの内容を抽出します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-452">Extract the contents of the setup package into the network share.</span></span>
    1.  <span data-ttu-id="da8ad-453">コマンド プロンプト ウィンドウを開き、 **MMASetup AMD64.exe/c**を実行し、</span><span class="sxs-lookup"><span data-stu-id="da8ad-453">Open a Command Prompt window, and then execute **MMASetup-AMD64.exe /c**</span></span>
    2.  <span data-ttu-id="da8ad-454">作成した共有を指定し、コンテンツを抽出します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-454">Specify the share you just created, and extract the content.</span></span>

4.  <span data-ttu-id="da8ad-455">新しいグループ ポリシー オブジェクトを作成し、Skype ルーム システム v2 のコンピューター アカウントが格納されている組織単位に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="da8ad-455">Create a new Group Policy Object and assign it to the organizational unit where Skype Room Systems v2 machine accounts are located.</span></span>

5.  <span data-ttu-id="da8ad-456">PowerShell 実行ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-456">Configure PowerShell execution policy:</span></span>
    1.  <span data-ttu-id="da8ad-457">新しく作成したグループ ポリシー オブジェクトを編集し、コンピューターの構成に移動\\ポリシー\\管理用テンプレート\\Windows コンポーネントの\\Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="da8ad-457">Edit the newly created Group Policy Object and navigate to Computer Configuration \\ Policies \\ Administrative Templates \\ Windows Components \\ Windows PowerShell</span></span>
    2.  <span data-ttu-id="da8ad-458">**スクリプトの実行を有効に**するを有効にして、**実行ポリシー**を**ローカルのスクリプトを許可する**に設定します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-458">Enable the **Turn on Script Execution** and set **Execution Policy** to **Allow Local Scripts**.</span></span>

6.  <span data-ttu-id="da8ad-459">スタートアップ ・ スクリプトを構成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-459">Configure the startup script:</span></span>
    1.  <span data-ttu-id="da8ad-460">次のスクリプトをコピーし、インストールを OMSAgent.ps1 として保存します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-460">Copy the following script and save it as Install-OMSAgent.ps1.</span></span>
    2.  <span data-ttu-id="da8ad-461">構成に合わせて、WorkspaceId、WorkspaceKey、および SetupPath のパラメーターを変更します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-461">Modify WorkspaceId, WorkspaceKey, and SetupPath parameters to match your configuration.</span></span>
    3.  <span data-ttu-id="da8ad-462">同じグループ ポリシー オブジェクトを編集し、コンピューターの構成に移動\\ポリシー \\ Windows の設定\\スクリプト (スタートアップ/シャット ダウン)</span><span class="sxs-lookup"><span data-stu-id="da8ad-462">Edit the same Group Policy Object and navigate to Computer Configuration \\ Policies \\ Windows Settings \\ Scripts (Startup/Shutdown)</span></span>
    4.  <span data-ttu-id="da8ad-463">ダブルクリックして**起動**を選択し、 **PowerShell スクリプト**します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-463">Double-click to select **Startup**, and then select **PowerShell Scripts**.</span></span>
    5.  <span data-ttu-id="da8ad-464">**ファイルを表示**] を選択し、そのフォルダーに**インストールを OMSAgent.ps1**ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="da8ad-464">Select **Show Files**, and then copy the **Install-OMSAgent.ps1** file to that folder.</span></span>
    6.  <span data-ttu-id="da8ad-465">**追加**して、**参照**を選択します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-465">Select **Add**, and then **Browse**.</span></span>
    7.  <span data-ttu-id="da8ad-466">コピーした ps1 スクリプトを選択します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-466">Select the ps1 script you just copied.</span></span>

7.  <span data-ttu-id="da8ad-467">Skype ルーム システム v2 のデバイスがインストールされ、2 つ目の再起動で、Microsoft の監視エージェントを構成します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-467">Skype Room Systems v2 devices should install and configure the Microsoft Monitoring agent with the second reboot.</span></span>


~~~
```
# Install-OMSAgent.ps1
<#
Date:        04/20/2018
Script:      Install-OMSAgent.ps1
Version:     1.0
#>

# Set the parameters
$WorkspaceId = "<your workspace id>"
$WorkspaceKey = "<your workspace key>"
$SetupPath = "\\Server\Share"

$SetupParameters = "/qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1 OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE=0 OPINSIGHTS_WORKSPACE_ID=$WorkspaceId OPINSIGHTS_WORKSPACE_KEY=$WorkspaceKey AcceptEndUserLicenseAgreement=1"

# $SetupParameters = $SetupParameters + " OPINSIGHTS_PROXY_URL=<Proxy server URL> OPINSIGHTS_PROXY_USERNAME=<Proxy server username> OPINSIGHTS_PROXY_PASSWORD=<Proxy server password>"

# Start PowerShell logging
Start-Transcript -Path C:\OMSAgentInstall.Log

# Check if the Microsoft Monitoring Agent is installed
$mma = New-Object -ComObject 'AgentConfigManager.MgmtSvcCfg'

# Check if the Microsoft Monitoring agent is installed
if (!$mma)
{
    #Install agent
    Start-Process -FilePath "$SetupPath\Setup.exe" -ArgumentList $SetupParameters -ErrorAction Stop -Wait
}

# Check if the agent has a valid configuration
$CheckOMS = $mma.GetCloudWorkspace($WorkspaceId).AgentId
if (!$CheckOMS)
{
    # Apply new configuration
    $mma.AddCloudWorkspace($WorkspaceId, $WorkspaceKey)
    $mma.ReloadConfiguration()
}

Stop-Transcript

```
~~~

> [!NOTE]
> <span data-ttu-id="da8ad-468">エージェントを再構成して、別のワークスペースに移動する、または最初のインストール後にプロキシの設定を変更する必要がある場合は、[エージェント ログの分析機能を維持して管理](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-manage)の資料を参照できます。</span><span class="sxs-lookup"><span data-stu-id="da8ad-468">You can refer to the article [Managing and maintaining the Log Analytics agent](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-manage) when you need to reconfigure an agent, move it to a different workspace, or modify proxy settings after the initial installation.</span></span>

## <a name="additional-solutions"></a><span data-ttu-id="da8ad-469">他のソリューション</span><span class="sxs-lookup"><span data-stu-id="da8ad-469">Additional Solutions</span></span>
<span data-ttu-id="da8ad-470"><a name="Solutions"> </a></span><span class="sxs-lookup"><span data-stu-id="da8ad-470"></span></span>

<span data-ttu-id="da8ad-471">操作の管理スイートは、お客様の環境を監視するため、[ソリューション ギャラリー](https://docs.microsoft.com/azure/log-analytics/log-analytics-add-solutions)でソリューションを組み込みを提供します。</span><span class="sxs-lookup"><span data-stu-id="da8ad-471">Operations Management Suite provides built-in solutions through its [solution gallery](https://docs.microsoft.com/azure/log-analytics/log-analytics-add-solutions) to further help you monitor your environment.</span></span> <span data-ttu-id="da8ad-472">操作の管理スイートのワークスペースを同様に、[警告の管理](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)と[エージェントの稼働状態](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-agenthealth)のソリューションを追加することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="da8ad-472">We highly recommend that you add [Alert Management](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) and [Agent Health](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-agenthealth) solutions to your Operations Management Suite workspace as well.</span></span>

<span data-ttu-id="da8ad-473">![OMS ビュー](../../media/Deploy_OMS_9.png "OMS ビュー")</span><span class="sxs-lookup"><span data-stu-id="da8ad-473">![OMS views](../../media/Deploy_OMS_9.png "OMS views")</span></span>

> [!NOTE]
> <span data-ttu-id="da8ad-474">エージェントの正常性のソリューションを使用して、お使いの環境では、古いか破損している操作の管理スイートのエージェントを特定でき、アラート管理ソリューションには、一定期間内に発生して、アラートに関する詳細情報が用意されています。</span><span class="sxs-lookup"><span data-stu-id="da8ad-474">The Agent Health solution can help you identify outdated or broken Operations Management Suite agents within your environment, and the Alert Management solution provides details about the alerts that have been raised within a given period.</span></span>

## <a name="see-also"></a><span data-ttu-id="da8ad-475">関連項目</span><span class="sxs-lookup"><span data-stu-id="da8ad-475">See also</span></span>

[<span data-ttu-id="da8ad-476">OMS を使用して Skype Room Systems バージョン 2 の管理を計画する</span><span class="sxs-lookup"><span data-stu-id="da8ad-476">Plan Skype Room Systems v2 management with OMS</span></span>](../../plan-your-deployment/clients-and-devices/oms-management.md)

[<span data-ttu-id="da8ad-477">OMS を使用した Skype Room Systems のデバイスを管理する</span><span class="sxs-lookup"><span data-stu-id="da8ad-477">Manage Skype Room Systems v2 devices with OMS</span></span>](../../manage/skype-room-systems-v2/oms.md)
