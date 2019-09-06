---
title: Azure モニターを使用して Microsoft Teams のルーム管理を展開する
ms.author: v-lanac
author: lanachin
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: この記事では、Azure モニターを使用して、統合されたエンドツーエンドの方法で Microsoft Teams 室デバイスの管理を展開する方法について説明します。
ms.openlocfilehash: 4be57f97ef3b0813afef2aefd70c551ee50422ee
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774686"
---
# <a name="deploy-microsoft-teams-rooms-management-with-azure-monitor"></a>Azure モニターを使用して Microsoft Teams のルーム管理を展開する

この記事では、Azure モニターを使用して、Microsoft Teams 室デバイスの統合されたエンドツーエンドの管理をセットアップして展開する方法について説明します。

Azure Monitor でログ分析を構成することで、Microsoft Teams 室の会議室のデバイスを管理するのに役立つ基本的なテレメトリとアラートを提供できます。 管理ソリューションの成熟に応じて、デバイスの可用性とパフォーマンスの詳細なビューを作成するために、追加のデータと管理機能を展開することができます。

このガイドに従うと、次の例のようなダッシュボードを使用して、デバイスの可用性、アプリケーションとハードウェアの正常性、および Microsoft Teams のアプリケーションとオペレーティングシステムのバージョンの配布に関する詳細な状態レポートを取得できます。

![Microsoft Teams のルームのサンプルログ分析ビューのスクリーンショット](../media/Deploy-Azure-Monitor-1.png "Microsoft Teams ルームのサンプルログ分析ビュー")

高いレベルでは、次のタスクを実行する必要があります。


