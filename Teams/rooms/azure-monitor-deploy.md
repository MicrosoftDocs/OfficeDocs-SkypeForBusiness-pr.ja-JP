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
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a>:::no-loc text="Microsoft Teams Rooms":::管理を展開する:::no-loc text="Azure Monitor":::

この記事では、を使用して、統合されたエンドツーエンドのデバイス管理をセットアップして展開する方法について説明し :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: ます。

会議室のデバイスを管理するのに :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor"::: 役立つ基本的なテレメトリとアラートを提供するように、内で構成することができ :::no-loc text="Microsoft Teams Rooms"::: ます。 管理ソリューションの成熟に応じて、デバイスの可用性とパフォーマンスの詳細なビューを作成するために、追加のデータと管理機能を展開することができます。

このガイドに従うと、次の例のようなダッシュボードを使用して、デバイスの可用性、アプリケーションとハードウェアの正常性、およびアプリケーションとオペレーティングシステムのバージョンの配布に関する詳細な状態レポートを取得でき :::no-loc text="Microsoft Teams Rooms"::: ます。

![Microsoft Teams ルームのサンプルログ分析ビューのスクリーンショット](../media/Deploy-Azure-Monitor-1.png "Microsoft Teams ルームのサンプルログ分析ビュー")

高いレベルでは、次のタスクを実行する必要があります。


