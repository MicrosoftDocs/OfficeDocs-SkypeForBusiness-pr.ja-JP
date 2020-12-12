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
ms.openlocfilehash: b05c490c157c9f6530ca79ecdd8df19f15d94c68
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662102"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a>次 :::no-loc text="Microsoft Teams Rooms"::: の方法で管理を展開します。 :::no-loc text="Azure Monitor":::

この記事では、デバイスの統合されたエンドツーエンド管理をセットアップして展開する方法 :::no-loc text="Microsoft Teams Rooms"::: について説明します :::no-loc text="Azure Monitor"::: 。

会議室デバイスの管理に役立つ基本的なテレメトリとアラートを提供するために、その中 :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor"::: :::no-loc text="Microsoft Teams Rooms"::: を構成できます。 管理ソリューションの成熟に合わせ、追加のデータと管理機能を展開して、デバイスの可用性とパフォーマンスの詳細なビューを作成することもできます。

このガイドに従って、次の例のようなダッシュボードを使用して、デバイスの可用性、アプリケーションとハードウェアの正常性、アプリケーションとオペレーティング システムのバージョンの配布に関する詳細な状態レポートを :::no-loc text="Microsoft Teams Rooms"::: 取得できます。

![Microsoft Teams の会議室のログ分析ビューのサンプルのスクリーンショット](../media/Deploy-Azure-Monitor-1.png "Microsoft Teams 会議室の [ログ分析] ビューの例")

高いレベルでは、次のタスクを実行する必要があります。


