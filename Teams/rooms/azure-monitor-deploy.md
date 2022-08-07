---
title: Azure Monitor を使用してMicrosoft Teams Rooms監視をデプロイする
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: この記事では、Azure Monitor を使用して、統合されたエンドツーエンドの方法でMicrosoft Teams Roomsの監視をデプロイする方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2b6d1931b0a1818b5146f6ac0e02c225fea3af52
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267452"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-monitoring-with-no-loc-textazure-monitor"></a>を使用して監視をデプロイする:::no-loc text="Microsoft Teams Rooms"::::::no-loc text="Azure Monitor":::

この記事では、デバイスの統合されたエンドツーエンドの監視:::no-loc text="Microsoft Teams Rooms"::::::no-loc text="Azure Monitor":::をセットアップして展開する方法について説明します。

管理に役立つ基本的なテレメトリとアラートを提供するように内部:::no-loc text="Azure Monitor":::を:::no-loc text="Microsoft Teams Rooms":::構成:::no-loc text="Log Analytics":::できます。 管理ソリューションが成熟するにつれて、追加のデータと管理機能をデプロイして、デバイスの可用性とパフォーマンスのより詳細なビューを作成できます。

このガイドに従うことで、次の例のようなダッシュボードを使用して、デバイスの可用性、アプリケーションとハードウェアの正常性 :::no-loc text="Microsoft Teams Rooms"::: 、およびアプリケーションとオペレーティング システムのバージョン分布に関する詳細な状態レポートを取得できます。

![Microsoft Teams Roomsのサンプル Log Analytics ビューのスクリーンショット。](../media/Deploy-Azure-Monitor-1.png "Microsoft Teams Roomsのサンプル Log Analytics ビュー")

高いレベルでは、次のタスクを実行する必要があります。