1. [構成の検証 :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#validate_LogAnalytics)
2. [管理セットアップ用にテストデバイスを構成する :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#configure_test_devices)
3. [カスタム フィールドをマップする](azure-monitor-deploy.md#Custom_fields)
4. [ビューの定義 :::no-loc text="Microsoft Teams Rooms"::::::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [通知を定義する](azure-monitor-deploy.md#Alerts)
6. [すべてのデバイスを監視対象として構成する](azure-monitor-deploy.md#configure_all_devices)
7. [その他のソリューションを構成する :::no-loc text="Azure Monitor":::](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> 最小限の構成では、 :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: オペレーティングシステムを実行しているコンピューターを監視できますが、 :::no-loc text="Windows"::: すべてのデバイスへのエージェントの展開を開始する前に、いくつか :::no-loc text="Microsoft Teams Rooms"::: の具体的な手順を実行する必要があり :::no-loc text="Microsoft Teams Rooms"::: ます。
> そのため、管理された設定と構成については、すべての構成手順を適切な順序で実行することを強くお勧めします。 最終的な結果の品質は、初期構成の品質によって大きく異なります。

## <a name="validate-no-loc-textlog-analytics-configuration"></a>構成の検証 :::no-loc text="Log Analytics":::
<a name="validate_LogAnalytics"> </a>

:::no-loc text="Log Analytics":::デバイスからのログの収集を開始するには、ワークスペースが必要 :::no-loc text="Microsoft Teams Rooms"::: です。 ワークスペースは、 :::no-loc text="Log Analytics"::: 独自のデータリポジトリ、データソース、およびソリューションを備えた、固有の環境です。 既存のワークスペースを既に持っている場合 :::no-loc text="Log Analytics"::: は、それを使って展開を監視する :::no-loc text="Microsoft Teams Rooms"::: か、または :::no-loc text="Log Analytics"::: 監視ニーズに合わせた専用のワークスペースを作成することができ :::no-loc text="Microsoft Teams Rooms"::: ます。

新しいワークスペースを作成する必要がある場合は、 :::no-loc text="Log Analytics"::: 「 [ :::no-loc text="Log Analytics"::: :::no-loc text="Azure"::: ポータルでワークスペースを作成](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)する」の手順に従います。

> [!NOTE]
> を使用するには :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor"::: 、有効なサブスクリプションが必要 :::no-loc text="Azure"::: です。 サブスクリプションを持っていない場合は :::no-loc text="Azure"::: 、出発点として [無料トライアルサブスクリプションを](https://azure.microsoft.com/free) 作成できます。

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>:::no-loc text="Log Analytics":::イベントログを収集するように構成する :::no-loc text="Microsoft Teams Rooms":::

:::no-loc text="Log Analytics"::: 設定で指定されたイベントログのイベントのみを収集し :::no-loc text="Windows"::: ます。 各ログについて、選択した重大度のイベントのみが収集されます。

:::no-loc text="Log Analytics":::デバイスとアプリケーションの状態を監視するために必要なログを収集するように構成する必要があり :::no-loc text="Microsoft Teams Rooms"::: ます。 :::no-loc text="Microsoft Teams Rooms"::: デバイスは **:::no-loc text="Skype Room System":::** イベントログを使います。

イベントを収集するように構成するには :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: 、「 [ :::no-loc text="Windows"::: イベント :::no-loc text="Azure Monitor"::: ログのデータソース](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)」を参照してください。

![イベントログ設定のスクリーンショット](../media/Deploy-Azure-Monitor-2.png "イベントログの設定")

> [!IMPORTANT]
> :::no-loc text="Windows":::イベントログの設定を構成し、イベントログの名前を入力して、 **:::no-loc text="Skype Room System":::** [**エラー**]、[**警告**]、[**情報**] のチェックボックスをオンにします。

## <a name="configure-test-devices-for-azure-monitoring"></a>Azure Monitoring のテストデバイスを構成する
<a name="configure_test_devices"> </a>

関連するイベントを監視できるように準備する必要があり :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: ます。 まず、 :::no-loc text="Microsoft Monitoring"::: 物理的にアクセスできる1つまたは2つのデバイスにエージェントを展開 :::no-loc text="Microsoft Teams Rooms"::: し、それらのテストデバイスでデータを生成してワークスペースにプッシュする必要があり :::no-loc text="Log Analytics"::: ます。

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>:::no-loc text="Microsoft Monitoring":::エージェントをインストールしてデバイスをテストする

:::no-loc text="Microsoft Monitoring":::「 [ :::no-loc text="Windows"::: コンピューターを :::no-loc text="Log Analytics"::: サービス :::no-loc text="Azure"::: に接続する](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)」で説明されている手順を使用して、エージェントをテストデバイスに展開します。 この記事では :::no-loc text="Microsoft Monitoring"::: 、エージェントの展開手順 :::no-loc text="Windows"::: 、 :::no-loc text="Log Analytics"::: ***ワークスペース ID*** の取得手順、展開に接続するデバイスを取得するための ***主キー*** 、 :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: およびインスタンスへのエージェントの接続性を確認する手順 :::no-loc text="Log Analytics"::: について詳しく説明します。

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>サンプルイベントを生成する :::no-loc text="Microsoft Teams Rooms":::

エージェントを :::no-loc text="Microsoft Monitoring"::: テストデバイスに展開した後、必要なイベントログデータがで収集されていることを確認し :::no-loc text="Azure Monitor"::: ます。

> [!NOTE]
> エージェントをインストールした後でデバイスを再起動 :::no-loc text="Microsoft Monitoring"::: し、 :::no-loc text="Microsoft Teams Rooms"::: アプリが新しいイベントを生成できるように会議アプリが開始されていることを確認します。

1.  [ :::no-loc text="Microsoft Azure"::: ポータル](https://portal.azure.com)にサインインして、ワークスペースに移動して :::no-loc text="Log Analytics"::: 選択します。

2.  デバイスによって生成されるハートビートイベントを一覧表示し :::no-loc text="Microsoft Teams Rooms"::: ます。
    1.  ワークスペースを選択して、[ **ログ** ] に移動し、[クエリ] を使用して、ユーザー設定フィールドを含むハートビートレコードを取得し :::no-loc text="Microsoft Teams Rooms"::: ます。
    2.  サンプルクエリ: `Event | where Source == "SRS-App" and EventID == 2000`

3.  会議アプリによって生成されたイベントを含むログレコードが、クエリによって返されていることを確認してください :::no-loc text="Microsoft Teams Rooms"::: 。

4.  ハードウェアの問題を生成し、必要なイベントがログに記録されていることを確認し :::no-loc text="Azure Log Analytics"::: ます。
    1.  テストシステムでいずれかの周辺機器を取り外し :::no-loc text="Microsoft Teams Rooms"::: ます。 カメラ、スピーカーフォン、マイク、またはフロントルームディスプレイの場合があります
    2.  イベントログが設定されるまで10分待ち :::no-loc text="Azure Log Analytics"::: ます。
    3.  クエリを使用して、ハードウェアエラーイベントを一覧表示します。 `Event | where Source == "SRS-App" and EventID == 3001`

5.  アプリケーションの問題を生成し、必要なイベントがログに記録されていることを確認します。
    1.  :::no-loc text="Microsoft Teams Rooms":::アプリケーションの構成を変更し、誤ったセッション開始プロトコル (SIP) アドレスとパスワードのペアを入力します。
    2.  イベントログが設定されるまで10分待ち :::no-loc text="Azure Log Analytics"::: ます。
    3.  クエリを使用して、アプリケーションエラーイベントを一覧表示します。 `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> カスタムフィールドを構成するには、これらのサンプルイベントログが必要です。 必要なイベントログを収集するまでは、次の手順に進んではいけません。

## <a name="map-custom-fields"></a>カスタム フィールドをマップする
<a name="Custom_fields"> </a>

カスタムフィールドを使って、イベントログから特定のデータを抽出します。 タイル、ダッシュボードビュー、およびアラートで後で使用されるカスタムフィールドを定義する必要があります。 カスタムフィールドの作成を開始する前に、「[ユーザー設定フィールド :::no-loc text="Log Analytics"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) 」を参照して、概念を理解しておいてください。

キャプチャしたイベントログからカスタムフィールドを抽出するには、次の手順を実行します。

1.  [ :::no-loc text="Microsoft Azure"::: ポータル](https://portal.azure.com)にサインインして、ワークスペースに移動して :::no-loc text="Log Analytics"::: 選択します。

2. デバイスによって生成されるイベントを一覧表示し :::no-loc text="Microsoft Teams Rooms"::: ます。
   1.  [ **ログ** ] に移動し、クエリを使用してユーザー設定フィールドを含むレコードを取得します。
   2.  サンプルクエリ: `Event | where Source == "SRS-App" and EventID == 2000`

3. いずれかのレコードを選び、左側のボタンを選んで、フィールド抽出ウィザードを開始します。
4. RenderedDescription から抽出するデータを強調表示し、フィールドタイトルを入力します。 使用する必要があるフィールド名は、表1に記載されています。
5. *表 1*に示されているマッピングを使用します。 :::no-loc text="Log Analytics":::新しいフィールドを定義するときに、自動的に** \_ CF**文字列が追加されます。

> [!IMPORTANT]
> JSON と :::no-loc text="Log Analytics"::: フィールドはすべて大文字と小文字が区別されることに注意してください。
> 
> 以下の表のユーザー設定フィールドごとに、必要なクエリに注意してください。 :::no-loc text="Log Analytics":::ユーザー設定フィールドの値を正しく抽出するには、適切なクエリを使用する必要があります。
> 
**表1**

| **JSON フィールド**                   | **:::no-loc text="Log Analytics"::: ユーザー設定フィールド** | **イベント ID** | **抽出に使用するクエリ**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| 説明                      | SRSEventDescription         | **2000**     | \|Source = = "SRS-アプリ" And EventID = = 2000 |
| ResourceState                    | SRSResourceState            | **2000**     | \|Source = = "SRS-アプリ" And EventID = = 2000 |
| OperationName                    | SRSOperationName            | **2000**     | \|Source = = "SRS-アプリ" And EventID = = 2000 |
| OperationResult                  | SRSOperationResult          | **2000**     | \|Source = = "SRS-アプリ" And EventID = = 2000 |
| OS                               | SRSOSVersion                | **2000**     | \|Source = = "SRS-アプリ" And EventID = = 2000 |
| OSVersion                        | SRSOSLongVersion            | **2000**     | \|Source = = "SRS-アプリ" And EventID = = 2000 |
| Alias                            | SRSAlias                    | **2000**     | \|Source = = "SRS-アプリ" And EventID = = 2000 |
| DisplayName                      | SRSDisplayName              | **2000**     | \|Source = = "SRS-アプリ" And EventID = = 2000 |
| AppVersion                       | SRSAppVersion               | **2000**     | \|Source = = "SRS-アプリ" And EventID = = 2000 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | \|Source = = "SRS-アプリ" And EventID = = 2000 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | \|Source = = "SRS-アプリ" And EventID = = 2000 |
| 会議のマイクの状態     | Srsconfマイクロ電話の状態     | **3001**     | \|Source = = "SRS-アプリ" And EventID = = 3001 |
| 会議のスピーカーの状態        | SRSConfSpeakerStatus        | **3001**     | \|Source = = "SRS-アプリ" And EventID = = 3001 |
| 既定のスピーカーの状態           | SRSDefaultSpeakerStatus     | **3001**     | \|Source = = "SRS-アプリ" And EventID = = 3001 |
| カメラの状態                    | SRSCameraStatus             | **3001**     | \|Source = = "SRS-アプリ" And EventID = = 3001 |
| 部屋の表面の表示状態     | SRSFORDStatus               | **3001**     | \|Source = = "SRS-アプリ" And EventID = = 3001 |
| モーションセンサーの状態             | SRSMotionSensorStatus       | **3001**     | \|Source = = "SRS-アプリ" And EventID = = 3001 |
| HDMI 取り込みの状態               | SRSHDMIIngestStatus         | **3001**     | \|Source = = "SRS-アプリ" And EventID = = 3001 |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>ビューの定義 :::no-loc text="Microsoft Teams Rooms"::::::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

データが収集され、ユーザー設定フィールドがマップされた後、ビューデザイナーを使用して、さまざまなタイルを含むダッシュボードを作成し、イベントを監視することができ :::no-loc text="Microsoft Teams Rooms"::: ます。 次のタイルを作成するには、[ビューデザイナーを使用します。 詳細については、「[デザイナー :::no-loc text="Log Analytics"::: でビューデザイナーを使用してカスタムビューを作成](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)する」を参照してください。

> [!NOTE]
> ダッシュボードタイルが正常に動作するためには、このガイドの前の手順が完了している必要があります。

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>インポート方法を使用して Microsoft Teams のルームダッシュボードを作成する

ダッシュボードをインポート :::no-loc text="Microsoft Teams Rooms"::: して、デバイスの監視をすばやく開始することができます。 ダッシュボードをインポートするには、次の手順を実行します。

1.  Omsview ダッシュボードファイル [SkypeRoomSystems_v2](https://go.microsoft.com/fwlink/?linkid=835675) を取得します。
2.  [ :::no-loc text="Microsoft Azure"::: ポータル](https://portal.azure.com)にサインインして、ワークスペースに移動して :::no-loc text="Log Analytics"::: 選択します。
3.  **ビューデザイナー**を開きます。
4.  [ **インポート**] を選択し、 **omsview ファイル SkypeRoomSystems_v2** を選択します。
5.  **[保存]** を選択します。

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Microsoft Teams のルームダッシュボードを手動で作成する

または、独自のダッシュボードを作成して、監視するタイルのみを追加することもできます。

#### <a name="configure-the-overview-tile"></a>概要タイルを構成する

1.  **ビューデザイナー**を開きます。
2.  [ **概要] タイル**を選択し、ギャラリーから **2 つの数値** を選択します。
3.  タイルに名前を指定 **:::no-loc text="Microsoft Teams Rooms":::** します。
4.  最初の **タイル**を定義します。<br>
    **凡例:** 1ヶ月以内に少なくとも1回、ハートビートを送信したデバイス<br>
    **クエリ:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  **2 番目のタイル**を定義します。<br>
    **凡例:** 1時間以内にハートビートを送信したアクティブなデバイス<br>
    **クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  **[適用]** を選択します。

### <a name="create-a-tile-that-displays-active-devices"></a>アクティブなデバイスを表示するタイルを作成する

1.  [ **ダッシュボードの表示** ] を選択して、タイルの追加を開始します。
2.  ギャラリーから **番号 & リスト** を選択する
3.  **一般的な**プロパティを定義します。<br>
    **グループタイトル:** ハートビートの状態<br>
    **新しいグループ:** 選択した
4.  **タイル**のプロパティを定義します。<br>
    **凡例:** アクティブなデバイス (過去20分間に送信されたハートビート)<br>
    **タイルのクエリ: ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  **リスト**のプロパティを定義します。<br>
    **リストクエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  **列のタイトル**を定義します。<br>
    **Name:** コンピューター名<br>
    **値:** 最終ハートビート
7.  **ナビゲーションクエリ**を定義します。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  [ **適用**]、[ **閉じる**] の順に選択します。

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>接続の問題が発生しているデバイスを表示するタイルを作成する

1.  ギャラリーから [ **番号 & リスト** ] を選び、新しいタイルを追加します。
2.  **一般的な**プロパティを定義します。<br>
    **グループタイトル:** 空のままにする<br>
    **新しいグループ:** 未選択
3.  **タイル**のプロパティを定義します。<br>
    **凡例:** 非アクティブなデバイス (過去20分間送信されたハートビートメッセージなし)<br>
    **タイルのクエリ: ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  **リスト**のプロパティを定義します。<br>
    **リストクエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  **列のタイトル**を定義します。<br>
    **Name:** コンピューター名<br>
    **値:** 最終ハートビート
6.  **ナビゲーションクエリ**を定義する:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  [ **適用**]、[ **閉じる**] の順に選択します。

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>ハードウェアエラーが発生したデバイスを表示するタイルを作成する

1.  ギャラリーから [ **番号 & リスト** ] を選び、新しいタイルを追加します。
2.  **一般的な**プロパティを定義します。<br>
    **グループタイトル:** ハードウェアの状態<br>
    **新しいグループ:** 選択した
3.  **タイル**のプロパティを定義します。<br>
    **凡例:** 過去1時間にハードウェアエラーが発生したデバイス<br>
    **タイルのクエリ: ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  **リスト**のプロパティを定義します。<br>
    **リストクエリ:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  **列のタイトル**を定義します。<br>
    **Name:** コンピューター名<br>
    **値:** 最後のエラー
6.  **ナビゲーションクエリ**を定義する:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  [ **適用**]、[ **閉じる**] の順に選択します。

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>オペレーティングシステムのバージョンを表示するタイルを作成する :::no-loc text="Microsoft Teams Rooms":::

1.  ギャラリーから [ **ドーナツ & リスト** ] を選び、新しいタイルを追加します。
2.  **一般的な**プロパティを定義します。<br>
    **グループタイトル:** オペレーティングシステムの詳細<br>
    **新しいグループ:** 選択した
3.  **ヘッダー**プロパティを定義します。<br>
    **タイトル:** オペレーティングシステムのバージョン<br>
    **サブタイトル:** 特定の OS バージョンを実行しているデバイス
4.  **ドーナツ**のプロパティを定義します。<br>
    **クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **テキストの中央揃え:** デバイス<br>
    **操作:** "
5.  **リスト**のプロパティを定義します。<br>
    **リストクエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **グラフの非表示:** 選択した<br>
    **スパークラインを有効にする:** 未選択
6.  **列のタイトル**を定義します。<br>
    **Name:** コンピューター名<br>
    **値:** 空のままにする
7.  **ナビゲーションクエリ**を定義します。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  [ **適用** ]、[ **閉じる**] の順に選択します。

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>アプリケーションのバージョンを表示するタイルを作成する :::no-loc text="Microsoft Teams Rooms":::

1.  ギャラリーから [ **ドーナツ & リスト** ] を選び、新しいタイルを追加します。
2.  **一般的な**プロパティを定義します。<br>
    **グループタイトル:** :::no-loc text="Microsoft Teams Rooms"::: アプリケーションの詳細<br>
    **新しいグループ:** 選択した
3.  **ヘッダー**プロパティを定義します。<br>
    **タイトル:** アプリケーションのバージョン<br>
    **サブタイトル:** 特定のアプリケーションバージョンを実行しているデバイス
4.  **ドーナツ**のプロパティを定義します。<br>
    **クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **テキストの中央揃え:** デバイス<br>
    **操作:** "
5.  **リスト**のプロパティを定義します。<br>
    **リストクエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **グラフの非表示:** 選択した<br>
    **スパークラインを有効にする:** 未選択
6.  **列のタイトル**を定義します。<br>
    **Name:** コンピューター名<br>
    **値:** 空のままにする
7.  **ナビゲーションクエリ**を定義します。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  [ **適用** ]、[ **閉じる**] の順に選択します。

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>アプリケーションエラーが発生しているデバイスを表示するタイルを作成する

1.  ギャラリーから [ **番号 & リスト** ] を選び、新しいタイルを追加します。
2.  **一般的な**プロパティを定義します。<br>
    **グループタイトル:** 空のままにする<br>
    **新しいグループ:** 未選択
3.  **タイル**のプロパティを定義します。<br>
    **凡例:** 過去1時間にアプリケーションにエラーが発生したデバイス<br>
    **タイルのクエリ: ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  **リスト**のプロパティを定義します。<br>
    **リストクエリ:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  **列のタイトル**を定義します。<br>
    **Name:** コンピューター名<br>
    **値:** 最後のエラー
6.  **ナビゲーションクエリ**を定義します。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  [ **適用** ]、[ **閉じる**] の順に選択します。

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>再起動されたデバイスを表示するタイルを作成する

1.  ギャラリーから [ **番号 & リスト** ] を選び、新しいタイルを追加します。
2.  **一般的な**プロパティを定義します。<br>
    **グループタイトル:** 空のままにする<br>
    **新しいグループ:** 未選択
3.  **タイル**のプロパティを定義します。<br>
    **凡例:** 過去24時間以内にアプリケーションを再起動したデバイスと再起動回数<br>
    **タイルのクエリ: ** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  **リスト**のプロパティを定義します。<br>
    **リストクエリ:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  **列のタイトル**を定義します。<br>
    **Name:** コンピューター名<br>
    **値:** 再起動回数
6.  **ナビゲーションクエリ**を定義します。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  [ **適用** ]、[ **閉じる**] の順に選択します。
8.  [ **保存** ] を選択してダッシュボードを保存します。

これで、ビューの作成が完了しました。

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>通知を設定する :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: コンソールで問題が発生したときに、管理者に通知する通知を生成でき :::no-loc text="Microsoft Teams Rooms"::: ます。

:::no-loc text="Azure Monitor"::: スケジュールされたログ検索を定期的に実行する組み込みの通知メカニズムが含まれています。 ログ検索の結果が特定の条件と一致する場合は、通知レコードが作成されます。

このルールでは、1つ以上のアクションを自動的に実行して、通知を事前に通知するか、別のプロセスを起動することができます。 次のような警告のオプションがあります。
-   メールを送信する
-   HTTP POST 要求による外部プロセスの呼び出し
-   サービスでの runbook の開始 :::no-loc text="Azure Automation":::

通知の詳細については、「[ログの警告 :::no-loc text="Azure Monitor"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) 」を参照してください :::no-loc text="Azure Monitor"::: 。

> [!NOTE]
> 次の例では、デバイスが :::no-loc text="Microsoft Teams Rooms"::: ハードウェアまたはアプリケーションエラーを生成したときにメール通知を送信します。

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>ハードウェアの問題に関する電子メール通知を構成する :::no-loc text="Microsoft Teams Rooms":::

:::no-loc text="Microsoft Teams Rooms":::過去1時間以内にハードウェアの問題が発生したデバイスを確認する通知ルールを構成します。
1.  [ :::no-loc text="Microsoft Azure"::: ポータル](https://portal.azure.com)にサインインして、ワークスペースに移動して :::no-loc text="Log Analytics"::: 選択します。

2. ワークスペースに移動して、[ :::no-loc text="Log Analytics"::: **警告**] を選択し、[**新しい通知ルール**] を選択します。

3. [**条件の追加**] を選択し、[**カスタムログの検索**] を選びます。

4.  [検索クエリ] テキストボックスに、次のクエリを入力します。<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  アラートのロジック設定を構成します。<br>
    **基準:** 結果の数<br>
    **条件:** より大きい<br>
    **しきい値:** 0<br>

6. 評価の設定を構成し、[ **完了**] を選択します。 <br>
    **期間 (分):** 60<br>
    **頻度 (分):** 60<br>

7. アクショングループを構成します。
    1.  [**新規作成**] を選ぶ
    2.  [ *アクショングループ名]* フィールドと [ *短縮名* ] フィールドに適切な名前を入力します。
    3.  一意の *アクション名* を指定し、[ **メール/SMS/プッシュ/ボイス**] を選択して、[ **詳細の編集**] を選択します。
    4.  [ **メール** ] チェックボックスをオンにして、アラートを受信するユーザーまたはグループのメールアドレスを入力します。
    5.  また、SMS、音声通話、またはその両方の通知を受け取るために、電話番号を入力することもできます。
    6. [ **OK]** を選びます。

8. 通知メールの件名行を上書きする場合は、[**アクションのカスタマイズ**を行う。

9. ルールの名前と説明を指定します。<br>
    **ルール名:** :::no-loc text="Microsoft Teams Rooms"::: ハードウェアエラーアラート<br>
    **説明:** 過去1時間以内にハードウェアの問題が発生したデバイスの一覧<br>

10. 目的の重要度を選び、ルールが有効になっていることを確認します。

11. [ **通知ルールの作成**] を選びます。

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>アプリケーションの問題に関する電子メール通知を構成する :::no-loc text="Microsoft Teams Rooms":::

同じ手順を繰り返しますが、次のクエリを使用して、過去1時間以内にアプリケーションの問題が発生したデバイスを一覧表示します。

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

これで、通知の定義が完了しました。 上記の例を使用して、追加の警告を定義できます。

アラートが生成されると、過去1時間以内に問題が発生したデバイスの一覧を示すメールが表示されます。

![サンプルの :::no-loc text="Azure Monitor"::: 通知メール] (.../media/Deploy-Azure-Monitor-6.png "サンプルの :::no-loc text="Azure Monitor"::: 通知メール")

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>すべてのデバイスを構成する :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"> </a>ダッシュボードとアラートを構成したら、すべてのデバイスでエージェントをセットアップして構成し、 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: 監視展開を完了することができます。

エージェントは各デバイスで手動でインストールして構成することもでき :::no-loc text="Microsoft Monitoring"::: ますが、既存のソフトウェア展開ツールと方法を活用することを強くお勧めします。

初めてデバイスを構築する場合は :::no-loc text="Microsoft Teams Rooms"::: 、 :::no-loc text="Microsoft Monitoring"::: 構築プロセスの一部としてエージェントのセットアップと構成の手順を含めることができます。 詳細については、「 [コマンドラインを使用してエージェントをインストール](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)する」を参照してください。

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>:::no-loc text="Microsoft Monitoring":::グループポリシーオブジェクト (GPO) を使用したエージェントの展開

実装前に既にデバイスを展開している場合は、提供されたスクリプトを使用して、 :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitoring"::: グループポリシーオブジェクトを使ってエージェントをセットアップし、構成することができ :::no-loc text="Active Directory"::: ます。

1.  共有ネットワークパスを作成し、 **ドメインコンピューター** グループに読み取りアクセス許可を付与します。

2.  64ビット版のエージェントをダウンロードする :::no-loc text="Microsoft Monitoring"::: には :::no-loc text="Windows"::: 、 <https://go.microsoft.com/fwlink/?LinkID=517476>

3.  ネットワーク共有にセットアップパッケージの内容を抽出します。
    1.  コマンドプロンプトウィンドウを開き、 **MMASetup-AMD64.exe/c**を実行します。
    2.  作成した共有を指定し、コンテンツを抽出します。

4.  新しいグループポリシーオブジェクトを作成し、 :::no-loc text="Microsoft Teams Rooms"::: コンピューターアカウントがある組織単位に割り当てます。

5.  PowerShell 実行ポリシーを構成します。
    1.  新しく作成されたグループポリシーオブジェクトを編集し、コンピューター構成 \\ ポリシー \\ 管理用テンプレートの \\ :::no-loc text="Windows"::: コンポーネント \\ に移動する :::no-loc text="Windows PowerShell":::
    2.  [**スクリプト実行を有効**にする] を有効にして、**ローカルスクリプトを許可**する**実行ポリシー**を設定します。

6.  スタートアップスクリプトを構成します。
    1.  次のスクリプトをコピーして Install-MMAgent.ps1 として保存します。
    2.  構成に合わせて WorkspaceId、WorkspaceKey、SetupPath の各パラメーターを変更します。
    3.  同じグループポリシーオブジェクトを編集して、コンピューター構成 \\ ポリシーの \\ :::no-loc text="Windows"::: 設定 \\ スクリプト (スタートアップ/シャットダウン) に移動します。
    4.  [ **スタートアップ**] をダブルクリックして選択し、[ **PowerShell スクリプト**] を選択します。
    5.  [ **ファイルの表示**] を選択し、 **Install-MMAgent.ps1** ファイルをそのフォルダーにコピーします。
    6.  [ **追加**]、[ **参照**] の順に選択します。
    7.  コピーした ps1 スクリプトを選択します。

7.  :::no-loc text="Microsoft Teams Rooms"::: デバイスは、 :::no-loc text="Microsoft Monitoring"::: 2 回目の再起動でエージェントをインストールして構成する必要があります。

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
> エージェントの再構成、別のワークスペースへの移動、または最初のインストール後のプロキシ設定の変更を行う必要がある場合は、「 [ :::no-loc text="Log Analytics"::: エージェントの管理と保守](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) 」を参照してください。

## <a name="additional-solutions"></a>その他の解決策
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor":::[ソリューションギャラリー](https://docs.microsoft.com/azure/azure-monitor/insights/solutions)を通じて、お客様の環境を監視するための組み込みの管理ソリューションを提供します。 [通知管理](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution)と[ :::no-loc text="Azure Log Analytics"::: エージェントの正常性](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth)の解決策もワークスペースに追加することを強くお勧めします。

> [!NOTE]
> エージェント正常性ソリューションは、環境内の古いまたは破損したエージェントを特定するのに役立ち :::no-loc text="Microsoft Monitoring"::: ます。また、アラート管理ソリューションは、一定の期間内に発生した警告に関する詳細情報を提供します。

## <a name="see-also"></a>関連項目

[計画 :::no-loc text="Microsoft Teams Rooms"::: 管理 :::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[:::no-loc text="Microsoft Teams Rooms":::デバイスの管理:::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