1. [構成を検証 :::no-loc text="Log Analytics"::: する](azure-monitor-deploy.md#validate_LogAnalytics)
2. [管理セットアップ用にテスト デバイス :::no-loc text="Log Analytics"::: を構成する](azure-monitor-deploy.md#configure_test_devices)
3. [カスタム フィールドをマップする](azure-monitor-deploy.md#Custom_fields)
4. [ビューを :::no-loc text="Microsoft Teams Rooms"::: 定義するには、 :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [通知を定義する](azure-monitor-deploy.md#Alerts)
6. [監視用のすべてのデバイスを構成する](azure-monitor-deploy.md#configure_all_devices)
7. [その他のソリューションを :::no-loc text="Azure Monitor"::: 構成する](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> 構成を最小限に抑えれば、オペレーティング システムを実行しているコンピューターを監視することができますが、すべてのデバイスへのエージェントの展開を開始する前に実行する必要があるいくつかの具体的な手順がまだ :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: :::no-loc text="Windows"::: :::no-loc text="Microsoft Teams Rooms"::: 存在 :::no-loc text="Microsoft Teams Rooms"::: します。
> そのため、制御されたセットアップと構成に対して、すべての構成手順を正しい順序で実行することを強くお勧めします。 結果の品質は、初期構成の品質によって大きな違いがあります。

## <a name="validate-no-loc-textlog-analytics-configuration"></a>構成を検証 :::no-loc text="Log Analytics"::: する
<a name="validate_LogAnalytics"> </a>

デバイスからログの収集 :::no-loc text="Log Analytics"::: を開始するには、ワークスペースが必要 :::no-loc text="Microsoft Teams Rooms"::: です。 ワークスペースは、独自のデータ リポジトリ、データ ソース、ソリューション :::no-loc text="Log Analytics"::: を持つ固有の環境です。 既に既存のワークスペースがある場合は、それを使用して展開を監視するか、監視のニーズに固有の専用ワークスペース :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: を作成できます。

新しいワークスペースを作成する必要がある場合は、「ポータルでワークスペースを作成する」の :::no-loc text="Log Analytics"::: [ :::no-loc text="Log Analytics"::: 記事の手順に従 :::no-loc text="Azure"::: ってください。](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> 一緒に :::no-loc text="Log Analytics"::: 使用 :::no-loc text="Azure Monitor"::: するには、アクティブなサブスクリプションが必要 :::no-loc text="Azure"::: です。 サブスクリプションを持ってない場合は、開始点として無料試用版 :::no-loc text="Azure"::: サブスクリプションを作成できます。 [](https://azure.microsoft.com/free)

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>イベント :::no-loc text="Log Analytics"::: ログを収集 :::no-loc text="Microsoft Teams Rooms"::: するために構成する

:::no-loc text="Log Analytics"::: 設定で指定されているイベント :::no-loc text="Windows"::: ログからのイベントのみを収集します。 ログごとに、選択した重大度のイベントだけが収集されます。

デバイスとアプリケーションの :::no-loc text="Log Analytics"::: 状態を監視するために必要なログを収集するために :::no-loc text="Microsoft Teams Rooms"::: 構成する必要があります。 :::no-loc text="Microsoft Teams Rooms"::: デバイスはイベント ログ **:::no-loc text="Skype Room System":::** を使用します。

イベントを :::no-loc text="Log Analytics"::: 収集するために構成 :::no-loc text="Microsoft Teams Rooms"::: するには[ :::no-loc text="Windows"::: :::no-loc text="Azure Monitor"::: 、](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)

![イベント ログの設定のスクリーンショット](../media/Deploy-Azure-Monitor-2.png "イベント ログの設定")

> [!IMPORTANT]
> イベント ログの設定を構成し、イベント ログ名として入力し、[エラー]、[警告]、および [情報] チェック ボックス :::no-loc text="Windows"::: **:::no-loc text="Skype Room System":::** をオンにします。   

## <a name="configure-test-devices-for-azure-monitoring"></a>Azure モニタリング用のテスト デバイスを構成する
<a name="configure_test_devices"> </a>

関連するイベント :::no-loc text="Log Analytics"::: を監視するには、準備 :::no-loc text="Microsoft Teams Rooms"::: が必要です。 最初に、物理的にアクセスできる 1 つか 2 つのデバイスにエージェントを展開し、それらのテスト デバイスにデータを生成してワークスペースにプッシュする必要 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Log Analytics"::: があります。

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>エージェント :::no-loc text="Microsoft Monitoring"::: をインストールしてデバイスをテストする

「コンピューターをサービスに接続する」に記載されている手順を使用して、エージェント :::no-loc text="Microsoft Monitoring"::: [ :::no-loc text="Windows"::: をテスト デバイス :::no-loc text="Log Analytics"::: に展開します :::no-loc text="Azure"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)。 この記事では、エージェントを展開する手順、ワークスペース :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Windows"::: :::no-loc text="Log Analytics":::  * *_ID_* _ _**_ :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: と主キーを取得してデバイスを展開に接続するための手順、およびインスタンスへのエージェント接続を確認する手順について詳しく説明します。

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>サンプル イベントを生成 :::no-loc text="Microsoft Teams Rooms"::: する

エージェントをテスト デバイスに展開した後、必要なイベント ログ データが収集 :::no-loc text="Microsoft Monitoring"::: されるのを確認します :::no-loc text="Azure Monitor"::: 。

> [!NOTE]
> エージェントのインストール後にデバイスを再起動し、会議アプリが開始され、イベント ログに新しいイベントを :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: 生成できます。

1.  ポータルにサインイン[ :::no-loc text="Microsoft Azure"::: し、](https://portal.azure.com)ワークスペースに移動 :::no-loc text="Log Analytics"::: して選択します。

2.  デバイスによって生成されたハートビート イベントを一覧表示 :::no-loc text="Microsoft Teams Rooms"::: します。
    1.  ワークスペースを選択し *、[_Logs]** に移動し、クエリを使用して、カスタム フィールドを持つハートビート レコードを取得します :::no-loc text="Microsoft Teams Rooms"::: 。
    2.  サンプル クエリ: `Event | where Source == "SRS-App" and EventID == 2000`

3.  クエリが、会議アプリによって生成されたイベントを含むログ レコードを :::no-loc text="Microsoft Teams Rooms"::: 返す必要があります。

4.  ハードウェアの問題を生成し、必要なイベントがログイン状態に入るのを確認します :::no-loc text="Azure Log Analytics"::: 。
    1.  テスト システム上の周辺機器の 1 つを取り外 :::no-loc text="Microsoft Teams Rooms"::: します。 カメラ、スピーカーフォン、マイク、フロント ルームディスプレイなど
    2.  イベント ログが入力されるのを 10 分待ちます :::no-loc text="Azure Log Analytics"::: 。
    3.  クエリを使用してハードウェア エラー イベントを一覧表示します。 `Event | where Source == "SRS-App" and EventID == 3001`

5.  アプリケーションの問題を生成し、必要なイベントがログに記録される検証を行います。
    1.  アプリケーション :::no-loc text="Microsoft Teams Rooms"::: 構成を変更し、正しくないセッション開始プロトコル (SIP) アドレス/パスワードのペアを入力します。
    2.  イベント ログが入力されるのを 10 分待ちます :::no-loc text="Azure Log Analytics"::: 。
    3.  クエリを使用してアプリケーションのエラー イベントを一覧表示します。 `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> これらのサンプル イベント ログは、カスタム フィールドを構成する前に必要です。 必要なイベント ログを収集するまで、次の手順に進む必要はありません。

## <a name="map-custom-fields"></a>カスタム フィールドをマップする
<a name="Custom_fields"> </a>

カスタム フィールドを使用して、イベント ログから特定のデータを抽出します。 後でタイル、ダッシュボード ビュー、通知で使用するカスタム フィールドを定義する必要があります。 カスタム[フィールドの :::no-loc text="Log Analytics"::: 作成を](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields)開始する前に、「カスタム フィールド」を参照し、概念を理解してください。

キャプチャされたイベント ログからカスタム フィールドを抽出するには、次の手順を実行します。

1.  ポータルにサインイン[ :::no-loc text="Microsoft Azure"::: し、](https://portal.azure.com)ワークスペースに移動 :::no-loc text="Log Analytics"::: して選択します。

2. デバイスによって生成されたイベントを一覧表示 :::no-loc text="Microsoft Teams Rooms"::: します。
   1.  [ログ **] に** 移動し、クエリを使用して、カスタム フィールドを含むレコードを取得します。
   2.  サンプル クエリ: `Event | where Source == "SRS-App" and EventID == 2000`

3. レコードのいずれかを選択し、左側のボタンを選択して、フィールド抽出ウィザードを開始します。
4. RenderedDescription から抽出するデータを強調表示し、フィールド タイトルを指定します。 使用する必要があるフィールド名は、表 1 に示されています。
5. 表 1 に示すマッピング *を使用します*。 :::no-loc text="Log Analytics":::は、新しいフィールド **\_ を定義** するときに CF 文字列を自動的に追加します。

> [!IMPORTANT]
> すべての JSON とフィールドでは大文字 :::no-loc text="Log Analytics"::: と小文字が区別されます。
> 
> 次の表のカスタム フィールドごとに必要なクエリに注意してください。 ユーザー設定フィールドの値を正常に抽出するには、正 :::no-loc text="Log Analytics"::: しいクエリを使用する必要があります。
> 
**表 1**

| **JSON フィールド**                   | **:::no-loc text="Log Analytics"::: ユーザー設定フィールド** | **イベント ID** | **抽出で使用するクエリ**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| 説明                      | SRSEventDescription         | **2000**     | \|Source == "SRS-App" と EventID == 2000 のイベント |
| ResourceState                    | SRSResourceState            | **2000**     | \|Source == "SRS-App" および EventID == 2000 のイベント |
| OperationName                    | SRSOperationName            | **2000**     | \|Source == "SRS-App" および EventID == 2000 のイベント |
| OperationResult                  | SRSOperationResult          | **2000**     | \|Source == "SRS-App" および EventID == 2000 のイベント |
| OS                               | SRSOSVersion                | **2000**     | \|Source == "SRS-App" および EventID == 2000 のイベント |
| OSVersion                        | SRSOSLongVersion            | **2000**     | \|Source == "SRS-App" と EventID == 2000 のイベント |
| Alias                            | SRSAlias                    | **2000**     | \|Source == "SRS-App" と EventID == 2000 のイベント |
| DisplayName                      | SRSDisplayName              | **2000**     | \|Source == "SRS-App" と EventID == 2000 のイベント |
| AppVersion                       | SRSAppVersion               | **2000**     | \|Source == "SRS-App" と EventID == 2000 のイベント |
| IPv4Address                      | SRSIPv4Address              | **2000**     | \|Source == "SRS-App" と EventID == 2000 のイベント |
| IPv6Address                      | SRSIPv6Address              | **2000**     | \|Source == "SRS-App" と EventID == 2000 のイベント |
| 電話会議マイクの状態     | SRSConfMicrophoneStatus     | **3001**     | \|Source == "SRS-App" および EventID == 3001 のイベント |
| 電話会議のスピーカーの状態        | SRSConfSpeakerStatus        | **3001**     | \|Source == "SRS-App" と EventID == 3001 のイベント |
| 既定のスピーカーの状態           | SRSDefaultSpeakerStatus     | **3001**     | \|Source == "SRS-App" および EventID == 3001 のイベント |
| カメラの状態                    | SRSCameraStatus             | **3001**     | \|Source == "SRS-App" および EventID == 3001 のイベント |
| [ルームの表示の前] の状態     | SRSFORDStatus               | **3001**     | \|Source == "SRS-App" と EventID == 3001 のイベント |
| モーション センサーの状態             | SRSMotionSensorStatus       | **3001**     | \|Source == "SRS-App" および EventID == 3001 のイベント |
| HDMI 取り込みの状態               | SRSHDMIIngestStatus         | **3001**     | \|Source == "SRS-App" および EventID == 3001 のイベント |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>ビューを :::no-loc text="Microsoft Teams Rooms"::: 定義するには、 :::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

データが収集され、カスタム フィールドがマップされた後は、ビュー デザイナーを使用して、イベントを監視するさまざまなタイルを含むダッシュボードを作成 :::no-loc text="Microsoft Teams Rooms"::: できます。 ビュー デザイナーを使用して、次のタイルを作成します。 詳細については、「ビュー デザイナー[を使用してカスタム ビューを :::no-loc text="Log Analytics"::: 作成する」を参照してください。](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> ダッシュボード タイルが正常に動作するには、このガイドの前の手順を完了する必要があります。

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>インポート方法を使用して Microsoft Teams Rooms ダッシュボードを作成する

ダッシュボードをインポートして :::no-loc text="Microsoft Teams Rooms"::: 、デバイスの監視をすばやく開始できます。 ダッシュボードをインポートするには、次の手順を実行します。

1.  [SkypeRoomSystems_v2.omsview ダッシュボード ファイルを](https://go.microsoft.com/fwlink/?linkid=835675)取得します。
2.  ポータルにサインイン[ :::no-loc text="Microsoft Azure"::: し、](https://portal.azure.com)ワークスペースに移動 :::no-loc text="Log Analytics"::: して選択します。
3.  ビュー **デザイナーを開きます**。
4.  [ **インポート]** を選択し **、SkypeRoomSystems_v2.omsview ファイルを選択** します。
5.  **[保存]** を選択します。

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Microsoft Teams の会議室ダッシュボードを手動で作成する

または、独自のダッシュボードを作成し、監視するタイルのみを追加することもできます。

#### <a name="configure-the-overview-tile"></a>概要タイルを構成する

1.  ビュー **デザイナーを開きます**。
2.  [ **概要] タイルを** 選択し、ギャラリーから **2 つの** 数字を選択します。
3.  タイルに名前を付 **:::no-loc text="Microsoft Teams Rooms":::** け.
4.  最初のタイル **を定義する**:<br>
    **凡例:** 先月に少なくとも 1 回はハートビートを送信したデバイス<br>
    **クエリ:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  2 つ目 **のタイルを定義する**:<br>
    **凡例:** 最後の 1 時間以内にハートビートを送信したアクティブ なデバイス<br>
    **クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  **[適用]** を選択します。

### <a name="create-a-tile-that-displays-active-devices"></a>アクティブなデバイスを表示するタイルを作成する

1.  [ダッシュボード **の表示] を** 選び、タイルの追加を開始します。
2.  ギャラリー **から [番号&リスト** を選択する
3.  [全般] プロパティ **を定義** します。<br>
    **グループ タイトル:** Heartbeat の状態<br>
    **新しいグループ:** 選択されている
4.  タイルのプロパティ **を定義** します。<br>
    **凡例:** アクティブ なデバイス (過去 20 分間に送信されたハートビート)<br>
    **タイルのクエリ:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  リストのプロパティ **を定義** します。<br>
    **リスト クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  列タイトル **を定義する**:<br>
    **名前:** コンピューター名<br>
    **値:** Last Heartbeat
7.  ナビゲーション **クエリを定義します**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  [適用 **] を選択** し、[閉じる] を **選択します**。

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>接続の問題があるデバイスを表示するタイルを作成する

1.  ギャラリー **から [番号&** リストを選択し、新しいタイルを追加します。
2.  [全般] プロパティ **を定義** します。<br>
    **グループ タイトル:** 空のままにする<br>
    **新しいグループ:** 選択されていない
3.  タイルのプロパティ **を定義** します。<br>
    **凡例:** 非アクティブデバイス (過去 20 分間に送信されたハートビート メッセージなし)<br>
    **タイルのクエリ:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  リストのプロパティ **を定義** します。<br>
    **リスト クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  列タイトル **を定義する**:<br>
    **名前:** コンピューター名<br>
    **値:** Last Heartbeat
6.  ナビゲーション **クエリを定義する**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  [適用 **] を選択** し、[閉じる] を **選択します**。

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>ハードウェア エラーが発生しているデバイスを表示するタイルを作成する

1.  ギャラリー **から [番号&** リストを選択し、新しいタイルを追加します。
2.  [全般] プロパティ **を定義** します。<br>
    **グループ タイトル:** ハードウェアの状態<br>
    **新しいグループ:** 選択されている
3.  タイルのプロパティ **を定義** します。<br>
    **凡例:** 過去 1 時間にハードウェア エラーが発生したデバイス<br>
    **タイルのクエリ:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  リストのプロパティ **を定義** します。<br>
    **リスト クエリ:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  列タイトル **を定義する**:<br>
    **名前:** コンピューター名<br>
    **値:** 最後のエラー
6.  ナビゲーション **クエリを定義する**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  [適用 **] を選択** し、[閉じる] を **選択します**。

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>オペレーティング システムのバージョンを表示する :::no-loc text="Microsoft Teams Rooms"::: タイルを作成する

1.  ギャラリー **から [ドーナツ&を** 選び、新しいタイルを追加します。
2.  [全般] プロパティ **を定義** します。<br>
    **グループ タイトル:** オペレーティング システムの詳細<br>
    **新しいグループ:** 選択されている
3.  ヘッダープロパティ **を定義** します。<br>
    **タイトル:** オペレーティング システムのバージョン<br>
    **サブタイトル:** 特定の OS バージョンを実行しているデバイス
4.  ドーナツ の **プロパティを定義** します。<br>
    **クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **テキストの中央:** デバイス<br>
    **操作:** 合計
5.  リストのプロパティ **を定義** します。<br>
    **リスト クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **グラフを非表示にする:** 選択されている<br>
    **スパークラインを有効にする:** 選択されていない
6.  列タイトル **を定義します**。<br>
    **名前:** コンピューター名<br>
    **値:** 空のままにする
7.  ナビゲーション **クエリを定義します**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  [適用 **] を選択** し、[閉じる] を **選択します**。

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>アプリケーションのバージョンを表示する :::no-loc text="Microsoft Teams Rooms"::: タイルを作成する

1.  ギャラリー **から [ドーナツ&を** 選び、新しいタイルを追加します。
2.  [全般] プロパティ **を定義** します。<br>
    **グループ タイトル:** :::no-loc text="Microsoft Teams Rooms"::: アプリケーションの詳細<br>
    **新しいグループ:** 選択されている
3.  ヘッダープロパティ **を定義** します。<br>
    **タイトル:** アプリケーションのバージョン<br>
    **サブタイトル:** 特定のアプリケーション バージョンを実行しているデバイス
4.  ドーナツ の **プロパティを定義** します。<br>
    **クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **テキストの中央:** デバイス<br>
    **操作:** 合計
5.  リストのプロパティ **を定義** します。<br>
    **リスト クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **グラフを非表示にする:** 選択されている<br>
    **スパークラインを有効にする:** 選択されていない
6.  列タイトル **を定義します**。<br>
    **名前:** コンピューター名<br>
    **値:** 空のままにする
7.  ナビゲーション **クエリを定義します**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  [適用 **] を選択** し、[閉じる] を **選択します**。

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>アプリケーション エラーが発生しているデバイスを表示するタイルを作成する

1.  ギャラリー **から [番号&** リストを選択し、新しいタイルを追加します。
2.  [全般] プロパティ **を定義** します。<br>
    **グループ タイトル:** 空のままにする<br>
    **新しいグループ:** 選択されていない
3.  タイルのプロパティ **を定義** します。<br>
    **凡例:** 過去 1 時間にアプリケーション エラーが発生したデバイス<br>
    **タイルのクエリ:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  リストのプロパティ **を定義** します。<br>
    **リスト クエリ:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  列タイトル **を定義します**。<br>
    **名前:** コンピューター名<br>
    **値:** 最後のエラー
6.  ナビゲーション **クエリを定義します**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  [適用 **] を選択** し、[閉じる] を **選択します**。

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>再起動されたデバイスを表示するタイルを作成する

1.  ギャラリー **から [番号&** リストを選択し、新しいタイルを追加します。
2.  [全般] プロパティ **を定義** します。<br>
    **グループ タイトル:** 空のままにする<br>
    **新しいグループ:** 選択されていない
3.  タイルのプロパティ **を定義** します。<br>
    **凡例:** 過去 24 時間にアプリケーションが再起動されたデバイスと再起動数<br>
    **タイルのクエリ:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  リストのプロパティ **を定義** します。<br>
    **リスト クエリ:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  列タイトル **を定義します**。<br>
    **名前:** コンピューター名<br>
    **値:** 再起動数
6.  ナビゲーション **クエリを定義します**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  [適用 **] を選択** し、[閉じる] を **選択します**。
8.  [保存 **] を** 選び、ダッシュボードを保存します。

これで、ビューの作成が完了しました。

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>[通知の構成] :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: 本体で問題が発生した場合に、管理者に通知 :::no-loc text="Microsoft Teams Rooms"::: する通知を送信できます。

:::no-loc text="Azure Monitor"::: には、定期的にスケジュールされたログ検索を実行する組み込みの通知メカニズムが含まれています。 ログ検索の結果が特定の条件と一致する場合は、通知レコードが作成されます。

その後、ルールは 1 つ以上のアクションを自動的に実行して、通知を事前に通知したり、別のプロセスを呼び出したりします。 通知で使用できるオプションは次のとおりです。
-   メールを送信する
-   HTTP POST 要求による外部プロセスの呼び出し
-   サービスで実行ブックを開始 :::no-loc text="Azure Automation"::: する

アラート[の詳細については :::no-loc text="Azure Monitor"::: 、](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log)ログインに関するページを参照してください :::no-loc text="Azure Monitor"::: 。

> [!NOTE]
> 次の例では、デバイスでハードウェアまたはアプリケーション エラーが生成された :::no-loc text="Microsoft Teams Rooms"::: 場合にメール通知を送信します。

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>ハードウェアの問題に関するメール通知 :::no-loc text="Microsoft Teams Rooms"::: を構成する

1 時間以内にハードウェアの問題が発生したデバイスをチェックする通知 :::no-loc text="Microsoft Teams Rooms"::: ルールを構成します。
1.  ポータルにサインイン[ :::no-loc text="Microsoft Azure"::: し、](https://portal.azure.com)ワークスペースに移動 :::no-loc text="Log Analytics"::: して選択します。

2. ワークスペースに移動し :::no-loc text="Log Analytics"::: 、[通知] を **選択** し、[新しい **通知ルール] を選択します。**

3. [条件 **の追加] を選択** し、[ **カスタム ログの検索] を選択する**

4.  [検索クエリ] テキスト ボックスに次のクエリを入力します。<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  通知ロジックの設定を構成します。<br>
    **次の条件に基づいて行います。** 結果の数<br>
    **条件:** 次に大きい<br>
    **しきい値:** 0<br>

6. 評価設定を構成し、[完了] を **選択します**。 <br>
    **期 (分数):** 60<br>
    **頻度 (分):** 60<br>

7. アクション グループを構成する:
    1.  [新規 **作成] を選択する**
    2.  [アクション] グループ名と *[短い名前] フィールドに適**した名前を指定* します。
    3.  一意のアクション *名を指定し* 、[ **メール/SMS/プッシュ/音声**] を選択し、[詳細の編集] **を選択します**。
    4.  [メール **] チェック** ボックスをオンにして、通知を受信するユーザーまたはグループのメール アドレスを指定します。
    5.  また、SMS、音声通話、または両方で通知を受け取る電話番号を入力できます。
    6. **[OK] を選択します**。

8. **通知メール** の件名行を上書きする場合は、アクションをカスタマイズします。

9. ルールの名前と説明を指定します。<br>
    **ルール名:** :::no-loc text="Microsoft Teams Rooms"::: ハードウェア障害通知<br>
    **説明:** 最後の 1 時間以内にハードウェアの問題が発生したデバイスの一覧<br>

10. 目的の重大度を選択し、ルールが有効になっているか確認します。

11. [通知 **ルールの作成] を選択します**。

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>アプリケーションの問題に関するメール :::no-loc text="Microsoft Teams Rooms"::: 通知を構成する

同じ手順を繰り返しますが、次のクエリを使用して、最後の 1 時間以内にアプリケーションの問題が発生したデバイスを一覧表示します。

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

これで、通知の定義が完了しました。 上記の例を使用して、追加の通知を定義できます。

通知が生成されると、1 時間以内に問題が発生したデバイスを一覧表示するメールが届きます。

![サンプル :::no-loc text="Azure Monitor"::: 通知メール](.../media/Deploy-Azure-Monitor-6.png "サンプル :::no-loc text="Azure Monitor"::: 通知メール")

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>すべてのデバイスの構成 :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"></a>ダッシュボードとアラートを構成したら、すべてのデバイスでエージェントを設定して構成し、監視 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: 展開を完了できます。

各デバイスにエージェントを手動でインストールして構成することができますが、既存のソフトウェア展開ツールと方法を活用することを :::no-loc text="Microsoft Monitoring"::: 強くお勧めします。

初めてデバイスを構築する場合は、ビルド プロセスの一部としてエージェントのセットアップと構成の手順を :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Microsoft Monitoring"::: 含める必要があります。 詳細については、コマンド ライン [を使用してエージェントをインストールするを参照してください](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)。

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>グループ ポリシー :::no-loc text="Microsoft Monitoring"::: オブジェクト (GPO) を使用したエージェントの展開

実装する前に既にデバイスを展開している場合は、提供されているスクリプトを使用して、グループ ポリシー オブジェクトを使用してエージェントを :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitoring"::: 設定および :::no-loc text="Active Directory"::: 構成できます。

1.  共有ネットワーク パスを作成し、[ドメイン コンピューター] グループへの読み取 **りアクセス権を付与** します。

2.  64 ビット版の :::no-loc text="Microsoft Monitoring"::: エージェントをダウンロードする :::no-loc text="Windows":::<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  セットアップ パッケージのコンテンツをネットワーク共有に抽出します。
    1.  コマンド プロンプト ウィンドウを開き **、/cMMASetup-AMD64.exe実行する**
    2.  作成した共有を指定し、コンテンツを抽出します。

4.  新しいグループ ポリシー オブジェクトを作成し、コンピューター アカウントがある組織単位 :::no-loc text="Microsoft Teams Rooms"::: に割り当てる。

5.  PowerShell 実行ポリシーを構成します。
    1.  新しく作成したグループ ポリシー オブジェクトを編集し、[コンピューター構成 \\ ポリシー管理用テンプレート コンポーネント \\ ] に \\ :::no-loc text="Windows"::: 移動する \\:::no-loc text="Windows PowerShell":::
    2.  スクリプトの **実行を有効にして、実行** ポリシーをローカル スクリプト **を許可****する設定を行います**。

6.  スタートアップ スクリプトを構成します。
    1.  次のスクリプトをコピーし、そのスクリプトをInstall-MMAgent.ps1。
    2.  WorkspaceId、WorkspaceKey、SetupPath のパラメーターを構成に合わせて変更します。
    3.  同じグループ ポリシー オブジェクトを編集し、コンピューター構成 \\ ポリシー \\ :::no-loc text="Windows"::: 設定 \\ スクリプト (スタートアップ/シャットダウン) に移動する
    4.  ダブルクリックして [スタートアップ] を **選択** し **、[PowerShell スクリプト] を選択します**。
    5.  [ **ファイルの表示]** を選択し、 **そのInstall-MMAgent.ps1ファイル** をコピーします。
    6.  [追加 **] を選択** し、[参照 **] を選択します**。
    7.  コピーした ps1 スクリプトを選択します。

7.  :::no-loc text="Microsoft Teams Rooms"::: デバイスは、2 回目の再起動 :::no-loc text="Microsoft Monitoring"::: でエージェントをインストールして構成する必要があります。

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
> エージェントを再構成する必要がある [ :::no-loc text="Log Analytics"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) 場合、エージェントを別のワークスペースに移動する必要がある場合、または最初のインストール後にプロキシ設定を変更する必要がある場合は、「エージェントを管理および保守する」を参照してください。

## <a name="additional-solutions"></a>その他のソリューション
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor":::は、環境の監視に役立つ[](https://docs.microsoft.com/azure/azure-monitor/insights/solutions)ソリューション ギャラリーを通じて組み込みの管理ソリューションを提供します。 通知管理ソリューション[とエージェント正常性](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution)[ :::no-loc text="Azure Log Analytics"::: ソリューションをワークスペース](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth)にも追加することを強くお勧めします。

> [!NOTE]
> エージェント正常性ソリューションは、環境内の古いエージェントまたは破損したエージェントを特定するのに役立ち、通知管理ソリューションは、指定した期間中に発生したアラートに関する詳細 :::no-loc text="Microsoft Monitoring"::: を提供します。

## <a name="see-also"></a>関連項目

[プラン :::no-loc text="Microsoft Teams Rooms"::: の管理 :::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[デバイス :::no-loc text="Microsoft Teams Rooms"::: を管理するには、 :::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