1. [ログ分析構成を検証する](azure-monitor-deploy.md#validate_LogAnalytics)
2. [ログ分析管理セットアップ用にテストデバイスを構成する](azure-monitor-deploy.md#configure_test_devices)
3. [カスタム フィールドをマップする](azure-monitor-deploy.md#Custom_fields)
4. [ログ分析で Microsoft Teams のルームビューを定義する](azure-monitor-deploy.md#Define_Views)
5. [通知を定義する](azure-monitor-deploy.md#Alerts)
6. [すべてのデバイスを監視対象として構成する](azure-monitor-deploy.md#configure_all_devices)
7. [追加の Azure モニターソリューションを構成する](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> 最小限の構成では、Azure Monitor Log Analytics は Windows オペレーティングシステムを実行しているコンピューターを監視できますが、Microsoft Teams の一部の機能については、すべての Microsoft Teams へのエージェントの展開を開始する前に実行する必要があります。会議室のデバイス。
> そのため、管理された設定と構成については、すべての構成手順を適切な順序で実行することを強くお勧めします。 最終的な結果の品質は、初期構成の品質によって大きく異なります。

## <a name="validate-log-analytics-configuration"></a>ログ分析構成を検証する
<a name="validate_LogAnalytics"> </a>

Microsoft Teams 室のデバイスからログの収集を開始するには、ログ分析ワークスペースが必要です。 ワークスペースは、独自のデータリポジトリ、データソース、およびソリューションを備えた固有のログ分析環境です。 既にログ分析ワークスペースを持っている場合は、それを使って Microsoft Teams ルームの展開を監視するか、または Microsoft Teams のルームの監視ニーズに合わせた専用のログ分析ワークスペースを作成することができます。

新しいログ分析ワークスペースを作成する必要がある場合は、「 [Azure ポータルでログ分析ワークスペースを作成](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)する」の手順に従います。

> [!NOTE]
> Azure モニターでログ分析を使用するには、アクティブな Azure サブスクリプションが必要です。 Azure サブスクリプションを持っていない場合は、出発点として[無料試用版サブスクリプションを](https://azure.microsoft.com/free)作成できます。

### <a name="configure-log-analytics-to-collect-microsoft-teams-rooms-event-logs"></a>Microsoft Teams ルームのイベントログを収集するためのログ分析を構成する

ログ分析は、設定で指定された Windows イベントログからのイベントのみを収集します。 各ログについて、選択した重大度のイベントのみが収集されます。

Microsoft Teams の会議のデバイスとアプリケーションの状態を監視するために必要なログを収集するために、ログ分析を構成する必要があります。 Microsoft Teams の Room デバイスでは、 **Skype Room System**のイベントログが使用されます。

Microsoft Teams の会議室のイベントを収集するためにログ分析を構成するには、「 [Azure モニターでの Windows イベントログのデータソース](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)」を参照してください。

![イベントログ設定のスクリーンショット](../media/Deploy-Azure-Monitor-2.png "イベントログの設定")

> [!IMPORTANT]
> Windows イベントログ設定を構成し、イベントログ名として「 **Skype Room System** 」と入力して、[**エラー**]、[**警告**]、[**情報**] のチェックボックスをオンにします。

## <a name="configure-test-devices-for-azure-monitoring"></a>Azure Monitoring のテストデバイスを構成する
<a name="configure_test_devices"> </a>

Microsoft Teams のルームに関連するイベントを監視できるようにするには、ログ分析を準備する必要があります。 まず、microsoft Monitoring agent を1つまたは2つの Microsoft Teams 室デバイスに展開して、物理的なアクセス権を持っていることを確認し、これらのテストデバイスでデータを生成して、ログ分析ワークスペースにプッシュする必要があります。

### <a name="install-microsoft-monitoring-agents-to-test-devices"></a>Microsoft Monitoring agent をインストールしてデバイスをテストする

「 [Windows コンピューターを Azure のログ分析サービスに接続する](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)」の指示に従って、Microsoft Monitoring agent をテストデバイスに展開します。 この記事では、microsoft Monitoring Agent for Windows を展開するための手順、ログ分析***ワークスペース ID***の入手方法、microsoft Teams のルームデバイスが接続される***主キー***を取得する手順について詳しく説明します。Azure モニターの展開と、ログ分析インスタンスへのエージェント接続を確認する手順。

### <a name="generate-sample-microsoft-teams-rooms-events"></a>サンプルの Microsoft Teams ルームイベントを生成する

Microsoft Monitoring agent をテストデバイスに展開した後、必要なイベントログデータが Azure Monitor によって収集されていることを確認します。

> [!NOTE]
> Microsoft Monitoring agent のインストール後にデバイスを再起動し、Microsoft Teams 会議アプリが開始されていることを確認して、イベントログに新しいイベントを生成できるようにします。

1.  [Microsoft Azure ポータル](https://portal.azure.com)にサインインし、[ログ分析] に移動して、ワークスペースを選びます。

2.  Microsoft Teams 室のデバイスによって生成されるハートビートイベントを一覧表示します。
    1.  ワークスペースを選択して、[**ログ**] に移動し、[クエリ] を使用して、Microsoft Teams のルームのユーザー設定フィールドを含むハートビートレコードを取得します。
    2.  サンプルクエリ:`Event | where Source == "SRS-App" and EventID == 2000`

3.  Microsoft Teams 会議アプリによって生成されたイベントを含むログレコードが、クエリによって返されていることを確認してください。

4.  ハードウェアの問題を生成し、必要なイベントが Azure Log Analytics に記録されていることを確認します。
    1.  Microsoft Teams 室のテストシステムでいずれかの周辺機器を取り外します。 カメラ、スピーカーフォン、マイク、またはフロントルームディスプレイの場合があります
    2.  Azure ログ分析にイベントログが入力されるまで10分待ちます。
    3.  クエリを使用して、ハードウェアエラーイベントを一覧表示します。`Event | where Source == "SRS-App" and EventID == 3001`

5.  アプリケーションの問題を生成し、必要なイベントがログに記録されていることを確認します。
    1.  Microsoft Teams 会議アプリケーションの構成を変更し、誤ったセッション開始プロトコル (SIP) アドレスとパスワードのペアを入力します。
    2.  Azure ログ分析にイベントログが入力されるまで10分待ちます。
    3.  クエリを使用して、アプリケーションエラーイベントを一覧表示します。`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> カスタムフィールドを構成するには、これらのサンプルイベントログが必要です。 必要なイベントログを収集するまでは、次の手順に進んではいけません。

## <a name="map-custom-fields"></a>カスタム フィールドをマップする
<a name="Custom_fields"> </a>

カスタムフィールドを使って、イベントログから特定のデータを抽出します。 タイル、ダッシュボードビュー、およびアラートで後で使用されるカスタムフィールドを定義する必要があります。 カスタムフィールドの作成を開始する前に、「[ログ分析のカスタムフィールド](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields)」を参照して、概念を理解しておいてください。

キャプチャしたイベントログからカスタムフィールドを抽出するには、次の手順を実行します。

1.  [Microsoft Azure ポータル](https://portal.azure.com)にサインインし、[ログ分析] に移動して、ワークスペースを選びます。

2. Microsoft Teams 室のデバイスによって生成されるイベントを一覧表示します。
   1.  [**ログ**] に移動し、クエリを使用してユーザー設定フィールドを含むレコードを取得します。
   2.  サンプルクエリ:`Event | where Source == "SRS-App" and EventID == 2000`

3. いずれかのレコードを選び、左側のボタンを選んで、フィールド抽出ウィザードを開始します。
4. RenderedDescription から抽出するデータを強調表示し、フィールドタイトルを入力します。 使用する必要があるフィールド名は、表1に記載されています。

   ![ユーザー設定フィールドの定義](../media/Deploy-Azure-Monitor-4.png "ユーザー設定フィールドの定義")

5. *表 1*に示されているマッピングを使用します。 ログ分析では、新しい** \_** フィールドを定義するときに、自動的に CF 文字列が追加されます。

> [!IMPORTANT]
> JSON と Log Analytics のすべてのフィールドは、大文字と小文字が区別されることに注意してください。
> 
> 以下の表のユーザー設定フィールドごとに、必要なクエリに注意してください。 適切なクエリを使用して、ユーザー設定フィールドの値を正しく抽出する必要があります。
> 
 ![ユーザー設定フィールドの定義](../media/Deploy-Azure-Monitor-5.png "ユーザー設定フィールドの定義")

**表1**

| **JSON フィールド**                   | **ログ分析のカスタムフィールド** | **イベント ID** | **抽出に使用するクエリ**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| 説明                      | SRSEventDescription         | **2000**     | \| Source = = "SRS-アプリ" and EventID = = 2000 |
| ResourceState                    | SRSResourceState            | **2000**     | \| Source = = "SRS-アプリ" and EventID = = 2000 |
| OperationName                    | SRSOperationName            | **2000**     | \| Source = = "SRS-アプリ" and EventID = = 2000 |
| OperationResult                  | SRSOperationResult          | **2000**     | \| Source = = "SRS-アプリ" and EventID = = 2000 |
| OS                               | SRSOSVersion                | **2000**     | \| Source = = "SRS-アプリ" and EventID = = 2000 |
| OSVersion                        | SRSOSLongVersion            | **2000**     | \| Source = = "SRS-アプリ" and EventID = = 2000 |
| Alias                            | SRSAlias                    | **2000**     | \| Source = = "SRS-アプリ" and EventID = = 2000 |
| DisplayName                      | SRSDisplayName              | **2000**     | \| Source = = "SRS-アプリ" and EventID = = 2000 |
| AppVersion                       | SRSAppVersion               | **2000**     | \| Source = = "SRS-アプリ" and EventID = = 2000 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | \| Source = = "SRS-アプリ" and EventID = = 2000 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | \| Source = = "SRS-アプリ" and EventID = = 2000 |
| 会議のマイクの状態     | Srsconfマイクロ電話の状態     | **3001**     | \| Source = = "SRS-アプリ" and EventID = = 3001 |
| 会議のスピーカーの状態        | SRSConfSpeakerStatus        | **3001**     | \| Source = = "SRS-アプリ" and EventID = = 3001 |
| 既定のスピーカーの状態           | SRSDefaultSpeakerStatus     | **3001**     | \| Source = = "SRS-アプリ" and EventID = = 3001 |
| カメラの状態                    | SRSCameraStatus             | **3001**     | \| Source = = "SRS-アプリ" and EventID = = 3001 |
| 部屋の表面の表示状態     | SRSFORDStatus               | **3001**     | \| Source = = "SRS-アプリ" and EventID = = 3001 |
| モーションセンサーの状態             | SRSMotionSensorStatus       | **3001**     | \| Source = = "SRS-アプリ" and EventID = = 3001 |
| HDMI 取り込みの状態               | SRSHDMIIngestStatus         | **3001**     | \| Source = = "SRS-アプリ" and EventID = = 3001 |


## <a name="define-the-microsoft-teams-rooms-views-in-log-analytics"></a>ログ分析で Microsoft Teams のルームビューを定義する
<a name="Define_Views"> </a>

データが収集され、ユーザー設定フィールドがマップされた後、ビューデザイナーを使用して、さまざまなタイルを含むダッシュボードを作成し、Microsoft Teams ルームのイベントを監視することができます。 次のタイルを作成するには、[ビューデザイナーを使用します。 詳細については、「[ログ分析のビューデザイナーを使用してカスタムビューを作成する](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)」を参照してください。

> [!NOTE]
> ダッシュボードタイルが正常に動作するためには、このガイドの前の手順が完了している必要があります。

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>インポート方法を使用して Microsoft Teams のルームダッシュボードを作成する

Microsoft Teams のルームダッシュボードをインポートして、デバイスの監視をすばやく開始することができます。 ダッシュボードをインポートするには、次の手順を実行します。

1.  SkypeRoomSystems_v2 の[omsview](https://go.microsoft.com/fwlink/?linkid=835675)ダッシュボードファイルを取得します。
2.  [Microsoft Azure ポータル](https://portal.azure.com)にサインインし、[ログ分析] に移動して、ワークスペースを選びます。
3.  **ビューデザイナー**を開きます。
4.  [**インポート**] を選択し、 **SkypeRoomSystems_v2**ファイルを選びます。
5.  [**保存**] を選びます。

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Microsoft Teams のルームダッシュボードを手動で作成する

または、独自のダッシュボードを作成して、監視するタイルのみを追加することもできます。

#### <a name="configure-the-overview-tile"></a>概要タイルを構成する

1.  **ビューデザイナー**を開きます。
2.  [**概要] タイル**を選択し、ギャラリーから**2 つの数値**を選択します。
3.  タイル**Microsoft Teams のルーム**に名前を指定します。
4.  最初の**タイル**を定義します。<br>
    **凡例:** 1ヶ月以内に少なくとも1回、ハートビートを送信したデバイス<br>
    **クエリ:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  **2 番目のタイル**を定義します。<br>
    **凡例:** 1時間以内にハートビートを送信したアクティブなデバイス<br>
    **クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  [**適用**] を選びます。

### <a name="create-a-tile-that-displays-active-devices"></a>アクティブなデバイスを表示するタイルを作成する

1.  [**ダッシュボードの表示**] を選択して、タイルの追加を開始します。
2.  ギャラリーから**番号 & リスト**を選択する
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
8.  [**適用**]、[**閉じる**] の順に選択します。

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>接続の問題が発生しているデバイスを表示するタイルを作成する

1.  ギャラリーから [**番号 & リスト**] を選び、新しいタイルを追加します。
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
7.  [**適用**]、[**閉じる**] の順に選択します。

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>ハードウェアエラーが発生したデバイスを表示するタイルを作成する

1.  ギャラリーから [**番号 & リスト**] を選び、新しいタイルを追加します。
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
7.  [**適用**]、[**閉じる**] の順に選択します。

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-operating-system-versions"></a>Microsoft Teams 室のオペレーティングシステムバージョンを表示するタイルを作成する

1.  ギャラリーから [**ドーナツ & リスト**] を選び、新しいタイルを追加します。
2.  **一般的な**プロパティを定義します。<br>
    **グループタイトル:** オペレーティングシステムの詳細<br>
    **新しいグループ:** 選択した
3.  **ヘッダー**プロパティを定義します。<br>
    **タイトル:** オペレーティングシステムのバージョン<br>
    **サブタイトル:** 特定の OS バージョンを実行しているデバイス
4.  **ドーナツ**のプロパティを定義します。<br>
    **クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **テキストの中央揃え:** デバイス<br>
    **操作:**"
5.  **リスト**のプロパティを定義します。<br>
    **リストクエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **グラフの非表示:** 選択した<br>
    **スパークラインを有効にする:** 未選択
6.  **列のタイトル**を定義します。<br>
    **Name:** コンピューター名<br>
    **値:** 空のままにする
7.  **ナビゲーションクエリ**を定義します。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  [**適用**]、[**閉じる**] の順に選択します。

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-application-versions"></a>Microsoft Teams ルームアプリケーションバージョンを表示するタイルを作成する

1.  ギャラリーから [**ドーナツ & リスト**] を選び、新しいタイルを追加します。
2.  **一般的な**プロパティを定義します。<br>
    **グループタイトル:** Microsoft Teams のルームアプリケーションの詳細<br>
    **新しいグループ:** 選択した
3.  **ヘッダー**プロパティを定義します。<br>
    **タイトル:** アプリケーションのバージョン<br>
    **サブタイトル:** 特定のアプリケーションバージョンを実行しているデバイス
4.  **ドーナツ**のプロパティを定義します。<br>
    **クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **テキストの中央揃え:** デバイス<br>
    **操作:**"
5.  **リスト**のプロパティを定義します。<br>
    **リストクエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **グラフの非表示:** 選択した<br>
    **スパークラインを有効にする:** 未選択
6.  **列のタイトル**を定義します。<br>
    **Name:** コンピューター名<br>
    **値:** 空のままにする
7.  **ナビゲーションクエリ**を定義します。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  [**適用**]、[**閉じる**] の順に選択します。

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>アプリケーションエラーが発生しているデバイスを表示するタイルを作成する

1.  ギャラリーから [**番号 & リスト**] を選び、新しいタイルを追加します。
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
7.  [**適用**]、[**閉じる**] の順に選択します。

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>再起動されたデバイスを表示するタイルを作成する

1.  ギャラリーから [**番号 & リスト**] を選び、新しいタイルを追加します。
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
7.  [**適用**]、[**閉じる**] の順に選択します。
8.  [**保存**] を選択してダッシュボードを保存します。

これで、ビューの作成が完了しました。

## <a name="configure-alerts-in-azure-monitor"></a>Azure モニターで通知を構成する
<a name="Alerts"> </a>

Microsoft Teams のルームコンソールで問題が発生した場合、Azure モニターは通知を生成し、管理者に通知することができます。

Azure モニターには、定期的にスケジュールされたログの検索によって実行される組み込みのアラートメカニズムが含まれています。 ログ検索の結果が特定の条件と一致する場合は、通知レコードが作成されます。

このルールでは、1つ以上のアクションを自動的に実行して、通知を事前に通知するか、別のプロセスを起動することができます。 次のような警告のオプションがあります。
-   メールを送信する
-   HTTP POST 要求による外部プロセスの呼び出し
-   Azure Automation service での runbook の開始

Azure モニターでのアラートの詳細については、「 [Azure monitor でのログの警告](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log)」を参照してください。

> [!NOTE]
> 次の例では、Microsoft Teams の会議室デバイスがハードウェアまたはアプリケーションエラーを生成したときにメール通知を送信します。

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-hardware-issues"></a>Microsoft Teams 室のハードウェアに関する問題のメール通知を構成する

過去1時間以内にハードウェアの問題が発生した Microsoft Teams 室のデバイスを確認する通知ルールを構成します。
1.  [Microsoft Azure ポータル](https://portal.azure.com)にサインインし、[ログ分析] に移動して、ワークスペースを選びます。

2. ログ分析ワークスペースに移動して、[**警告**] を選択し、[**新しい通知ルール**] を選択します。

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
    **Treshold:** 0<br>

6. 評価の設定を構成し、[**完了**] を選択します。 <br>
    **期間 (分):** 60<br>
    **頻度 (分):** 60<br>

7. アクショングループを構成します。
    1.  [**新規作成**] を選ぶ
    2.  [*アクショングループ名]* フィールドと [*短縮名*] フィールドに適切な名前を入力します。
    3.  一意の*アクション名*を指定し、[**メール/SMS/プッシュ/ボイス**] を選択して、[**詳細の編集**] を選択します。
    4.  [メール] チェックボックスをオンにして、アラートを受信するユーザーまたはグループのメールアドレスを入力します。
    5.  また、SMS、音声通話、またはその両方の通知を受け取るために、電話番号を入力することもできます。
    6. [ **OK]** を選びます。

8. 通知メールの件名行を上書きする場合は、[**アクションのカスタマイズ**を行う。

9. ルールの名前と説明を指定します。<br>
    **ルール名:** Microsoft Teams の会議室ハードウェアエラーアラート<br>
    **説明:** 過去1時間以内にハードウェアの問題が発生したデバイスの一覧<br>

10. 目的の重要度を選び、ルールが有効になっていることを確認します。

11. [**通知ルールの作成**] を選びます。

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-application-issues"></a>Microsoft Teams 室のアプリケーションに関する問題のメール通知を構成する

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

![Azure モニター通知メールの例](../media/Deploy-Azure-Monitor-6.png "Azure モニター通知メールの例")

## <a name="configure-all-devices-for-azure-monitoring"></a>Azure Monitoring のすべてのデバイスを構成する
<a name="configure_all_devices"></a>ダッシュボードとアラートを構成した後で、microsoft Teams のすべてのルームデバイスで microsoft monitoring agent を設定および構成して、監視展開を完了することができます。

Microsoft Monitoring agent は各デバイスに手動でインストールして構成することもできますが、既存のソフトウェア展開ツールとメソッドを利用することを強くお勧めします。

Microsoft Teams のルームデバイスを初めて構築する場合は、ビルドプロセスの一部として Microsoft Monitoring agent のセットアップと構成の手順を含めることができます。 詳細については、「[コマンドラインを使用してエージェントをインストール](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)する」を参照してください。

### <a name="deploying-microsoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>グループポリシーオブジェクト (GPO) を使用して Microsoft Monitoring agent を展開する

Azure Monitoring を実装する前に Microsoft Teams のルームデバイスを既に展開している場合は、提供されたスクリプトを使用して、Active Directory グループポリシーオブジェクトを使用してエージェントをセットアップし、構成することができます。

1.  共有ネットワークパスを作成し、**ドメインコンピューター**グループに読み取りアクセス許可を付与します。

2.  Windows 用の64ビットバージョンの Microsoft Monitoring Agent をダウンロードします。<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  ネットワーク共有にセットアップパッケージの内容を抽出します。
    1.  コマンドプロンプトウィンドウを開き、MMASetup-AMD64 を実行し**ます。**
    2.  作成した共有を指定し、コンテンツを抽出します。

4.  新しいグループポリシーオブジェクトを作成して、Microsoft Teams のルームのコンピューターアカウントがある組織単位に割り当てます。

5.  PowerShell 実行ポリシーを構成します。
    1.  新しく作成されたグループポリシーオブジェクトを編集して\\ 、 \\コンピューター構成\\ポリシーの\\管理用テンプレートに移動します。 windows コンポーネント windows PowerShell
    2.  [**スクリプト実行を有効**にする] を有効にして、**ローカルスクリプトを許可**する**実行ポリシー**を設定します。

6.  スタートアップスクリプトを構成します。
    1.  次のスクリプトをコピーし、Install-MMAgent として保存します。
    2.  構成に合わせて WorkspaceId、WorkspaceKey、SetupPath の各パラメーターを変更します。
    3.  同じグループポリシーオブジェクトを編集して、コンピューター構成\\ポリシー \\の Windows \\設定スクリプト (スタートアップ/シャットダウン) に移動する
    4.  [**スタートアップ**] をダブルクリックして選択し、[ **PowerShell スクリプト**] を選択します。
    5.  [**ファイルの表示**] を選択し、 **Install-MMAgent**ファイルをそのフォルダーにコピーします。
    6.  [**追加**]、[**参照**] の順に選択します。
    7.  コピーした ps1 スクリプトを選択します。

7.  Microsoft Teams の会議室デバイスでは、2回目の再起動で Microsoft Monitoring agent をインストールして構成する必要があります。

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
> エージェントを再構成する、別のワークスペースに移動する、または最初のインストール後にプロキシ設定を変更する必要がある場合は、「[ログ分析エージェントの管理と保守](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage)」の記事を参照してください。

## <a name="additional-solutions"></a>その他の解決策
<a name="Solutions"> </a>

Azure Monitor は、[ソリューションギャラリー](https://docs.microsoft.com/azure/azure-monitor/insights/solutions)を通じて、お客様の環境を監視するための組み込みの管理ソリューションを提供します。 [アラート管理](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution)と[Azure Log Analytics Agent の正常性](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth)解決策もワークスペースに追加することを強くお勧めします。

> [!NOTE]
> エージェント正常性ソリューションは、環境内の古いまたは破損した Microsoft Monitoring agent を特定するのに役立ちます。また、アラート管理ソリューションは、一定の期間内に発生したアラートに関する詳細情報を提供します。

## <a name="see-also"></a>関連項目

[Azure モニターを使用して Microsoft Teams の会議室の管理を計画する](azure-monitor-plan.md)

[Azure モニターを使用して Microsoft Teams 室のデバイスを管理する](azure-monitor-manage.md)
