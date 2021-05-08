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
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a>を使用 :::no-loc text="Microsoft Teams Rooms"::: して管理をデプロイする :::no-loc text="Azure Monitor":::

この記事では、 を使用してデバイスの統合されたエンドツーエンド管理を設定およびデプロイする方法 :::no-loc text="Microsoft Teams Rooms"::: について説明します :::no-loc text="Azure Monitor"::: 。

内を構成 :::no-loc text="Log Analytics"::: して、会議室デバイスの管理に役立つ基本的な :::no-loc text="Azure Monitor"::: テレメトリとアラート :::no-loc text="Microsoft Teams Rooms"::: を提供できます。 管理ソリューションの成熟に合わせ、追加のデータと管理機能をデプロイして、デバイスの可用性とパフォーマンスの詳細なビューを作成できます。

このガイドに従って、次の例のようなダッシュボードを使用して、デバイスの可用性、アプリケーションとハードウェアの正常性、アプリケーションとオペレーティング システムのバージョンの配布に関する詳細な状態レポート :::no-loc text="Microsoft Teams Rooms"::: を取得できます。

![サンプルの Log Analytics ビューのスクリーンショット (Microsoft Teams ミーティング](../media/Deploy-Azure-Monitor-1.png "サンプル Log Analytics ビュー (Microsoft Teams ミーティング")

高いレベルでは、次のタスクを実行する必要があります。


1. [構成の :::no-loc text="Log Analytics"::: 検証](azure-monitor-deploy.md#validate_LogAnalytics)
2. [管理セットアップ用にテスト デバイス :::no-loc text="Log Analytics"::: を構成する](azure-monitor-deploy.md#configure_test_devices)
3. [カスタム フィールドをマップする](azure-monitor-deploy.md#Custom_fields)
4. [でビュー :::no-loc text="Microsoft Teams Rooms"::: を定義する :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [アラートを定義する](azure-monitor-deploy.md#Alerts)
6. [監視用にすべてのデバイスを構成する](azure-monitor-deploy.md#configure_all_devices)
7. [その他のソリューションを :::no-loc text="Azure Monitor"::: 構成する](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> 最小限の構成では、オペレーティング システムを実行しているコンピューターを監視することができますが、すべてのデバイスへのエージェントのデプロイを開始する前に実行する必要があるいくつかの具体的な手順がまだ :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: :::no-loc text="Windows"::: :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Microsoft Teams Rooms"::: 存在します。
> そのため、制御されたセットアップと構成に対して、すべての構成手順を適切な順序で実行することを強くお勧めします。 結果の品質は、初期構成の品質によって大きな違いがあります。

## <a name="validate-no-loc-textlog-analytics-configuration"></a>構成の :::no-loc text="Log Analytics"::: 検証
<a name="validate_LogAnalytics"> </a>

デバイスからログの収集 :::no-loc text="Log Analytics"::: を開始するには、ワークスペースが必要 :::no-loc text="Microsoft Teams Rooms"::: です。 ワークスペースは、独自の :::no-loc text="Log Analytics"::: データ リポジトリ、データ ソース、ソリューションを備える一意の環境です。 既存のワークスペースが既に存在する場合は、それを使用してデプロイを監視するか、または監視ニーズに固有の専用ワークスペース :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Log Analytics"::: を :::no-loc text="Microsoft Teams Rooms"::: 作成できます。

新しいワークスペースを作成する必要がある場合は、「ポータルでワークスペースを作成する」の :::no-loc text="Log Analytics"::: [ :::no-loc text="Log Analytics"::: 手順に従 :::no-loc text="Azure"::: ってください。](/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> で使用 :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor"::: するには、アクティブなサブスクリプションが必要 :::no-loc text="Azure"::: です。 サブスクリプションをお持ちでない :::no-loc text="Azure"::: 場合は、開始点として[](https://azure.microsoft.com/free)無料試用版サブスクリプションを作成できます。

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>イベント :::no-loc text="Log Analytics"::: ログを収集 :::no-loc text="Microsoft Teams Rooms"::: する構成

:::no-loc text="Log Analytics"::: 設定で指定されているイベント :::no-loc text="Windows"::: ログからのイベントのみを収集します。 ログごとに、選択した重大度のイベントだけが収集されます。

デバイスとアプリケーションの :::no-loc text="Log Analytics"::: 状態を監視するために必要なログを収集するために :::no-loc text="Microsoft Teams Rooms"::: 構成する必要があります。 :::no-loc text="Microsoft Teams Rooms"::: デバイスはイベント ログ **:::no-loc text="Skype Room System":::** を使用します。

イベントを :::no-loc text="Log Analytics"::: 収集するために構成 :::no-loc text="Microsoft Teams Rooms"::: するには、 の[ :::no-loc text="Windows"::: イベント ログ データ :::no-loc text="Azure Monitor"::: ソースに関するページを参照してください。](/azure/azure-monitor/platform/data-sources-windows-events)

![イベント ログ設定のスクリーンショット](../media/Deploy-Azure-Monitor-2.png "イベント ログの設定")

> [!IMPORTANT]
> イベント ログの設定を構成し、イベント ログ名として「」と入力し、[エラー]、[警告]、および [情報] :::no-loc text="Windows"::: **:::no-loc text="Skype Room System":::** チェック ボックスをオンにします。   

## <a name="configure-test-devices-for-azure-monitoring"></a>Azure Monitoring のテスト デバイスを構成する
<a name="configure_test_devices"> </a>

関連するイベント :::no-loc text="Log Analytics"::: を監視できる状態 :::no-loc text="Microsoft Teams Rooms"::: を準備する必要があります。 最初に、物理的にアクセスできる 1 台または 2 台のデバイスにエージェントをデプロイし、それらのテスト デバイスにデータを生成してワークスペースにプッシュする :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: 必要 :::no-loc text="Log Analytics"::: があります。

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>エージェント :::no-loc text="Microsoft Monitoring"::: をインストールしてデバイスをテストする

エージェントをテスト デバイスにデプロイするには、次のコンピューターに関するページに記載Connectを使用して :::no-loc text="Microsoft Monitoring"::: [、 :::no-loc text="Windows"::: :::no-loc text="Log Analytics"::: のサービスにデプロイします :::no-loc text="Azure"::: ](/azure/azure-monitor/platform/agent-windows)。 この記事では、エージェントをデプロイする手順について詳しく説明します。ワークスペース ID _ と _ 主キー :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Windows"::: :::no-loc text="Log Analytics":::  * *** :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: を取得してデプロイに接続するデバイスを取得する手順と、インスタンスへのエージェント接続を確認する手順について説明します。

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>サンプル イベントを生成 :::no-loc text="Microsoft Teams Rooms"::: する

エージェントを :::no-loc text="Microsoft Monitoring"::: テスト デバイスにデプロイした後、必要なイベント ログ データが によって収集されるのを確認します :::no-loc text="Azure Monitor"::: 。

> [!NOTE]
> エージェントのインストール後にデバイスを再起動し、会議アプリが開始され、イベント ログに新しいイベントを生成できるよう :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: します。

1.  ポータルにサインイン[ :::no-loc text="Microsoft Azure"::: し、 に](https://portal.azure.com)移動して :::no-loc text="Log Analytics"::: ワークスペースを選択します。

2.  デバイスによって生成されたハートビート イベントを一覧表示 :::no-loc text="Microsoft Teams Rooms"::: します。
    1.  ワークスペースを選択し、[ログ] **に移動** し、クエリを使用して、 のカスタム フィールドを持つハートビート レコードを取得します :::no-loc text="Microsoft Teams Rooms"::: 。
    2.  サンプル クエリ: `Event | where Source == "SRS-App" and EventID == 2000`

3.  クエリが、会議アプリによって生成されたイベントを含むログ レコードを返す :::no-loc text="Microsoft Teams Rooms"::: 必要があります。

4.  ハードウェアの問題を生成し、必要なイベントが に記録されるのを検証します :::no-loc text="Azure Log Analytics"::: 。
    1.  テスト システムの周辺機器の 1 つを取り外 :::no-loc text="Microsoft Teams Rooms"::: します。 カメラ、スピーカーフォン、マイク、フロント ルーム ディスプレイなどです。
    2.  イベント ログが に設定されるのを 10 分待ちます :::no-loc text="Azure Log Analytics"::: 。
    3.  クエリを使用してハードウェア エラー イベントを一覧表示します。 `Event | where Source == "SRS-App" and EventID == 3001`

5.  アプリケーションの問題を生成し、必要なイベントがログに記録されるのを検証します。
    1.  アプリケーション :::no-loc text="Microsoft Teams Rooms"::: の構成を変更し、正しくないセッション開始プロトコル (SIP) アドレスとパスワードのペアを入力します。
    2.  イベント ログが に設定されるのを 10 分待ちます :::no-loc text="Azure Log Analytics"::: 。
    3.  クエリを使用して、アプリケーション エラー イベントを一覧表示します。 `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> これらのサンプル イベント ログは、カスタム フィールドを構成する前に必要です。 必要なイベント ログを収集するまで、次の手順に進む必要はありません。

## <a name="map-custom-fields"></a>カスタム フィールドをマップする
<a name="Custom_fields"> </a>

カスタム フィールドを使用して、イベント ログから特定のデータを抽出します。 後でタイル、ダッシュボード ビュー、アラートで使用するカスタム フィールドを定義する必要があります。 カスタム[フィールドの :::no-loc text="Log Analytics"::: 作成を開始](/azure/azure-monitor/platform/custom-fields)する前に、「カスタム フィールド」を参照し、概念を理解してください。

キャプチャしたイベント ログからカスタム フィールドを抽出するには、次の手順に従います。

1.  ポータルにサインイン[ :::no-loc text="Microsoft Azure"::: し、 に](https://portal.azure.com)移動して :::no-loc text="Log Analytics"::: ワークスペースを選択します。

2. デバイスによって生成されたイベントを一覧表示 :::no-loc text="Microsoft Teams Rooms"::: します。
   1.  [ログ **] に** 移動し、クエリを使用して、カスタム フィールドを持つレコードを取得します。
   2.  サンプル クエリ: `Event | where Source == "SRS-App" and EventID == 2000`

3. レコードのいずれかを選択し、左側のボタンを選択して、フィールド抽出ウィザードを開始します。
4. RenderedDescription から抽出するデータを強調表示し、フィールド タイトルを指定します。 使用する必要があるフィールド名を表 1 に示します。
5. 表 1 に示すマッピング *を使用します*。 :::no-loc text="Log Analytics":::は、新しいフィールド **\_ を定義** するときに CF 文字列を自動的に追加します。

> [!IMPORTANT]
> すべての JSON とフィールドでは大文字 :::no-loc text="Log Analytics"::: と小文字が区別されます。
> 
> 次の表のカスタム フィールドごとに必要なクエリに注意してください。 カスタム フィールド値を正常に抽出するには、 の :::no-loc text="Log Analytics"::: 適切なクエリを使用する必要があります。
> 
**表 1**

| **JSON フィールド**                   | **:::no-loc text="Log Analytics"::: カスタム フィールド** | **イベント ID** | **抽出で使用するクエリ**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| 説明                      | SRSEventDescription         | **2000**     | \|Source == "SRS-App" と EventID == 2000 のイベント |
| ResourceState                    | SRSResourceState            | **2000**     | \|Source == "SRS-App" と EventID == 2000 のイベント |
| OperationName                    | SRSOperationName            | **2000**     | \|Source == "SRS-App" と EventID == 2000 のイベント |
| OperationResult                  | SRSOperationResult          | **2000**     | \|Source == "SRS-App" と EventID == 2000 のイベント |
| OS                               | SRSOSVersion                | **2000**     | \|Source == "SRS-App" と EventID == 2000 のイベント |
| OSVersion                        | SRSOSLongVersion            | **2000**     | \|Source == "SRS-App" と EventID == 2000 のイベント |
| Alias                            | SRSAlias                    | **2000**     | \|Source == "SRS-App" と EventID == 2000 のイベント |
| DisplayName                      | SRSDisplayName              | **2000**     | \|Source == "SRS-App" と EventID == 2000 のイベント |
| AppVersion                       | SRSAppVersion               | **2000**     | \|Source == "SRS-App" と EventID == 2000 のイベント |
| IPv4Address                      | SRSIPv4Address              | **2000**     | \|Source == "SRS-App" と EventID == 2000 のイベント |
| IPv6Address                      | SRSIPv6Address              | **2000**     | \|Source == "SRS-App" と EventID == 2000 のイベント |
| 電話会議マイクの状態     | SRSConfMicrophoneStatus     | **3001**     | \|Source == "SRS-App" と EventID == 3001 のイベント |
| 電話会議の発表者の状態        | SRSConfSpeakerStatus        | **3001**     | \|Source == "SRS-App" と EventID == 3001 のイベント |
| スピーカーの既定の状態           | SRSDefaultSpeakerStatus     | **3001**     | \|Source == "SRS-App" と EventID == 3001 のイベント |
| カメラの状態                    | SRSCameraStatus             | **3001**     | \|Source == "SRS-App" と EventID == 3001 のイベント |
| ルームの前面の表示状態     | SRSFORDStatus               | **3001**     | \|Source == "SRS-App" と EventID == 3001 のイベント |
| モーション センサーの状態             | SRSMotionSensorStatus       | **3001**     | \|Source == "SRS-App" と EventID == 3001 のイベント |
| HDMI 取り込み状態               | SRSHDMIIngestStatus         | **3001**     | \|Source == "SRS-App" と EventID == 3001 のイベント |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>でビュー :::no-loc text="Microsoft Teams Rooms"::: を定義する :::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

データが収集され、カスタム フィールドがマップされた後、ビュー デザイナーを使用して、イベントを監視するさまざまなタイルを含むダッシュボードを開発 :::no-loc text="Microsoft Teams Rooms"::: できます。 ビュー デザイナーを使用して、次のタイルを作成します。 詳細については、「ビュー デザイナーを[使用してカスタム ビューを :::no-loc text="Log Analytics"::: 作成する」を参照してください。](/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> ダッシュボード タイルが正常に動作するには、このガイドの前の手順を完了している必要があります。

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>import メソッドMicrosoft Teams ミーティングダッシュボードを作成する

ダッシュボードをインポートして :::no-loc text="Microsoft Teams Rooms"::: 、デバイスの監視をすばやく開始できます。 ダッシュボードをインポートするには、次の手順を実行します。

1.  [SkypeRoomSystems_v2.omsview ダッシュボード ファイルを](https://go.microsoft.com/fwlink/?linkid=835675)取得します。
2.  ポータルにサインイン[ :::no-loc text="Microsoft Azure"::: し、 に](https://portal.azure.com)移動して :::no-loc text="Log Analytics"::: ワークスペースを選択します。
3.  ビュー **デザイナー を開きます**。
4.  [ **インポート]** を選択し **、SkypeRoomSystems_v2.omsview ファイルを選択** します。
5.  **[保存]** を選択します。

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>ダッシュボードを手動Microsoft Teams ミーティング作成する

または、独自のダッシュボードを作成し、監視するタイルのみを追加することもできます。

#### <a name="configure-the-overview-tile"></a>[概要] タイルを構成する

1.  ビュー **デザイナー を開きます**。
2.  [概要 **タイル] を** 選択し、ギャラリーから **[2 つの** 数値] を選択します。
3.  タイルに という名前を付 **:::no-loc text="Microsoft Teams Rooms":::** けします。
4.  最初のタイル **を定義します**。<br>
    **凡例:** 前月に少なくとも 1 回ハートビートを送信したデバイス<br>
    **クエリ:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  2 番目 **のタイルを定義します**。<br>
    **凡例:** 最後の 1 時間以内にハートビートを送信したアクティブ なデバイス<br>
    **クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  **[適用]** を選択します。

### <a name="create-a-tile-that-displays-active-devices"></a>アクティブなデバイスを表示するタイルを作成する

1.  [ダッシュボード **の表示] を** 選択して、タイルの追加を開始します。
2.  ギャラリー **から [番号&リスト** ] を選択します。
3.  [全般] **プロパティを定義** します。<br>
    **グループ タイトル:** ハートビートの状態<br>
    **新しいグループ:** 選択
4.  タイルのプロパティ **を定義** します。<br>
    **凡例:** アクティブなデバイス (過去 20 分間に送信されたハートビート)<br>
    **タイルのクエリ:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  List プロパティ **を定義** します。<br>
    **リスト クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  列 **タイトルを定義する**:<br>
    **名前:** コンピューター名<br>
    **値:** 最後のハートビート
7.  ナビゲーション **クエリ を定義します**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  [適用 **] を選択** し、[閉じる] **を選択します**。

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>接続の問題があるデバイスを表示するタイルを作成する

1.  ギャラリー **から [&番号** ] リストを選択し、新しいタイルを追加します。
2.  [全般] **プロパティを定義** します。<br>
    **グループ タイトル:** 空のままにする<br>
    **新しいグループ:** 選択されていない
3.  タイルのプロパティ **を定義** します。<br>
    **凡例:** 非アクティブなデバイス (過去 20 分間にハートビート メッセージが送信されません)<br>
    **タイルのクエリ:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  List プロパティ **を定義** します。<br>
    **リスト クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  列 **タイトルを定義する**:<br>
    **名前:** コンピューター名<br>
    **値:** 最後のハートビート
6.  ナビゲーション **クエリを定義する**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  [適用 **] を選択** し、[閉じる] **を選択します**。

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>ハードウェア エラーが発生したデバイスを表示するタイルを作成する

1.  ギャラリー **から [&番号** ] リストを選択し、新しいタイルを追加します。
2.  [全般] **プロパティを定義** します。<br>
    **グループ タイトル:** ハードウェアの状態<br>
    **新しいグループ:** 選択
3.  タイルのプロパティ **を定義** します。<br>
    **凡例:** 過去 1 時間にハードウェア エラーが発生したデバイス<br>
    **タイルのクエリ:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  List プロパティ **を定義** します。<br>
    **リスト クエリ:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  列 **タイトルを定義する**:<br>
    **名前:** コンピューター名<br>
    **値:** 最後のエラー
6.  ナビゲーション **クエリを定義する**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  [適用 **] を選択** し、[閉じる] **を選択します**。

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>オペレーティング システムのバージョンを表示 :::no-loc text="Microsoft Teams Rooms"::: するタイルを作成する

1.  ギャラリー **から [&] リスト** を選択し、新しいタイルを追加します。
2.  [全般] **プロパティを定義** します。<br>
    **グループ タイトル:** オペレーティング システムの詳細<br>
    **新しいグループ:** 選択
3.  ヘッダーのプロパティ **を定義** します。<br>
    **タイトル:** オペレーティング システムのバージョン<br>
    **字幕:** 特定の OS バージョンを実行しているデバイス
4.  Donut **プロパティを定義** します。<br>
    **クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **中央のテキスト:** デバイス<br>
    **操作:** 合計
5.  List プロパティ **を定義** します。<br>
    **リスト クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **[非表示Graph:** 選択<br>
    **スパークラインを有効にする:** 選択されていない
6.  列タイトル **を定義します**。<br>
    **名前:** コンピューター名<br>
    **値:** 空のままにする
7.  ナビゲーション **クエリ を定義します**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  [適用 **] を選択** し、[閉じる] **を選択します**。

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>アプリケーションのバージョンを表示する :::no-loc text="Microsoft Teams Rooms"::: タイルを作成する

1.  ギャラリー **から [&] リスト** を選択し、新しいタイルを追加します。
2.  [全般] **プロパティを定義** します。<br>
    **グループ タイトル:** :::no-loc text="Microsoft Teams Rooms"::: アプリケーションの詳細<br>
    **新しいグループ:** 選択
3.  ヘッダーのプロパティ **を定義** します。<br>
    **タイトル:** アプリケーションのバージョン<br>
    **字幕:** 特定のアプリケーション バージョンを実行しているデバイス
4.  Donut **プロパティを定義** します。<br>
    **クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **中央のテキスト:** デバイス<br>
    **操作:** 合計
5.  List プロパティ **を定義** します。<br>
    **リスト クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **[非表示Graph:** 選択<br>
    **スパークラインを有効にする:** 選択されていない
6.  列タイトル **を定義します**。<br>
    **名前:** コンピューター名<br>
    **値:** 空のままにする
7.  ナビゲーション **クエリ を定義します**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  [適用 **] を選択** し、[閉じる] **を選択します**。

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>アプリケーション エラーが発生したデバイスを表示するタイルを作成する

1.  ギャラリー **から [&番号** ] リストを選択し、新しいタイルを追加します。
2.  [全般] **プロパティを定義** します。<br>
    **グループ タイトル:** 空のままにする<br>
    **新しいグループ:** 選択されていない
3.  タイルのプロパティ **を定義** します。<br>
    **凡例:** 過去 1 時間にアプリケーション エラーが発生したデバイス<br>
    **タイルのクエリ:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  List プロパティ **を定義** します。<br>
    **リスト クエリ:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  列タイトル **を定義します**。<br>
    **名前:** コンピューター名<br>
    **値:** 最後のエラー
6.  ナビゲーション **クエリ を定義します**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  [適用 **] を選択** し、[閉じる] **を選択します**。

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>再起動されたデバイスを表示するタイルを作成する

1.  ギャラリー **から [&番号** ] リストを選択し、新しいタイルを追加します。
2.  [全般] **プロパティを定義** します。<br>
    **グループ タイトル:** 空のままにする<br>
    **新しいグループ:** 選択されていない
3.  タイルのプロパティ **を定義** します。<br>
    **凡例:** 過去 24 時間にアプリケーションが再起動されたデバイスと再起動数<br>
    **タイルのクエリ:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  List プロパティ **を定義** します。<br>
    **リスト クエリ:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  列タイトル **を定義します**。<br>
    **名前:** コンピューター名<br>
    **値:** 再起動の数
6.  ナビゲーション **クエリ を定義します**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  [適用 **] を選択** し、[閉じる] **を選択します**。
8.  [保存 **] を** 選択してダッシュボードを保存します。

これで、ビューの作成が完了しました。

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>でアラートを構成する :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: は、本体で問題が発生した場合に管理者に :::no-loc text="Microsoft Teams Rooms"::: 通知するアラートを生成できます。

:::no-loc text="Azure Monitor"::: には、定期的にスケジュールされたログ検索を実行する組み込みのアラート メカニズムが含まれています。 ログ検索の結果が特定の条件と一致する場合は、アラート レコードが作成されます。

その後、ルールは 1 つ以上のアクションを自動的に実行して、アラートを事前に通知したり、別のプロセスを呼び出したりすることができます。 アラートで使用できるオプションは次のとおりです。
-   メールの送信
-   HTTP POST 要求を介した外部プロセスの呼び出し
-   サービスでの Runbook の :::no-loc text="Azure Automation"::: 開始

の[アラートの詳細 :::no-loc text="Azure Monitor"::: については、「](/azure/azure-monitor/platform/alerts-unified-log)ログイン アラート」を参照してください :::no-loc text="Azure Monitor"::: 。

> [!NOTE]
> 次の例では、デバイスがハードウェアまたはアプリケーション エラー :::no-loc text="Microsoft Teams Rooms"::: を生成するときに電子メール アラートを送信します。

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>ハードウェアの問題に関する電子 :::no-loc text="Microsoft Teams Rooms"::: メール アラートを構成する

前の 1 時間以内にハードウェアの問題が発生したデバイスをチェックするアラート :::no-loc text="Microsoft Teams Rooms"::: ルールを構成します。
1.  ポータルにサインイン[ :::no-loc text="Microsoft Azure"::: し、 に](https://portal.azure.com)移動して :::no-loc text="Log Analytics"::: ワークスペースを選択します。

2. ワークスペースに移動し :::no-loc text="Log Analytics"::: 、[アラート] を **選択し** 、[新しいアラート **ルール] を選択します。**

3. [条件 **の追加] を** 選択し、[ **カスタム ログ検索] を選択します。**

4.  [検索クエリ] テキスト ボックスに次のクエリを入力します。<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  アラート ロジックの設定を構成します。<br>
    **次の条件に基づいて、** 結果の数<br>
    **条件:** 次に大きい<br>
    **しきい値:** 0<br>

6. 評価設定を構成し、[完了] を **選択します**。 <br>
    **期間 (分):** 60<br>
    **頻度 (分):** 60<br>

7. アクション グループを構成する:
    1.  [Create **New]を選択します。**
    2.  [アクション グループ名] フィールドと *[短い名前] フィールドに**適した名前を指定* します。
    3.  一意の *アクション名を指定し*、[**電子メール/携帯ショートメール/プッシュ/** 音声] を選択し、[詳細の編集]**を選択します**。
    4.  [電子メール **] チェック** ボックスをオンにして、アラートを受信するユーザーまたはグループのメール アドレスを指定します。
    5.  また、電話番号を入力して、通話、音声通話、携帯ショートメール通知を受け取る場合があります。
    6. **[OK] を選択します**。

8. **アラート メール** の件名行をオーバーライドする場合は、[アクション] をカスタマイズします。

9. ルールの名前と説明を指定します。<br>
    **ルール名:** :::no-loc text="Microsoft Teams Rooms"::: ハードウェア障害アラート<br>
    **説明:** 最後の 1 時間以内にハードウェアの問題が発生したデバイスの一覧<br>

10. 目的の重大度を選択し、ルールが有効になっているか確認します。

11. [アラート **ルールの作成] を選択します**。

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>アプリケーションの問題に関する電子メール :::no-loc text="Microsoft Teams Rooms"::: アラートを構成する

同じ手順を繰り返しますが、次のクエリを使用して、最後の 1 時間以内にアプリケーションの問題が発生したデバイスを一覧表示します。

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

これで、アラートの定義が完了しました。 上記の例を使用して、追加のアラートを定義できます。

アラートが生成されると、前の 1 時間以内に問題が発生したデバイスを一覧表示する電子メールが届きます。

![アラート :::no-loc text="Azure Monitor"::: 電子メールのサンプル](../media/Deploy-Azure-Monitor-6.png " :::no-loc text=&quot;Azure Monitor&quot;::: サンプル アラート 電子メール")

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>すべてのデバイスを構成する :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"></a>ダッシュボードとアラートを構成したら、すべてのデバイスでエージェントを設定して構成し、監視 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: のデプロイを完了できます。

各デバイスにエージェントを手動でインストールして構成することもできますが、既存のソフトウェア展開ツールと方法を活用 :::no-loc text="Microsoft Monitoring"::: することを強くお勧めします。

初めてデバイスをビルドする場合は、ビルド プロセスの一部としてエージェントのセットアップと構成 :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Microsoft Monitoring"::: の手順を含める必要があります。 詳細については、コマンド ラインを [使用したエージェントのインストールに関するページを参照してください](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)。

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>グループ ポリシー :::no-loc text="Microsoft Monitoring"::: オブジェクト (GPO) を使用したエージェントのデプロイ

を実装する前にデバイスを既にデプロイしている場合は、提供されているスクリプトを使用して、グループ ポリシー オブジェクトを使用してエージェントを :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitoring"::: :::no-loc text="Active Directory"::: 設定および構成できます。

1.  共有ネットワーク パスを作成し、ドメイン コンピューター グループへの読み取 **りアクセス権を付与** します。

2.  エージェントの 64 ビット バージョンを :::no-loc text="Microsoft Monitoring"::: からダウンロード :::no-loc text="Windows"::: します。 <https://go.microsoft.com/fwlink/?LinkID=517476>

3.  セットアップ パッケージの内容をネットワーク共有に抽出します。
    1.  コマンド プロンプト ウィンドウを開き、/cMMASetup-AMD64.exe **実行します。**
    2.  作成した共有を指定し、コンテンツを抽出します。

4.  新しいグループ ポリシー オブジェクトを作成し、マシン アカウントがある組織単位 :::no-loc text="Microsoft Teams Rooms"::: に割り当てる。

5.  PowerShell 実行ポリシーの構成:
    1.  新しく作成したグループ ポリシー オブジェクトを編集し、[コンピューター構成ポリシー] \\ 管理用テンプレート コンポーネント \\ に \\ :::no-loc text="Windows"::: 移動します。 \\:::no-loc text="Windows PowerShell":::
    2.  [スクリプトの **実行を有効にする] を有効にして**、[**実行ポリシー] を [ローカル****スクリプトを許可] に設定します**。

6.  スタートアップ スクリプトを構成します。
    1.  次のスクリプトをコピーし、次のスクリプトとしてInstall-MMAgent.ps1。
    2.  構成に合わせて WorkspaceId、WorkspaceKey、SetupPath パラメーターを変更します。
    3.  同じグループ ポリシー オブジェクトを編集し、[コンピューター構成ポリシー] 設定 \\ \\ :::no-loc text="Windows"::: \\ (スタートアップ/シャットダウン) に移動します。
    4.  ダブルクリックして [スタートアップ]**を選択し****、[PowerShell スクリプト] を選択します**。
    5.  [ **ファイルの表示]** を選択し、Install-MMAgent.ps1 **ファイルを** そのフォルダーにコピーします。
    6.  [追加 **] を選択** し、[参照] **を選択します**。
    7.  コピーした ps1 スクリプトを選択します。

7.  :::no-loc text="Microsoft Teams Rooms"::: デバイスは、2 回目の再起動で :::no-loc text="Microsoft Monitoring"::: エージェントをインストールして構成する必要があります。

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
> エージェントの再構成、別の [ :::no-loc text="Log Analytics"::: ](/azure/azure-monitor/platform/agent-manage) ワークスペースへの移動、または初期インストール後のプロキシ設定の変更が必要な場合のエージェントの管理と保守に関する記事を参照してください。

## <a name="additional-solutions"></a>その他のソリューション
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor"::: は、環境の監視に [役立つソリューション](/azure/azure-monitor/insights/solutions) ギャラリーを通じて組み込みの管理ソリューションを提供します。 アラート管理ソリューションと[Agent](/azure/azure-monitor/platform/alert-management-solution) [ :::no-loc text="Azure Log Analytics"::: Health](/azure/azure-monitor/insights/solution-agenthealth)ソリューションもワークスペースに追加することを強くお勧めします。

> [!NOTE]
> Agent Health ソリューションは、環境内の古いエージェントや破損したエージェントを特定するのに役立ちます。アラート管理ソリューションは、特定の期間に発生したアラートに関する詳細 :::no-loc text="Microsoft Monitoring"::: を提供します。

## <a name="see-also"></a>関連項目

[を :::no-loc text="Microsoft Teams Rooms"::: 使用した計画管理 :::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[を :::no-loc text="Microsoft Teams Rooms"::: 使用してデバイスを管理する :::no-loc text="Azure Monitor":::](azure-monitor-manage.md)