1. [構成を検証する:::no-loc text="Log Analytics":::](azure-monitor-deploy.md#validate_LogAnalytics)
2. [管理セットアップ用にテスト デバイスを :::no-loc text="Log Analytics"::: 構成する](azure-monitor-deploy.md#configure_test_devices)
3. [カスタム フィールドをマップする](azure-monitor-deploy.md#Custom_fields)
4. [でビューを定義する:::no-loc text="Microsoft Teams Rooms"::::::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [アラートを定義する](azure-monitor-deploy.md#Alerts)
6. [監視用のすべてのデバイスを構成する](azure-monitor-deploy.md#configure_all_devices)
7. [その他のソリューションを :::no-loc text="Azure Monitor"::: 構成する](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> 最小限の構成では、 :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics":::オペレーティング システムを実行しているコンピューターを:::no-loc text="Windows":::監視できますが、すべての:::no-loc text="Microsoft Teams Rooms":::デバイスへのエージェントの展開を開始する前に実行する必要がある具体的な手順がいくつかあります:::no-loc text="Microsoft Teams Rooms":::。
> そのため、制御されたセットアップと構成に対して、すべての構成手順を適切な順序で実行することを非常に推奨します。 最終的な結果の品質は、初期構成の品質に大きく依存します。

## <a name="validate-no-loc-textlog-analytics-configuration"></a>構成を検証する:::no-loc text="Log Analytics":::
<a name="validate_LogAnalytics"> </a>

からログ:::no-loc text="Microsoft Teams Rooms":::の収集を:::no-loc text="Log Analytics":::開始するには、ワークスペースが必要です。 ワークスペースは、独自のデータ リポジトリ、データ ソース、ソリューションを備えた一意 :::no-loc text="Log Analytics"::: の環境です。 既に既存 :::no-loc text="Log Analytics"::: のワークスペースがある場合は、それを使用してデプロイを :::no-loc text="Microsoft Teams Rooms"::: 監視するか、または監視ニーズに固有の専用 :::no-loc text="Log Analytics"::: ワークスペースを :::no-loc text="Microsoft Teams Rooms"::: 作成できます。

新しい:::no-loc text="Log Analytics":::ワークスペースを作成する必要がある場合は、「[ポータルでワークスペースを作成する:::no-loc text="Log Analytics":::」の記事の手順に:::no-loc text="Azure":::](/azure/azure-monitor/learn/quick-create-workspace)従います。

> [!NOTE]
> で使用:::no-loc text="Log Analytics":::するには、アクティブなサブスクリプションが必要です:::no-loc text="Azure":::。:::no-loc text="Azure Monitor"::: サブスクリプションをお持 :::no-loc text="Azure"::: ちでない場合は、 [無料試用版サブスクリプションを](https://azure.microsoft.com/free) 開始点として作成できます。

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>イベント ログを収集:::no-loc text="Microsoft Teams Rooms":::するように構成:::no-loc text="Log Analytics":::する

:::no-loc text="Log Analytics"::: は、設定で指定された :::no-loc text="Windows"::: イベント ログからのみイベントを収集します。 ログごとに、選択した重大度を持つイベントのみが収集されます。

デバイスとアプリケーションの状態を監視:::no-loc text="Microsoft Teams Rooms":::するために必要なログを収集するように構成:::no-loc text="Log Analytics":::する必要があります。 :::no-loc text="Microsoft Teams Rooms"::: イベント ログを使用します **:::no-loc text="Skype Room System":::** 。

イベントを収集するように構成:::no-loc text="Log Analytics":::するには、次の:::no-loc text="Microsoft Teams Rooms":::[イベント ログ データ ソースを:::no-loc text="Azure Monitor":::参照してください:::no-loc text="Windows":::](/azure/azure-monitor/platform/data-sources-windows-events)。

![イベント ログ設定のスクリーンショット。](../media/Deploy-Azure-Monitor-2.png "イベント ログの設定")

> [!IMPORTANT]
> イベント ログの設定を構成 :::no-loc text="Windows"::: し、イベント ログ名として入力 **:::no-loc text="Skype Room System":::** し、[ **エラー**]、[ **警告**]、[ **情報** ] チェック ボックスをオンにします。

## <a name="configure-test-devices-for-azure-monitoring"></a>Azure Monitoring のテスト デバイスを構成する
<a name="configure_test_devices"> </a>

関連するイベントを監視:::no-loc text="Microsoft Teams Rooms":::できるように準備:::no-loc text="Log Analytics":::する必要があります。 まず、物理アクセス権を持つ 1 つまたは 2 つの:::no-loc text="Microsoft Teams Rooms":::デバイスにエージェントをデプロイ:::no-loc text="Microsoft Monitoring":::し、それらのテスト デバイスにデータを生成してワークスペースにプッシュする:::no-loc text="Log Analytics":::必要があります。

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>デバイスをテストするためのエージェントのインストール:::no-loc text="Microsoft Monitoring":::

「コンピューターを:::no-loc text="Microsoft Monitoring":::[サービス:::no-loc text="Azure":::に接続:::no-loc text="Windows":::する」の手順を使用して、テスト デバイスにエージェントを:::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/agent-windows)展開します。 この記事では、エージェントを:::no-loc text="Windows":::デプロイ:::no-loc text="Microsoft Monitoring":::する手順、**ワークスペース ID** _ を取得する手順、デプロイに接続されている:::no-loc text="Azure Monitor":::デバイスを:::no-loc text="Log Analytics"::: *取得:::no-loc text="Microsoft Teams Rooms":::するための _ *_primary キー_** について説明し、エージェントのインスタンスへの接続を確認する手順について:::no-loc text="Log Analytics":::説明します。

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>サンプル イベントを :::no-loc text="Microsoft Teams Rooms"::: 生成する

エージェントが:::no-loc text="Microsoft Monitoring":::テスト デバイスにデプロイされたら、必要なイベント ログ データが .:::no-loc text="Azure Monitor":::

> [!NOTE]
> エージェントのインストール後にデバイスを :::no-loc text="Microsoft Monitoring"::: 再起動し、会議アプリが開始されていることを確認 :::no-loc text="Microsoft Teams Rooms"::: して、イベント ログに新しいイベントを生成できるようにします。

1.  ポータルに[:::no-loc text="Microsoft Azure":::](https://portal.azure.com)サインインし、ワークスペースに:::no-loc text="Log Analytics":::移動して選択します。

2.  デバイスによって生成されたハートビート イベントを :::no-loc text="Microsoft Teams Rooms"::: 一覧表示します。
    1.  ワークスペースを選択して **[ログ]** に移動し、クエリを使用して、ユーザー設定フィールド :::no-loc text="Microsoft Teams Rooms":::を含むハートビート レコードを取得します。
    2.  サンプル クエリ: `Event | where Source == "SRS-App" and EventID == 2000`

3.  会議アプリによって生成されたイベントを含むログ レコードが :::no-loc text="Microsoft Teams Rooms"::: クエリから返されることを確認します。

4.  ハードウェアの問題を生成し、必要なイベントがログイン :::no-loc text="Azure Log Analytics":::していることを検証します。
    1.  テスト :::no-loc text="Microsoft Teams Rooms"::: システムの周辺機器の 1 つを取り外します。 カメラ、スピーカー、マイク、フロント ルーム ディスプレイなどです。
    2.  イベント ログが入力 :::no-loc text="Azure Log Analytics":::されるまで 10 分待ちます。
    3.  クエリを使用してハードウェア エラー イベントを一覧表示します。 `Event | where Source == "SRS-App" and EventID == 3001`

5.  アプリケーションの問題を生成し、必要なイベントがログに記録されていることを検証します。
    1.  アカウント構成を変更:::no-loc text="Microsoft Teams Rooms":::し、正しくないEmailとパスワードのペアを入力します。
    2.  イベント ログが入力 :::no-loc text="Azure Log Analytics":::されるまで 10 分待ちます。
    3.  クエリを使用して、アプリケーション エラー イベントを一覧表示します。 `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> これらのサンプル イベント ログは、ユーザー設定フィールドを構成する前に必要です。 必要なイベント ログを収集するまで、次の手順に進んではいないでください。

## <a name="map-custom-fields"></a>カスタム フィールドをマップする
<a name="Custom_fields"> </a>

ユーザー設定フィールドを使用して、イベント ログから特定のデータを抽出します。 タイル、ダッシュボード ビュー、アラートで後で使用するカスタム フィールドを定義する必要があります。 カスタム フィールドの作成を開始する前 [に、「カスタム フィールド」 :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/custom-fields) を参照し、概念について理解してください。

キャプチャされたイベント ログからカスタム フィールドを抽出するには、次の手順に従います。

1.  ポータルに[:::no-loc text="Microsoft Azure":::](https://portal.azure.com)サインインし、ワークスペースに:::no-loc text="Log Analytics":::移動して選択します。

2. デバイスによって生成されたイベントを :::no-loc text="Microsoft Teams Rooms"::: 一覧表示します。
   1.  **[ログ]** に移動し、クエリを使用して、ユーザー設定フィールドを持つレコードを取得します。
   2.  サンプル クエリ: `Event | where Source == "SRS-App" and EventID == 2000`

3. レコードのいずれかを選択し、左側のボタンを選択して、フィールド抽出ウィザードを開始します。
4. RenderedDescription から抽出するデータを強調表示し、フィールド タイトルを指定します。 使用する必要があるフィールド名を表 1 に示します。
5. *表 1* に示すマッピングを使用します。 :::no-loc text="Log Analytics":::新しいフィールドを **\_** 定義すると、CF 文字列が自動的に追加されます。

> [!IMPORTANT]
> すべての JSON とフィールドでは大文字と :::no-loc text="Log Analytics"::: 小文字が区別されます。
> 
> 次の表の各ユーザー設定フィールドに必要なクエリに注意してください。 ユーザー設定フィールド値を正常に抽出するには、適切な :::no-loc text="Log Analytics"::: クエリを使用する必要があります。
> 
**表 1**

| **JSON フィールド**                   | **:::no-loc text="Log Analytics"::: ユーザー設定フィールド** | **イベント ID** | **抽出で使用するクエリ**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| 説明                      | SRSEventDescription         | **2000**     | \| Source == "SRS-App" と EventID == 2000 のイベント |
| ResourceState                    | SRSResourceState            | **2000**     | \| Source == "SRS-App" と EventID == 2000 のイベント |
| OperationName                    | SRSOperationName            | **2000**     | \| Source == "SRS-App" と EventID == 2000 のイベント |
| OperationResult                  | SRSOperationResult          | **2000**     | \| Source == "SRS-App" と EventID == 2000 のイベント |
| OS                               | SRSOSVersion                | **2000**     | \| Source == "SRS-App" と EventID == 2000 のイベント |
| OSVersion                        | SRSOSLongVersion            | **2000**     | \| Source == "SRS-App" と EventID == 2000 のイベント |
| Alias                            | SRSAlias                    | **2000**     | \| Source == "SRS-App" と EventID == 2000 のイベント |
| DisplayName                      | SRSDisplayName              | **2000**     | \| Source == "SRS-App" と EventID == 2000 のイベント |
| AppVersion                       | SRSAppVersion               | **2000**     | \| Source == "SRS-App" と EventID == 2000 のイベント |
| IPv4Address                      | SRSIPv4Address              | **2000**     | \| Source == "SRS-App" と EventID == 2000 のイベント |
| IPv6Address                      | SRSIPv6Address              | **2000**     | \| Source == "SRS-App" と EventID == 2000 のイベント |
| 会議マイクの状態     | SRSConfMicrophoneStatus     | **3001**     | \| Source == "SRS-App" と EventID == 3001 のイベント |
| 会議講演者の状態        | SRSConfSpeakerStatus        | **3001**     | \| Source == "SRS-App" と EventID == 3001 のイベント |
| 既定の話者の状態           | SRSDefaultSpeakerStatus     | **3001**     | \| Source == "SRS-App" と EventID == 3001 のイベント |
| カメラの状態                    | SRSCameraStatus             | **3001**     | \| Source == "SRS-App" と EventID == 3001 のイベント |
| ルームの前面の表示状態     | SRSFORDStatus               | **3001**     | \| Source == "SRS-App" と EventID == 3001 のイベント |
| モーション センサーの状態             | SRSMotionSensorStatus       | **3001**     | \| Source == "SRS-App" と EventID == 3001 のイベント |
| HDMI 取り込み状態               | SRSHDMIIngestStatus         | **3001**     | \| Source == "SRS-App" と EventID == 3001 のイベント |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>でビューを定義する:::no-loc text="Microsoft Teams Rooms"::::::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

データが収集され、カスタム フィールドがマップされたら、ビュー デザイナーを使用して、さまざまなタイルを含むダッシュボードを開発してイベントを監視 :::no-loc text="Microsoft Teams Rooms"::: できます。 ビュー デザイナーを使用して、次のタイルを作成します。 詳細については、「[ビュー デザイナーを使用してカスタム ビューを作成する」を:::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/view-designer)参照してください。

> [!NOTE]
> このガイドの前の手順は、ダッシュボード タイルが正常に機能するように完了している必要があります。
>
> [!IMPORTANT]
> [Azure Monitor のビュー デザイナーは 2023 年 8 月 31 日に廃止され、2020](https://azure.microsoft.com/updates/view-designer-in-azure-monitor-is-retiring-on-31-august-2023/) 年 11 月 30 日に機能の作成と複製が無効になっています。 代わりにブックを使用できます。 ビュー デザイナーのブックへの切り替えガイドの詳細については、 [プリセット ビュー デザイナー テンプレートを使用したクイック スタート](/azure/azure-monitor/visualize/view-designer-conversion-tasks#quickstart-with-preset-view-designer-templates)に関するページを参照してください。

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Microsoft Teams Rooms ダッシュボードを手動で作成する

または、独自のダッシュボードを作成し、監視するタイルのみを追加することもできます。

#### <a name="configure-the-overview-tile"></a>概要タイルを構成する

1.  **ビュー デザイナーを** 開きます。
2.  [ **概要] タイル** を選択し、ギャラリーから **[2 つの数値** ] を選択します。
3.  タイルに名前を付けます **:::no-loc text="Microsoft Teams Rooms":::**。
4.  最初の **タイル** を定義します。<br>
    **伝説：** 過去 1 か月以内に少なくとも 1 回ハートビートを送信したデバイス<br>
    **クエリ：** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  **2 番目のタイル** を定義します。<br>
    **伝説：** 過去 1 時間以内にハートビートを送信したアクティブなデバイス<br>
    **クエリ：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  **[適用]** を選択します。

### <a name="create-a-tile-that-displays-active-devices"></a>アクティブなデバイスを表示するタイルを作成する

1.  [ **ダッシュボードの表示** ] を選択して、タイルの追加を開始します。
2.  ギャラリーから **[数値&一覧** を選択する]
3.  **General** プロパティを定義します。<br>
    **グループ タイトル:** ハートビートの状態<br>
    **新しいグループ:** 選択
4.  **Tile** プロパティを定義します。<br>
    **伝説：** アクティブなデバイス (過去 20 分間に送信されたハートビート)<br>
    **タイルのクエリ:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  List プロパティを定義 **します** 。<br>
    **リスト クエリ:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  **列タイトルを定義する**:<br>
    **名前：** コンピューター名<br>
    **値：** 最後のハートビート
7.  **ナビゲーション クエリを定義します**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  [ **適用]**、[ **閉じる**] の順に選択します。

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>接続の問題があるデバイスを表示するタイルを作成する

1.  ギャラリーから **[数値&一覧** ] を選択し、新しいタイルを追加します。
2.  **General** プロパティを定義します。<br>
    **グループ タイトル:** 空のままにする<br>
    **新しいグループ:** [選択されていません]
3.  **Tile** プロパティを定義します。<br>
    **伝説：** 非アクティブなデバイス (過去 20 分間にハートビート メッセージが送信されない)<br>
    **タイルのクエリ:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  List プロパティを定義 **します** 。<br>
    **リスト クエリ:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  **列タイトルを定義する**:<br>
    **名前：** コンピューター名<br>
    **値：** 最後のハートビート
6.  **ナビゲーション クエリを定義する:**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  [ **適用]**、[ **閉じる**] の順に選択します。

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>ハードウェア エラーが発生したデバイスを表示するタイルを作成する

1.  ギャラリーから **[数値&一覧** ] を選択し、新しいタイルを追加します。
2.  **General** プロパティを定義します。<br>
    **グループ タイトル:** ハードウェアの状態<br>
    **新しいグループ:** 選択
3.  **Tile** プロパティを定義します。<br>
    **伝説：** 過去 1 時間にハードウェア エラーが発生したデバイス<br>
    **タイルのクエリ:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  List プロパティを定義 **します** 。<br>
    **リスト クエリ:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  **列タイトルを定義する**:<br>
    **名前：** コンピューター名<br>
    **値：** 最後のエラー
6.  **ナビゲーション クエリを定義する:**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  [ **適用]**、[ **閉じる**] の順に選択します。

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>オペレーティング システムのバージョンを表示する :::no-loc text="Microsoft Teams Rooms"::: タイルを作成する

1.  ギャラリーから **[ドーナツ&一覧** ] を選択し、新しいタイルを追加します。
2.  **General** プロパティを定義します。<br>
    **グループ タイトル:** オペレーティング システムの詳細<br>
    **新しいグループ:** 選択
3.  ヘッダープロパティを定義 **します** 。<br>
    **タイトル：** オペレーティング システムのバージョン<br>
    **字幕：** 特定の OS バージョンを実行しているデバイス
4.  **Donut** プロパティを定義します。<br>
    **クエリ：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **中央揃えテキスト:** デバイス<br>
    **操作：** 合計
5.  List プロパティを定義 **します** 。<br>
    **リスト クエリ:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **グラフを非表示にする:** 選択<br>
    **Sparklines を有効にする:** [選択されていません]
6.  **列タイトルを定義します**。<br>
    **名前：** コンピューター名<br>
    **値：** 空のままにする
7.  **ナビゲーション クエリを定義します**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  [ **適用]** 、[ **閉じる**] の順に選択します。

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>アプリケーションバージョンを表示するタイルを :::no-loc text="Microsoft Teams Rooms"::: 作成する

1.  ギャラリーから **[ドーナツ&一覧** ] を選択し、新しいタイルを追加します。
2.  **General** プロパティを定義します。<br>
    **グループ タイトル:** :::no-loc text="Microsoft Teams Rooms"::: アプリケーションの詳細<br>
    **新しいグループ:** 選択
3.  ヘッダープロパティを定義 **します** 。<br>
    **タイトル：** アプリケーションのバージョン<br>
    **字幕：** 特定のアプリケーション バージョンを実行しているデバイス
4.  **Donut** プロパティを定義します。<br>
    **クエリ：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **中央揃えテキスト:** デバイス<br>
    **操作：** 合計
5.  List プロパティを定義 **します** 。<br>
    **リスト クエリ:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **グラフを非表示にする:** 選択<br>
    **Sparklines を有効にする:** [選択されていません]
6.  **列タイトルを定義します**。<br>
    **名前：** コンピューター名<br>
    **値：** 空のままにする
7.  **ナビゲーション クエリを定義します**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  [ **適用]** 、[ **閉じる**] の順に選択します。

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>アプリケーション エラーが発生したデバイスを表示するタイルを作成する

1.  ギャラリーから **[数値&一覧** ] を選択し、新しいタイルを追加します。
2.  **General** プロパティを定義します。<br>
    **グループ タイトル:** 空のままにする<br>
    **新しいグループ:** [選択されていません]
3.  **Tile** プロパティを定義します。<br>
    **伝説：** 過去 1 時間にアプリケーション エラーが発生したデバイス<br>
    **タイルのクエリ:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  List プロパティを定義 **します** 。<br>
    **リスト クエリ:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  **列タイトルを定義します**。<br>
    **名前：** コンピューター名<br>
    **値：** 最後のエラー
6.  **ナビゲーション クエリを定義します**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  [ **適用]** 、[ **閉じる**] の順に選択します。

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>再起動されたデバイスを表示するタイルを作成する

1.  ギャラリーから **[数値&一覧** ] を選択し、新しいタイルを追加します。
2.  **General** プロパティを定義します。<br>
    **グループ タイトル:** 空のままにする<br>
    **新しいグループ:** [選択されていません]
3.  **Tile** プロパティを定義します。<br>
    **伝説：** 過去 24 時間にアプリケーションが再起動されたデバイスと再起動回数<br>
    **タイルのクエリ:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  List プロパティを定義 **します** 。<br>
    **リスト クエリ:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  **列タイトルを定義します**。<br>
    **名前：** コンピューター名<br>
    **値：** 再起動の数
6.  **ナビゲーション クエリを定義します**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  [ **適用]** 、[ **閉じる**] の順に選択します。
8.  **[保存] を** 選択してダッシュボードを保存します。

これで、ビューの作成が完了しました。

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>でアラートを構成する :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: は、コンソールで問題が発生したときに :::no-loc text="Microsoft Teams Rooms"::: 管理者に通知するアラートを発生させることができます。

:::no-loc text="Azure Monitor"::: には、定期的にスケジュールされたログ検索を実行する組み込みのアラート メカニズムが含まれています。 ログ検索の結果が特定の条件と一致する場合は、アラート レコードが作成されます。

その後、ルールは 1 つ以上のアクションを自動的に実行して、アラートを事前に通知したり、別のプロセスを呼び出したりできます。 アラートで使用できるオプションは次のとおりです。
-   電子メールの送信
-   HTTP POST 要求を使用した外部プロセスの呼び出し
-   サービスでの Runbook の :::no-loc text="Azure Automation"::: 開始

アラートの詳細については、「[アラートをログに:::no-loc text="Azure Monitor":::記録](/azure/azure-monitor/platform/alerts-unified-log)する」を:::no-loc text="Azure Monitor":::参照してください。

> [!NOTE]
> 次の例では、デバイスがハードウェアまたはアプリケーション エラーを :::no-loc text="Microsoft Teams Rooms"::: 生成したときに電子メール アラートを送信します。

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>ハードウェアの問題に関する電子メール アラートを :::no-loc text="Microsoft Teams Rooms"::: 構成する

過去 1 時間以内にハードウェアの問題が発生したデバイスを確認 :::no-loc text="Microsoft Teams Rooms"::: するアラート ルールを構成します。
1.  ポータルに[:::no-loc text="Microsoft Azure":::](https://portal.azure.com)サインインし、ワークスペースに:::no-loc text="Log Analytics":::移動して選択します。

2. ワークスペースに:::no-loc text="Log Analytics":::移動し、[**アラート**] を選択し、[**新しいアラート ルール**] を選択します。

3. **[条件の追加]** を選択し、[**カスタム ログ検索**] を選択します。

4.  [検索クエリ] テキスト ボックスに次のクエリを入力します。<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  アラート ロジック設定を構成します。<br>
    **に基づいて：** 結果の数<br>
    **条件：** より大きい<br>
    **しきい値:** 0<br>

6. 評価設定を構成し、[ **完了**] を選択します。 <br>
    **期間 (分単位):** 60<br>
    **頻度 (分単位):** 60<br>

7. アクション グループを構成する:
    1.  **[新規作成**] を選択する
    2.  *[アクション グループ* 名] フィールドと [短い名前] フィールドに適切 *な名前を指定します*。
    3.  一意の *アクション名* を指定し、**Email/SMS/プッシュ/音声** を選択して、[**詳細の編集]** を選択します。
    4.  **[Email**] チェック ボックスをオンにし、アラートを受信するユーザーまたはグループの電子メール アドレスを指定します。
    5.  また、SMS、音声通話、またはその両方で通知を受け取るために電話番号を入力することもできます。
    6. [ **OK] を選択します**。

8. アラート メールの件名をオーバーライドする場合は、**アクションをカスタマイズ** します。

9. ルールの名前と説明を指定します。<br>
    **ルール名:** :::no-loc text="Microsoft Teams Rooms"::: ハードウェア障害アラート<br>
    **説明：** 過去 1 時間以内にハードウェアの問題が発生したデバイスの一覧<br>

10. 目的の重大度を選択し、ルールが有効になっていることを確認します。

11. [ **アラート ルールの作成**] を選択します。

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>アプリケーションの問題に対する電子メール アラートを :::no-loc text="Microsoft Teams Rooms"::: 構成する

同じ手順を繰り返しますが、次のクエリを使用して、過去 1 時間以内にアプリケーションの問題が発生したデバイスを一覧表示します。

 ```
 Event
 | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
 | summarize arg_max(TimeGenerated, *) by Computer
 | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
 | sort by TimeGenerated desc
 ```

これでアラートの定義が完了しました。 上記の例を使用して、追加のアラートを定義できます。

アラートが生成されると、過去 1 時間以内に問題が発生したデバイスを一覧表示する電子メールが届きます。

![サンプル :::no-loc text="Azure Monitor"::: アラート 電子メール](../media/Deploy-Azure-Monitor-6.png "サンプル :::no-loc text=&quot;Azure Monitor&quot;::: アラート 電子メール")

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>すべてのデバイスを構成する :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"> </a>ダッシュボードとアラートが構成されたら、すべての:::no-loc text="Microsoft Teams Rooms":::デバイスでエージェントを設定して構成:::no-loc text="Microsoft Monitoring":::し、監視デプロイを完了できます。

各デバイスにエージェントを :::no-loc text="Microsoft Monitoring"::: 手動でインストールして構成できますが、既存のソフトウェア展開ツールと方法を利用することを非常に推奨します。

初めてデバイスを :::no-loc text="Microsoft Teams Rooms"::: ビルドする場合は、ビルド プロセスの一部としてエージェントの :::no-loc text="Microsoft Monitoring"::: セットアップと構成の手順を含めることができます。 詳細については、「 [コマンド ラインを使用してエージェントをインストールする」を](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)参照してください。

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>:::no-loc text="Microsoft Monitoring":::グループ ポリシー オブジェクト (GPO) を使用したエージェントの展開

実装:::no-loc text="Azure Monitoring":::する前にデバイスを:::no-loc text="Microsoft Teams Rooms":::既にデプロイしている場合は、指定されたスクリプトを使用して、グループ ポリシー オブジェクトを使用してエージェントを:::no-loc text="Active Directory":::設定および構成できます。

1.  共有ネットワーク パスを作成し、 **ドメイン コンピューター** グループへの読み取りアクセス権を付与します。

2.  エージェントの 64 ビット バージョンを :::no-loc text="Microsoft Monitoring"::: ダウンロードします :::no-loc text="Windows"::: 。 <https://go.microsoft.com/fwlink/?LinkID=517476>

3.  セットアップ パッケージの内容をネットワーク共有に抽出します。
    1.  コマンド プロンプト ウィンドウを開き、**/cMMASetup-AMD64.exe** 実行します。
    2.  作成した共有を指定し、コンテンツを抽出します。

4.  新しいグループ ポリシー オブジェクトを作成し、マシン アカウントがある:::no-loc text="Microsoft Teams Rooms":::組織単位に割り当てます。

5.  PowerShell 実行ポリシーを構成する:
    1.  新しく作成したグループ ポリシー オブジェクトを編集し、コンピューター構成\\ポリシー\\管理用テンプレート \\ :::no-loc text="Windows"::: コンポーネント\\に移動します :::no-loc text="Windows PowerShell":::
    2.  **[スクリプトの実行を有効にする] を有効に** し、[**実行ポリシー]** を **[ローカル スクリプトを許可する]** に設定します。

6.  スタートアップ スクリプトを構成します。
    1.  次のスクリプトをコピーし、Install-MMAgent.ps1として保存します。
    2.  WorkspaceId、WorkspaceKey、および SetupPath パラメーターを構成に合わせて変更します。
    3.  同じグループ ポリシー オブジェクトを編集し、コンピューター構成\\ポリシー \\ :::no-loc text="Windows":::設定\\スクリプト (スタートアップ/シャットダウン) に移動します。
    4.  ダブルクリックして **[スタートアップ]** を選択し、[ **PowerShell スクリプト**] を選択します。
    5.  [ **ファイルの表示**] を選択し、 **Install-MMAgent.ps1** ファイルをそのフォルダーにコピーします。
    6.  [ **追加]**、[参照] の順に選択 **します**。
    7.  コピーした ps1 スクリプトを選択します。

7.  :::no-loc text="Microsoft Teams Rooms"::: は、2 回目の再起動でエージェントを :::no-loc text="Microsoft Monitoring"::: インストールして構成する必要があります。

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
> エージェントを再構成したり、別のワークスペースに移動したり、初回インストール後にプロキシ設定を変更したりする必要がある場合は、エージェントの[管理と保守:::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/agent-manage)に関する記事を参照してください。

## <a name="additional-solutions"></a>その他のソリューション
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor"::: には、環境の監視をさらに支援するために [、ソリューション ギャラリー](/azure/azure-monitor/insights/solutions) を通じて組み込みの管理ソリューションが用意されています。 [アラート管理](/azure/azure-monitor/platform/alert-management-solution)ソリューションと[:::no-loc text="Azure Log Analytics":::エージェント正常性](/azure/azure-monitor/insights/solution-agenthealth)ソリューションもワークスペースに追加することを非常に推奨します。

> [!NOTE]
> Agent Health ソリューションは、環境内の古いエージェントや破損した :::no-loc text="Microsoft Monitoring"::: エージェントを特定するのに役立ちます。アラート管理ソリューションは、特定の期間内に発生したアラートに関する詳細を提供します。

## <a name="see-also"></a>関連項目

[を使用して管理を計画 :::no-loc text="Microsoft Teams Rooms"::: する :::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[を使用してデバイスを管理 :::no-loc text="Microsoft Teams Rooms"::: する :::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
